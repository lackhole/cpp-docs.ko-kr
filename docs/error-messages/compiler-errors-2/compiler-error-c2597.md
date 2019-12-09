---
title: 컴파일러 오류 C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: 680268948f8642b02768bd4b3092666982e14eb7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759310"
---
# <a name="compiler-error-c2597"></a>컴파일러 오류 C2597

비정적 멤버 'identifier'에 대한 참조가 잘못되었습니다.

가능한 원인

1. 비정적 멤버가 정적 멤버 함수에 지정되었습니다. 비정적 멤버에 액세스하려면 클래스의 로컬 인스턴스를 전달하거나 만들고 멤버 액세스 연산자(`.` 또는 `->`)를 사용해야 합니다.

1. 지정한 식별자가 클래스, 구조체 또는 공용 구조체의 멤버가 아닙니다. 식별자 맞춤법을 검사합니다.

1. 멤버 액세스 연산자가 비멤버 함수를 참조합니다.

1. 다음 샘플에서는 C2597을 생성하고 해결 방법을 보여 줍니다.

```cpp
// C2597.cpp
// compile with: /c
struct s1 {
   static void func();
   static void func2(s1&);
   int i;
};

void s1::func() {
   i = 1;    // C2597 - static function can't access non-static data member
}

// OK - fix by passing an instance of s1
void s1::func2(s1& a) {
   a.i = 1;
}
```
