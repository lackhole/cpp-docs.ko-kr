---
title: tgamma, tgammaf, tgammal
ms.date: 04/05/2018
apiname:
- tgamma
- tgammaf
- tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
ms.openlocfilehash: c9ff92658163fc20ce21496aba34b22b3661748b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155617"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

지정된 값의 감마 함수를 결정합니다.

## <a name="syntax"></a>구문

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
감마를 찾을 값입니다.

## <a name="return-value"></a>반환 값

성공 하면 반환의 감마 *x*합니다.

범위 오류가 발생할 수 있습니다의 크기가 *x* 너무 크거나 너무 작은 데이터 형식에 대 한 합니다. 도메인 오류 또는 범위 오류는 경우 발생할 수 있습니다 *x* < = 0.

|문제|반환|
|-----------|------------|
|x = ±0|±INFINITY|
|x = 음의 정수|NaN|
|x = -INFINITY|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|도메인 오류|NaN|
|극 오류|±HUGE_VAL, ±HUGE_VALF, 또는 ±HUGE_VALL|
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF, 또는 ±HUGE_VALL|
|언더플로 범위 오류|반올림 후의 올바른 값|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **tgamma** 및 반환 하는 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **tgamma** 항상 받아서 반환 된 **double**합니다.

X가 자연수인 경우 이 함수는 (x-1)의 계승을 반환합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**tgamma**, **tgammaf**,  **tgammal**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
