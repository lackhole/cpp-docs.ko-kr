---
title: 컴파일러 오류 C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 4d6f415c8b3c8275ac45ef4d4313021100d9a833
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755150"
---
# <a name="compiler-error-c3160"></a>컴파일러 오류 C3160

'pointer': 관리되는 클래스나 WinRT 클래스의 데이터 멤버는 이 형식을 가질 수 없습니다.

내부 가비지 컬렉션 포인터는 관리되는 클래스나 WinRT 클래스의 내부를 가리킬 수 있습니다. 이 포인터는 전체 개체 포인터보다 더 느리고 가비지 수집기에 의한 특수 처리가 필요하므로 내부 관리되는 포인터를 클래스 멤버로 선언할 수 없습니다.

다음 샘플에서는 C3160 오류가 발생하는 경우를 보여 줍니다.

```cpp
// C3160.cpp
// compile with: /clr
ref struct A {
   // cannot create interior pointers inside a class
   interior_ptr<int> pg;   // C3160
   int g;   // OK
   int* pg2;   // OK
};

int main() {
   interior_ptr<int> pg2;   // OK
}
```
