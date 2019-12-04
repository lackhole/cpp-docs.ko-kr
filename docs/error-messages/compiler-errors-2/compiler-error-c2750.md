---
title: 컴파일러 오류 C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 56f4e6e1d6c392fc377fe5fdf11643ae8a2e503a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759609"
---
# <a name="compiler-error-c2750"></a>컴파일러 오류 C2750

' type ': 참조 형식에 ' n e w '를 사용할 수 없습니다. 대신 ' gcnew '를 사용 하십시오.

인스턴스가 가비지 수집 힙에 배치 되도록 하는 CLR 형식의 인스턴스를 만들려면 [gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md)를 사용 해야 합니다.

다음 샘플에서는 C2750를 생성 합니다.

```cpp
// C2750.cpp
// compile with: /clr
ref struct Y1 {};

int main() {
   Y1 ^ x = new Y1;   // C2750

   // try the following line instead
   Y1 ^ x2 = gcnew Y1;
}
```
