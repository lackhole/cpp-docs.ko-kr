---
title: _getmaxstdio
ms.date: 11/04/2016
apiname:
- _getmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmaxstdio
- getmaxstdio
helpviewer_keywords:
- files [C++], number open
- _getmaxstdio function
- getmaxstdio function
- open files, getting number
ms.assetid: 700ca8ce-4a8c-4e00-9467-dfa9d6b831a0
ms.openlocfilehash: ea8e516b4c0806230376ea52e399c9fa1f9a858a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331729"
---
# <a name="getmaxstdio"></a>_getmaxstdio

스트림 I/O 수준에서 허용되는 동시에 열리는 파일 수를 반환합니다.

## <a name="syntax"></a>구문

```C
int _getmaxstdio( void );
```

## <a name="return-value"></a>반환 값

현재 허용 되는 동시에 열리는 파일 수를 나타내는 숫자를 반환 합니다 **stdio** 수준입니다.

## <a name="remarks"></a>설명

사용 하 여 [_setmaxstdio](setmaxstdio.md) 에서 허용 되는 동시에 열리는 파일 수를 구성 하는 **stdio** 수준입니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_getmaxstdio**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_setmaxstdio.c
// The program retrieves the maximum number
// of open files and prints the results
// to the console.

#include <stdio.h>

int main()
{
   printf( "%d\n", _getmaxstdio());

   _setmaxstdio(2048);

   printf( "%d\n", _getmaxstdio());
}
```

```Output
512
2048
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
