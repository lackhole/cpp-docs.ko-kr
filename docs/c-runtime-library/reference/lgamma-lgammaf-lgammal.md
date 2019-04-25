---
title: lgamma, lgammaf, lgammal
ms.date: 04/05/2018
apiname:
- lgamma
- lgammaf
- lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: 43ce1599ab9161b9fadf5643ddd2ec739ab2d8b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157308"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

지정된 값에 대한 감마 함수 절대 값의 자연 로그를 확인합니다.

## <a name="syntax"></a>구문

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
계산할 값입니다.

## <a name="return-value"></a>반환 값

성공한 경우의 감마 함수 절대 값의 자연 로그를 반환 *x*합니다.

|문제|반환|
|-----------|------------|
|*x* = NaN|NaN|
|*x* = ±0|+INFINITY|
|*x*= 음의 정수|+INFINITY|
|±INFINITY|+INFINITY|
|극 오류|+HUGE_VAL, +HUGE_VALF 또는 +HUGE_VALL|
|오버플로 범위 오류|±HUGE_VAL, ±HUGE_VALF, 또는 ±HUGE_VALL|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **lgamma** 및 반환 하는 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **lgamma** 항상 받아서 반환 된 **double**합니다.

X가 유리수 인 경우이 함수는 (x-1)의 계승의 로그를 반환 합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**lgamma**, **lgammaf**, **lgammal**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
