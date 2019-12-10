---
title: 컴파일러 오류 C3182
ms.date: 11/04/2016
f1_keywords:
- C3182
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
ms.openlocfilehash: c6b183eb30dd0e617e69ab9aac58bea5cb721591
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761662"
---
# <a name="compiler-error-c3182"></a>컴파일러 오류 C3182

' class ': 관리 되는 또는 WinRTtype 내에서 using 선언 또는 액세스 선언 멤버를 사용할 수 없습니다.

[Using](../../cpp/using-declaration.md) 선언은 모든 형식의 관리 되는 클래스에서 사용할 수 없습니다.

다음 샘플에서는 C3182 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C3182a.cpp
// compile with: /clr /c
ref struct B {
   void mf(int) {
   }
};

ref struct D : B {
   using B::mf;   // C3182, delete to resolve
   void mf(char) {
   }
};
```
