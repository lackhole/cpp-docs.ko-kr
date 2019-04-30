---
title: remainder, remainderf, remainderl
ms.date: 04/05/2018
apiname:
- remainderl
- remainder
- remainderf
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- remainderf
- remainder
- remainderl
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
ms.openlocfilehash: 9a9abe82e69122ca87f44e293e1da725c97045d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357644"
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

부동 소수점 나머지 *x* / *y*합니다. 경우 값 *y* 는 0.0 **나머지** quiet NaN을 반환 합니다. 자동 NaN 표현에 대 한 자세한 합니다 **printf** 제품군을 참조 하십시오 [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)합니다.

## <a name="remarks"></a>설명

합니다 **나머지** 함수는 부동 소수점 나머지를 계산 *r* 의 *x* / *y* 되도록 *x*   =  *n* \* *y* + *r*여기서 *n*되는 정수 값에서 가장 가까운 *x* / *y* 하 고 *n*짝수 때마다 &#124; *n*  -  *x* / *y* &#124; = 1/2입니다. 때 *r* = 0 이면 *r* 와 부호가 같도록 *x*합니다.

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **나머지** 및 반환 하는 **float** 또는 **긴** **double** 값입니다. C 프로그램에서 **나머지** 는 두 가지는 항상 **double** 인수 및 반환을 **double**합니다.

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
