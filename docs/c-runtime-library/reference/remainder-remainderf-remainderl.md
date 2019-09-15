---
title: remainder, remainderf, remainderl
ms.date: 04/05/2018
api_name:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
ms.openlocfilehash: 851f022325bb617cb2b0ae9a331b680b9d9fd303
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949420"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

두 부동 소수점 값 몫의 나머지를 가장 가까운 적분 값으로 반올림하여 계산합니다.

## <a name="syntax"></a>구문

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
```

```cpp
float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>매개 변수

*x*<br/>
분자입니다.

*y*<br/>
분모입니다.

## <a name="return-value"></a>반환 값

*X* / *y*의 부동 소수점 나머지입니다. *Y* 값이 0.0 이면 **나머지가** 자동 NaN을 반환 합니다. **Printf** 패밀리의 자동 NaN 표현에 대 한 자세한 내용은 [printf, _printf_l, wprintf, _printf_l](printf-printf-l-wprintf-wprintf-l.md)을 참조 하세요.

## <a name="remarks"></a>설명

**나머지** 함수 *는 x* =  / *n* *y r 인*x y의 부동 소수점 나머지 *r* 을 계산 합니다. 여기서 n +  \* -  *x* /  &#124; &#124;y에 대 한 값에 가장 가까운 정수 이며 n x y = 1/2 인 경우에도 마찬가지입니다. /  *R* = 0 인 경우 *r* 은 *x*와 동일한 부호를 가집니다.

는 C++ 오버 로드를 허용 하므로 **float** 또는 **long** **double** 값을 사용 하 고 반환 하는 **나머지** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **나머지** 는 항상 두 개의 **double** 인수를 사용 하 고 **double**을 반환 합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------|-|
|**remainder**, **remainderf**, **remainderl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_remainder.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = remainder(w, x);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
