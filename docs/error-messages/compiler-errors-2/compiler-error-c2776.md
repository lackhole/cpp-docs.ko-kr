---
title: 컴파일러 오류 C2776
ms.date: 11/04/2016
f1_keywords:
- C2776
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
ms.openlocfilehash: 79758c88e595e6d5ebb5cd4b39a8df8fc1339752
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740067"
---
# <a name="compiler-error-c2776"></a>컴파일러 오류 C2776

속성 당 ' get ' 메서드를 하나만 지정할 수 있습니다.

[속성](../../cpp/property-cpp.md) 확장 특성에는 `get` 함수를 하나만 지정할 수 있습니다. 이 오류는 여러 개의 `get` 함수가 지정 된 경우에 발생 합니다.

다음 샘플에서는 C2776를 생성 합니다.

```cpp
// C2776.cpp
struct A {
   __declspec(property(get=GetProp,get=GetPropToo))
   // try the following line instead
   // __declspec(property(get=GetProp))
      int prop;   // C2776
   int GetProp(void);
   int GetPropToo(void);
};
```
