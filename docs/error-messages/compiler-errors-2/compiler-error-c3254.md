---
title: 컴파일러 오류 C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 6b9ff41fb4f45d9570869ca90e3c6091cc03a58a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754253"
---
# <a name="compiler-error-c3254"></a>컴파일러 오류 C3254

' explicit override ': 클래스에 명시적 재정의 ' override '가 포함 되어 있지만 함수 선언을 포함 하는 인터페이스에서 파생 되지 않습니다.

메서드를 [명시적으로 재정의할](../../cpp/explicit-overrides-cpp.md) 때 재정의를 포함 하는 클래스가 재정의 하는 함수를 포함 하는 형식에서 직접 또는 간접적으로 파생 되어야 합니다.

다음 샘플에서는 C3254를 생성 합니다.

```cpp
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```
