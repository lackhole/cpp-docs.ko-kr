---
title: 컴파일러 오류 C3912
ms.date: 11/04/2016
f1_keywords:
- C3912
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
ms.openlocfilehash: 9054124cbfe2d86c062c6e97651bd69eebe5471c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748751"
---
# <a name="compiler-error-c3912"></a>컴파일러 오류 C3912

' event ': 이벤트 형식이 대리자 형식 이어야 합니다.

이벤트가 선언 되었지만 적절 한 형식이 아닙니다.

자세한 내용은 [이벤트](../../extensions/event-cpp-component-extensions.md)를 참조 하세요.

다음 샘플에서는 C3912를 생성 합니다.

```cpp
// C3912.cpp
// compile with: /clr
delegate void H();
ref class X {
   event int Ev;   // C3912
   event H^ Ev2;   // OK
};
```
