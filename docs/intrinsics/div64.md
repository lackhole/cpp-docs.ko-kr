---
title: _div64
ms.date: 04/17/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: a221cc7cf0655a41873c6777aecd8a9b27131b74
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59982422"
---
# <a name="div64"></a>_div64

`_div64` 내장 함수는 32 비트 정수가 64 비트 정수를 나눕니다. 반환 값의 몫을 보유 하 고 내장 함수 포인터 매개 변수를 통해 나머지를 반환 합니다. `_div64` 됩니다 **Microsoft 전용**합니다.

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
[in] 64 비트 정수 나누기입니다.

*divisor* \
[in] 나눌 32 비트 정수입니다.

*remainder* \
[out] 나머지의 32 비트 정수 비트입니다.

## <a name="return-value"></a>반환 값

몫의 32 비트입니다.

## <a name="remarks"></a>설명

합니다 `_div64` 내장 나눕니다 *피제수* 하 여 *divisor*합니다. 나머지 가리키는 32 비트 정수에 저장 *나머지*, 몫의 32 비트를 반환 합니다.

`_div64` 내장 함수는 Visual Studio 2019 RTM에서 사용할 수 있는 시작 합니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|헤더|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>참고자료

[_udiv64](udiv64.md) \
[컴파일러 내장 함수](compiler-intrinsics.md)
