---
title: 사용자 정의 변환(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
ms.openlocfilehash: 8f168582e56e77f1ec848928b7ffd36879ba341a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384532"
---
# <a name="user-defined-conversions-ccli"></a>사용자 정의 변환(C++/CLI)

이 섹션에서는 참조 또는 값 형식 또는 참조 형식의 인스턴스를 변환 형식 중 하나가 인 경우 사용자 정의 변환 (UDC)를 설명 합니다.

## <a name="implicit-and-explicit-conversions"></a>암시적 변환과 명시적 변환

사용자 정의 변환이 암시적 또는 명시적 일 수 있습니다.  UDC 변환 정보 손실이 발생 하지 않습니다 하는 경우 암시적 이어야 합니다. 그렇지 않은 경우는 명시적 UDC 정의 되어야 합니다.

네이티브 클래스의 생성자를 사용 하 여 기본 클래스에 참조 또는 값 형식을 변환할 수 있습니다.

변환에 대 한 자세한 내용은 참조 하세요. [Boxing](../extensions/boxing-cpp-component-extensions.md) 하 고 [표준 변환](../cpp/standard-conversions.md)합니다.

```
// mcpp_User_Defined_Conversions.cpp
// compile with: /clr
#include "stdio.h"
ref class R;
class N;

value class V {
   static operator V(R^) {
      return V();
   }
};

ref class R {
public:
   static operator N(R^);
   static operator V(R^) {
      System::Console::WriteLine("in R::operator N");
      return V();
   }
};

class N {
public:
   N(R^) {
      printf("in N::N\n");
   }
};

R::operator N(R^) {
   System::Console::WriteLine("in R::operator N");
   return N(nullptr);
}

int main() {
   // Direct initialization:
   R ^r2;
   N n2(r2);   // direct initialization, calls constructor
   static_cast<N>(r2);   // also direct initialization

   R ^r3;
   // ambiguous V::operator V(R^) and R::operator V(R^)
   // static_cast<V>(r3);
}
```

**출력**

```Output
in N::N
in N::N
```

## <a name="convert-from-operators"></a>Convert-From 연산자

Convert-from 연산자는 다른 클래스의 개체에서 연산자가 정의 된 클래스의 개체를 만듭니다.

표준 C++ convert-from 연산자;를 지원 하지 않습니다 표준 C++ 이 목적을 위해 생성자를 사용 합니다. 그러나 CLR 형식에서 시각적 개체를 사용 하는 경우 C++ convert-from 연산자를 호출 하는 것에 대 한 구문 지원을 제공 합니다.

다른 CLS 규격 언어에서 잘 상호 운용, 지정된 된 클래스에 대 한 각 사용자 정의 단항 생성자는 해당 변환에서 연산자를 사용 하 여 래핑할 수도 있습니다.

Convert-from 연산자:

- 정적 함수로 정의 해야 합니다.

- 중일 수 있습니다 (짧은-int와 같은 전체 자릿수 손실 되지 않습니다는 변환)에 대 한 암시적 또는 명시적 때 정밀도 떨어질 수 있습니다.

- 포함 하는 클래스의 개체를 반환 해야 합니다.

- 보유할 수 있는 유일한 매개 변수 형식으로 "에서" 형식입니다.

다음 샘플에서는 암시적 및 명시적 "변환에서", 사용자 정의 변환 (UDC) 연산자를 보여 줍니다.

```
// clr_udc_convert_from.cpp
// compile with: /clr
value struct MyDouble {
   double d;

   MyDouble(int i) {
      d = static_cast<double>(i);
      System::Console::WriteLine("in constructor");
   }

   // Wrap the constructor with a convert-from operator.
   // implicit UDC because conversion cannot lose precision
   static operator MyDouble (int i) {
      System::Console::WriteLine("in operator");
      // call the constructor
      MyDouble d(i);
      return d;
   }

   // an explicit user-defined conversion operator
   static explicit operator signed short int (MyDouble) {
      return 1;
   }
};

int main() {
   int i = 10;
   MyDouble md = i;
   System::Console::WriteLine(md.d);

   // using explicit user-defined conversion operator requires a cast
   unsigned short int j = static_cast<unsigned short int>(md);
   System::Console::WriteLine(j);
}
```

**출력**

```Output
in operator
in constructor
10
1
```

## <a name="convert-to-operators"></a>변환 연산자를 사용 합니다.

변환 연산자는 다른 개체에 연산자가 정의 된 클래스의 개체를 변환 합니다. 다음 예제는 암시적 변환 간, 사용자 정의 변환 연산자 보여 줍니다.

```
// clr_udc_convert_to.cpp
// compile with: /clr
using namespace System;
value struct MyInt {
   Int32 i;

   // convert MyInt to String^
   static operator String^ ( MyInt val ) {
      return val.i.ToString();
   }

   MyInt(int _i) : i(_i) {}
};

int main() {
   MyInt mi(10);
   String ^s = mi;
   Console::WriteLine(s);
}
```

**출력**

```Output
10
```

명시적 사용자 정의 변환 간 변환 연산자는 어떤 방식으로든에서 데이터를 잃을 수 있으므로 변환에 적합 합니다. 에 명시적 변환 연산자를 호출 하는 캐스트를 사용 해야 합니다.

```
// clr_udc_convert_to_2.cpp
// compile with: /clr
value struct MyDouble {
   double d;
   // convert MyDouble to Int32
   static explicit operator System::Int32 ( MyDouble val ) {
      return (int)val.d;
   }
};

int main() {
   MyDouble d;
   d.d = 10.3;
   System::Console::WriteLine(d.d);
   int i = 0;
   i = static_cast<int>(d);
   System::Console::WriteLine(i);
}
```

**출력**

```Output
10.3
10
```

## <a name="to-convert-generic-classes"></a>제네릭 클래스 변환

제네릭 클래스를 T로 변환할 수 있습니다.

```
// clr_udc_generics.cpp
// compile with: /clr
generic<class T>
public value struct V {
   T mem;
   static operator T(V v) {
      return v.mem;
   }

   void f(T t) {
      mem = t;
   }
};

int main() {
   V<int> v;
   v.f(42);
   int i = v;
   i += v;
   System::Console::WriteLine(i == (42 * 2) );
}
```

**출력**

```Output
True
```

변환 생성자 형식을 사용 및 사용 하 여 개체를 만듭니다.  변환 생성자가 직접 초기화만;를 사용 하 여 호출 됩니다. 캐스팅은 변환 생성자를 호출 하지 않습니다. 기본적으로 변환 생성자는 CLR 형식에 대 한 명시적입니다.

```
// clr_udc_converting_constructors.cpp
// compile with: /clr
public ref struct R {
   int m;
   char c;

   R(int i) : m(i) { }
   R(char j) : c(j) { }
};

public value struct V {
   R^ ptr;
   int m;

   V(R^ r) : ptr(r) { }
   V(int i) : m(i) { }
};

int main() {
   R^ r = gcnew R(5);

   System::Console::WriteLine( V(5).m);
   System::Console::WriteLine( V(r).ptr);
}
```

**출력**

```Output
5
R
```

이 코드 샘플에서는 암시적 정적 변환 함수를 명시적 변환 생성자로 동일한 작업을 수행 합니다.

```
public value struct V {
   int m;
   V(int i) : m(i) {}
   static operator V(int i) {
      V v(i*100);
      return v;
   }
};

public ref struct R {
   int m;
   R(int i) : m(i) {}
   static operator R^(int i) {
      return gcnew R(i*100);
   }
};

int main() {
   V v(13);   // explicit
   R^ r = gcnew R(12);   // explicit

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);

   // explicit ctor can't be called here: not ambiguous
   v = 5;
   r = 20;

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);
}
```

**출력**

```Output
13
12
500
2000
```

## <a name="see-also"></a>참고자료

[클래스 및 구조체(C++)](../extensions/classes-and-structs-cpp-component-extensions.md)
