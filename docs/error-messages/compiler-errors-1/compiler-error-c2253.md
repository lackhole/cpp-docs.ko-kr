---
title: 컴파일러 오류 C2253
ms.date: 11/04/2016
f1_keywords:
- C2253
helpviewer_keywords:
- C2253
ms.assetid: bd6445ae-b2c1-4669-9657-a8f4acf80b16
ms.openlocfilehash: 89acfd8a03dc0ee2dc25e14e0b3a63ab25151cc6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758855"
---
# <a name="compiler-error-c2253"></a>컴파일러 오류 C2253

' function ': 순수 지정자 또는 추상 재정의 지정자는 가상 함수 에서만 사용할 수 있습니다.

비가상 함수는 순수 `virtual`로 지정 됩니다.

다음 샘플에서는 C2253를 생성 합니다.

```cpp
// C2253.cpp
// compile with: /c
class A {
public:
   void func1() = 0;   // C2253 not virtual
   virtual void func2() = 0;   // OK
};
```

다음 샘플에서는 C2253를 생성 합니다.

```cpp
// C2253_2.cpp
// compile with: /clr /c
ref struct A {
   property int Prop_3 {
      int get() abstract;   // C2253
      // try the following line instead
      // virtual int get() abstract;

      void set(int i) abstract;   // C2253
      // try the following line instead
      // virtual void set(int i) abstract;
   }
};
```
