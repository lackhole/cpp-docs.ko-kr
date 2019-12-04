---
title: 컴파일러 오류 C2216
ms.date: 11/04/2016
f1_keywords:
- C2216
helpviewer_keywords:
- C2216
ms.assetid: 250f6bdc-a5e1-495f-a1e8-6e8e7021ad9d
ms.openlocfilehash: 78426722a4d23f8cf0b94c0b1989002e6a23f90b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741315"
---
# <a name="compiler-error-c2216"></a>컴파일러 오류 C2216

'keyword1'은 'keyword2'와 함께 사용할 수 없습니다.

함께 사용할 수 없는 두 키워드를 함께 사용했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2216을 생성합니다.

```cpp
// C2216.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   static int staticConst2 = 10;   // C2216
};
```

## <a name="example"></a>예제

다음 샘플에서는 C2216을 생성합니다.

```cpp
// C2216b.cpp
// compile with: /clr /c
public ref class X {
   extern property int i { int get(); }   // C2216 extern not allowed on property
   typedef property int i2;   // C2216 typedef not allowed on property
};
```

## <a name="example"></a>예제

다음 샘플에서는 C2216을 생성합니다.

```cpp
// C2216c.cpp
// compile with: /clr /c
public interface struct I {
   double f();
   double g();
   double h();
};

public ref struct R : I {
   virtual double f() new override { return 0.0; }   // C2216
   virtual double g() new { return 0.0; }   // OK
   virtual double h() override { return 0.0; }   // OK
};
```
