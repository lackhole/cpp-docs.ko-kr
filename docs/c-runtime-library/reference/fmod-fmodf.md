---
title: fmod, fmodf, fmodl
ms.date: 04/05/2018
api_name:
- fmod
- fmodf
- fmodl
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fmod
- _fmodl
- fmodf
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
ms.openlocfilehash: e98432a73df8b872593d4cd610139bdfa72a25c4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957075"
---
# <a name="fmod-fmodf-fmodl"></a>fmod, fmodf, fmodl

부동 소수점 나머지를 계산합니다.

## <a name="syntax"></a>구문

```C
double fmod(
   double x,
   double y
);
float fmod(
   float x,
   float y
);  // C++ only
long double fmod(
   long double x,
   long double y
);  // C++ only
float fmodf(
   float x,
   float y
);
long double fmodl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>매개 변수

*x*, *y*<br/>
부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**fmod** 는 *x* / *y*의 부동 소수점 나머지를 반환 합니다. *Y* 값이 0.0 이면 **fmod** 가 자동 NaN을 반환 합니다. **Printf** 패밀리의 자동 NaN 표현에 대 한 자세한 내용은 [printf](printf-printf-l-wprintf-wprintf-l.md)를 참조 하세요.

## <a name="remarks"></a>설명

**Fmod** 함수는 *x* /  i =  xy와같이xy의부동소수점나머지f를계산합니다\* . 여기서 i는 +  는 정수이 고, *f* 는 *x*와 동일한 부호를 가지 며, *f* 의 절대값은 *y*의 절대값 보다 낮습니다.

C++는 오버 로드를 허용 하므로 **float** 및 **long** **double** 값을 사용 하 고 반환 하는 **fmod** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **fmod** 는 항상 두 개의 **double** 인수를 사용 하 고 **double**을 반환 합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fmod**, **fmodf**, **fmodl**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fmod.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = fmod( w, x );
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[_CIfmod](../../c-runtime-library/cifmod.md)<br/>
