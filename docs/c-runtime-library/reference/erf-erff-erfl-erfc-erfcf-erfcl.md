---
title: erf, erff, erfl, erfc, erfcf, erfcl
ms.date: 01/31/2019
api_name:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
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
ms.openlocfilehash: df724ed056c02d79b5b51f97ae4aaf8ae267fde5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70937615"
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

**Erf** 함수는 *x*의 가우스 오차 함수를 반환 합니다. **Erfc** 함수는 *x*의 보완 가우스 오차 함수를 반환 합니다.

## <a name="remarks"></a>설명

**Erf** 함수는 다음과 같이 정의 되는 *x*의 가우스 오차 함수를 계산 합니다.

![X의 오류 함수](media/crt_erf_formula.PNG "X의 오류 함수")

보완적인 가우스 오류 함수는 erf (x)로 정의 됩니다. **Erf** 함수는-1.0 ~ 1.0 범위의 값을 반환 합니다. 반환되는 오류가 없습니다. **Erfc** 함수는 0 ~ 2 범위의 값을 반환 합니다. *X* 가 **erfc**에 대해 너무 크면 **errno** 변수는 **ERANGE**로 설정 됩니다.

는 C++ 오버 로드를 허용 하기 때문에 **float** 및 **long** **double** 형식을 사용 하 고 반환 하는 **erf** 및 **erfc** 오버 로드를 호출할 수 있습니다. C 프로그램에서 **erf** 및 **erfc** 는 항상 **double**을 사용 하 고 반환 합니다.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
