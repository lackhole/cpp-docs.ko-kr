---
title: '&lt;variant&gt; 연산자'
ms.date: 04/04/2019
f1_keywords:
- variant/std::operator!=
- variant/std::operator==
- variant/std::operatoroperator&gt;
- variant/std::operatoroperator&gt=;
- variant/std::operatoroperator&lt;
- variant/std::operatoroperator&lt;=
helpviewer_keywords:
- std::operator!= (variant)
- std::operator== (variant)
- std::operatoroperator&gt; (variant)
- std::operatoroperator&gt=; (variant)
- std::operatoroperator&lt; (variant)
- std::operatoroperator&lt;= (variant)
ms.openlocfilehash: 0c4042ca1d89f9835b32924b268ef17a56619009
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268565"
---
# <a name="ltvariantgt-operators"></a>&lt;variant&gt; 연산자

## <a name="op_eq_eq"></a> 연산자 = =

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체와 같은지 테스트합니다.

```cpp
template <class... Types>
    constexpr bool operator==(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_neq"></a> operator!=

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체와 같지 않은지 테스트합니다.

```cpp
template <class... Types>
    constexpr bool operator!=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_lt"></a> 연산자&lt;

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 작은지 테스트합니다.

```cpp
template <class... Types>
    constexpr bool operator<(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_lt_eq"></a> 연산자&lt;=

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 작거나 같은지 테스트합니다.

```cpp
template <class... Types>
    constexpr bool operator<=(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_gt"></a> 연산자&gt;

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 큰지 테스트합니다.

```cpp
template <class... Types> constexpr
    bool operator>(const variant<Types...>&, const variant<Types...>&);
```

## <a name="op_gt_eq"></a> 연산자&gt;=

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 크거나 같은지 테스트합니다.

```cpp
template <class... Types> constexpr
    bool operator>=(const variant<Types...>&, const variant<Types...>&);
```
