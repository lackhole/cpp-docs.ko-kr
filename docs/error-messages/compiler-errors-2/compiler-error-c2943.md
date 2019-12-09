---
title: 컴파일러 오류 C2943
ms.date: 11/04/2016
f1_keywords:
- C2943
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
ms.openlocfilehash: ac704c06ac0e455cccdb2b035d0947ae9ec04bd5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755397"
---
# <a name="compiler-error-c2943"></a>컴파일러 오류 C2943

'class': type-class-id가 템플릿의 형식 인수로 재정의되었습니다.

제네릭 또는 템플릿 클래스를 기호 대신 제네릭 또는 템플릿 형식 인수로 사용할 수 없습니다.

다음 샘플에서는 C2943을 생성합니다.

```cpp
// C2943.cpp
// compile with: /c
template<class T>
class List {};

template<class List<int> > class MyList;   // C2943
template<class T >  class MyList;
```
