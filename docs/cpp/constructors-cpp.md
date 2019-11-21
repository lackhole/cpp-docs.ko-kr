---
title: 생성자 (C++)
ms.date: 11/19/2019
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: 6cdf6241542c3f93484097c65015181a91647d49
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246612"
---
# <a name="constructors-c"></a>생성자 (C++)

To customize how class members are initialized, or to invoke functions when an object of your class is created, define a *constructor*. 생성자는 클래스와 같은 이름을 사용하며 반환 값이 없습니다. You can define as many overloaded constructors as needed to customize initialization in various ways. Typically, constructors have public accessibility so that code outside the class definition or inheritance hierarchy can create objects of the class. But you can also declare a constructor as **protected** or **private**.

Constructors can optionally take a member init list. This is a more efficient way to initialize class members than assigning values in the constructor body. The following example shows a class `Box` with three overloaded constructors. The last two use member init lists:

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    explicit Box(int i) : m_width(i), m_length(i), m_height(i) // member init list
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}

    int Volume() { return m_width * m_length * m_height; }

private:
    // Will have value of 0 when default constructor is called.
    // If we didn't zero-init here, default constructor would
    // leave them uninitialized with garbage values.
    int m_width{ 0 };
    int m_length{ 0 };
    int m_height{ 0 };
};
```

When you declare an instance of a class, the compiler chooses which constructor to invoke based on the rules of overload resolution:

```cpp
int main()
{
    Box b; // Calls Box()

    // Using uniform initialization (preferred):
    Box b2 {5}; // Calls Box(int)
    Box b3 {5, 8, 12}; // Calls Box(int, int, int)

    // Using function-style notation:
    Box b4(2, 4, 6); // Calls Box(int, int, int)
}
```

- Constructors may be declared as **inline**, [explicit](#explicit_constructors), **friend** or [constexpr](#constexpr_constructors).
- A constructor can initialize an object that has been declared as **const**, **volatile** or **const volatile**. The object becomes **const** after the constructor completes.
- To define a constructor in an implementation file, give it a qualified name as with any other member function: `Box::Box(){...}`.

## <a name="member_init_list"></a> Member initializer lists

A constructor can optionally have a member initializer list, which initializes class members prior to execution of the constructor body. (Note that a member initializer list is not the same thing as an *initializer list* of type [std::initializer_list\<T>](../standard-library/initializer-list-class.md).)

Using a member initializer list is preferred over assigning values in the body of the constructor because it directly initializes the member. In the following example shows the member initializer list consists of all the **identifier(argument)** expressions after the colon:

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

The identifier must refer to a class member; it is initialized with the value of the argument. The argument can be one of the constructor parameters, a function call or a [std::initializer_list\<T>](../standard-library/initializer-list-class.md).

**const** members and members of reference type must be initialized in the member initializer list.

Calls to parameterized base class constructors should be made in the initializer list to ensure the base class is fully initialized prior to execution of the derived constructor.

## <a name="default_constructors"></a> Default constructors

*Default constructors* typically have no parameters, but they can have parameters with default values.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Default constructors are one of the [special member functions](special-member-functions.md). If no constructors are declared in a class, the compiler provides an implicit **inline** default constructor.

```cpp
#include <iostream>
using namespace std;

class Box {
public:
    int Volume() {return m_width * m_height * m_length;}
private:
    int m_width { 0 };
    int m_height { 0 };
    int m_length { 0 };
};

int main() {
    Box box1; // Invoke compiler-generated constructor
    cout << "box1.Volume: " << box1.Volume() << endl; // Outputs 0
}
```

If you rely on an implicit default constructor, be sure to initialize members in the class definition, as shown in the previous example. Without those initializers, the members would be uninitialized and the Volume() call would produce a garbage value. In general, it is good practice to initialize members in this way even when not relying on an implicit default constructor.

You can prevent the compiler from generating an implicit default constructor by defining it as [deleted](#explicitly_defaulted_and_deleted_constructors):

```cpp
    // Default constructor
    Box() = delete;
