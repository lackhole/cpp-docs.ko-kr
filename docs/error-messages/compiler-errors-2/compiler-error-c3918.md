---
title: 컴파일러 오류 C3918
ms.date: 11/04/2016
f1_keywords:
- C3918
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
ms.openlocfilehash: 2c2d2f2598d06ca228a96f2786fcb02888e29a1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386618"
---
# <a name="compiler-error-c3918"></a>컴파일러 오류 C3918

사용 현황 데이터 멤버를 ' member' 필요

C3918은 이벤트와 관련 된 여러 가지 이유로 발생할 수 있습니다.

## <a name="example"></a>예제

C3918은 클래스 멤버는 현재 컨텍스트에서 필요 하기 때문에 발생할 수 있습니다. 다음 샘플 C3918를 생성합니다.

```
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

C3918는 null (이벤트 이름을 더 이상 직접 액세스할 백업 저장소 대리자에 이벤트에 대 한) trivial 이벤트를 확인 하려는 경우에 발생 합니다.

다음 샘플 C3918를 생성합니다.

```
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

C3918 올바르게 구독 하는 경우 없습니다 이벤트에도 발생할 수 있습니다. 다음 샘플 C3918를 생성합니다.

```
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