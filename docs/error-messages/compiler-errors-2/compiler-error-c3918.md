---
title: 컴파일러 오류 C3918
ms.date: 11/04/2016
f1_keywords:
- C3918
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
ms.openlocfilehash: ff2b59338c707767fa1d3c382feaa1bfcdf29ce2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758491"
---
# <a name="compiler-error-c3918"></a>컴파일러 오류 C3918

사용 하려면 ' member '를 데이터 멤버로 사용 해야 합니다.

C3918는 이벤트와 관련 된 여러 가지 이유로 발생할 수 있습니다.

## <a name="example"></a>예제

C3918는 클래스 멤버가 현재 컨텍스트에 필요 하기 때문에 발생할 수 있습니다. 다음 샘플에서는 C3918를 생성 합니다.

```cpp
// C3918.cpp
// compile with: /clr /c
public ref class C {
public:
   System::Object ^ o;
   delegate void Del();

   event Del^ MyEvent {
      void add(Del^ev) {
         if ( MyEvent != nullptr) {}   // C3918
         if ( o != nullptr) {}   // OK
   }
   void remove(Del^){}
   }
};
```

## <a name="example"></a>예제

C3918는 null에 대 한 trivial 이벤트를 확인 하려고 하는 경우에도 발생 합니다. 이벤트 이름은 이벤트의 백업 저장소 대리자에 직접 액세스 하는 것을 더 이상 제공 하지 않습니다.

다음 샘플에서는 C3918를 생성 합니다.

```cpp
// C3918_2.cpp
// compile with: /clr /c
using namespace System;
public delegate int MyDel(int);

interface struct IEFace {
   event MyDel ^ E;
};

ref struct EventSource : public IEFace {
   virtual event MyDel ^ E;
   void Fire_E(int i) {
      if (E)   // C3918
         E(i);
   }
};
```

## <a name="example"></a>예제

C3918는 이벤트를 잘못 구독 하는 경우에도 발생할 수 있습니다. 다음 샘플에서는 C3918를 생성 합니다.

```cpp
// C3918_3.cpp
// compile with: /clr /c
using namespace System;

public delegate void del();

public ref class A {
public:
   event del^ e {
      void add(del ^handler ) {
         d += handler;
      }

      void remove(del ^handler) {
         d -= handler;
      }

      void raise() {
         d();
      }
   }

   del^ d;
   void f() {}

   A() {
      e = gcnew del(this, &A::f);   // C3918
      // try the following line instead
      // e += gcnew del(this, &A::f);
      e();
   }
};

int main() {
   A a;
}
```
