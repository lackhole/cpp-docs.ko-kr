---
title: 컴파일러 오류 C2575
ms.date: 11/04/2016
f1_keywords:
- C2575
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
ms.openlocfilehash: a63696ba35a8b923f8fbf0c6d6387f2402969cff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755462"
---
# <a name="compiler-error-c2575"></a>컴파일러 오류 C2575

' identifier ': 멤버 함수와 기본만 virtual 일 수 있습니다.

전역 함수 또는 클래스가 `virtual`선언 됩니다. 이는 허용되지 않습니다.

다음 샘플에서는 C2575를 생성 합니다.

```cpp
// C2575.cpp
// compile with: /c
virtual void func() {}   // C2575

void func2() {}
struct A {
   virtual void func2(){}
};
```
