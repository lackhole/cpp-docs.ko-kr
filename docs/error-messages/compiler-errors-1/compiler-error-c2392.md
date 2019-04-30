---
title: 컴파일러 오류 C2392
ms.date: 11/04/2016
f1_keywords:
- C2392
helpviewer_keywords:
- C2392
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
ms.openlocfilehash: 5977d9bf41d55ef6db8409e0187153fdbf91149e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393599"
---
# <a name="compiler-error-c2392"></a>컴파일러 오류 C2392

'method1': 관리 되는 공변 (covariant) 반환 형식에서 지원 되지 않습니다 또는 WinRTtypes, 그렇지 않으면 'method2'를 재정의할 수는

공변 (covariant) 반환 형식은 허용 되지 않습니다 Windows 런타임 멤버 함수 또는로 컴파일하는 경우는 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2392 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```
// C2392.cpp
// compile with: /clr
public ref struct B {
public:
   int i;
};

public ref struct D: public B{};

public ref struct B1 {
public:
   virtual B^ mf() {
      B^ pB = gcnew B;
      pB->i = 11;
      return pB;
   }
};

public ref struct D1: public B1 {
public:
   virtual D^ mf() override {  // C2392
   // try the following line instead
   // virtual B^ mf() override {
   // return type D^ is covariant with B^, not allowed with CLR types
      D^ pD = gcnew D;
      pD->i = 12;
      return pD;
   }
};

int main() {
   B1^ pB1 = gcnew D1;
   B^ pB = pB1->mf();
   D^ pD = dynamic_cast<D^>(pB);
}
```