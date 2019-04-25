---
title: independent_bits_engine 클래스
ms.date: 11/04/2016
f1_keywords:
- random/std::independent_bits_engine
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
ms.openlocfilehash: 8f420ca054d20cd222b8eda9a4a35a383a8e535a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159225"
---
# <a name="independentbitsengine-class"></a>independent_bits_engine 클래스

기본 엔진에서 반환한 값의 비트를 다시 압축하여 지정된 수의 비트를 사용하여 숫자의 임의 시퀀스를 생성합니다.

## <a name="syntax"></a>구문

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>매개 변수

*엔진*<br/>
기본 엔진 유형입니다.

*W*<br/>
**단어 크기**. 생성된 각 수의 크기입니다(비트). **사전 조건**: `0 < W ≤ numeric_limits<UIntType>::digits`

*UIntType*<br/>
부호가 없는 정수 결과 형식입니다. 가능한 형식은 [\<random>](../standard-library/random.md)를 참조하세요.

## <a name="members"></a>멤버

||||
|-|-|-|
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|

엔진 구성원에 대한 자세한 내용은 [\<random>](../standard-library/random.md)을 참조하세요.

## <a name="remarks"></a>설명

이 템플릿 클래스는 *엔진 어댑터* 발생 하는 기본 엔진에서 반환 되는 값의 비트를 다시 압축 하 여 값을 생성 *W*-비트 값입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<random>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<random>](../standard-library/random.md)<br/>
