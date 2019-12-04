---
title: 컴파일러 오류 C2689
ms.date: 11/04/2016
f1_keywords:
- C2689
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
ms.openlocfilehash: f3b35d8f68087c9f10d7f2a5d219800fc7a9084a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760224"
---
# <a name="compiler-error-c2689"></a>컴파일러 오류 C2689

' function ': friend 함수는 지역 클래스 내에 정의할 수 없습니다.

로컬 클래스에서 friend 함수를 선언 하 고 정의할 수는 없습니다.

다음 샘플에서는 C2689를 생성 합니다.

```cpp
// C2689.cpp
// compile with: /c
void g() {
   void f2();
   class X {
      friend void f2(){}   // C2689
      friend void f2();   // OK
   };
}
```
