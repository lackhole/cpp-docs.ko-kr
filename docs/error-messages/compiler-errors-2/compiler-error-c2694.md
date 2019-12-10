---
title: 컴파일러 오류 C2694
ms.date: 11/04/2016
f1_keywords:
- C2694
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
ms.openlocfilehash: ca378c3e0ce88b454cb89fc08470a277a7be6f47
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755228"
---
# <a name="compiler-error-c2694"></a>컴파일러 오류 C2694

' override ': 재정의 가상 함수에 기본 클래스 가상 멤버 함수 ' base ' 보다 덜 제한적인 예외 사양이 있습니다.

가상 함수가 재정의 되었지만 [/za](../../build/reference/za-ze-disable-language-extensions.md)에서 재정의 하는 함수에 덜 제한적인 [예외 사양이](../../cpp/exception-specifications-throw-cpp.md)있습니다.

다음 샘플에서는 C2694를 생성 합니다.

```cpp
// C2694.cpp
// compile with: /Za /c
class MyBase {
public:
   virtual void f(void) throw(int) {
   }
};

class Derived : public MyBase {
public:
   void f(void) throw(...) {}   // C2694
   void f2(void) throw(int) {}   // OK
};
```