```

A compiler-generated default constructor will be defined as deleted if any class members are not default-constructible. For example, all members of class type, and their class-type members, must have a default constructor and destructors that are accessible. All data members of reference type, as well as **const** members must have a default member initializer.

When you call a compiler-generated default constructor and try to use parentheses, a warning is issued:

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

이는 가장 까다로운 구문 분석 문제의 한 예입니다. 예제 식을 함수 선언 또는 기본 생성자 호출로 해석할 수 있고 C++ 파서에서는 선언을 다른 항목보다 우선하므로 식이 함수 선언으로 처리됩니다. For more information, see [Most Vexing Parse](https://en.wikipedia.org/wiki/Most_vexing_parse).

기본값이 아닌 생성자가 선언된 경우 컴파일러는 기본 생성자를 제공하지 않습니다.

```cpp
class Box {
public:
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height){}
private:
    int m_width;
    int m_length;
    int m_height;

};

int main(){

    Box box1(1, 2, 3);
    Box box2{ 2, 3, 4 };
    Box box3; // C2512: no appropriate default constructor available
}
```

클래스에 기본 생성자가 없는 경우 대괄호 구문만 사용하여 해당 클래스의 개체 배열을 생성할 수 없습니다. 예를 들어 이전 코드 블록에서 다음과 같이 상자 배열을 선언할 수 없습니다.

```cpp
Box boxes[3]; // C2512: no appropriate default constructor available
```

However, you can use a set of initializer lists to initialize an array of Box objects:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

For more information, see [Initializers](initializers.md).

## <a name="copy_and_move_constructors"></a> Copy constructors

A *copy constructor* initializes an object by copying the member values from an object of the same type. If your class members are all simple types such as scalar values, the compiler-generated copy constructor is sufficient and you do not need to define your own. If your class requires more complex initialization, then you need to implement a custom copy constructor. For example, if a class member is a pointer then you need to define a copy constructor to allocate new memory and copy the values from the other's pointed-to object. The compiler-generated copy constructor simply copies the pointer, so that the new pointer still points to the other's memory location.

A copy constructor may have one of these signatures:

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

When you define a copy constructor, you should also define a copy assignment operator (=). For more information, see [Assignment](assignment.md) and [Copy constructors and copy assignment operators](copy-constructors-and-copy-assignment-operators-cpp.md).

You can prevent your object from being copied by defining the copy constructor as deleted:

```cpp
    Box (const Box& other) = delete;
```

Attempting to copy the object produces error *C2280: attempting to reference a deleted function*.

## <a name="move_constructors"></a> Move constructors

A *move constructor* is a special member function that moves ownership of an existing object's data to a new variable without copying the original data. It takes an rvalue reference as its first parameter, and any additional parameters must have default values. Move constructors can significantly increase your program's efficiency when passing around large objects.

```cpp
Box(Box&& other);
```

The compiler chooses a move constructor in certain situations where the object is being initialized by another object of the same type that is about to be destroyed and no longer needs its resources. The following example shows one case when a move constructor is selected by overload resolution. In the constructor that calls `get_Box()`, the returned value is an *xvalue* (eXpiring value). It is not assigned to any variable and is therefore about to go out of scope. To provide motivation for this example, let's give Box a large vector of strings that represent its contents. Rather than copying the vector and its strings, the move constructor "steals" it from the expiring value "box" so that the vector now belongs to the new object. The call to `std::move` is all that's needed because both `vector` and `string` classes implement their own move constructors.

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
using namespace std;

class Box {
public:
    Box() { std::cout << "default" << std::endl; }
    Box(int width, int height, int length)
       : m_width(width), m_height(height), m_length(length)
    {
        std::cout << "int,int,int" << std::endl;
    }
    Box(Box& other)
       : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        std::cout << "copy" << std::endl;
    }
    Box(Box&& other) : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        m_contents = std::move(other.m_contents);
        std::cout << "move" << std::endl;
    }
    int Volume() { return m_width * m_height * m_length; }
    void Add_Item(string item) { m_contents.push_back(item); }
    void Get_Contents()
    {
        for (const auto& item : m_contents)
        {
            cout << item << " ";
        }
    }
private:
    int m_width{ 0 };
    int m_height{ 0 };
    int m_length{ 0 };
    vector<string> m_contents;
};

Box get_Box()
{
    Box b(5, 10, 18); // "int,int,int"
    b.Add_Item("Toupee");
    b.Add_Item("Megaphone");
    b.Add_Item("Suit");

    return b;
}

int main()
{
    Box b; // "default"
    Box b1(b); // "copy"
    Box b2(get_Box()); // "move"
    cout << "b2 contents: ";
    b2.Get_Contents(); // Prove that we have all the values

    char ch;
    cin >> ch; // keep window open
    return 0;
}
```

