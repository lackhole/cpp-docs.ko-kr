---
title: 컴파일러 오류 C3830
ms.date: 11/04/2016
f1_keywords:
- C3830
helpviewer_keywords:
- C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
ms.openlocfilehash: 14272d2c0b0f8de63f55d2ba3d1c01cf04e0dfbd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741640"
---
# <a name="compiler-error-c3830"></a>컴파일러 오류 C3830

' type1 ': ' type2 '에서 상속할 수 없습니다. 값 형식은 인터페이스 클래스 에서만 상속할 수 있습니다.

값 형식은 기본 클래스를 상속할 수 없습니다.  자세한 내용은 [클래스 및 구조체](../../extensions/classes-and-structs-cpp-component-extensions.md)를 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3830를 생성 합니다.

```cpp
// C3830a.cpp
// compile with: /clr /c
public value struct MyStruct4 {
   int i;
};

public value class MyClass : public MyStruct4 {};   // C3830

// OK
public interface struct MyInterface4 {
   void i();
};

public value class MyClass2 : public MyInterface4 {
public:
   virtual void i(){}
};
```
