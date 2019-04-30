---
title: '&lt;set&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: 3873a85218c738b3a9693926e064a10b82a553c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412620"
---
# <a name="ltsetgt-functions"></a>&lt;set&gt; 함수

|||
|-|-|
|[swap(map)](#swap)|[swap (multiset)](#swap_multiset)|

## <a name="swap"></a>  swap  (map)

두 set의 요소를 교환합니다.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*right*<br/>
교환할 요소를 제공 하는 집합 또는 set와 교환할 요소가 들어 있는 집합 *왼쪽*합니다.

*left*<br/>
Set와 교환할 요소가 들어 있는 집합 *오른쪽*합니다.

### <a name="remarks"></a>설명

템플릿 함수는 컨테이너 클래스 멤버 함수를 실행 하려면 set에서 특수화 된 알고리즘 `left.` [스왑](../standard-library/set-class.md#swap)(`right`). 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스 내 템플릿 함수의 일반 버전

`template` \< **classT**> **void swap**( **T&**, **T&**)

는 할당을 통해 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.

### <a name="example"></a>예제

`swap`의 템플릿 버전 사용 예제를 보려면 구성원 클래스 [set::swap](../standard-library/set-class.md#swap)에 대한 코드 예제를 참조하세요.

## <a name="swap_multiset"></a>  swap  (multiset)

두 multiset의 요소를 교환합니다.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*right*<br/>
교환할 요소를 제공 하는 multiset 또는 multiset와 교환할 요소가 들어 있는 multiset *왼쪽*합니다.

*left*<br/>
Multiset와 교환할 요소가 들어 있는 multiset *오른쪽*합니다.

### <a name="remarks"></a>설명

템플릿 함수는 멤버 함수를 실행 하는 컨테이너 클래스 multiset에서 특수화 된 알고리즘 `left.` [스왑](../standard-library/multiset-class.md#swap)(`right`). 이 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 함수를 호출할 때 템플릿이 고유하게 일치하지 않는 방식으로 템플릿 함수가 오버로드되면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스 내 템플릿 함수의 일반 버전

`template` \< **classT**> **void swap**( **T&**, **T&**)

는 할당을 통해 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.

### <a name="example"></a>예제

`swap`의 템플릿 버전 사용 예제를 보려면 구성원 클래스 [multiset::swap](../standard-library/multiset-class.md#swap)에 대한 코드 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[\<set>](../standard-library/set.md)<br/>
