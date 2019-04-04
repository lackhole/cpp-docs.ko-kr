---
title: 컴파일러 오류 C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 5bf4e2e42b4534d47a2a7d3c9a838c404a99ba68
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769991"
---
# <a name="compiler-error-c3379"></a>컴파일러 오류 C3379

'class': 중첩된 클래스 선언의 일부로 어셈블리 액세스 지정자를 사용할 수 없습니다

클래스 또는 구조체와 같은 관리 되는 형식에 적용 하는 경우는 [공용](../../cpp/public-cpp.md) 하 고 [개인](../../cpp/private-cpp.md) 키워드는 클래스가 어셈블리 메타 데이터를 통해 노출 될 지 여부를 나타냅니다. `public` 또는 `private` 바깥쪽 클래스의 어셈블리 액세스 권한을 상속 하는 중첩된 클래스를 적용할 수 없습니다.

와 함께 사용할 때 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)의 `ref` 하 고 `value` 키워드 관리 되는 클래스를 나타냅니다 (참조 [클래스 및 구조체](../../extensions/classes-and-structs-cpp-component-extensions.md)).

다음 샘플에서는 C3379 오류가 생성 됩니다.

```
// C3379a.cpp
// compile with: /clr
using namespace System;

public ref class A {
public:
   static int i = 9;

   public ref class BA {   // C3379
   // try the following line instead
   // ref class BA {
   public:
      static int ii = 8;
   };
};

int main() {

   A^ myA = gcnew A;
   Console::WriteLine(myA->i);

   A::BA^ myBA = gcnew A::BA;
   Console::WriteLine(myBA->ii);
}
```
