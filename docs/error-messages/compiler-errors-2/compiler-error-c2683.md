---
title: 컴파일러 오류 C2683
ms.date: 11/04/2016
f1_keywords:
- C2683
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
ms.openlocfilehash: 8526dc1fe3cacc872aa91ca058677d15318fd703
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760272"
---
# <a name="compiler-error-c2683"></a>컴파일러 오류 C2683

' cast ': ' type '은 (는) 다형 형식이 아닙니다.

비 다형 클래스 (가상 함수가 없는 클래스)에서 변환 하는 데 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 를 사용할 수 없습니다.

[Static_cast](../../cpp/static-cast-operator.md) 를 사용 하 여 비 다형성 형식의 변환을 수행할 수 있습니다. 그러나 `static_cast`는 런타임 검사를 수행 하지 않습니다.

다음 샘플에서는 C2683를 생성 합니다.

```cpp
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```
