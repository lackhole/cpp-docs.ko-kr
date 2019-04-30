---
title: 컴파일러 오류 C2694
ms.date: 11/04/2016
f1_keywords:
- C2694
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
ms.openlocfilehash: 4897512f6bd27465b7281d7a27757918128202d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367748"
---
# <a name="compiler-error-c2694"></a>컴파일러 오류 C2694

'override': 재정의 가상 함수에 기본 클래스 보다 덜 제한적인 예외 사양이 가상 멤버 함수 'base'

가상 함수 재정의 되었습니다 [/Za](../../build/reference/za-ze-disable-language-extensions.md)의 함수를 재정의 했습니다 덜 제한적인 [예외 사양이](../../cpp/exception-specifications-throw-cpp.md)합니다.

다음 샘플에서는 C2694 오류가 생성 됩니다.

```
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