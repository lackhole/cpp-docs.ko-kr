---
title: fmin, fminf, fminl
ms.date: 04/05/2018
apiname:
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
ms.openlocfilehash: f73853e18bd5d7f699cd2c3109fe5fb830859bf1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333380"
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl

지정된 두 값 중 더 작은 값을 확인합니다.

## <a name="syntax"></a>구문

```C
double fmin(
   double x,
   double y
);

float fmin(
   float x,
   float y
); //C++ only

long double fmin(
   long double x,
   long double y
); //C++ only

float fminf(
   float x,
   float y
);

long double fminl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>매개 변수

*x*<br/>
비교할 첫 번째 값입니다.

*y*<br/>
비교할 두 번째 값입니다.

## <a name="return-value"></a>반환 값

성공 하면 반환 중 더 작은 *x* 하거나 *y*합니다.

|입력|결과|
|-----------|------------|
|*x* 가 NaN|*y*|
|*y* 가 NaN|*x*|
|*x* 하 고 *y* = nan|NaN|

함수는 발생 하지 않습니다 [_matherr](matherr.md) 를 호출 하려면 모든 부동 소수점 예외를 발생 시킬 또는 값을 변경 **errno**합니다.

## <a name="remarks"></a>설명

때문에 C++ 오버 로드를 사용 하면 오버 로드를 호출할 수 있습니다 **fmin** 및 반환 하는 **float** 및 **긴** **double** 형식입니다. C 프로그램에서 **fmin** 항상 받아서 반환 된 **double**합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**fmin**, **fminf**, **fminl**|C: \<math.h><br />C++: \<math.h> 또는 \<cmath>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
