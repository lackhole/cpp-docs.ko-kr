---
title: exp, expf, expl
ms.date: 04/05/2018
apiname:
- expf
- expl
- exp
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
- _expl
- expf
- expl
- exp
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
ms.openlocfilehash: b9fb38adcc442e60864ec632cd92793f16e47502
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288190"
---
# <a name="exp-expf-expl"></a>exp, expf, expl

지수를 계산합니다.

## <a name="syntax"></a>구문

```C
double exp(
   double x
);
float exp(
   float x
);  // C++ only
long double exp(
   long double x
);  // C++ only
float expf(
   float x
);
long double expl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값을 exponentiate 자연 밑 *e* 여 합니다.

## <a name="return-value"></a>반환 값

합니다 **exp** 함수는 부동 소수점 매개 변수의 지 수 값을 반환 *x*성공 하는 경우. 결과 이므로 *e*<sup>*x*</sup>여기서 *e* 는 자연 로그의 밑수입니다. 함수는 INF (무한대) 오버플로 및 언더플로 **exp** 0을 반환 합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|비활성화 상태에서 자동 NaN|없음|_DOMAIN|
|무한대|INVALID|_DOMAIN|
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|

합니다 **exp** 함수는 sse2(스트리밍 SIMD 확장 2 ()를 사용 하는 구현 합니다. SSE2 구현의 사용 제한 사항 및 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](set-sse2-enable.md)을 참조하세요.

## <a name="remarks"></a>설명

C++오버 로드를 호출할 수 있도록 오버 로드를 허용 **exp** 사용 하는 한 **float** 또는 **long double** 인수입니다. C 프로그램에서 **exp** 항상 받아서 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 C 헤더|필수 C++ 헤더|
|--------------|---------------------|---|
|**exp**, **expf**, **expl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_exp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.302585093, y;

   y = exp( x );
   printf( "exp( %f ) = %f\n", x, y );
}
```

```Output
exp( 2.302585 ) = 10.000000
```

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[_CIexp](../../c-runtime-library/ciexp.md)<br/>
