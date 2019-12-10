---
title: 컴파일러 오류 C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: cf92f0fabecfa7292a4d6a8644746c489cbf139f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759752"
---
# <a name="compiler-error-c3375"></a>컴파일러 오류 C3375

'function': 대리자 함수가 모호합니다.

대리자 인스턴스화가 정적 멤버 함수로 될 수 있습니다. 또는 바인딩되지 않은 대리자로서 인스턴스 함수가 될 수 있으므로 컴파일러에서 이 오류가 발생했습니다.

자세한 내용은 [delegate (C++ 구성 요소 확장)](../../extensions/delegate-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3375를 생성합니다.

```cpp
// C3375.cpp
// compile with: /clr
ref struct R {
   static void f(R^) {}
   void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::f);   // C3375
}
```
