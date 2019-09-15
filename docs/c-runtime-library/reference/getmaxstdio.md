---
title: _getmaxstdio
ms.date: 11/04/2016
api_name:
- _getmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getmaxstdio
- getmaxstdio
helpviewer_keywords:
- files [C++], number open
- _getmaxstdio function
- getmaxstdio function
- open files, getting number
ms.assetid: 700ca8ce-4a8c-4e00-9467-dfa9d6b831a0
ms.openlocfilehash: cf3f55262e54ec4d5205d08dfcb499f2802ded23
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955031"
---
# <a name="_getmaxstdio"></a>_getmaxstdio

스트림 I/O 수준에서 허용되는 동시에 열리는 파일 수를 반환합니다.

## <a name="syntax"></a>구문

```C
int _getmaxstdio( void );
```

## <a name="return-value"></a>반환 값

현재 **stdio.h** 수준에서 허용 되는 동시에 열려 있는 파일 수를 나타내는 숫자를 반환 합니다.

## <a name="remarks"></a>설명

[_Setmaxstdio](setmaxstdio.md) 를 사용 하 여 **stdio.h** 수준에서 허용 되는 동시에 열리는 파일 수를 구성 합니다.

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
