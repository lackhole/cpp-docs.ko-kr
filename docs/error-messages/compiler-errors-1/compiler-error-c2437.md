---
title: 컴파일러 오류 C2437
ms.date: 11/04/2016
f1_keywords:
- C2437
helpviewer_keywords:
- C2437
ms.assetid: 2d2b3c6c-856a-4b27-ae10-64813b3e5483
ms.openlocfilehash: 745ab4f53223ec60e745068b1857206ed114086a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744344"
---
# <a name="compiler-error-c2437"></a>컴파일러 오류 C2437

' identifier ': 이미 초기화 되었습니다.

개체는 한 번만 초기화할 수 있습니다.

다음 샘플에서는 C2437를 생성 합니다.

```cpp
// C2437.cpp
// compile with: /c
class A {
public:
   A(int i) {}
};

class B : A {
   B() : A(1), A(2) {}   // C2437
   B() : A(1) {}   // OK
};
```
