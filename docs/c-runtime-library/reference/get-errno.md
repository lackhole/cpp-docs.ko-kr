---
title: _get_errno
ms.date: 11/04/2016
apiname:
- _get_errno
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
- _get_errno
helpviewer_keywords:
- get_errno function
- errno global variable
- _get_errno function
ms.assetid: b3fd5ebc-f41b-4314-a2f4-2f2d79d6e740
ms.openlocfilehash: fb0897451c72020cd72a821ec9928ed655d84b7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287735"
---
# <a name="geterrno"></a>_get_errno

errno 전역 변수의 현재 값을 가져옵니다.

## <a name="syntax"></a>구문

```C
errno_t _get_errno(
   int * pValue
);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
현재 값으로 채워지는 정수에 대 한 포인터를 **errno** 변수입니다.

## <a name="return-value"></a>반환 값

성공하는 경우 0을 반환하고, 실패하는 경우 오류 코드를 반환합니다. 하는 경우 *pValue* 됩니다 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 됩니다 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행은 계속 하도록 허용 하는 경우이 함수를 설정 합니다 **errno** 하 **EINVAL** 반환 **EINVAL**합니다.

## <a name="remarks"></a>설명

가능한 값 **errno** Errno.h에 정의 됩니다. [errno 상수](../../c-runtime-library/errno-constants.md)를 참조하세요.

## <a name="example"></a>예제

```C
// crt_get_errno.c
#include <stdio.h>
#include <fcntl.h>
#include <sys/stat.h>
#include <share.h>
#include <errno.h>

int main()
{
   errno_t err;
   int pfh;
   _sopen_s( &pfh, "nonexistent.file", _O_WRONLY, _SH_DENYNO, _S_IWRITE );
   _get_errno( &err );
   printf( "errno = %d\n", err );
   printf( "fyi, ENOENT = %d\n", ENOENT );
}
```

```Output
errno = 2
fyi, ENOENT = 2
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_get_errno**|\<stdlib.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_set_errno](set-errno.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
