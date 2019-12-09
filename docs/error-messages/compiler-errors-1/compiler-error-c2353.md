---
title: 컴파일러 오류 C2353
ms.date: 11/04/2016
f1_keywords:
- C2353
helpviewer_keywords:
- C2353
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
ms.openlocfilehash: 89a4a4030e6a38f3a2d95c38b76132c9db0695a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759960"
---
# <a name="compiler-error-c2353"></a>컴파일러 오류 C2353

예외 사양을 사용할 수 없습니다.

관리 되는 클래스의 멤버 함수에는 예외 사양을 사용할 수 없습니다.

다음 샘플에서는 C2353를 생성 합니다.

```cpp
// C2353.cpp
// compile with: /clr /c
ref class X {
   void f() throw(int);   // C2353
   void f();   // OK
};
```
