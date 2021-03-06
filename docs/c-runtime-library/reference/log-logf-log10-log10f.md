---
title: log, logf, logl, log10, log10f, log10l
ms.date: 04/05/2018
api_name:
- log10f
- logf
- log10
- log
- log10l
- logl
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
- logf
- logl
- _log10l
- log
- _logl
- log10f
- log10l
- log10
helpviewer_keywords:
- calculating logarithms
- log10f function
- log10 function
- log function
- log10l function
- logl function
- logf function
- logarithms
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
ms.openlocfilehash: f610ead4d71a877051fdec8df2a1564089141eea
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953227"
---
# <a name="log-logf-logl-log10-log10f-log10l"></a>log, logf, logl, log10, log10f, log10l

로그를 계산합니다.

## <a name="syntax"></a>구문

```C
double log( double x );
float logf( float x );
long double logl( double x );
double log10( double x );
float log10f ( float x );
long double log10l( double x );
```

```cpp
float log( float x );  // C++ only
long double log( long double x );  // C++ only
float log10( float x );  // C++ only
long double log10( long double x );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
로그가 있는 값입니다.

## <a name="return-value"></a>반환 값

성공 하는 경우 **로그** 함수는 *x* 의 자연 로그 (밑 *e*)를 반환 합니다. **Log10** 함수는 상용 로그를 반환 합니다. *X* 가 음수인 경우 이러한 함수는 기본적으로 무한 (IND)을 반환 합니다. *X* 가 0 이면 무한대 (INF)를 반환 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± QNAN, IND|없음|_DOMAIN|
|± 0|ZERODIVIDE|_SING|
|*x* < 0|INVALID|_DOMAIN|

**로그** 및 **LOG10** 에는 SSE2 (스트리밍 SIMD 확장 2)를 사용 하는 구현이 있습니다. SSE2 구현의 사용 제한 사항 및 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

## <a name="remarks"></a>설명

C++는 오버 로드를 허용 하므로 **float** 또는 **long double** 값을 사용 하 고 반환 하는 **로그** 및 **log10** 오버 로드를 호출할 수 있습니다. C 프로그램에서 **log** 및 **log10** 는 항상 **double**을 사용 하 고 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**log**, **logf**, **logl**, **log10**, **log10f**, **log10l**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_log.c
/* This program uses log and log10
* to calculate the natural logarithm and
* the base-10 logarithm of 9,000.
*/

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 9000.0;
   double y;

   y = log( x );
   printf( "log( %.2f ) = %f\n", x, y );
   y = log10( x );
   printf( "log10( %.2f ) = %f\n", x, y );
}
```

```Output
log( 9000.00 ) = 9.104980
log10( 9000.00 ) = 3.954243
```

다른 밑에 대한 로그를 생성하려면 수학적 관계 즉, a의 로그 밑 b == 자연 로그(a) / 자연 로그(b)를 사용합니다.

```cpp
// logbase.cpp
#include <math.h>
#include <stdio.h>

double logbase(double a, double base)
{
   return log(a) / log(base);
}

int main()
{
   double x = 65536;
   double result;

   result = logbase(x, 2);
   printf("Log base 2 of %lf is %lf\n", x, result);
}
```

```Output
Log base 2 of 65536.000000 is 16.000000
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[_matherr](matherr.md) <br/>
[pow, powf, powl](pow-powf-powl.md) <br/>
[_CIlog](../../c-runtime-library/cilog.md) <br/>
[_CIlog10](../../c-runtime-library/cilog10.md)<br/>
