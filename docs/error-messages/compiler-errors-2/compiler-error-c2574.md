---
title: 컴파일러 오류 C2574
ms.date: 11/04/2016
f1_keywords:
- C2574
helpviewer_keywords:
- C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
ms.openlocfilehash: e0959d875065f7548706b07b032798a68bb4639b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755475"
---
# <a name="compiler-error-c2574"></a>컴파일러 오류 C2574

' 소멸자 ': static으로 선언할 수 없습니다.

`static`소멸자 나 생성자를 모두 선언할 수 없습니다.

다음 샘플에서는 C2574를 생성 합니다.

```cpp
// C2574.cpp
// compile with: /c
class A {
   virtual static ~A();   // C2574
   //  try the following line instead
   // virtual ~A();
};
```
