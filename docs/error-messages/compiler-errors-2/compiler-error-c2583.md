---
title: 컴파일러 오류 C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: b78b9dd69b701e1a66646234d4603973657e90c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366396"
---
# <a name="compiler-error-c2583"></a>컴파일러 오류 C2583

'identifier': ' const/volatile ' 'this'이 포인터가 생성자/소멸자에 대해 잘못 되었습니다.

생성자 나 소멸자를 선언 `const` 또는 `volatile`합니다. 이것은 허용되지 않습니다.

다음 샘플에서는 C2583 오류가 생성 됩니다.

```
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