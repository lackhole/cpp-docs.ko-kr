---
title: operator&gt;(&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
ms.openlocfilehash: 6d195148e725857c16a0f037b87a7fa0f71841a4
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220481"
---
# <a name="operatorgt-ltsample-containergt"></a>operator&gt;(&lt;sample container&gt;)

> [!NOTE]
> 이 항목은 Microsoft C++ 설명서에 사용 되는 컨테이너의 작동 하지 않는 예로 C++ 표준 라이브러리입니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

**operator>** 를 오버로드하여 템플릿 클래스 [Container](../standard-library/sample-container-class.md)의 개체 두 개를 비교합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
bool operator*gt;(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>반환 값

`right < left`를 반환합니다.

## <a name="see-also"></a>참고자료

[\<sample container>](../standard-library/sample-container.md)<br/>
