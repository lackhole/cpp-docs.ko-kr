---
title: 컴파일러 오류 C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: 7dd47ffbd9481f69f3799a94a17a53ccdffb2a84
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745020"
---
# <a name="compiler-error-c2391"></a>컴파일러 오류 C2391

' identifier ': 형식 정의 중에는 ' friend '를 사용할 수 없습니다.

`friend` 선언에는 완전 한 클래스 선언이 포함 됩니다. `friend` 선언에서 멤버 함수 또는 상세 형식 지정자를 지정할 수 있지만 전체 클래스 선언은 지정할 수 없습니다.

다음 샘플에서는 C2326을 생성합니다.

```cpp
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```
