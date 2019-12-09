---
title: 컴파일러 오류 C2254
ms.date: 11/04/2016
f1_keywords:
- C2254
helpviewer_keywords:
- C2254
ms.assetid: 49bb3d7e-3bdf-4af6-937c-fa627be412a9
ms.openlocfilehash: 38220575a48720a9df0e232ef74c8743e7e056c7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758842"
---
# <a name="compiler-error-c2254"></a>컴파일러 오류 C2254

' function ': 순수 지정자 또는 추상 재정의 지정자는 friend 함수에 사용할 수 없습니다.

`friend` 함수는 순수 `virtual`로 지정 됩니다.

다음 샘플에서는 C2254를 생성 합니다.

```cpp
// C2254.cpp
// compile with: /c
class A {
public:
   friend void func1() = 0;   // C2254, func1 is friend
   void virtual func2() = 0;   // OK, pure virtual
   friend void func3();   // OK, friend not virtual nor pure
};

void func1() {};
void func3() {};
```
