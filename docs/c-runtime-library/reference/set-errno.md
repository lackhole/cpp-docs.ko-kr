---
title: _set_errno
ms.date: 11/04/2016
api_name:
- _set_errno
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_errno
- _set_errno
helpviewer_keywords:
- errno global variable
- set_errno function
- _set_errno function
ms.assetid: d338914a-1894-4cf3-ae45-f2c4eb26590b
ms.openlocfilehash: 09800276886ecf1c2fdd2ffee63ddcb8cc57f61e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948601"
---
# <a name="_set_errno"></a>_set_errno

**Errno** 전역 변수의 값을 설정 합니다.

## <a name="syntax"></a>구문

```C
errno_t _set_errno( int error_value );
```

### <a name="parameters"></a>매개 변수

*error_value*<br/>
**Errno**의 새 값입니다.

## <a name="return-value"></a>반환 값

성공하면 0을 반환합니다.

## <a name="remarks"></a>설명

가능한 값은 Errno.h에서 정의됩니다. [errno 상수](../../c-runtime-library/errno-constants.md)를 참조하세요.

## <a name="example"></a>예제

```C
// crt_set_errno.c
#include <stdio.h>
#include <errno.h>

int main()
{
   _set_errno( EILSEQ );
   perror( "Oops" );
}
```

```Output
Oops: Illegal byte sequence
```

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_set_errno**|\<stdlib.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_get_errno](get-errno.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
