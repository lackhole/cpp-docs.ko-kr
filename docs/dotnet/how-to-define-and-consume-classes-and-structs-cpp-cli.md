---
title: '방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)'
ms.date: 09/12/2018
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 2c43234ca05c661d8f3d920b1129256a7550a5e2
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751832"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)

이 문서에서는 정의 및 사용자 정의 참조 형식 및 C + 값 형식을 사용 하는 방법을 보여 줍니다. + CLI입니다.

##  <a name="BKMK_Contents"></a> 목차

[개체 인스턴스화](#BKMK_Object_instantiation)

[암시적 추상 클래스](#BKMK_Implicitly_abstract_classes)

[형식 표시 유형](#BKMK_Type_visibility)

[멤버 표시 유형](#BKMK_Member_visibility)

[Public 및 private 네이티브 클래스](#BKMK_Public_and_private_native_classes)

[정적 생성자](#BKMK_Static_constructors)

[이 의미 체계 포인터](#BKMK_Semantics_of_the_this_pointer)

[서명으로 숨기기 함수](#BKMK_Hide_by_signature_functions)

[복사 생성자](#BKMK_Copy_constructors)

[소멸자 및 종료자](#BKMK_Destructors_and_finalizers)

##  <a name="BKMK_Object_instantiation"></a> 개체 인스턴스화

관리 되는 힙에서 하지 스택이나 네이티브 힙에 참조 (ref) 형식만 인스턴스화할 수 있습니다. 값 형식은 스택이나 관리 되는 힙 인스턴스화할 수 있습니다.

```cpp
// mcppv2_ref_class2.cpp
// compile with: /clr
ref class MyClass {
public:
   int i;

   // nested class
   ref class MyClass2 {
   public:
      int i;
   };

   // nested interface
   interface struct MyInterface {
      void f();
   };
};

ref class MyClass2 : public MyClass::MyInterface {
public:
   virtual void f() {
      System::Console::WriteLine("test");
   }
};

public value struct MyStruct {
   void f() {
      System::Console::WriteLine("test");
   }
};

int main() {
   // instantiate ref type on garbage-collected heap
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass -> i = 4;

   // instantiate value type on garbage-collected heap
   MyStruct ^ p_MyStruct = gcnew MyStruct;
   p_MyStruct -> f();

   // instantiate value type on the stack
   MyStruct p_MyStruct2;
   p_MyStruct2.f();

   // instantiate nested ref type on garbage-collected heap
   MyClass::MyClass2 ^ p_MyClass2 = gcnew MyClass::MyClass2;
   p_MyClass2 -> i = 5;
}
```

##  <a name="BKMK_Implicitly_abstract_classes"></a> 암시적 추상 클래스

*암시적 추상 클래스* 인스턴스화할 수 없습니다. 클래스의 기본 형식이 인터페이스이며 클래스가 인터페이스의 모든 멤버 함수를 구현하지 않는 경우 클래스는 암시적 추상입니다.

인터페이스에서 파생된 클래스의 개체를 만들 수 없는 경우 해당 이유는 클래스가 암시적 추상이기 때문입니다. 추상 클래스에 대 한 자세한 내용은 참조 하세요. [추상](../windows/abstract-cpp-component-extensions.md)합니다.

다음 코드 예제는 `MyClass` 함수가 구현되지 않아서 `MyClass::func2` 클래스를 인스턴스화할 수 없음을 보여 줍니다. 해당 예제를 컴파일하려면 `MyClass::func2`의 주석 처리를 제거하십시오.

```cpp
// mcppv2_ref_class5.cpp
// compile with: /clr
interface struct MyInterface {
   void func1();
   void func2();
};

ref class MyClass : public MyInterface {
public:
   void func1(){}
   // void func2(){}
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;   // C2259
                                          // To resolve, uncomment MyClass::func2.
}
```

##  <a name="BKMK_Type_visibility"></a> 형식 표시 유형

어셈블리가 참조된 경우 어셈블리의 형식이 어셈블리 외부에서 표시되거나 표시되지 않도록 CLR(공용 언어 런타임)의 표시 유형을 제어할 수 있습니다.

`public` 형식을 포함 하는 소스 파일에 표시 되는지 나타냅니다는 `#using` 형식을 포함 하는 어셈블리에 대 한 지시문입니다.  `private` 형식이 포함 된 소스 파일에 표시 되지 않음을 나타냅니다는 `#using` 형식을 포함 하는 어셈블리에 대 한 지시문입니다. 그러나 private 형식은 동일한 어셈블리 내에는 표시됩니다. 기본적으로 클래스에 대한 표시 유형은 `private`입니다.

기본적으로 Visual C++ 2005 이전에는 네이티브 형식에 어셈블리 외부의 public 액세스 가능성이 있었습니다. 사용 하도록 설정 [컴파일러 경고 (수준 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) 참조는 private 네이티브 형식이 잘못 사용할 수 있도록 합니다. 사용 된 [make_public](../preprocessor/make-public.md) pragma를 수정할 수 없는 소스 코드 파일에서 네이티브 형식에 public 액세스 가능성을 제공 합니다.

자세한 내용은 [#using 지시문](../preprocessor/hash-using-directive-cpp.md)을 참조하세요.

다음 샘플은 형식을 선언하고 해당 액세스 가능성을 지정한 다음 어셈블리 내부에서 이러한 형식에 액세스하는 방법을 보여 줍니다. 물론 `#using`을 사용하여 private 형식의 어셈블리를 참조하는 경우 어셈블리 내에서 public 형식만 표시됩니다.

```cpp
// type_visibility.cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// default accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   Private_Class ^ b = gcnew Private_Class;
   b->Test();

   Private_Class_2 ^ c = gcnew Private_Class_2;
   c->Test();
}
```

**출력**

```Output
in Public_Class
in Private_Class
in Private_Class_2
```

이제 DLL로 빌드되도록 이전 샘플을 다시 작성합니다.

```cpp
// type_visibility_2.cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside the assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// by default, accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};
```

다음 샘플은 어셈블리 외부에서 형식에 액세스하는 방법을 보여 줍니다. 이 샘플에서 클라이언트는 이전 샘플에서 빌드한 구성 요소를 사용합니다.

```cpp
// type_visibility_3.cpp
// compile with: /clr
#using "type_visibility_2.dll"
int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   // private types not accessible outside the assembly
   // Private_Class ^ b = gcnew Private_Class;
   // Private_Class_2 ^ c = gcnew Private_Class_2;
}
```

**출력**

```Output
in Public_Class
```

##  <a name="BKMK_Member_visibility"></a> 멤버 표시 유형


  `public`, `protected` 및 `private` 액세스 지정자 쌍을 사용하여 어셈블리 외부에서 public 클래스의 멤버에 액세스하는 것과 다르게 동일한 어셈블리 내에서 public 클래스의 멤버에 액세스할 수 있습니다.

이 표에서는 다양한 액세스 지정자의 효과를 요약하여 보여 줍니다.

|지정자|효과|
|---------------|------------|
|public|멤버는 어셈블리 내부 및 외부에서 액세스할 수 있습니다.  참조 [공용](../cpp/public-cpp.md) 자세한 내용은 합니다.|
|private|멤버는 어셈블리 내부 및 외부 모두에서 액세스할 수 없습니다.  참조 [개인](../cpp/private-cpp.md) 자세한 내용은 합니다.|
|protected|멤버는 파생된 형식에 한해 어셈블리 내부 및 외부에서 액세스할 수 있습니다.  참조 [보호](../cpp/protected-cpp.md) 자세한 내용은 합니다.|
|internal|멤버가는 어셈블리 내부에서 public 이지만 어셈블리 외부에서는 private입니다.  `internal`는 상황에 맞는 키워드입니다.  자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)합니다.|
|공용 보호 또는 보호 된 공용|멤버는 어셈블리 내부에서 public이지만 어셈블리 외부에서는 protected입니다.|
|개인 보호 또는 보호 된 개인|멤버는 어셈블리 내부에서 protected이지만 어셈블리 외부에서는 private입니다.|

다음 샘플은 다른 액세스 가능성으로 선언된 멤버가 포함된 public 형식을 보여 준 다음 어셈블리 내부에서 해당 멤버의 액세스를 보여 줍니다.

```cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();
   a->Protected_Public_Function();
   a->Public_Protected_Function();

   // accessible inside but not outside the assembly
   a->Internal_Function();

   // call protected functions
   b->Test();

   // not accessible inside or outside the assembly
   // a->Private_Function();
}
```

**출력**

```Output
in Public_Function
in Protected_Public_Function
in Public_Protected_Function
in Internal_Function
=======================
in function of derived class
in Protected_Function
in Protected_Private_Function
in Private_Protected_Function
exiting function of derived class
=======================
```

이제 DLL로 이전 샘플을 빌드합니다.

```cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};
```

다음 샘플은 이전 샘플에서 만들어진 구성 요소를 사용하므로 어셈블리 외부에서 멤버에 액세스하는 방법을 보여 줍니다.

```cpp
// compile with: /clr
#using "type_member_visibility_2.dll"
using namespace System;
// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Public_Function();
      Public_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();

   // call protected functions
   b->Test();

   // can't be called outside the assembly
   // a->Private_Function();
   // a->Internal_Function();
   // a->Protected_Private_Function();
   // a->Private_Protected_Function();
}
```

**출력**

```Output
in Public_Function
=======================
in function of derived class
in Protected_Function
in Protected_Public_Function
in Public_Protected_Function
exiting function of derived class
=======================
```

##  <a name="BKMK_Public_and_private_native_classes"></a> Public 및 private 네이티브 클래스

네이티브 형식은 관리되는 형식에서 참조될 수 있습니다.  예를 들어 관리되는 형식의 함수는 네이티브 구조체 형식의 매개 변수를 사용할 수 있습니다.  관리되는 형식과 함수가 어셈블리 내에서 public이면 네이티브 형식도 public이어야 합니다.

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

다음으로 네이티브 형식을 사용하는 소스 코드 파일을 만듭니다.

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

이제 클라이언트를 컴파일합니다.

```cpp
// compile with: /clr
#using "mcppv2_ref_class3.dll"

#include "mcppv2_ref_class3.h"

int main() {
   R ^r = gcnew R;
   N n;
   r->f(n);
}
```

##  <a name="BKMK_Static_constructors"></a> 정적 생성자

클래스나 구조체 같은 CLR 형식은 정적 데이터 멤버를 초기화하는 데 사용할 수 있는 정적 생성자를 보유할 수 있습니다.  정적 생성자는 한 번만 호출되며 형식의 정적 멤버가 처음으로 액세스하기 전에 호출됩니다.

인스턴스 생성자는 항상 정적 생성자가 실행된 후 실행됩니다.

컴파일러는 클래스에 정적 생성자가 있는 경우 생성자에 대한 호출을 인라인할 수 없습니다.  컴파일러는 클래스가 값 형식이고, 클래스에 정적 생성자는 있지만 인스턴스 생성자가 없는 경우 멤버 함수에 대한 호출을 인라인할 수 없습니다.  CLR은 호출을 인라인할 수 있지만 컴파일러는 인라인할 수 없습니다.

CLR에 의해서만 호출될 수 있도록 정적 생성자를 private 멤버 함수로 정의합니다.

정적 생성자에 대 한 자세한 내용은 참조 하세요. [방법: 인터페이스 정적 생성자 정의 (C + + /cli CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) 합니다.

```cpp
// compile with: /clr
using namespace System;

ref class MyClass {
private:
   static int i = 0;

   static MyClass() {
      Console::WriteLine("in static constructor");
      i = 9;
   }

public:
   static void Test() {
      i++;
      Console::WriteLine(i);
   }
};

int main() {
   MyClass::Test();
   MyClass::Test();
}
```

**출력**

```Output
in static constructor
10
11
```

##  <a name="BKMK_Semantics_of_the_this_pointer"></a> 이 의미 체계 포인터

Visual C++를 사용하여 형식을 정의하는 경우 참조 형식에서 `this` 포인터는 "핸들" 형식입니다. 값 형식에서 `this` 포인터는 "내부 포인터" 형식입니다.

이러한 서로 다른 의미 체계의 `this` 포인터는 기본 인덱서가 호출될 때 예기치 않은 동작이 발생할 수 있습니다. 다음 예제에서는 참조 형식과 값 형식 모두에서 기본 인덱서에 액세스하는 올바른 방법을 보여 줍니다.

자세한 내용은 다음 항목을 참조하세요.

- [개체 연산자 (^)에 대 한 핸들](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)

- [interior_ptr(C++/CLI)](../windows/interior-ptr-cpp-cli.md)

```cpp
// compile with: /clr
using namespace System;

ref struct A {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }

   A() {
      // accessing default indexer
      Console::WriteLine("{0}", this[3.3]);
   }
};

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      // accessing default indexer
      Console::WriteLine("{0}", this->default[3.3]);
   }
};

int main() {
   A ^ mya = gcnew A();
   B ^ myb = gcnew B();
   myb->Test();
}
```

**출력**

```Output
10.89
10.89
```

##  <a name="BKMK_Hide_by_signature_functions"></a> 서명으로 숨기기 함수

표준 C++에서 기본 클래스의 함수는 파생 클래스 함수에 동일하지 않은 매개 변수의 수나 종류가 있는 경우에도 파생 클래스에서 동일한 이름을 가진 함수에 의해 숨겨져 있습니다. 이 이라고 *이름순 숨기기* 의미 합니다. 참조 형식에서 기본 클래스의 함수는 이름 및 매개 변수의 목록이 모두 동일한 경우 파생 클래스의 함수에 의해서만 숨겨질 수 있습니다. 이 이라고 *서명으로 숨기기* 의미 합니다.

클래스의 모든 함수가 메타데이터에 `hidebysig`로 표시되면 클래스는 hide-by-signature 클래스라고 간주됩니다. 기본적으로 아래에 생성 된 모든 클래스 **/clr** 가 `hidebysig` 함수입니다. 클래스에 `hidebysig` 함수가 있는 경우 컴파일러는 함수를 직접 기본 클래스의 이름으로 숨기지 않습니다. 하지만 컴파일러에서 상속 체인의 hide-by-name 클래스를 발견하는 경우 hide-by-name 동작이 계속됩니다.

hide-by-signature 의미 체계에 따라 함수가 객체에 호출되면 컴파일러는 함수 호출을 충족할 수 있는 함수가 포함된 가장 많이 파생된 클래스를 식별합니다. 호출을 충족할 수 있는 함수가 클래스에 하나 뿐인 경우 컴파일러는 해당 함수를 호출합니다. 호출을 충족할 수 있는 함수가 클래스에 둘 이상이 있는 경우 컴파일러는 오버로드 확인 규칙을 사용하여 호출할 함수를 결정합니다. 오버 로드 규칙에 대 한 자세한 내용은 참조 하세요. [함수 오버 로드](../cpp/function-overloading.md)합니다.

지정된 함수 호출의 경우 기본 클래스의 함수는 파생 클래스의 함수보다 조금 더 일치하는 시그니처를 가지고 있을 수 있습니다. 그러나 함수가 파생 클래스의 객체에 명시적으로 호출된 경우 파생 클래스의 함수가 호출됩니다.

반환 값이 함수 시그니처의 일부분으로 간주되지 않으므로 반환 값의 형식이 다른 경우에도 기본 클래스 함수가 파생 클래스 함수와 이름이 동일하며 인수의 수와 종류가 동일한 경우 기본 클래스 함수가 숨겨집니다.

다음 샘플은 기본 클래스의 함수가 파생 클래스의 함수에 의해 숨겨지지 않음을 보여 줍니다.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test() {
      Console::WriteLine("Base::Test");
   }
};

ref struct Derived : public Base {
   void Test(int i) {
      Console::WriteLine("Derived::Test");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Test() in the base class will not be hidden
   t->Test();
}
```

**출력**

```Output
Base::Test
```

다음 샘플은 Visual C++ 컴파일러가 매개 변수를 하나 이상 일치하기 위해 변환이 필요한 경우에도 가장 많이 파생된 클래스의 함수를 호출하고 함수 호출과 더 잘 일치하는 기본 클래스의 함수를 호출하지 않음을 보여 줍니다.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test2(Single d) {
      Console::WriteLine("Base::Test2");
   }
};

ref struct Derived : public Base {
   void Test2(Double f) {
      Console::WriteLine("Derived::Test2");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Base::Test2 is a better match, but the compiler
   // calls a function in the derived class if possible
   t->Test2(3.14f);
}
```

**출력**

```Output
Derived::Test2
```

다음 샘플은 기본 클래스에 파생 클래스와 동일한 시그니처가 있는 경우에도 함수를 숨길 수 있음을 보여 줍니다.

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   int Test4() {
      Console::WriteLine("Base::Test4");
      return 9;
   }
};

ref struct Derived : public Base {
   char Test4() {
      Console::WriteLine("Derived::Test4");
      return 'a';
   }
};

int main() {
   Derived ^ t = gcnew Derived;

   // Base::Test4 is hidden
   int i = t->Test4();
   Console::WriteLine(i);
}
```

**출력**

```Output
Derived::Test4
97
```

##  <a name="BKMK_Copy_constructors"></a> 복사 생성자

C++ 표준에 따르면 복사 생성자는 개체가 동일한 주소에서 생성되고 제거되는 것처럼 개체가 이동하면 호출됩니다.

그러나 때 **/clr** 컴파일 및 MSIL 호출 있는 네이티브 클래스 네이티브 함수에 컴파일된 함수에는-하나 이상의-값 및 복사 생성자 및/또는 소멸자, 복사본이 없는 네이티브 클래스에 의해 전달 됩니다 생성자가 호출 하 고 개체와 다른 주소를 생성 된 위치에서 제거 됩니다. 클래스 자체에 대한 포인터가 있거나 코드가 주소로 개체를 추적하는 경우 문제가 발생할 수 있습니다.

자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

다음 샘플은 복사 생성자가 생성되지 않는 경우를 보여 줍니다.

```cpp
// compile with: /clr
#include<stdio.h>

struct S {
   int i;
   static int n;

   S() : i(n++) {
      printf_s("S object %d being constructed, this=%p\n", i, this);
   }

   S(S const& rhs) : i(n++) {
      printf_s("S object %d being copy constructed from S object "
               "%d, this=%p\n", i, rhs.i, this);
   }

   ~S() {
      printf_s("S object %d being destroyed, this=%p\n", i, this);
   }
};

int S::n = 0;

#pragma managed(push,off)
void f(S s1, S s2) {
   printf_s("in function f\n");
}
#pragma managed(pop)

int main() {
   S s;
   S t;
   f(s,t);
}
```

**출력**

```Output
S object 0 being constructed, this=0018F378
S object 1 being constructed, this=0018F37C
S object 2 being copy constructed from S object 1, this=0018F380
S object 3 being copy constructed from S object 0, this=0018F384
S object 4 being copy constructed from S object 2, this=0018F2E4
S object 2 being destroyed, this=0018F380
S object 5 being copy constructed from S object 3, this=0018F2E0
S object 3 being destroyed, this=0018F384
in function f
S object 5 being destroyed, this=0018F2E0
S object 4 being destroyed, this=0018F2E4
S object 1 being destroyed, this=0018F37C
S object 0 being destroyed, this=0018F378
```

##  <a name="BKMK_Destructors_and_finalizers"></a> 소멸자 및 종료자

참조 형식에서 소멸자는 리소스의 명확한 정리를 수행합니다. 종료자는 관리되지 않는 리소스를 정리하고 소멸자에 의해 명확하게 호출되거나 가비지 수집기에 의해 불명확하게 호출될 수 있습니다. 표준 c + +에서 소멸자에 대 한 정보를 참조 하세요 [소멸자](../cpp/destructors-cpp.md)합니다.

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

관리되는 Visual C++ 클래스의 소멸자와 Managed Extensions for C++의 소멸자는 동작이 다릅니다. 이 변경에 대 한 자세한 내용은 참조 하세요. [소멸자 의미의 변경 내용](../dotnet/changes-in-destructor-semantics.md)합니다.

CLR 가비지 수집기는 사용하지 않은 관리되는 개체를 삭제하고 더 이상 필요하지 않은 경우 메모리를 해제합니다. 그러나 형식에서 가비지 수집기가 해제하는 방법을 알지 못하는 리소스를 사용할 수도 있습니다. 이러한 리소스를 관리되지 않는 리소스(예: 네이티브 파일 핸들)라고 합니다. 종료자에서 관리되지 않는 리소스는 모두 해제하는 것이 좋습니다. 관리되는 리소스는 가비지 수집기에 의해 불명확하게 해제되므로 종료자에서 관리되는 리소스가 안전하다고 할 수 없습니다. 이는 가비지 수집기가 이미 관리되는 리소스를 정리했을 수도 있기 때문입니다.

Visual C++ 종료자와 <xref:System.Object.Finalize%2A> 메서드는 같지 않습니다. CLR 문서는 종료자와 <xref:System.Object.Finalize%2A> 메서드를 같은 뜻으로 사용합니다. 
  <xref:System.Object.Finalize%2A> 메서드는 클래스 상속 체인의 각 종료자를 호출하는 가비지 수집기에 의해 호출됩니다. Visual C++ 소멸자와 달리 파생 클래스 종료자가 호출되면 컴파일러는 모든 기본 클래스의 종료자를 호출하지 않습니다.

Visual C++ 컴파일러는 리소스의 명확한 해제를 지원하므로 <xref:System.IDisposable.Dispose%2A> 또는 <xref:System.Object.Finalize%2A> 메서드를 구현하지 마십시오. 그러나 이러한 메서드에 익숙한 경우 Visual C++ 종료자 및 소멸자가 <xref:System.IDisposable.Dispose%2A> 패턴에 매핑하도록 종료자를 호출하는 방법은 다음과 같습니다.

```cpp
// Visual C++ code
ref class T {
   ~T() { this->!T(); }   // destructor calls finalizer
   !T() {}   // finalizer
};

// equivalent to the Dispose pattern
void Dispose(bool disposing) {
   if (disposing) {
      ~T();
   } else {
      !T();
   }
}
```

관리되는 형식은 명확하게 해제하려는 관리되는 리소스도 사용할 수 있으며 개체가 더 이상 필요하지 않게 된 후 어느 시점에 가비지 수집기가 불명확하게 해제하도록 허용하지 않습니다. 리소스의 명확한 해제는 성능을 현저하게 개선할 수 있습니다.

Visual C++ 컴파일러는 소멸자의 정의를 사용하여 개체를 명확하게 정리할 수 있습니다. 소멸자를 사용하여 명확하게 해제하려는 리소스를 모두 해제하십시오.  종료자가 존재하는 경우 코드의 중복을 피하기 위해 소멸자에서 호출하십시오.

```cpp
// compile with: /clr /c
ref struct A {
   // destructor cleans up all resources
   ~A() {
      // clean up code to release managed resource
      // ...
      // to avoid code duplication,
      // call finalizer to release unmanaged resources
      this->!A();
   }

   // finalizer cleans up unmanaged resources
   // destructor or garbage collector will
   // clean up managed resources
   !A() {
      // clean up code to release unmanaged resources
      // ...
   }
};
```

형식을 사용하는 코드가 소멸자를 호출하지 않으면 가비지 수집기는 결국 관리되는 리소스를 모두 해제합니다.

소멸자의 존재가 종료자의 존재를 의미하지는 않습니다. 그러나 종료자의 존재는 소멸자를 정의해야 하고 해당 소멸자에서 종료자를 호출해야 함을 의미합니다. 이는 관리되지 않은 리소스의 명확한 해제를 제공합니다.


  <xref:System.GC.SuppressFinalize%2A>를 통해 소멸자를 호출하여 개체의 종료를 막습니다. 소멸자가 호출되지 않으면 해당 형식의 종료자가 결국 가비지 수집기에 의해 호출됩니다.

소멸자를 호출하여 개체의 리소스를 명확하게 정리하면 CLR이 불명확하게 개체를 종료하는 것에 비해 성능을 향상시킬 수 있습니다.

Visual c + +로 작성 된 개이고 사용 하 여 컴파일된 코드 **/clr** 경우 형식의 소멸자를 실행 합니다.

- 스택 의미 체계를 사용하여 만들어진 개체가 범위를 벗어난 경우. 자세한 내용은 [참조 형식에 대 한 c + + 스택 의미 체계](../dotnet/cpp-stack-semantics-for-reference-types.md)합니다.

- 개체의 생성 중에 예외가 발생한 경우

- 개체가 소멸자를 실행 중인 개체의 멤버인 경우

- 호출 된 [삭제](../cpp/delete-operator-cpp.md) 핸들에 대 한 연산자 ([개체 연산자 (^)에 대 한 핸들](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)).

- 명시적으로 소멸자를 호출한 경우

다른 언어로 작성된 클라이언트에 의해 형식이 사용 중인 경우 소멸자가 다음과 같이 호출됩니다.

- 
  <xref:System.IDisposable.Dispose%2A>에 대한 호출인 경우

- 형식의 `Dispose(void)`에 대한 호출인 경우

- 형식이 C#의 `using` 문의 범위를 벗어나는 경우

(참조 형식에 대 한 스택 의미 체계 사용 하지 않음) 관리 되는 힙에서 참조 형식의 개체를 만드는 경우 사용할 [try-finally](../cpp/try-finally-statement.md) 구문 예외가 소멸자가 실행 되지 않도록 방지 하지는 되도록 합니다.

```cpp
// compile with: /clr
ref struct A {
   ~A() {}
};

int main() {
   A ^ MyA = gcnew A;
   try {
      // use MyA
   }
   finally {
      delete MyA;
   }
}
```

형식에 소멸자가 있는 경우 컴파일러는 `Dispose`을 구현하는 <xref:System.IDisposable> 메서드를 생성합니다. Visual C++로 작성되고 다른 언어에서 사용된 소멸자가 있는 형식의 경우 해당 형식에서 `IDisposable::Dispose`를 호출하면 해당 형식의 소멸자가 호출됩니다. 형식이 Visual C++ 클라이언트에서 사용되면 `Dispose`를 직접 호출할 수 없습니다. 대신 `delete` 연산자를 사용하여 소멸자를 호출합니다.

형식에 종료자가 있는 경우 컴파일러는 `Finalize(void)`를 재정의하는 <xref:System.Object.Finalize%2A> 메서드를 생성합니다.

형식에 종료자 또는 소멸자가 있는 경우 컴파일러는 디자인 패턴에 따라 `Dispose(bool)` 메서드를 생성합니다. (내용은 [Dispose 패턴](/dotnet/standard/design-guidelines/dispose-pattern)). Visual C++에서 `Dispose(bool)`를 명시적으로 작성하거나 호출할 수 없습니다.

형식에 디자인 패턴을 따르는 기본 클래스가 있는 경우 파생 클래스의 소멸자가 호출될 때 모든 기본 클래스의 소멸자가 호출됩니다. Visual C++에서 형식이 작성된 경우 컴파일러는 형식이 이 패턴을 구현했는지 확인합니다. 다시 말해서 참조 클래스의 소멸자는 C++ 표준에 의해 지정된 기본 항목 및 멤버에 연결됩니다. 먼저 클래스의 소멸자가 실행되면 그 후에 생성된 순서의 반대로 해당 멤버의 소멸자가 실행됩니다. 마지막으로 해당 기본 클래스의 소멸자가 생성된 순서의 반대로 실행됩니다.

소멸자 및 종료자는 값 형식 또는 인터페이스 내부에서 허용되지 않습니다.

종료자는 참조 형식에서만 정의되거나 선언될 수 있습니다. 생성자와 소멸자와 같이 종료자는 반환 형식이 없습니다.

개체의 종료자가 실행된 후 기본 클래스의 종료자도 최소 파생된 형식으로 시작하여 호출됩니다. 데이터 멤버의 종료자는 클래스의 종료자에 의해 자동으로 연결되지 않습니다.

종료자가 관리되는 형식에서 네이티브 포인터를 삭제한 경우에는 네이티브 포인터에 대한 또는 네이티브 포인터를 통한 참조가 이미 수집되었는지 확인하고 <xref:System.GC.KeepAlive%2A>를 사용하는 대신 관리되는 형식에서 소멸자를 호출합니다.

컴파일 타임에서 형식에 종료자 또는 소멸자가 있는지 확인할 수 있습니다. 자세한 내용은 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.

다음 샘플은 관리되지 않은 리소스가 있는 형식과 명확하게 해제된 관리되는 리소스가 있는 형식을 보여 줍니다.

```cpp
// compile with: /clr
#include <vcclr.h>
#include <stdio.h>
using namespace System;
using namespace System::IO;

ref class SystemFileWriter {
   FileStream ^ file;
   array<Byte> ^ arr;
   int bufLen;

public:
   SystemFileWriter(String ^ name) : file(File::Open(name, FileMode::Append)),
                                     arr(gcnew array<Byte>(1024)) {}

   void Flush() {
      file->Write(arr, 0, bufLen);
      bufLen = 0;
   }

   ~SystemFileWriter() {
      Flush();
      delete file;
   }
};

ref class CRTFileWriter {
   FILE * file;
   array<Byte> ^ arr;
   int bufLen;

   static FILE * getFile(String ^ n) {
      pin_ptr<const wchar_t> name = PtrToStringChars(n);
      FILE * ret = 0;
      _wfopen_s(&ret, name, L"ab");
      return ret;
   }

public:
   CRTFileWriter(String ^ name) : file(getFile(name)), arr(gcnew array<Byte>(1024) ) {}

   void Flush() {
      pin_ptr<Byte> buf = &arr[0];
      fwrite(buf, 1, bufLen, file);
      bufLen = 0;
   }

   ~CRTFileWriter() {
      this->!CRTFileWriter();
   }

   !CRTFileWriter() {
      Flush();
      fclose(file);
   }
};

int main() {
   SystemFileWriter w("systest.txt");
   CRTFileWriter ^ w2 = gcnew CRTFileWriter("crttest.txt");
}
```

## <a name="see-also"></a>참고자료

[클래스 및 구조체(C++)](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[클래스 및 구조체(C++)](../windows/classes-and-structs-cpp-component-extensions.md)
