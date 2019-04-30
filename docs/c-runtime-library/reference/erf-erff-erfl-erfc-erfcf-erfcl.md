---
title: erf, erff, erfl, erfc, erfcf, erfcl
ms.date: 01/31/2019
apiname:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
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
- erfl
- erf
- erff
- erfc
- erfcf
- erfcl
helpviewer_keywords:
- erfl function
- erff function
- erf function
- erfcl function
- erfcf function
- erfc function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: 4270d8366686ea282a4dd37741d9f8e37991b88f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62289213"
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

값의 오차 함수 또는 보상 오차 함수를 계산합니다.

## <a name="syntax"></a>구문

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
부동 소수점 값입니다.

## <a name="return-value"></a>반환 값

합니다 **erf** 함수는 가우스의 오류 함수는 반환 *x*합니다. 합니다 **erfc** 함수는 가우스의 오류 함수는 반환 *x*합니다.

## <a name="remarks"></a>설명

**erf** 함수 계산의 가우스 오차 함수 *x*, 정의 됩니다.

![X의 오차 함수](media/crt_erf_formula.PNG "x의 오차 함수")

가우스 보상 오차 함수 란 1-erf (x). 합니다 **erf** 함수 1.0-1.0 범위의 값을 반환 합니다. 반환되는 오류가 없습니다. 합니다 **erfc** 함수는 0 ~ 2 범위에 값을 반환 합니다. 하는 경우 *x* 에 대해 너무 큽니다 **erfc**의 **errno** 변수로 설정 됩니다 **ERANGE**합니다.

때문에 C++ 오버 로드를 허용의 오버 로드를 호출할 수 있습니다 **erf** 하 고 **erfc** 및 반환 하는 **float** 하 고 **긴** **이중** 형식입니다. C 프로그램에서 **erf** 하 고 **erfc** 항상 하 고 반환을 **double**합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
