---
title: 컴파일러 오류 C2903
ms.date: 11/04/2016
f1_keywords:
- C2903
helpviewer_keywords:
- C2903
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
ms.openlocfilehash: df097cf38fea47702b639b44fd2f2ac3341df2ba
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735907"
---
# <a name="compiler-error-c2903"></a>컴파일러 오류 C2903

'identifier': 기호가 클래스 템플릿 또는 함수 템플릿이 아닙니다.

코드에서 템플릿이 아닌 항목에 대해 명시적 인스턴스화를 시도합니다.

다음 샘플에서는 C2903을 생성합니다.

```cpp
// C2903.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template Y y;   // C2903
   N::X<N::Y> y;   // OK
}
```

제네릭을 사용할 때도 C2903이 발생할 수 있습니다.

```cpp
// C2903b.cpp
// compile with: /clr /c
namespace N {
   class Y {};
   generic<class T> ref class Z {};
}

void f() {
   N::generic Y y;   // C2903
   N:: generic Z<int>^ z;   // OK
}
```
