---
title: 컴파일러 오류 C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: 6129ff691f804b31fdb8cb487ac4609e4bca6ef2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755189"
---
# <a name="compiler-error-c2698"></a>컴파일러 오류 C2698

' 선언 1 '에 대 한 using 선언은 ' 선언 2 '에 대 한 기존 using 선언과 함께 사용할 수 없습니다.

데이터 멤버에 대 한 [using 선언이](../../cpp/using-declaration.md) 있으면 함수는 오버 로드 될 수 있으므로 동일한 이름을 사용 하는 동일한 범위에 있는 using 선언은 허용 되지 않습니다.

다음 샘플에서는 C2698를 생성 합니다.

```cpp
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```
