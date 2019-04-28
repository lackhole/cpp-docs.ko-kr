---
title: _access_s, _waccess_s
ms.date: 11/04/2016
apiname:
- _access_s
- _waccess_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- waccess_s
- access_s
- _waccess_s
- _access_s
helpviewer_keywords:
- access_s function
- taccess_s function
- _taccess_s function
- waccess_s function
- _access_s function
- _waccess_s function
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
ms.openlocfilehash: 17d19527323f3e97edecd22ca7c0a0262b1cfbad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335687"
---
# <a name="accesss-waccesss"></a>_access_s, _waccess_s

파일 읽기/쓰기 권한을 결정합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_access, _waccess](access-waccess.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _access_s(
   const char *path,
   int mode
);
errno_t _waccess_s(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>매개 변수

*path*<br/>
파일 또는 디렉터리 경로입니다.

*모드*<br/>
권한 설정

## <a name="return-value"></a>반환 값

파일에 지정된 모드가 있으면 각 함수는 0을 반환합니다. 명명된 파일이 없거나 지정된 모드에서 액세스할 수 없는 경우 함수는 오류 코드를 반환합니다. 이 경우 함수는 다음과 같이 집합에서 오류 코드를 반환하고 `errno`를 같은 값으로 설정합니다.

|errno 값|조건|
|-|-|
`EACCES`|액세스가 거부되었습니다. 파일의 권한 설정이 지정된 액세스를 허용하지 않습니다.
`ENOENT`|파일 이름 또는 경로를 찾을 수 없습니다.
`EINVAL`|잘못된 매개 변수입니다.

자세한 내용은 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

파일을 사용 하는 경우는 **_access_s** 함수는 지정 된 파일이 있고으로 액세스할 수 있는지 여부를 결정의 값으로 지정 된 *모드*합니다. 디렉터리와 함께 사용할 때 **_access_s** 지정한 디렉터리가 있는지만 확인 합니다. Windows 2000 이상의 운영 체제에서 모든 디렉터리에 읽기 및 쓰기 액세스 합니다.

|모드 값|파일 검사|
|----------------|---------------------|
|00|존재만.|
|02|쓰기 권한.|
|04|읽기 권한.|
|06|읽기 및 쓰기 권한.|

파일 읽기 권한 또는 쓰기 권한은 파일을 열기 위한 충분한 권한이 아닙니다. 예를 들어 파일을 다른 프로세스에 의해 잠겨 있으면이 액세스할 수 없습니다 하더라도 **_access_s** 0을 반환 합니다.

**_waccess_s** 의 와이드 문자 버전이 **_access_s**여기서는 *경로* 인수 **_waccess_s** 는 와이드 문자 문자열입니다. 그렇지 않으면 **_waccess_s** 하 고 **_access_s** 동일 하 게 작동 합니다.

이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 하는 경우 *경로* 가 NULL 또는 *모드* 유효한 모드를 지정 하지 않는에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess_s`|**_access_s**|**_access_s**|**_waccess_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_access_s**|\<io.h>|\<errno.h>|
|**_waccess_s**|\<wchar.h> 또는 \<io.h>|\<errno.h>|

## <a name="example"></a>예제

이 예제에서는 **_access_s** 존재 하는지 여부 및 쓰기가 허용 되는지를 crt_access_s.c 라는 파일을 확인 합니다.

```C
// crt_access_s.c

#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    errno_t err = 0;

    // Check for existence.
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )
    {
        printf_s( "File crt_access_s.c exists.\n" );

        // Check for write permission.
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )
        {
            printf_s( "File crt_access_s.c does have "
                      "write permission.\n" );
        }
        else
        {
            printf_s( "File crt_access_s.c does not have "
                      "write permission.\n" );
        }
    }
    else
    {
        printf_s( "File crt_access_s.c does not exist.\n" );
    }
}
```

```Output
File crt_access_s.c exists.
File crt_access_s.c does not have write permission.
```

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat 함수](stat-functions.md)