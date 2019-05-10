---
title: operator&gt;=
ms.date: 11/04/2016
f1_keywords:
- operator>=
- std::>=
- std.operator>=
- '>='
- std.>=
- std::operator>=
helpviewer_keywords:
- '>= operator, comparing specific objects'
- operator >=
- operator>=
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
ms.openlocfilehash: 9994456a1345276af426bddd883fa7c53d7b93d0
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220288"
---
# <a name="operatorgt"></a>operator&gt;=

> [!NOTE]
> 이 항목은 Microsoft C++ 설명서에 사용 되는 컨테이너의 작동 하지 않는 예로 C++ 표준 라이브러리입니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

**operator>=** 를 오버로드하여 템플릿 클래스 [Container](../standard-library/sample-container-class.md)의 개체 두 개를 비교합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
bool operator>=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>반환 값

`!(left < right)`를 반환합니다.

## <a name="see-also"></a>참고자료

[\<sample container>](../standard-library/sample-container.md)<br/>
