---
title: 컴파일러 오류 C2253
ms.date: 11/04/2016
f1_keywords:
- C2253
helpviewer_keywords:
- C2253
ms.assetid: bd6445ae-b2c1-4669-9657-a8f4acf80b16
ms.openlocfilehash: 847c37c6ae5edf14205d3d46ca624a572c8d6b6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397564"
---
# <a name="compiler-error-c2253"></a>컴파일러 오류 C2253

'function': 순수 지정자 또는 추상 재정의 지정자는 가상 함수에만 사용할 수

비가상 함수를 순수 지정 `virtual`합니다.

다음 샘플에서는 C2253 오류가 생성 됩니다.

```
// C2253.cpp
// compile with: /c
class A {
public:
   void func1() = 0;   // C2253 not virtual
   virtual void func2() = 0;   // OK
};
```

다음 샘플에서는 C2253 오류가 생성 됩니다.

```
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