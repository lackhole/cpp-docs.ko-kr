---
title: 컴파일러 오류 C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: a0154d1d9a57d0faa795e639640eb6cb42e7c7cb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748647"
---
# <a name="compiler-error-c2583"></a>컴파일러 오류 C2583

' identifier ': ' const/volatile ' ' this ' 포인터는 생성자/소멸자에 사용할 수 없습니다.

생성자 또는 소멸자가 `const` 또는 `volatile`선언 되었습니다. 이는 허용되지 않습니다.

다음 샘플에서는 C2583를 생성 합니다.

```cpp
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```
