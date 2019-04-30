---
title: Concurrency::fast_math 네임스페이스
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::fast_math
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
ms.openlocfilehash: e774c2d8e4431960e796ee1e6cc87b924d04174b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405601"
---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math 네임스페이스

함수는 `fast_math` 네임 스페이스는 정확성이 낮으며, 단 정밀도 지원 (`float`), DirectX 내장 함수를 호출 합니다. 두 가지 버전의 각 함수에 예를 들어 `cos` 고 `cosf`입니다. 버전을 모두 사용 하 고 반환 된 `float`, 하지만 각 호출에 동일한 DirectX 내장 함수입니다.

## <a name="syntax"></a>구문

```
namespace fast_math;
```

## <a name="members"></a>멤버

### <a name="functions"></a>함수

|이름|설명|
|----------|-----------------|
|[cos](concurrency-fast-math-namespace-functions.md#cos)|인수의 아크코사인 계산|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|인수의 아크코사인 계산|
|[asin](concurrency-fast-math-namespace-functions.md#asin)|인수의 아크사인 계산|
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|인수의 아크사인 계산|
|[atan](concurrency-fast-math-namespace-functions.md#atan)|인수의 아크탄젠트를 계산합니다.|
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|_Y/_X의 아크탄젠트를 계산합니다.|
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|_Y/_X의 아크탄젠트를 계산합니다.|
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|인수의 아크탄젠트를 계산합니다.|
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|인수의 한계를 계산합니다.|
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|인수의 한계를 계산합니다.|
|[cos](concurrency-fast-math-namespace-functions.md#cos)|인수의 코사인 계산|
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|인수의 코사인 계산|
|[cosh](concurrency-fast-math-namespace-functions.md#cosh)|인수의 쌍 곡 코사인 값을 계산합니다.|
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|인수의 쌍 곡 코사인 값을 계산합니다.|
|[exp](concurrency-fast-math-namespace-functions.md#exp)|밑이 e 인수를 계산합니다.|
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|밑이 2 인수를 계산합니다.|
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|밑이 2 인수를 계산합니다.|
|[expf](concurrency-fast-math-namespace-functions.md#expf)|밑이 e 인수를 계산합니다.|
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|인수의 절대값을 반환 합니다.|
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|인수의 절대값을 반환 합니다.|
|[floor](concurrency-fast-math-namespace-functions.md#floor)|인수의 밑을 계산합니다.|
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|인수의 밑을 계산합니다.|
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|인수의 최대 숫자 값을 확인|
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|인수의 최대 숫자 값을 확인|
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|인수의 최소 숫자 값을 확인|
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|인수의 최소 숫자 값을 확인|
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|_X/_Y의 부동 소수점 나머지를 계산합니다.|
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|_X/_Y의 부동 소수점 나머지를 계산합니다.|
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|_X의 지 수 고가 수를 가져옵니다.|
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|_X의 지 수 고가 수를 가져옵니다.|
|[isfinite](concurrency-fast-math-namespace-functions.md#isfinite)|인수가 유한 값에 있는지 여부를 결정 합니다.|
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|인수가 무한대 인지 여부를 결정 합니다.|
|[isnan](concurrency-fast-math-namespace-functions.md#isnan)|인수가 NaN 인지 확인|
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|가 수 및 지 수에서 실수를 계산합니다.|
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|가 수 및 지 수에서 실수를 계산합니다.|
|[log](concurrency-fast-math-namespace-functions.md#log)|인수의 밑 e 인 로그를 계산|
|[log10](concurrency-fast-math-namespace-functions.md#log10)|인수의 밑이 10 인 로그 계산|
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|인수의 밑이 10 인 로그 계산|
|[log2](concurrency-fast-math-namespace-functions.md#log2)|인수의 밑이 2 인 로그 계산|
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|인수의 밑이 2 인 로그 계산|
|[logf](concurrency-fast-math-namespace-functions.md#logf)|인수의 밑 e 인 로그를 계산|
|[modf](concurrency-fast-math-namespace-functions.md#modf)|_X를 소수 부분과 정수 부분으로 분할합니다.|
|[modff](concurrency-fast-math-namespace-functions.md#modff)|_X를 소수 부분과 정수 부분으로 분할합니다.|
|[pow](concurrency-fast-math-namespace-functions.md#pow)|_X의 _Y 승을 계산 합니다.|
|[powf](concurrency-fast-math-namespace-functions.md#powf)|_X의 _Y 승을 계산 합니다.|
|[round](concurrency-fast-math-namespace-functions.md#round)|_X를 가장 가까운 정수로 반올림 합니다.|
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|_X를 가장 가까운 정수로 반올림 합니다.|
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|인수의 제곱근의 역 수를 반환합니다.|
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|인수의 제곱근의 역 수를 반환합니다.|
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|인수의 부호를 반환합니다.|
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|인수의 부호를 반환합니다.|
|[sin](concurrency-fast-math-namespace-functions.md#sin)|인수의 사인 값을 계산합니다.|
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|_X의 사인 및 코사인 값 계산|
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|_X의 사인 및 코사인 값 계산|
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|인수의 사인 값을 계산합니다.|
|[sinh](concurrency-fast-math-namespace-functions.md#sinh)|인수의 쌍 곡 사인 값을 계산합니다.|
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|인수의 쌍 곡 사인 값을 계산합니다.|
|[sqrt](concurrency-fast-math-namespace-functions.md#sqrt)|인수의 제곱근을 계산합니다.|
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|인수의 제곱근을 계산합니다.|
|[tan](concurrency-fast-math-namespace-functions.md#tan)|인수의 탄젠트 값을 계산합니다.|
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|인수의 탄젠트 값을 계산합니다.|
|[tanh](concurrency-fast-math-namespace-functions.md#tanh)|인수의 쌍 곡 탄젠트 값을 계산합니다.|
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|인수의 쌍 곡 탄젠트 값을 계산합니다.|
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|인수는 정수 구성 요소를 자르는|
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|인수는 정수 구성 요소를 자르는|

## <a name="requirements"></a>요구 사항

**헤더:** amp_math.h

**네임스페이스:** Concurrency::fast_math

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
