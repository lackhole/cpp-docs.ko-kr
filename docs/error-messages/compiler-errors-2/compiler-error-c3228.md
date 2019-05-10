---
title: 컴파일러 오류 C3228
ms.date: 11/04/2016
f1_keywords:
- C3228
helpviewer_keywords:
- C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
ms.openlocfilehash: 63e7afa16c21aa8c4e335d22693ca71d7ab8d6a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173985"
---
# <a name="compiler-error-c3228"></a>컴파일러 오류 C3228

'function': 'param'에 대한 제네릭 형식 인수는 'type'일 수 없으며 값 형식이거나 핸들 형식이어야 합니다.

잘못된 형식이 제네릭 형식 인수로 전달되었습니다.

다음 샘플에서는 C3228을 생성합니다.

```
// C3228.cpp
// compile with: /clr
class A {};

value class B {};

generic <class T>
void Test() {}

ref class C {
public:
   generic <class T>
   static void f() {}
};

int main() {
   C::f<A>();   // C3228
   C::f<B>();   // OK

   Test<C>();   // C3228
   Test<C ^>();   // OK
}
```