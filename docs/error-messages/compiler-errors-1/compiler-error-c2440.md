---
title: 컴파일러 오류 C2440
ms.date: 03/28/2017
f1_keywords:
- C2440
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
ms.openlocfilehash: 8de433361901b5d247616c154afc48d637373d43
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448035"
---
# <a name="compiler-error-c2440"></a>컴파일러 오류 C2440

'conversion': 'type1'에서 'type2'으로 변환할 수 없습니다

컴파일러에서 캐스팅할 수 없습니다 `type1` 에 `type2`입니다.

## <a name="example"></a>예제

C2440은 비 const를 초기화 하려고 하면 발생할 수 있습니다 `char*` (또는 `wchar_t*`)에서 리터럴 문자열을 사용 하 여 C++ 코드, 컴파일러 성능 옵션 [/zc: strictstrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) 설정 됩니다. C에서 문자열 리터럴의 형식은 배열의 `char`, 하지만 C++의 배열입니다 `const char`합니다. 이 샘플에서는 C2440을 생성합니다.

```cpp
// C2440s.cpp
// Build: cl /Zc:strictStrings /W3 C2440s.cpp
// When built, the compiler emits:
// error C2440: 'initializing' : cannot convert from 'const char [5]'
// to 'char *'
//        Conversion from string literal loses const qualifier (see
// /Zc:strictStrings)

int main() {
   char* s1 = "test"; // C2440
   const char* s2 = "tests"; // OK
}
```

## <a name="example"></a>예제

C2440은 void * 하는 멤버에 대 한 포인터를 변환 하려는 경우에 발생할 수 있습니다. 다음 샘플에서는 C2440을 생성합니다.

```cpp
// C2440.cpp
class B {
public:
   void  f(){;}

   typedef void (B::*pf)();

   void f2(pf pf) {
       (this->*pf)();
       void* pp = (void*)pf;   // C2440
   }

   void f3() {
      f2(f);
   }
};
```

## <a name="example"></a>예제

C2440은 전방 선언 되기만 되었지만 정의 되지 않았습니다 하는 형식에서 캐스팅을 시도 하는 경우 발생할 수 있습니다. 이 샘플에서는 C2440을 생성합니다.

```cpp
// c2440a.cpp
struct Base { }; // Defined

struct Derived; // Forward declaration, not defined

Base * func(Derived * d) {
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'
}
```

## <a name="example"></a>예제

줄 15 및 16의 다음 샘플에 있는 C2440 오류는 정규화 된 `Incompatible calling conventions for UDT return value` 메시지입니다. A *UDT* 클래스, 구조체 또는 공용 구조체와 같은 사용자 정의 형식입니다. 이러한 종류의 비호환 오류는 UDT의 호출 규칙은 반환 형식의 udt 및 함수 포인터와 연관 된 실제 호출 규칙과 충돌 하는 정방향 선언에 지정 된 경우에 발생 합니다.

예제에서는 먼저 가지; 구조체를 반환 하는 함수 및 구조체에 대 한 정방향 선언 구조체는 컴파일러의 C++ 호출 규칙입니다. 다음은 기본적으로 C를 사용 하는 struct 정의 사용 하는 호출 규칙입니다. 호출 규칙은 반환 형식의 구조체에 대 한 전체 구조체를 읽을 때까지 컴파일러는 구조체의 호출 규칙을 알지 못하므로 `get_c2` 로 간주 됩니다 C++합니다.

구조체는 구조체를 반환 하는 다른 함수 선언이 옵니다 못하지만 시점에서 컴파일러는 struct의 호출 규칙은 C++입니다. 마찬가지로 구조체를 반환 하는 함수 포인터에 정의 됩니다 구조체 정의 다음 컴파일러는 구조체는 알 수 있도록 합니다 C++ 호출 규칙입니다.

호환 되지 않는 호출 규칙으로 인해 발생 하는 C2440을 해결 하려면 UDT 정의 다음에 UDT를 반환 하는 함수를 선언 합니다.

```cpp
// C2440b.cpp
struct MyStruct;

MyStruct get_c1();

struct MyStruct {
   int i;
   static MyStruct get_C2();
};

MyStruct get_C3();

typedef MyStruct (*FC)();

FC fc1 = &get_c1;   // C2440, line 15
FC fc2 = &MyStruct::get_C2;   // C2440, line 16
FC fc3 = &get_C3;

class CMyClass {
public:
   explicit CMyClass( int iBar)
      throw()   {
   }

   static CMyClass get_c2();
};

int main() {
   CMyClass myclass = 2;   // C2440
   // try one of the following
   // CMyClass myclass{2};
   // CMyClass myclass(2);

   int *i;
   float j;
   j = (float)i;   // C2440, cannot cast from pointer to int to float
}
```

## <a name="example"></a>예제

C2440은 내부 포인터에 0을 할당 하는 경우에 발생할 수 있습니다.

```cpp
// C2440c.cpp
// compile with: /clr
int main() {
   array<int>^ arr = gcnew array<int>(100);
   interior_ptr<int> ipi = &arr[0];
   ipi = 0;   // C2440
   ipi = nullptr;   // OK
}
```

## <a name="example"></a>예제

