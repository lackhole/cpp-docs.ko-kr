---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 5e8cc9ca3dbf19a04d07edb1d73df84f2e29a5c3
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857985"
---
# <a name="_udiv128"></a>_udiv128

`_udiv128` 내장 함수는 128 비트 부호 없는 정수를 64 비트 부호 없는 정수로 나눕니다. 반환 값은 몫을 보유 하 고 내장 함수는 포인터 매개 변수를 통해 나머지를 반환 합니다. `_udiv128`는 **Microsoft**전용입니다.

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
진행 피제수의 상위 64 비트입니다.

*lowDividend* \
진행 피제수의 하위 64 비트입니다.

*divisor* \
진행 로 나눌 64 비트 정수입니다.

*remainder* \
제한이 나머지의 64 비트 정수 비트입니다.

## <a name="return-value"></a>반환 값

몫의 64 비트입니다.

## <a name="remarks"></a>주의

*Highdividend*에서 128 비트 피제수의 상한 64 비트와 *lowdividend*의 하위 64 비트를 전달 합니다. 내장 함수는이 값을 *제수로*나눕니다. *나머지*를 가리키는 64 비트 부호 없는 정수에 나머지를 저장 하 고 몫의 64 비트를 반환 합니다.

`_udiv128` 내장 함수는 Visual Studio 2019 RTM부터 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|Header|
|---------------|------------------|------------|
|`_udiv128`|x64|\<immintrin.h>|

## <a name="see-also"></a>참조

[_div128](div128.md) \
[컴파일러 내장 함수](compiler-intrinsics.md)
