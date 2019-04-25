---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 04/05/2018
apiname:
- nearbyint
- nearbyintf
- nearbyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
ms.openlocfilehash: 827286c840c6564c8c3f8b351197b0201509d241
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156202"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

지정된 부동 소수점 값을 정수로 반올림하고 부동 소수점 형식으로 해당 값을 반환합니다.

## <a name="syntax"></a>구문

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
```

```cpp
float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>매개 변수

*x*<br/>
반올림할 값입니다.

## <a name="return-value"></a>반환 값

성공 하면 반환 *x*가 보고 현재 반올림 형식을 사용 하 여, 가장 가까운 정수로 반올림 [fegetround](fegetround-fesetround2.md)합니다. 그렇지 않은 경우에는 함수가 다음 값 중 하나를 반환할 수 있습니다.

|문제|반환|
|-----------|------------|
|*x* = ±INFINITY|±INFINITY, 수정 되지 않은|
|*x* = ±0|±0, 수정 되지 않은|
|*x* = NaN|NaN|

통해 오류가 보고 되지 않습니다 [_matherr](matherr.md)구체적으로이 함수는 모든 보고 하지 **FE_INEXACT** 예외입니다.

## <a name="remarks"></a>설명

이 함수 간의 주요 차이점 및 [인쇄](rint-rintf-rintl.md) 는이 함수는 부정확 한 부동 소수점 예외가 발생 하지 않습니다.

최대 부동 소수점 값은 정확한 정수이므로 이 함수 자체는 오버플로되지 않으며, 사용하는 함수의 버전에 따라 출력이 반환 값을 오버플로할 수는 있습니다.

C++오버 로드를 호출할 수 있도록 오버 로드를 허용 **nearbyint** 및 반환 하는 **float** 하거나 **긴** **double** 매개 변수입니다. C 프로그램에서 **nearbyint** 항상 double 값 두 개를 사용 하며 double 값을 반환 합니다.

## <a name="requirements"></a>요구 사항

|기능|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**nearbyint**, **nearbyintf**, **nearbyintl**|\<math.h>|\<cmath> 또는 \<math.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[수학식 및 부동 소수점 지원](../floating-point-support.md)<br/>
