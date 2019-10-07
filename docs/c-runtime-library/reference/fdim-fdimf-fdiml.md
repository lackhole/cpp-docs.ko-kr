---
title: fdim, fdimf, fdiml
ms.date: 04/05/2018
api_name:
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
ms.openlocfilehash: 74935f724b678b08e39604d9916c7c5de5925aee
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941295"
---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml

첫 번째 값과 두 번째 값의 양의 차이를 결정합니다.

## <a name="syntax"></a>구문

```C
double fdim(
   double x,
   double y
);

float fdim(
   float x,
   float y
); //C++ only

long double fdim(
   long double x,
   long double y
); //C++ only

float fdimf(
   float x,
   float y
);

long double fdiml(
   long double x,
   long double y
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
첫 번째 값입니다.

*y*<br/>
두 번째 값입니다.

## <a name="return-value"></a>반환 값

*X* 와 *y*의 양수 차이를 반환 합니다.

|반환 값|시나리오|
|------------------|--------------|
|x-y|if x > y|
|0|if x <= y|

그렇지 않으면 다음 오류 중 하나를 반환할 수 있습니다.

|문제점|반환|
|-----------|------------|
|오버플로 범위 오류|+HUGE_VAL, +HUGE_VALF 또는 +HUGE_VALL|
|언더플로 범위 오류|올바른 값(반올림 후)|
|*x* 또는 *y* 는 NaN입니다.|NaN|

오류는 [_matherr](matherr.md)에 지정된 대로 보고됩니다.

## <a name="remarks"></a>설명

는 C++ 오버 로드를 허용 하기 때문에 **float** 및 **long** **double** 형식을 사용 하 고 반환 하는 **fdim** 의 오버 로드를 호출할 수 있습니다. C 프로그램에서 **fdim** 은 항상 **double**을 사용 하 고 반환 합니다.

NaN 처리를 제외 하 고이 함수는와 동일 `fmax(x - y, 0)`합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**fdim**, **fdimf**, **fdiml**|\<math.h>|\<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
