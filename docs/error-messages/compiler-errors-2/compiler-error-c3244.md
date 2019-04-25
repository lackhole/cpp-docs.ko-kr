---
title: 컴파일러 오류 C3244
ms.date: 11/04/2016
f1_keywords:
- C3244
helpviewer_keywords:
- C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
ms.openlocfilehash: fe17ac0f20c5644fd5bb81094242403b244bd1d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174928"
---
# <a name="compiler-error-c3244"></a>컴파일러 오류 C3244

'method': 이 메서드는 'interface'에 의해 정의되었습니다('interface'에 의해 정의되지 않음).

지정된 인터페이스에 없지만 다른 기본 클래스에 있는 멤버를 [명시적으로 재정의](../../cpp/explicit-overrides-cpp.md) 하려고 시도했습니다.

다음 샘플에서는 C3244를 생성합니다.

```
// C3244.cpp
#pragma warning(disable:4199)

__interface IX15A {
   void f();
};

__interface IX15B {
   void g();
};

class CX15 : public IX15A, public IX15B {
public:
   void IX15A::f();
   void IX15B::g();
};

void CX15::IX15A::g()   // C3244 occurs here
{
}
```