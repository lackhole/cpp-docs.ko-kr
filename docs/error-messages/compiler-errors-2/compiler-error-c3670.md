---
title: 컴파일러 오류 C3670
ms.date: 11/04/2016
f1_keywords:
- C3670
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
ms.openlocfilehash: a9fe72501152891d3f82567f09922dda9a9b711a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775480"
---
# <a name="compiler-error-c3670"></a>컴파일러 오류 C3670

'override': 액세스할 수 없는 기본 클래스 ' method'를 재정의할 수 없습니다.

재정의 해당 액세스 수준에 따라 파생된 형식에서 사용할 수 있는 함수만을 시에만 사용할 수 있습니다. 자세한 내용은 [명시적으로 재정의](../../extensions/explicit-overrides-cpp-component-extensions.md)합니다.

다음 샘플에서는 C3670 오류가 생성 됩니다.

```
// C3670.cpp
// compile with: /clr /c
public ref class C {
// Uncomment the following line to resolve.
// public:
   virtual void g() { }
};

public ref class D : public C {
public:
   virtual void f() new sealed = C::g {};   // C3670
};
```