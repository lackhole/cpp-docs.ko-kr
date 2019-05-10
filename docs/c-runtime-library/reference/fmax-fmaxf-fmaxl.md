---
title: fmax, fmaxf, fmaxl
ms.date: 04/05/2018
apiname:
- fmax
- fmaxf
- fmaxl
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
- fmax
- fmaxf
- fmaxl
- math/fmax
- math/fmaxf
- math/fmaxl
helpviewer_keywords:
- fmax function
- fmaxf function
- fmaxl function
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
ms.openlocfilehash: 371d53257427f2235048807968c82fec1b8bf699
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333435"
---
# <a name="fmax-fmaxf-fmaxl"></a>fmax, fmaxf, fmaxl

지정된 두 개의 숫자 값 중 더 큰 값을 확인합니다.

## <a name="syntax"></a>구문

```C
double fmax(
   double x,
   double y
);

float fmax(
   float x,
   float y
); //C++ only

long double fmax(
   long double x,
   long double y
); //C++ only

float fmaxf(
   float x,
   float y
);

long double fmaxl(
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

성공 하면 반환 중 더 큰 *x* 하거나 *y*합니다. 반환 값은 정확하고 반올림 형식의 영향을 받지 않습니다.

그렇지 않으면 다음 값 중 하나를 반환할 수 있습니다.

|문제|반환|
|-----------|------------|
|*x* = NaN|*y*|
|*y* = NaN|*x*|
|*x* 하 고 *y* = NaN|NaN|

이 함수는 [_matherr](matherr.md)에 지정된 오류를 사용하지 않습니다.

## <a name="remarks"></a>설명

C++는 오버로드를 허용하기 때문에 float 및 long double 형식을 사용하고 반환하는 fmax의 오버로드를 호출할 수 있습니다. C 프로그램에서 fmax는 항상 Double을 사용하고 반환합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**fmax**, **fmaxf**, **fmaxl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[fmin, fminf, fminl](fmin-fminf-fminl.md)<br/>
