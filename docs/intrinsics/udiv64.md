---
title: _udiv64
ms.date: 04/17/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 73a29b180eeda49a9a25e9e568d25c7563234fad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390154"
---
# <a name="udiv64"></a>_udiv64

`_udiv64` 내장 함수는 64 비트 부호 없는 정수 32 비트 부호 없는 정수로 나눕니다. 반환 값의 몫을 보유 하 고 내장 함수 포인터 매개 변수를 통해 나머지를 반환 합니다. `_udiv64` 됩니다 **Microsoft 전용**합니다.

## <a name="syntax"></a>구문

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>매개 변수

*dividend*<br/>
[in] 나누는 데 64 비트 부호 없는 정수입니다.

*divisor*<br/>
[in] 32 비트 부호 없는 정수를 나눕니다.

*remainder*<br/>
[out] 32 비트 부호 없는 정수 나머지입니다.

## <a name="return-value"></a>반환 값

몫의 32 비트입니다.

## <a name="remarks"></a>설명

합니다 `_udiv64` 내장 나눕니다 *피제수* 하 여 *divisor*합니다. 나머지 가리키는 32 비트 부호 없는 정수에 저장 *나머지*, 몫의 32 비트를 반환 합니다.

`_udiv64` 내장 함수는 Visual Studio 2019 RTM에서 사용할 수 있는 시작 합니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|헤더|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>참고자료

[_div64](div64.md) \
[컴파일러 내장 함수](compiler-intrinsics.md)
