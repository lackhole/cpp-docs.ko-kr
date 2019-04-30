---
title: 컴파일러 오류 C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: 11cb2b83d958f0c59d05034a716a022f00b326ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353199"
---
# <a name="compiler-error-c2553"></a>컴파일러 오류 C2553

'base_function': 재정의 가상 함수의 반환 형식은 'override_function'에서 다릅니다.

파생된 클래스의 함수가 기본 클래스에서 가상 함수를 재정의 하려고 하지만 파생된 클래스는 기본 클래스 함수의 반환 형식이 없는 합니다.  함수 시그니처는 재정의 재정의 되는 함수의 시그니처와 일치 해야 합니다.

다음 샘플에서는 C2553 오류가 생성 됩니다.

```
// C2553.cpp
// compile with: /clr /c
ref struct C {
   virtual void f();
};

ref struct D : C {
   virtual int f() override ;   // C2553

   // try the following line instead
   // virtual void f() override;
};
```