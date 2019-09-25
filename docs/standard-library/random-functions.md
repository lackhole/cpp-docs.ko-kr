---
title: '&lt;random&gt; 함수'
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 3d94f607fc6b7bdf22d7f573f590b451dbaa718d
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273835"
---
# <a name="ltrandomgt-functions"></a>&lt;random&gt; 함수

## <a name="generate_canonical"></a>generate_canonical

임의 시퀀스에서 부동 소수점 값을 반환합니다.

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>매개 변수

*RealType*\
부동 소수점 정수 형식입니다. 가능한 형식은 [\<random>](../standard-library/random.md)을 참조하세요.

*비트씩*\
사용할 임의의 비트 수입니다.

*생성기*\
난수 생성기 클래스입니다.

*차세대*\
*생성기* 형식의 난수 생성기 인스턴스에 대한 참조입니다.

### <a name="remarks"></a>설명

템플릿 함수는 *Gen*의 `operator()`를 반복해서 호출하고 반환된 값을 `x`에서 지정된 가수(mantissa) 비트 수를 수집할 때까지 *RealType* 유형의 부동 소수점 값 `x`에 압축합니다. 지정된 숫자는 *Bits* 중 작은 숫자(0이 아니어야 함)와 *RealType*의 전체 가수 비트 수입니다. 첫 번째 호출은 최하위 비트를 제공합니다. 이 함수는 `x`를 반환합니다.
