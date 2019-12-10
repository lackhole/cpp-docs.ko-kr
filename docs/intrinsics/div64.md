---
title: _div64
ms.date: 09/02/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: 59c5eae66f9e93cb88f9512e405376f2ef5f1ceb
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858024"
---
# <a name="_div64"></a>_div64

`_div64` 내장 함수는 64 비트 정수를 32 비트 정수로 나눕니다. 반환 값은 몫을 보유 하 고 내장 함수는 포인터 매개 변수를 통해 나머지를 반환 합니다. `_div64`는 **Microsoft**전용입니다.

## <a name="syntax"></a>구문

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>매개 변수

*dividend* \
진행 나눌 64 비트 정수입니다.

*divisor* \
진행 로 나눌 32 비트 정수입니다.

*remainder* \
제한이 나머지의 32 비트 정수 비트입니다.

## <a name="return-value"></a>반환 값

몫의 32 비트입니다.

## <a name="remarks"></a>주의

`_div64` 내장 함수는 *배당* 을 *제수로*나눕니다. *나머지*를 가리키는 32 비트 정수에 나머지를 저장 하 고 몫의 32 비트를 반환 합니다.

`_div64` 내장 함수는 Visual Studio 2019 RTM부터 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|Header|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>참조

[_udiv64](udiv64.md) \
[컴파일러 내장 함수](compiler-intrinsics.md)
