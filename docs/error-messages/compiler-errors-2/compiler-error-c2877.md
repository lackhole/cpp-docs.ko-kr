---
title: 컴파일러 오류 C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: b28a301b757e41e6ba238f361520bc89e0744eba
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736323"
---
# <a name="compiler-error-c2877"></a>컴파일러 오류 C2877

' symbol '은 ' class '에서 액세스할 수 없습니다.

기본 클래스에서 파생 된 모든 멤버는 파생 클래스에서 액세스할 수 있어야 합니다.

다음 샘플에서는 C2877를 생성 합니다.

```cpp
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```
