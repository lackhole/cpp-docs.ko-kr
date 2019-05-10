---
title: 컴파일러 오류 C2683
ms.date: 11/04/2016
f1_keywords:
- C2683
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
ms.openlocfilehash: 49e4897ad5db866aa1ca42589859bedff12718df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266870"
---
# <a name="compiler-error-c2683"></a>컴파일러 오류 C2683

'cast': 'type' 다형 형식이 아닙니다.

사용할 수 없습니다 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 다형 클래스 (가상 함수가 없는 클래스)에서 변환 합니다.

사용할 수 있습니다 [static_cast](../../cpp/static-cast-operator.md) 비 다형 형식의 변환을 수행할 수 있습니다. 그러나 `static_cast` 런타임 검사를 수행 하지 않습니다.

다음 샘플에서는 C2683 오류가 생성 됩니다.

```
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```