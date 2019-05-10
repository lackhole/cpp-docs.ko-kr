---
title: 컴파일러 경고(수준 2) C4250
ms.date: 11/04/2016
f1_keywords:
- C4250
helpviewer_keywords:
- C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
ms.openlocfilehash: 8baf3c03c87dc70a80b785d7f81cbee4e1d828f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349713"
---
# <a name="compiler-warning-level-2-c4250"></a>컴파일러 경고(수준 2) C4250

'class1': 'class2::member' 우위를 상속 합니다.

두 개 이상의 멤버 이름이 같습니다. 있는 `class2` 이 멤버를 포함 하는 다른 클래스에 대 한 기본 클래스 이므로 상속 됩니다.

C4250를 표시 하지 않으려면 사용 합니다 [경고](../../preprocessor/warning.md) pragma입니다.

가상 기본 클래스에서 여러 파생된 클래스 간에 공유 되므로 이름이 파생된 클래스에서 기본 클래스의 이름의 지배 합니다. 예를 들어, 다이아몬드에서 상속 하는 func의 두 가지 정의 가지는 아래의 클래스 계층 구조를 지정 합니다: 약한 클래스와 기준 클래스를 통해 되 통해 vbc::func() 인스턴스. 다이아몬드 클래스 개체를 통해 되는 정규화 되지 않은 호출 dominate 되 인스턴스를 항상 호출 합니다.  -약한 클래스 되의 인스턴스를 모두 정의 우위를 차지 하는 경우 호출이 모호한 것으로 플래그가 지정 됩니다.

```
// C4250.cpp
// compile with: /c /W2
#include <stdio.h>
struct vbc {
   virtual void func() { printf("vbc::func\n"); }
};

struct weak : public virtual vbc {};

struct dominant : public virtual vbc {
   void func() { printf("dominant::func\n"); }
};

struct diamond : public weak, public dominant {};

int main() {
   diamond d;
   d.func();   // C4250
}
```

## <a name="example"></a>예제

다음 샘플에서는 C4250 오류가 발생 합니다.

```
// C4250_b.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;
class A {
public:
   virtual operator int () {
      return 2;
   }
};

class B : virtual public A {
public:
   virtual operator int () {
      return 3;
   }
};

class C : virtual public A {};

class E : public B, public C {};   // C4250

int main() {
   E eObject;
   cout << eObject.operator int() << endl;
}
```

## <a name="example"></a>예제

이 샘플에는 더 복잡 한 상황을 보여 줍니다. 다음 샘플에서는 C4250 오류가 발생 합니다.

```
// C4250_c.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;

class V {
public:
   virtual int f() {
      return 1024;
   }
};

class B : virtual public V {
public:
   int b() {
      return f(); // B::b() calls V::f()
   }
};

class M : virtual public V {
public:
   int f() {
      return 7;
   }
};

// because of dominance, f() is M::f() inside D,
// changing the meaning of B::b's f() call inside a D
class D : public B, public M {};   // C4250

int main() {
   D d;
   cout << "value is: " << d.b();   // invokes M::f()
}
```