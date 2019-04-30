---
title: remquo, remquof, remquol
ms.date: 04/05/2018
apiname:
- remquof
- remquo
- remquol
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
- remquof
- remquol
- remquo
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
ms.openlocfilehash: 4c7e93806600ff674baf186a66662aafdeceeaca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357553"
---
# <a name="remquo-remquof-remquol"></a>remquo, remquof, remquol

두 정수값의 나머지를 계산하고, 몫의 대략적인 크기와 부호가 포함된 정수값을 매개 변수에 지정된 위치에 저장합니다.

## <a name="syntax"></a>구문

```C
double remquo( double numer, double denom, int* quo );
float remquof( float numer, float denom, int* quo );
long double remquol( long double numer, long double denom, int* quo );
```

```cpp
float remquo( float numer, float denom, int* quo ); /* C++ only */
long double remquo( long double numer, long double denom, int* quo ); /* C++ only */
```

### <a name="parameters"></a>매개 변수

*numer*<br/>
분자입니다.

*denom*<br/>
분모입니다.

*quo*<br/>
몫의 대략적인 크기와 부호가 포함된 값을 저장하는 정수에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**remquo** 부동 소수점 나머지를 반환 합니다 *x* / *y*합니다. 경우 값 *y* 는 0.0 **remquo** quiet NaN을 반환 합니다. 자동 NaN 표현에 대 한 자세한 합니다 **printf** 제품군을 참조 하십시오 [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)합니다.

## <a name="remarks"></a>설명

합니다 **remquo** 함수는 부동 소수점 나머지를 계산 *f* 의 *x* / *y* 되도록 *x*   =  *합니까* \* *y* + *f*여기서 *있습니까* 정수가 를 *f* 와 부호가 같도록 *x*, 및의 절대값 *f* 의 절대값 보다 작습니다 *y*합니다.

C++오버 로드를 호출할 수 있도록 오버 로드를 허용 **remquo** 및 반환 하는 **float** 하거나 **긴** **double** 값입니다. C 프로그램에서 **remquo** 는 항상 두 가지 **double** 인수 및 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더(C)|필수 헤더(C++)|
|--------------|---------------------|-|
|**remquo**, **remquof**, **remquol**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_remquo.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;
   int quo = 0;

   z = remquo(w, x, &quo);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
   printf("Approximate signed quotient is %d\n", quo);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
Approximate signed quotient is -3
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
