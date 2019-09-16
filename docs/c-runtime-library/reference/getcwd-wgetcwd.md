---
title: _getcwd, _wgetcwd
ms.date: 11/04/2016
api_name:
- _wgetcwd
- _getcwd
api_location:
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
ms.openlocfilehash: 78b02871aafca85db50df2eea74a2210c578c204
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955244"
---
# <a name="_getcwd-_wgetcwd"></a>_getcwd, _wgetcwd

현재 작업 디렉터리를 가져옵니다.

## <a name="syntax"></a>구문

```C
char *_getcwd(
   char *buffer,
   int maxlen
);
wchar_t *_wgetcwd(
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
경로의 스토리지 위치입니다.

*maxlen*<br/>
경로의 최대 길이 (문자: **_getcwd** 의 경우 **char** , **_wgetcwd**의 경우 **wchar_t** )입니다.

## <a name="return-value"></a>반환 값

*버퍼*에 대 한 포인터를 반환 합니다. **Null** 반환 값은 오류를 나타내고 **errno** 는 *maxlen* 바이트를 할당할 메모리가 부족 함을 나타내는 **enomem**( **null** 인수가 *버퍼로*지정 된 경우) 또는 ERANGE로 설정 됩니다. *maxlen* 자 보다 긴 경로를 나타내는입니다. *Maxlen* 가 0 보다 작거나 같으면이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

**_Getcwd** 함수는 기본 드라이브에 대 한 현재 작업 디렉터리의 전체 경로를 가져오고이를 *버퍼*에 저장 합니다. 정수 인수 *maxlen* 는 경로에 대 한 최대 길이를 지정 합니다. 경로의 길이 (null 종결 문자 포함)가 *maxlen*를 초과 하면 오류가 발생 합니다. *Buffer* 인수는 **NULL**일 수 있습니다. **malloc**를 사용 하 여 경로를 저장 하는 최소 크기의 *maxlen* (필요한 경우에만) 버퍼가 자동으로 할당 됩니다. 이 버퍼는 나중에 **free** 를 호출 하 고 **_getcwd** 반환 값 (할당 된 버퍼에 대 한 포인터)을 전달 하 여 해제할 수 있습니다.

**_getcwd** 은 현재 작업 디렉터리의 경로를 나타내는 문자열을 반환 합니다. 현재 작업 디렉터리가 루트 이면 문자열이 백슬래시 ( **\\** )로 끝납니다. 현재 작업 디렉터리가 루트 이외의 디렉터리이면 문자열은 백슬래시가 아닌 디렉터리 이름으로 끝납니다.

**_wgetcwd** 는 **_getcwd**의 와이드 문자 버전입니다. **_wgetcwd** 의 *buffer* 인수와 반환 값은 와이드 문자 문자열입니다. **_wgetcwd** 및 **_getcwd** 는 동일 하 게 동작 합니다.

**_Debug** 및 **_CRTDBG_MAP_ALLOC** 가 정의 되 면 **_getcwd** 및 **_wgetcwd** 호출은 **_getcwd_dbg** 및 **_wgetcwd_dbg** 에 대 한 호출로 대체 되어 메모리 할당 디버깅을 허용 합니다. 자세한 내용은 [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md)를 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_getcwd**|\<direct.h>|
|**_wgetcwd**|\<direct.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>참고자료

[디렉터리 제어](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
