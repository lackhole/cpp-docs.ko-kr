---
title: 컴파일러 오류 C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 2570ee9abb148b919242de7786cd6fa91765286f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773582"
---
# <a name="compiler-error-c3764"></a>컴파일러 오류 C3764

'override_function': 기본 클래스 메서드 'base_class_function'를 재정의할 수 없습니다.

컴파일러가 잘못 된 형식의 재정의 발견 했습니다. 예를 들어, 기본 클래스 함수가 없습니다 `virtual`합니다. 자세한 내용은 [재정의](../../extensions/override-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3764를 생성합니다.

```
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>예제

C3764 기본 클래스 메서드를 명시적으로 경우에 발생할 수 있습니다 및 명명 된 재정의 합니다. 다음 샘플 C3764를 생성합니다.

```
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```