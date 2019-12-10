---
title: 컴파일러 오류 C2784
ms.date: 11/04/2016
f1_keywords:
- C2784
helpviewer_keywords:
- C2784
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
ms.openlocfilehash: 1ff91135f6a6207921aa1f83d42ebd1689e711a1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739638"
---
# <a name="compiler-error-c2784"></a>컴파일러 오류 C2784

'declaration': 'type'의 템플릿 인수를 'type'에서 추론할 수 없습니다.

컴파일러가 제공된 함수 인수에서 템플릿 인수를 확인할 수 없습니다.

다음 샘플에서는 C2784를 생성하고 해결 방법을 보여 줍니다.

```cpp
// C2784.cpp
template<class T> class X {};
template<class T> void f(X<T>) {}

int main() {
   X<int> x;
   f(1);   // C2784

   // To fix it, try the following line instead
   f(x);
}
```
