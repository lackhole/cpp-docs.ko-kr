---
title: pow, powf, powl
ms.date: 04/05/2018
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
ms.openlocfilehash: edf6116413caba52f9311f03bdfcc1d87e68a011
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232236"
---
# <a name="pow-powf-powl"></a>pow, powf, powl

계산 *x* 의 거듭제곱 *y*합니다.

## <a name="syntax"></a>구문

```C
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
```

```cpp
double pow( double x, int y );  // C++ only
float pow( float x, float y );  // C++ only
float pow( float x, int y );  // C++ only
long double pow( long double x, long double y );  // C++ only
long double pow( long double x, int y );  // C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
밑입니다.

*y*<br/>
지수입니다.

## <a name="return-value"></a>반환 값

값을 반환 *x*<sup>*y*</sup>합니다. 오버플로 또는 언더플로 시 오류 메시지는 인쇄되지 않습니다.

|x 및 y의 값|pow의 반환 값|
|-----------------------|-------------------------|
|*x* ! = 0.0 및 *y* 0.0 = =|1|
|*x* 0.0 = = 및 *y* 0.0 = =|1|
|*x* 0.0 = = 및 *y* < 0|INF|

## <a name="remarks"></a>설명

**pow** 2 자리 보다 큰 정수 부동 소수점 값을 인식 하지 못하는<sup>64</sup> (예를 들어 1.0E100).

**pow** sse2(스트리밍 SIMD 확장 2 ()를 사용 하는 구현 합니다. SSE2 구현의 사용 제한 사항 및 그 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

때문에 C++ 오버 로드를 사용 하면 다양 한 오버 로드 중 하나를 호출할 수 있습니다 **pow**합니다. C 프로그램에서 **pow** 는 항상 두 가지 **double** 값 및 반환을 **double** 값입니다.

`pow(int, int)` 오버로드는 더 이상 사용할 수 없습니다. 이 오버 로드를 사용 하는 경우 컴파일러가 내보낼 수 있습니다 [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md)합니다. 이 문제를 방지 하려면 첫 번째 매개 변수를 캐스팅 **이중**를 **float**, 또는 **긴** **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|
|-|-|-|
|**pow**, **powf**, **powl**|\<math.h>|\<math.h> 또는 \<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_pow.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.0, y = 3.0, z;

   z = pow( x, y );
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );
}
```

```Output
2.0 to the power of 3.0 is 8.0
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md) <br/>
[sqrt, sqrtf, sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
