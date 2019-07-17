---
title: '&lt;vector&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: cdf67b3cb34546f5d0dfcd9a4f3bd96500c18af9
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68241035"
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt; 함수

## <a name="swap"></a> 교환

두 벡터의 요소를 교환합니다.

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
교환할 요소를 제공 하는 벡터 또는 벡터와 교환할 요소가 벡터 *왼쪽*합니다.

*왼쪽*\
교환할 벡터의 요소가 벡터 *오른쪽*합니다.

### <a name="remarks"></a>설명

템플릿 함수는 멤버 함수를 실행 하는 컨테이너 클래스 벡터에서 특수화 된 알고리즘 `left`합니다. [vector:: swap](../standard-library/vector-class.md) *(오른쪽*). 이러한 함수는 컴파일러에서 지정하는 함수 템플릿의 부분 순서 인스턴스입니다. 템플릿 함수가 이러한 방식으로 오버로드되어 함수를 호출할 때 템플릿이 고유하게 일치하지 않으면 컴파일러는 템플릿 함수의 가장 특수화된 버전을 선택합니다. 알고리즘 클래스에서 템플릿 함수의 일반 버전인 **template** \< **class T**> **void swap**( **T&** , **T&** )는 할당을 기준으로 작동하며 속도가 느린 작업입니다. 각 컨테이너의 특수화된 버전은 컨테이너 클래스의 내부 표현을 사용할 수 있으므로 속도가 훨씬 빠릅니다.

### <a name="example"></a>예제

`swap`의 템플릿 버전을 사용하는 예제를 확인하려면 구성원 함수 [vector:: swap](../standard-library/vector-class.md)의 코드 예제를 참조하세요.
