---
title: 컴파일러 오류 C2509
ms.date: 11/04/2016
f1_keywords:
- C2509
helpviewer_keywords:
- C2509
ms.assetid: 339c1fcd-ec4a-456c-9f18-a9b24d9921af
ms.openlocfilehash: f0322c1d6f80f26b81ac0e93b944a2f3277026ce
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746814"
---
# <a name="compiler-error-c2509"></a>컴파일러 오류 C2509

' identifier ': 멤버 함수가 ' class '에 선언 되지 않았습니다.

함수가 지정 된 클래스에 선언 되지 않았습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2509를 생성 합니다.

```cpp
// C2509.cpp
// compile with: /c
struct A {
   virtual int vfunc() = 0;
   virtual int vfunc2() = 0;
};

struct B : private A {
   using A::vfunc;
   virtual int vfunc2();
};

int B::vfunc() { return 1; }   // C2509
int B::vfunc2() { return 1; }   // OK
```
