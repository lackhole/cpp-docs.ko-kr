---
title: 컴파일러 오류 C2254
ms.date: 11/04/2016
f1_keywords:
- C2254
helpviewer_keywords:
- C2254
ms.assetid: 49bb3d7e-3bdf-4af6-937c-fa627be412a9
ms.openlocfilehash: da89741811bbb9055f3f6793d115a357d80ab79a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397538"
---
# <a name="compiler-error-c2254"></a>컴파일러 오류 C2254

'function': 순수 지정자 또는 추상 재정의 지정자는 friend 함수를 사용할 수 없습니다

A `friend` 함수를 순수 지정한 `virtual`합니다.

다음 샘플에서는 C2254를 생성합니다.

```
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