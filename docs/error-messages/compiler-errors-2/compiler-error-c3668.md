---
title: 컴파일러 오류 C3668
ms.date: 11/04/2016
f1_keywords:
- C3668
helpviewer_keywords:
- C3668
ms.assetid: 53a96698-bde4-4447-95b5-b5108291f60c
ms.openlocfilehash: 770294eb58c09024ddfb4269357b77de7b7ea7d0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776394"
---
# <a name="compiler-error-c3668"></a>컴파일러 오류 C3668

'method': 재정의 지정자 'override' 메서드는 기본 클래스 메서드를 재정의 하지 않았습니다

존재 하지 않는 함수를 재정의 하려고 하는 함수입니다.

자세한 내용은 [명시적으로 재정의](../../extensions/explicit-overrides-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3668를 생성합니다.

```
// C3668.cpp
// compile with: /c
__interface I {
   void f(int);   // virtual by default
};

class J {
public:
   void g(int);
   virtual void h(int);
};

struct R : I,J {
   virtual void f() override {}   // C3668
   virtual void f(int) override {}   // OK

   virtual void g(int) override {}   // C3668
   virtual void h(int) override {}   // OK
};
```