---
title: _udiv64
ms.date: 09/02/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 6dabbc94260ef578eb1a58a1b289b4a4654decdd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219686"
---
# <a name="_udiv64"></a>_udiv64

`_udiv64` 내장 함수는 64 비트 부호 없는 정수를 32 비트 부호 없는 정수로 나눕니다. 반환 값은 몫을 보유 하 고 내장 함수는 포인터 매개 변수를 통해 나머지를 반환 합니다. `_udiv64`는 **Microsoft 전용**입니다.

## <a name="syntax"></a>구문

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>매개 변수

*dividend*\
진행 나눌 64 비트 부호 없는 정수입니다.

*divisor*\
진행 로 나눌 32 비트 부호 없는 정수입니다.

*remainder*\
제한이 32 비트 부호 없는 정수 나머지입니다.

## <a name="return-value"></a>반환 값

몫의 32 비트입니다.

## <a name="remarks"></a>설명

내장 `_udiv64` 함수는 *피제수* 로피제수를 나눕니다. *나머지*를 가리키는 32 비트 부호 없는 정수에 나머지를 저장 하 고 몫의 32 비트를 반환 합니다.

`_udiv64` 내장 함수는 Visual Studio 2019 RTM부터 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|헤더|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>참고자료

[_div64](div64.md) \
[컴파일러 내장 함수](compiler-intrinsics.md)
