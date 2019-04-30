---
title: 컴파일러 오류 C2594
ms.date: 11/04/2016
f1_keywords:
- C2594
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
ms.openlocfilehash: 75e3b438dd69f8879fdc2273a8f0357229941340
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386904"
---
# <a name="compiler-error-c2594"></a>컴파일러 오류 C2594

'operator': 'type1'에서 'type2'의 모호한 변환입니다.

변환이 *type1* 하 *type2* 다른 보다 직접적 합니다. 변환 하기 위한 두 가지 방법이 것이 좋습니다 *type1* 하 *type2*합니다. 첫 번째 옵션에서 직접 변환을 정의 하는 것 *type1* 하 *type2*를 두 번째 옵션에서 변환의 순서를 지정 하 고 *type1* 를  *type2*합니다.

다음 샘플 C2594를 생성합니다. 오류에 대 한 권장된 해결 방법의 변환 순서 같습니다.

```
// C2594.cpp
// compile with: /c
struct A{};
struct I1 : A {};
struct I2 : A {};
struct D : I1, I2 {};

A *f (D *p) {
   return (A*) (p);    // C2594

// try the following line instead
// return static_cast<A *>(static_cast<I1 *>(p));
}
```