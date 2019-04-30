---
title: '방법: safe_cast를 사용 하 여 C++/CLI'
ms.date: 11/04/2016
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
ms.openlocfilehash: 66faadba9530bc7f3c12513277582e405e1b1b34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389088"
---
# <a name="how-to-use-safecast-in-ccli"></a>방법: safe_cast를 사용 하 여 C++/CLI

이 문서에서 safe_cast를 사용 하는 방법을 보여 줍니다 C++/CLI 응용 프로그램입니다. Safe_cast에 대 한 내용은 C++/CX, 참조 [safe_cast](../extensions/safe-cast-cpp-component-extensions.md)합니다.

## <a name="upcasting"></a>업 캐스트

업 캐스트는 기본 클래스 중 하나에 파생된 형식에서 캐스팅입니다. 이 캐스트는 안전 하며 명시적 캐스트 표기법 필요 하지 않습니다. 다음 샘플에는 업 캐스트를 수행 하는 방법을 보여 줍니다 `safe_cast` 및 없이 합니다.

```cpp
// safe_upcast.cpp
// compile with: /clr
using namespace System;
interface class A {
   void Test();
};

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test");
   }

   void Test2() {
      Console::WriteLine("in B::Test2");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test");
   };
};

int main() {
   C ^ c = gcnew C;

   // implicit upcast
   B ^ b = c;
   b->Test();
   b->Test2();

   // upcast with safe_cast
   b = nullptr;
   b = safe_cast<B^>(c);
   b->Test();
   b->Test2();
}
```

```Output
in C::Test
in B::Test2
in C::Test
in B::Test2
```

## <a name="downcasting"></a>다운 캐스팅

다운 캐스트는 기본 클래스에서 파생 된 클래스에 기본 클래스에서 캐스트입니다.  다운 캐스트는 런타임에 주소가 지정 된 개체는 파생된 클래스 개체를 처리 하는 경우에 안전 합니다.  와 달리 `static_cast`, `safe_cast` 동적 검사를 수행 하 고 throw <xref:System.InvalidCastException> 변환에 실패 하는 경우.

```cpp
// safe_downcast.cpp
// compile with: /clr
using namespace System;

interface class A { void Test(); };

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test()");
   }

   void Test2() {
      Console::WriteLine("in B::Test2()");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test()");
   }
};

interface class I {};

value struct V : public I {};

int main() {
   A^ a = gcnew C();
   a->Test();
   B^ b = safe_cast<B^>(a);
   b->Test();
   b->Test2();

   V v;
   I^ i = v;   // i boxes V
   V^ refv = safe_cast<V^>(i);

   Object^ o = gcnew B;
   A^ a2= safe_cast<A^>(o);
}
```

```Output
in C::Test()
in C::Test()
in B::Test2()
```

## <a name="safecast-with-user-defined-conversions"></a>사용자 정의 변환 통한 safe_cast

다음 샘플을 사용 하는 방법을 보여 줍니다 `safe_cast` 사용자 정의 변환을 호출 합니다.

```cpp
// safe_cast_udc.cpp
// compile with: /clr
using namespace System;
value struct V;

ref struct R {
   int x;
   R() {
      x = 1;
   }

   R(int argx) {
      x = argx;
   }

   static operator R::V^(R^ r);
};

value struct V {
   int x;
   static operator R^(V& v) {
      Console::WriteLine("in operator R^(V& v)");
      R^ r = gcnew R();
      r->x = v.x;
      return r;
   }

   V(int argx) {
      x = argx;
   }
};

   R::operator V^(R^ r) {
      Console::WriteLine("in operator V^(R^ r)");
      return gcnew V(r->x);
   }

int main() {
   bool fReturnVal = false;
   V v(2);
   R^ r = safe_cast<R^>(v);   // should invoke UDC
   V^ v2 = safe_cast<V^>(r);   // should invoke UDC
}
```

