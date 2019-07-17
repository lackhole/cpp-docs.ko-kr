---
title: '&lt;random&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 87b640d4f3aa3fbfa23ad5603d84102301e71ea4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240391"
---
# <a name="ltrandomgt-functions"></a>&lt;random&gt; 함수

## <a name="generate_canonical"></a> generate_canonical

임의 시퀀스에서 부동 소수점 값을 반환합니다.

> [!NOTE]
> ISO C++ 표준에 따르면 이 함수는 범위 [ `0`, `1`) 내 값을 반환해야 합니다. Visual Studio는 아직 이 제약 조건을 따르고 있지 않습니다. 이 범위에 속하는 값을 생성하려면 [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md)을 사용합니다.

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>매개 변수

*RealType*\
부동 소수점 정수 형식입니다. 가능한 형식은 [\<random>](../standard-library/random.md)를 참조하세요.

*비트*\
난수 생성기입니다.

*범용*\
난수 생성기입니다.

### <a name="remarks"></a>설명

템플릿 함수 호출 `operator()` 의 *Gen* 반복적으로 및 부동 소수점 값으로 반환된 된 값을 팩 `x` 형식의 *RealType* 지정된 된 수를 수집 될 때까지 가 수 비트 `x`합니다. 지정된 된 수의 작은 값입니다 *Bits* (0이 아니어야 함) 및 전체가 수 비트 수가 *RealType*합니다. 첫 번째 호출은 최하위 비트를 제공합니다. 함수에서 `x`을 반환합니다.
