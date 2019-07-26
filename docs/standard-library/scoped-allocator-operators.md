---
title: '&lt;scoped_allocator&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 071fc3b73cd3378b110d6d412bb7575e35a77478
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447336"
---
# <a name="ltscopedallocatorgt-operators"></a>&lt;scoped_allocator&gt; 연산자

|||
|-|-|
|[operator!=](#op_neq)|[연산자==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

두 `scoped_allocator_adaptor` 개체가 다른지 비교합니다.

```cpp
template <class Outer, class... Inner>
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>매개 변수

*비어*\
왼쪽 `scoped_allocator_adaptor` 개체입니다.

*오른쪽*\
오른쪽 `scoped_allocator_adaptor` 개체입니다.

### <a name="return-value"></a>반환 값

`!(left == right)`

## <a name="op_eq_eq"></a>  operator==

두 `scoped_allocator_adaptor` 개체가 같은지 테스트합니다.

```cpp
template <class Outer, class... Inner>
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;
```

### <a name="parameters"></a>매개 변수

*비어*\
왼쪽 `scoped_allocator_adaptor` 개체입니다.

*오른쪽*\
오른쪽 `scoped_allocator_adaptor` 개체입니다.

### <a name="return-value"></a>반환 값

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>참고자료

[<scoped_allocator>](../standard-library/scoped-allocator.md)