C2440은 사용자 정의 변환을 잘못 사용할 발생할 수 있습니다. 예를 들어 경우 변환 연산자 정의 된 `explicit`, 컴파일러는 암시적 변환에서 사용할 수 없습니다. 사용자 정의 변환에 대 한 자세한 내용은 참조 하세요. [사용자 정의 변환 (C++/CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). 이 샘플에서는 C2440을 생성합니다.

```cpp
// C2440d.cpp
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
   int i;
   i = d;   // C2440
   // Uncomment the following line to resolve.
   // i = static_cast<int>(d);
}
```

## <a name="example"></a>예제

C2440은 시각적 개체의 인스턴스를 만들려고 할 경우에 발생할 수 있습니다 C++ 형식의 배열을 <xref:System.Array>합니다.  자세한 내용은 [배열](../../extensions/arrays-cpp-component-extensions.md)합니다.  다음 샘플에서는 C2440을 생성합니다.

```cpp
// C2440e.cpp
// compile with: /clr
using namespace System;
int main() {
   array<int>^ intArray = Array::CreateInstance(__typeof(int), 1);   // C2440
   // try the following line instead
   // array<int>^ intArray = safe_cast<array<int> ^>(Array::CreateInstance(__typeof(int), 1));
}
```

## <a name="example"></a>예제

C2440은 특성 기능이 변경 내용으로 인해 발생할 수 있습니다.  다음 샘플에서는 c2440 오류가 발생 합니다.

```cpp
// c2440f.cpp
// compile with: /LD
[ module(name="PropDemoLib", version=1.0) ];   // C2440
// try the following line instead
// [ module(name="PropDemoLib", version="1.0") ];
```

## <a name="example"></a>예제

Microsoft C++ 컴파일러는 더 이상 허용 합니다 [const_cast 연산자](../../cpp/const-cast-operator.md) 다운 캐스트가 경우 소스 코드를 사용 하는 **/clr** 프로그래밍 컴파일됩니다.

이 C2440을 해결 하려면 올바른 캐스트 연산자를 사용 합니다. 자세한 내용은 [캐스팅 연산자](../../cpp/casting-operators.md)합니다.

이 샘플에서는 C2440을 생성합니다.

```cpp
// c2440g.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};
int main() {
   Derived ^d = gcnew Derived;
   Base ^b = d;
   d = const_cast<Derived^>(b);   // C2440
   d = dynamic_cast<Derived^>(b);   // OK
}
```

## <a name="example"></a>예제

C2440은 Visual Studio 2015 업데이트 3에서 컴파일러 규칙 변경으로 인해 발생할 수 있습니다. 이전에 컴파일러 잘못 처리 특정 개별 식 같은 형식으로 일치 하는 서식 파일을 식별 하는 경우는 `static_cast` 작업 합니다. 이전에 의존 하는 이제 컴파일러는 형식이 올바르게 구분 하 고 코드 `static_cast` 동작 손상 되었습니다. 이 문제를 해결 하려면 변경 템플릿 매개 변수 형식과 일치 하거나 사용 하 여 템플릿 인수는 `reinterpret_cast` 또는 C 스타일 캐스트 합니다.

이 샘플에서는 C2440을 생성합니다.

```cpp
// c2440h.cpp

template<int *a>
struct S1 {};

int g;
struct S2 : S1<&g> {
};

int main()
{
    S2 s;
    static_cast<S1<&*&g>>(s); // C2440 in VS 2015 Update 3
    // This compiles correctly:
    // static_cast<S1<&g>>(s);
}

This error can appear in ATL code that uses the SINK_ENTRY_INFO macro defined in <atlcom.h>.
```

## <a name="example"></a>예제

### <a name="copy-list-initialization"></a>Copy-list-initialization

Visual Studio 2017 이상 올바르게 Visual Studio 2015에서 파악 되지 및 작동 중단 시킬 수 있는 이니셜라이저 목록을 사용한 개체 만들기에 관련 된 컴파일러 오류를 발생 시키는 나 런타임 동작이 정의 되지 않은 합니다. C + + 17 복사-목록 초기화를에서 컴파일러 오버 로드 확인에 대 한 명시적 생성자를 고려해 야 할 필요 하지만 오버 로드 하는 실제로 선택 되는 경우 오류가 발생 해야 합니다.

다음 예제에서는 Visual Studio 2017 아니라 Visual Studio 2015에서 컴파일합니다.

```cpp
// C2440j.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot
                         // convert from 'int' to 'const A &'
}
```

오류를 수정하려면 직접 초기화를 사용합니다.

```cpp
// C2440k.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    const A& a2{ 1 };
}
```

## <a name="example"></a>예제

### <a name="cv-qualifiers-in-class-construction"></a>클래스 생성의 cv 한정자

Visual Studio 2015에서는 컴파일러가 생성자 호출을 통해 클래스 개체를 생성할 때 cv 한정자를 잘못 무시하는 경우가 있습니다. 이로 인해 잠재적으로 크래시 또는 예기치 않은 런타임 동작이 발생할 수 있습니다. 다음 예제에서는 Visual Studio 2015에서는 컴파일되지만 Visual Studio 2017 이상 컴파일러 오류를 발생 시킵니다.

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

오류를 수정하려면 operator int()를 생성자로 선언합니다.
