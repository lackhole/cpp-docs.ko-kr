---
title: 컴파일러 오류 C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 3ede846c9068978ad5d283e97b1c96d3527bf67c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757238"
---
# <a name="compiler-error-c3764"></a>컴파일러 오류 C3764

' override_function ': 기본 클래스 메서드 ' base_class_function '을 (를) 재정의할 수 없습니다.

컴파일러가 잘못 된 형식의 재정의를 검색 했습니다. 예를 들어 기본 클래스 함수는 `virtual`되지 않았습니다. 자세한 내용은 [override](../../extensions/override-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3764를 생성 합니다.

```cpp
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

C3764 기본 클래스 메서드가 명시적이 고 이름이 재정의 된 경우에도 발생할 수 있습니다. 다음 샘플에서는 C3764를 생성 합니다.

```cpp
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
