---
title: '&lt;scoped_allocator&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
ms.openlocfilehash: 7c9f2c3a2425bf3ac6e62ce7fcecfe9315c3e04e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348200"
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

*left*<br/>
왼쪽 `scoped_allocator_adaptor` 개체입니다.

*right*<br/>
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

*left*<br/>
왼쪽 `scoped_allocator_adaptor` 개체입니다.

*right*<br/>
오른쪽 `scoped_allocator_adaptor` 개체입니다.

### <a name="return-value"></a>반환 값

`left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`

## <a name="see-also"></a>참고자료

[<scoped_allocator>](../standard-library/scoped-allocator.md)<br/>
