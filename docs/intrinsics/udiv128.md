---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 0e66bbe978199f47134aa288bdd2bac4eb3e332a
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59982442"
---
# <a name="udiv128"></a>_udiv128

`_udiv128` 내장 함수는 64 비트 부호 없는 정수는 128 비트 부호 없는 정수로 나눕니다. 반환 값의 몫을 보유 하 고 내장 함수 포인터 매개 변수를 통해 나머지를 반환 합니다. `_udiv128` 됩니다 **Microsoft 전용**합니다.

## <a name="syntax"></a>구문

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>매개 변수

*highDividend* \
[in] 피제수의 상위 64 비트입니다.

*lowDividend* \
[in] 피제수의 하위 64 비트입니다.

*divisor* \
[in] 나눌 64 비트 정수입니다.

*remainder* \
[out] 나머지의 64 비트 정수 비트입니다.

## <a name="return-value"></a>반환 값

몫의 64 비트입니다.

## <a name="remarks"></a>설명

전달에 128 비트 피제수의 상위 64 비트 *highDividend*, 및의 하위 64 비트 *lowDividend*합니다. 내장 함수에서이 값을 나눕니다 *divisor*합니다. 나머지가 가리키는 64 비트 부호 없는 정수에 저장 *나머지*, 몫의 64 비트를 반환 합니다.

`_udiv128` 내장 함수는 Visual Studio 2019 RTM에서 사용할 수 있는 시작 합니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|헤더|
|---------------|------------------|------------|
|`_udiv128`|X64|\<immintrin.h>|

## <a name="see-also"></a>참고자료

[_div128](div128.md) \
[컴파일러 내장 함수](compiler-intrinsics.md)
