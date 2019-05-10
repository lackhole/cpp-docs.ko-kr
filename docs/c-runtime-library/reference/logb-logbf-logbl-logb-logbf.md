---
title: logb, logbf, logbl, _logb, _logbf
ms.date: 04/05/2018
apiname:
- logb
- _logb
- _logbl
- logbf
- logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
ms.openlocfilehash: 9f598eedaf30b1f2a1858129e648a117355d112e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285715"
---
# <a name="logb-logbf-logbl-logb-logbf"></a>logb, logbf, logbl, _logb, _logbf

부동 소수점 인수의 지수 값을 추출합니다.

## <a name="syntax"></a>구문

```C
double logb(
   double x
);
float logb(
   float x
); // C++ only
long double logb(
   long double x
); // C++ only
float logbf(
   float x
);
long double logbl(
   long double x
);
double _logb(
   double x
);
float _logbf(
   float x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

**logb** 비편향된 지 수 값을 반환 *x* 부동 소수점 값으로 표현 하는 부호 있는 정수입니다.

## <a name="remarks"></a>설명

합니다 **logb** 함수에 부동 소수점 인수의 지 수 값을 추출 *x*처럼 *x* 무한 범위로 표현 된 합니다. 경우는 인수 *x* 는 비 정규화 것 처럼 처리 됩니다 정규화 된 합니다.

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **logb** 및 반환 하는 **float** 또는 **긴** **double** 값입니다. C 프로그램에서 **logb** 항상 받아서 반환 된 **double**합니다.

|입력|SEH 예외|Matherr 예외|
|-----------|-------------------|-----------------------|
|± QNAN,IND|없음|_DOMAIN|
|± 0|ZERODIVIDE|_SING|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_logb**|\<float.h>|
|**logb**, **logbf**, **logbl**, **_logbf**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
