---
title: fma, fmaf, fmal
ms.date: 04/05/2018
apiname:
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: f96592e245e443bae2f3334da51cae5572753708
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333497"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

두 값을 함께 곱하고, 세 번째 값을 더하고 나서, 결과를 반올림하면 중간 반올림으로 인한 정밀도 손실이 없습니다.

## <a name="syntax"></a>구문

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
곱할 첫 번째 값입니다.

*y*<br/>
곱할 두 번째 값입니다.

*z*<br/>
추가할 값입니다.

## <a name="return-value"></a>반환 값

`(x * y) + z`를 반환합니다. 반환 값은 현재 반올림 형식을 사용하여 반올림됩니다.

그렇지 않으면 다음 값 중 하나를 반환할 수 있습니다.

|문제|반환|
|-----------|------------|
|*x* 무한대 = *y* = 0 또는<br /><br /> *x* = 0, *y* = INFINITY|NaN|
|*x* 나 *y* 정확한에서 무한대 = *z* 부호가 반대 무한대 =|NaN|
|*x* 나 *y* = NaN|NaN|
|없습니다 (*x* = 0 이면 *y*= indefinite) 및 *z* = NaN<br /><br /> 없습니다 (*x*= indefinite, *y*= 0) 및 *z* = NaN|NaN|
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF, 또는 ±HUGE_VALL|
|언더플로 범위 오류|올바른 값, 반올림 후.|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **fma** 및 반환 하는 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **fma** 항상 받아서 반환 된 **double**합니다.

이 함수는 무한 정밀도에 도달한 것처럼 값을 계산하고 최종 결과를 반올림합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**fma**, **fmaf**, **fmal**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
