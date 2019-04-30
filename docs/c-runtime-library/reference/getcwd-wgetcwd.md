---
title: _getcwd, _wgetcwd
ms.date: 11/04/2016
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 4c533f0e716cb9a13c152b9be3c46f60291118d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331794"
---
# <a name="getcwd-wgetcwd"></a>_getcwd, _wgetcwd

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
문자에서는 경로의 최대 길이: **char** 에 대 한 **_getcwd** 하 고 **wchar_t** 에 대 한 **_wgetcwd**합니다.

## <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 *버퍼*합니다. A **NULL** 반환 값은 오류를 나타내고 및 **errno** 설정 됩니다 **ENOMEM**를 할당할 메모리가 부족 한지를 나타내는 *maxlen* 바이트 (경우는 **NULL** 인수도 제공 됩니다 *버퍼*), 또는 **ERANGE**, 경로 보다 긴 임을 나타내는 *maxlen*  문자입니다. 하는 경우 *maxlen* 보다 작거나 0 이면이 함수는 잘못 된 매개 변수 처리기를 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.

## <a name="remarks"></a>설명

합니다 **_getcwd** 함수 기본 드라이브에 대 한 현재 작업 디렉터리의 전체 경로 가져오고에 저장 *버퍼*합니다. 정수 인수 *maxlen* 경로 대 한 최대 길이 지정 합니다. (Null 종결 문자 포함) 경로의 길이 초과 하는 경우 오류가 발생 *maxlen*합니다. 합니다 *버퍼* 인수로 사용할 수 있습니다 **NULL**; 크기 이상의 버퍼 *maxlen* (필요한 경우에)는 자동 할당을 사용 하 여 **malloc**경로 저장 합니다. 호출 하 여 나중에이 버퍼를 해제할 수 **무료** 전달 하는 **_getcwd** 값 (할당된 된 버퍼에 포인터)를 반환 합니다.

**_getcwd** 현재 작업 디렉터리의 경로 나타내는 문자열을 반환 합니다. 현재 작업 디렉터리가 루트 이면 문자열이 백슬래시 끝나는 경우 ( **\\** ). 현재 작업 디렉터리가 루트 이외의 디렉터리이면 문자열은 백슬래시가 아닌 디렉터리 이름으로 끝납니다.

**_wgetcwd** 의 와이드 문자 버전이 **_getcwd**; *버퍼* 의 인수와 반환 값 **_wgetcwd** 는 와이드 문자 문자열입니다. **_wgetcwd** 하 고 **_getcwd** 동일 하 게 작동 합니다.

때 **_DEBUG** 하 고 **_CRTDBG_MAP_ALLOC** 정의 된, 호출 하는 **_getcwd** 하 고 **_wgetcwd** 호출으로 대체 됩니다 **_ getcwd_dbg** 하 고 **_wgetcwd_dbg** 메모리 할당 디버깅을 허용 합니다. 자세한 내용은 [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md)를 참조하세요.

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
