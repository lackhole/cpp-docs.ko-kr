---
title: perror, _wperror
ms.date: 11/04/2016
apiname:
- _wperror
- perror
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wperror
- _tperror
- perror
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
ms.openlocfilehash: c9026a96ecc74640eb2bcd7004d5d1e0fc287e38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156107"
---
# <a name="perror-wperror"></a>perror, _wperror

오류 메시지를 인쇄합니다.

## <a name="syntax"></a>구문

```C
void perror(
   const char *message
);
void _wperror(
   const wchar_t *message
);
```

### <a name="parameters"></a>매개 변수

*message*<br/>
인쇄할 문자열 메시지입니다.

## <a name="remarks"></a>설명

합니다 **perror** 함수는 오류 메시지를 출력 **stderr**합니다. **_wperror** 의 와이드 문자 버전이 **_perror**; *메시지* 인수 **_wperror** 는 와이드 문자 문자열입니다. **_wperror** 하 고 **_perror** 동일 하 게 작동 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tperror**|**perror**|**perror**|**_wperror**|

*메시지* 인쇄 먼저 뒤에 콜론을 다음의 오류를 발생 시킨 마지막 라이브러리 호출에 대 한 시스템 오류 메시지에서 마지막에 줄 바꿈 문자입니다. 하는 경우 *메시지* 이 null 포인터 이거나 null 문자열에 대 한 포인터 **perror** 시스템 오류 메시지를 출력 합니다.

오류 번호는 ERRNO.H에 정의되어 있는 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수에 저장됩니다. [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수를 통해 시스템 오류 메시지에 액세스합니다. 이 변수는 오류 번호순으로 정렬된 메시지 배열입니다. **perror** 사용 하 여 적절 한 오류 메시지를 인쇄 합니다 **errno** 값에 대 한 인덱스로 **_sys_errlist**합니다. 변수 값 [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 에 있는 요소의 최대 수로 정의 됩니다 합니다 **_sys_errlist** 배열입니다.

정확한 결과 호출 **perror** 라이브러리 루틴이 오류와 함께 반환 된 직후입니다. 후속 호출을 덮어쓸 수이 고, 그렇지 합니다 **errno** 값입니다.

에 Windows 운영 체제의 경우 일부 **errno** ERRNO에 나열 된 값입니다. H 사용 되지 않습니다. 이러한 값은 UNIX 운영 체제에서 사용되도록 예약되어 있습니다. 참조 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 목록은 **errno** Windows 운영 체제에서 사용 되는 값입니다. **perror** 에 대 한 빈 문자열을 인쇄 **errno** 이러한 플랫폼이 지 사용 하지 않는 값입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**perror**|\<stdio.h> 또는 \<stdlib.h>|
|**_wperror**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_perror.c
// compile with: /W3
/* This program attempts to open a file named
* NOSUCHF.ILE. Because this file probably doesn't exist,
* an error message is displayed. The same message is
* created using perror, strerror, and _strerror.
*/

#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <share.h>

int main( void )
{
   int  fh;

   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )
   {
      /* Three ways to create error message: */
      perror( "perror says open failed" );
      printf( "strerror says open failed: %s\n",
         strerror( errno ) ); // C4996
      printf( _strerror( "_strerror says open failed" ) ); // C4996
      // Note: strerror and _strerror are deprecated; consider
      // using strerror_s and _strerror_s instead.
   }
   else
   {
      printf( "open succeeded on input file\n" );
      _close( fh );
   }
}
```

```Output
perror says open failed: No such file or directory
strerror says open failed: No such file or directory
_strerror says open failed: No such file or directory
```

## <a name="see-also"></a>참고자료

[프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md)<br/>