```Output
in operator R^(V& v
in operator V^(R^ r)
```

## <a name="safecast-and-boxing-operations"></a>safe_cast 및 boxing 작업

### <a name="boxing"></a>boxing

Boxing은 컴파일러 삽입, 사용자 정의 변환으로 정의 됩니다.  따라서 사용할 수 있습니다 `safe_cast` CLR 힙에 값 상자에 있습니다.

다음 샘플에서는 간단 하 고 사용자 정의 값 형식과 boxing을 보여 줍니다.  `safe_cast` 상자 값 형식 변수는 네이티브 스택에 있도록 가비지 수집 힙에 변수에 할당할 수 있습니다.

```cpp
// safe_cast_boxing.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct V : public I {
   int m_x;

   V(int i) : m_x(i) {}
};

int main() {
   // box a value type
   V v(100);
   I^ i = safe_cast<I^>(v);

   int x = 100;
   V^ refv = safe_cast<V^>(v);
   int^ refi = safe_cast<int^>(x);
}
```

다음 샘플에서 사용자 정의 변환을 통해 boxing의 우선 순위를 보여 줍니다는 `safe_cast` 작업 합니다.

```cpp
// safe_cast_boxing_2.cpp
// compile with: /clr
static bool fRetval = true;

interface struct I {};
value struct V : public I {
   int x;

   V(int argx) {
      x = argx;
   }

   static operator I^(V v) {
      fRetval = false;
      I^ pi = v;
      return pi;
   }
};

ref struct R {
   R() {}
   R(V^ pv) {}
};

int main() {
   V v(10);
   I^ pv = safe_cast<I^>(v);   // boxing will occur, not UDC "operator I^"
}
```

### <a name="unboxing"></a>unboxing

Unboxing 컴파일러 삽입, 사용자 정의 변환이 정의 됩니다.  따라서 사용할 수 있습니다 `safe_cast` unbox CLR 힙에 값입니다.

Boxing을 달리 unboxing 해야 하지만 사용자 정의 변환, unboxing은 명시적-, 의해 수행 되어야 합니다는 `static_cast`C 스타일 캐스팅, 또는 `safe_cast`; unboxing 암시적 수행할 수 없는 합니다.

```cpp
// safe_cast_unboxing.cpp
// compile with: /clr
int main() {
   System::Object ^ o = 42;
   int x = safe_cast<int>(o);
}
```

다음 샘플에서는 값 형식 및 기본 형식을 사용 하 여 unboxing를 보여 줍니다.

```cpp
// safe_cast_unboxing_2.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct VI : public I {};

void test1() {
   Object^ o = 5;
   int x = safe_cast<Int32>(o);
}

value struct V {
   int x;
   String^ s;
};

void test2() {
   V localv;
   Object^ o = localv;
   V unboxv = safe_cast<V>(o);
}

void test3() {
   V localv;
   V^ o2 = localv;
   V unboxv2 = safe_cast<V>(o2);
}

void test4() {
   I^ refi = VI();
   VI vi  = safe_cast<VI>(refi);
}

int main() {
   test1();
   test2();
   test3();
   test4();
}
```

## <a name="safecast-and-generic-types"></a>safe_cast 및 제네릭 형식

다음 샘플을 사용 하는 방법을 보여 줍니다 `safe_cast` 제네릭 형식으로 다운 캐스팅을 수행 하 합니다.

```cpp
// safe_cast_generic_types.cpp
// compile with: /clr
interface struct I {};

generic<class T> where T:I
ref struct Base {
   T t;
   void test1() {}
};

generic<class T> where T:I
ref struct Derived:public Base <T> {};

ref struct R:public I {};

typedef Base<R^> GBase_R;
typedef Derived<R^> GDerived_R;

int main() {
   GBase_R^ br = gcnew GDerived_R();
   GDerived_R^ dr = safe_cast<GDerived_R^>(br);
}
```

## <a name="see-also"></a>참고자료

[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)
