---
title: 컴파일러 경고(수준 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: c816c1b3f5481ccff19fd2a2377c5fc98f950fee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404080"
---
# <a name="compiler-warning-level-1-c4488"></a>컴파일러 경고(수준 1) C4488

'function': 인터페이스 메서드 'interface_method'를 구현 하는 'keyword' 키워드를 필요

클래스는 자신이 직접 상속 된 인터페이스의 모든 멤버를 구현 해야 합니다. 구현 된 멤버를 public 액세스 가능성이 있어야 및 virtual로 표시할 수 있습니다.

## <a name="example"></a>예제

구현 된 멤버를 public이 아닙니다 C4488 발생할 수 있습니다. 다음 샘플 C4488를 생성합니다.

```
// C4488.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

// implemented member not public
ref class B : MyI { virtual void f1() {} };  // C4488

// OK
ref class C : MyI {
public:
   virtual void f1() {}
};
```

## <a name="example"></a>예제

구현 된 멤버를 가상 표시 되지 않으면 C4488 발생할 수 있습니다. 다음 샘플 C4488를 생성합니다.

```
// C4488_b.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

ref struct B : MyI { void f1() {} };   // C4488
ref struct C : MyI { virtual void f1() {} };   // OK
```