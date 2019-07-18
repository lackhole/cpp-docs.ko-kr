---
title: '&lt;forward_list&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: 64a49273cafd72158f176ee34ec271557ebee097
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240657"
---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt; 연산자

## <a name="op_eq_eq"></a> 연산자 = =

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체와 같은지 테스트합니다.

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`forward_list` 형식의 개체입니다.

*오른쪽*\
`forward_list` 형식의 개체입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `operator==`을 오버로드하여 템플릿 클래스 `forward_list`의 개체 두 개를 비교합니다. 함수에서 `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`을 반환합니다.

## <a name="op_neq"></a> operator!=

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체와 같지 않은지 테스트합니다.

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`forward_list` 형식의 개체입니다.

*오른쪽*\
`forward_list` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

목록이 같지 않으면 **true**이고 목록이 같으면 **false**입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `!(left == right)`를 반환합니다.

## <a name="op_lt"></a> 연산자&lt;

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 작은지 테스트합니다.

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`forward_list` 형식의 개체입니다.

*오른쪽*\
`forward_list` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 목록이 연산자 우변의 목록보다 작지만 같지 않으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `operator<`을 오버로드하여 템플릿 클래스 `forward_list`의 개체 두 개를 비교합니다. 함수에서 `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`을 반환합니다.

## <a name="op_lt_eq"></a> 연산자&lt;=

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 작거나 같은지 테스트합니다.

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`forward_list` 형식의 개체입니다.

*오른쪽*\
`forward_list` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 목록이 연산자 우변의 목록보다 작거나 같으면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `!(right < left)`를 반환합니다.

## <a name="op_gt"></a> 연산자&gt;

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 큰지 테스트합니다.

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`forward_list` 형식의 개체입니다.

*오른쪽*\
`forward_list` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

연산자 좌변의 목록이 연산자 우변의 목록보다 크면 **true**이고 그렇지 않으면 **false**입니다.

### <a name="remarks"></a>설명

이 템플릿 함수는 `right < left`를 반환합니다.

## <a name="op_gt_eq"></a> 연산자&gt;=

연산자의 좌변에 있는 정방향 목록 개체가 우변에 있는 정방향 목록 개체보다 크거나 같은지 테스트합니다.

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
`forward_list` 형식의 개체입니다.

*오른쪽*\
`forward_list` 형식의 개체입니다.

### <a name="return-value"></a>반환 값

**true 이면** 연산자의 좌 변에 있는 정방향 목록 보다 큰 또는 연산자의 오른쪽에 있는 정방향 목록에는 같지 않으면 이면 **false**합니다.

### <a name="remarks"></a>설명

템플릿 함수가 `!(left < right)`을 반환합니다.
