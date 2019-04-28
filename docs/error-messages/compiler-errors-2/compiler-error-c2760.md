---
title: 컴파일러 오류 C2760
ms.date: 11/04/2016
f1_keywords:
- C2760
helpviewer_keywords:
- C2760
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
ms.openlocfilehash: 24c33d90c0f91aa3c4b01142902afc4333c1c732
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257792"
---
# <a name="compiler-error-c2760"></a>컴파일러 오류 C2760

구문 오류: 'name1'가 필요 하지 'name2'

캐스팅 연산자에 잘못 된 연산자를 사용 하 여 사용 됩니다.

다음 샘플에서는 C2760 오류가 생성 됩니다.

```
// C2760.cpp
class B {};
class D : public B {};

void f(B* pb) {
    D* pd1 = static_cast<D*>(pb);
    D* pd2 = static_cast<D*>=(pb);  // C2760
    D* pd3 = static_cast<D*=(pb);   // C2760
}
```