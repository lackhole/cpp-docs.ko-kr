---
title: 컴파일러 오류 C2888
ms.date: 11/04/2016
f1_keywords:
- C2888
helpviewer_keywords:
- C2888
ms.assetid: 244f593e-ff25-4dad-b31f-84dafa3bc84a
ms.openlocfilehash: 93fe37c72a04e8c942f910ed3a631e5ba2a542bc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760917"
---
# <a name="compiler-error-c2888"></a>컴파일러 오류 C2888

' identifier ': ' namespace ' 네임 스페이스 내에서 기호를 정의할 수 없습니다.

네임 스페이스에 속하는 기호는를 포함 하는 네임 스페이스에 정의 되어야 합니다.

다음 샘플에서는 C2888를 생성 합니다.

```cpp
// C2888.cpp
// compile with: /c
namespace M {
   namespace N {
      void f1();
      void f2();
   }

   void N::f1() {}   // OK: namspace M encloses N
}

namespace O {
   void M::N::f2() {}   // C2888 namespace O does not enclose M
}
```