If a class does not define a move constructor, the compiler generates an implicit one if there is no user-declared copy constructor, copy assignment operator, move assignment operator, or destructor. If no explicit or implicit move constructor is defined, operations that would otherwise use a move constructor use the copy constructor instead. If a class declares a move constructor or move assignment operator, the implicitly declared copy constructor is defined as deleted.

An implicitly declared move constructor is defined as deleted if any members that are class types lack a destructor or the compiler cannot determine which constructor to use for the move operation.

For more information about how to write a non-trivial move constructor, see [Move Constructors and Move Assignment Operators (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

## <a name="explicitly_defaulted_and_deleted_constructors"></a> Explicitly defaulted and deleted constructors

You can explicitly *default* copy constructors, default constructors, move constructors, copy assignment operators, move assignment operators, and destructors. You can explicitly *delete* all of the special member functions.

```cpp
class Box
{
public:
    Box2() = delete;
    Box2(const Box2& other) = default;
    Box2& operator=(const Box2& other) = default;
    Box2(Box2&& other) = default;
    Box2& operator=(Box2&& other) = default;
    //...
};
```

For more information, see [Explicitly Defaulted and Deleted Functions](../cpp/explicitly-defaulted-and-deleted-functions.md).

## <a name="constexpr_constructors"></a> constexpr constructors

A constructor may be declared as [constexpr](constexpr-cpp.md) if

- it is either declared as defaulted or else it satisfies all the conditions for [constexpr functions](constexpr-cpp.md#constexpr_functions) in general;
- the class has no virtual base classes;
- each of the parameters is a [literal type](trivial-standard-layout-and-pod-types.md#literal_types);
- the body is not a function try-block;
- all non-static data members and base class sub-objects are initialized;
- if the class is (a) a union having variant members, or (b) has anonymous unions, only one of the union members is initialized;
- every non-static data member of class type, and all base-class sub-objects have a constexpr constructor

## <a name="init_list_constructors"></a> Initializer list constructors

If a constructor takes a [std::initializer_list\<T\>](../standard-library/initializer-list-class.md) as its parameter, and any other parameters have default arguments, that constructor will be selected in overload resolution when the class is instantiated through direct initialization. You can use the initializer_list to initialize any member that can accept it. For example, assume the Box class (shown previously) has a `std::vector<string>` member `m_contents`. You can provide a constructor like this:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

And then create Box objects like this:

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit_constructors"></a> Explicit constructors

클래스에 단일 매개 변수를 사용하는 생성자가 있거나 하나를 제외한 모든 매개 변수에서 기본값을 사용하는 경우 이 매개 변수 형식은 클래스 형식으로 암시적으로 변환할 수 있습니다. 예를 들어 `Box` 클래스에 다음과 같은 생성자가 있는 경우입니다.

```cpp
Box(int size): m_width(size), m_length(size), m_height(size){}
```

다음과 같이 Box를 초기화할 수 있습니다.

```cpp
Box b = 42;
```

또는 Box를 사용하는 함수에 int를 전달합니다.

```cpp
class ShippingOrder
{
public:
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}

private:
    Box m_box;
    double m_postage;
}
//elsewhere...
    ShippingOrder so(42, 10.8);
```

경우에 따라 이러한 변환은 유용할 수 있지만 코드에서 미세하지만 심각한 오류를 발생시키는 경우가 더 자주 있습니다. As a general rule, you should use the **explicit** keyword on a constructor (and user-defined operators) to prevent this kind of implicit type conversion:

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

생성자가 명시적인 경우 `ShippingOrder so(42, 10.8);` 줄에서 컴파일 오류가 발생합니다.  For more information, see [User-Defined Type Conversions](../cpp/user-defined-type-conversions-cpp.md).

## <a name="order_of_construction"></a> Order of construction

생성자는 다음과 같은 순서로 작업을 수행합니다.

1. 생성자는 선언 순서대로 기본 클래스 및 멤버 생성자를 호출합니다.

1. 클래스가 가상 기본 클래스에서 파생된 경우 해당 클래스는 개체의 가상 기본 포인터를 초기화합니다.

1. 클래스가 가상 함수를 포함하거나 상속하는 경우 해당 클래스는 개체의 가상 함수 포인터를 초기화합니다. 가상 함수 포인터는 클래스의 가상 함수 테이블을 가리켜서 가상 함수 호출의 올바른 바인딩이 코딩되도록 합니다.

1. 이러한 포인터는 함수 본문의 모든 코드를 실행합니다.

다음 예제에서는 파생 클래스의 생성자에서 기본 클래스 및 멤버 생성자가 호출되는 순서를 보여 줍니다. 먼저 기본 생성자를 호출하고, 기본 클래스 멤버를 클래스 선언에 표시되는 순서대로 초기화한 다음 파생된 생성자를 호출합니다.

```cpp
#include <iostream>

using namespace std;

class Contained1 {
public:
    Contained1() { cout << "Contained1 ctor\n"; }
};

class Contained2 {
public:
    Contained2() { cout << "Contained2 ctor\n"; }
};

class Contained3 {
public:
    Contained3() { cout << "Contained3 ctor\n"; }
};

class BaseContainer {
public:
    BaseContainer() { cout << "BaseContainer ctor\n"; }
private:
    Contained1 c1;
    Contained2 c2;
};

class DerivedContainer : public BaseContainer {
public:
    DerivedContainer() : BaseContainer() { cout << "DerivedContainer ctor\n"; }
private:
    Contained3 c3;
};

int main() {
    DerivedContainer dc;
}
```

출력은 다음과 같습니다.

```Output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

파생 클래스 생성자는 항상 기본 클래스 생성자를 호출하므로, 완전히 생성된 기본 클래스를 통해서만 다른 작업을 수행할 수 있습니다. The base class constructors are called in order of derivation—for example, if `ClassA` is derived from `ClassB`, which is derived from `ClassC`, the `ClassC` constructor is called first, then the `ClassB` constructor, then the `ClassA` constructor.

기본 클래스에 기본 생성자가 없는 경우 파생 클래스 생성자에 기본 클래스 생성자 매개 변수를 제공해야 합니다.

```cpp
class Box {
public:
    Box(int width, int length, int height){
       m_width = width;
       m_length = length;
       m_height = height;
    }

private:
    int m_width;
    int m_length;
    int m_height;
};

class StorageBox : public Box {
public:
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){
        m_label = label;
    }
private:
    string m_label;
};

int main(){

    const string aLabel = "aLabel";
    StorageBox sb(1, 2, 3, aLabel);
}
```

생성자가 예외를 throw하는 경우 소멸 순서는 생성의 역순입니다.

1. 생성자 함수 본문의 코드가 해제됩니다.

1. 기본 클래스 및 멤버 개체가 선언의 역순으로 제거됩니다.

1. 생성자가 비대리자인 경우 제대로 생성된 기본 클래스 개체 및 멤버가 모두 소멸됩니다. 하지만 개체가 완전히 생성되지 않으므로 소멸자는 실행되지 않습니다.

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Constructors for classes that have multiple inheritance

클래스가 여러 기본 클래스에서 파생되는 경우 기본 클래스 생성자는 파생 클래스 선언에 나열된 순서대로 호출됩니다.

```cpp
#include <iostream>
using namespace std;

class BaseClass1 {
public:
    BaseClass1() { cout << "BaseClass1 ctor\n"; }
};
class BaseClass2 {
public:
    BaseClass2() { cout << "BaseClass2 ctor\n"; }
};
class BaseClass3 {
public:
    BaseClass3() { cout << "BaseClass3 ctor\n"; }
};
class DerivedClass : public BaseClass1,
                     public BaseClass2,
                     public BaseClass3
                     {
public:
    DerivedClass() { cout << "DerivedClass ctor\n"; }
};

int main() {
    DerivedClass dc;
}
```

다음과 같이 출력됩니다.

```Output
BaseClass1 ctor
BaseClass2 ctor
BaseClass3 ctor
DerivedClass ctor
```

## <a name="delegating_constructors"></a> Delegating constructors

A *delegating constructor* calls a different constructor in the same class to do some of the work of initialization. This is useful when you have multiple constructors that all have to perform similar work. You can write the main logic in one constructor and invoke it from others. In the following trivial example, Box(int) delegates its work to Box(int,int,int):

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    Box(int i) :  Box(i, i, i);  // delegating constructor
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
    //... rest of class as before
};
```

생성자에 의해 만들어지는 개체는 생성자가 완료되는 즉시 완전하게 초기화됩니다. For more information, see [Delegating Constructors](../cpp/delegating-constructors.md).

## <a name="inheriting_constructors"></a> Inheriting constructors (C++11)

A derived class can inherit the constructors from a direct base class by using a **using** declaration as shown in the following example:

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    Base() { cout << "Base()" << endl; }
    Base(const Base& other) { cout << "Base(Base&)" << endl; }
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }

private:
    int num;
    char letter;
};

class Derived : Base
{
public:
    // Inherit all constructors from Base
    using Base::Base;

private:
    // Can't initialize newMember from Base constructors.
    int newMember{ 0 };
};

int main()
{
    cout << "Derived d1(5) calls: ";
    Derived d1(5);
    cout << "Derived d1('c') calls: ";
    Derived d2('c');
    cout << "Derived d3 = d2 calls: " ;
    Derived d3 = d2;
    cout << "Derived d4 calls: ";
    Derived d4;
}

/* Output:
Derived d1(5) calls: Base(int)
Derived d1('c') calls: Base(char)
Derived d3 = d2 calls: Base(Base&)
Derived d4 calls: Base()*/
```

::: moniker range=">=vs-2017"

**Visual Studio 2017 and later**: The **using** statement in **/std:c++17** mode brings into scope all constructors from the base class except those that have an identical signature to constructors in the derived class. 일반적으로 파생 클래스에서 새 데이터 멤버나 생성자를 선언하지 않는 경우 상속 생성자를 사용하는 것이 가장 좋습니다. See also [Improvements in Visual Studio 2017 version 15.7](https://docs.microsoft.com/cpp/overview/cpp-conformance-improvements?view=vs-2017#improvements_157).

::: moniker-end

클래스 템플릿은 해당 형식이 기본 클래스를 지정하는 경우 형식 인수에서 모든 생성자를 상속할 수 있습니다.

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};
```

파생 클래스는 다중 기본 클래스에 동일한 서명을 사용하는 생성자가 있는 경우 해당 다중 기본 클래스에서 상속할 수 없습니다.

## <a name="constructors_in_composite_classes"></a> Constructors and composite classes

Classes that contain class-type members are known as *composite classes*. 복합 클래스의 클래스 형식 멤버를 만들 때 생성자가 클래스의 자체 생성자보다 먼저 호출됩니다. 포함된 클래스에 기본 생성자가 없는 경우 복합 클래스의 생성자에서 초기화 목록을 사용해야 합니다. 이전 `StorageBox` 예제에서 `m_label` 멤버 변수의 형식을 새 `Label` 클래스로 변경할 경우 기본 클래스 생성자를 호출하고 `m_label` 생성자에서 `StorageBox` 변수를 초기화해야 합니다.

```cpp
class Label {
public:
    Label(const string& name, const string& address) { m_name = name; m_address = address; }
    string m_name;
    string m_address;
};

class StorageBox : public Box {
public:
    StorageBox(int width, int length, int height, Label label)
        : Box(width, length, height), m_label(label){}
private:
    Label m_label;
};

int main(){
// passing a named Label
    Label label1{ "some_name", "some_address" };
    StorageBox sb1(1, 2, 3, label1);

    // passing a temporary label
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });

    // passing a temporary label as an initializer list
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});
}
```

## <a name="in-this-section"></a>이 섹션의 내용

- [Copy constructors and copy assignment operators](copy-constructors-and-copy-assignment-operators-cpp.md)
- [Move constructors and move assignment operators](move-constructors-and-move-assignment-operators-cpp.md)
- [Delegating constructors](delegating-constructors.md)

## <a name="see-also"></a>참조

[Classes and structs](classes-and-structs-cpp.md)
