---
title: 생성자 (C++)
ms.date: 04/06/2018
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: a45cee1abd9351a8fef56769706fe8944a7965b8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779104"
---
# <a name="constructors-c"></a>생성자 (C++)

클래스 멤버가 초기화 되는 방법을 사용자 지정 또는 함수를 호출할 클래스의 개체를 만들 때 정의 된 *생성자*합니다. 생성자는 클래스와 같은 이름을 사용하며 반환 값이 없습니다. 다양 한 방법으로 초기화를 사용자 지정 하는 데 필요한 만큼 오버 로드 된 생성자를 정의할 수 있습니다. 일반적으로 생성자에 public 액세스 가능성이 클래스 정의 또는 상속 계층 구조 외부 코드 클래스의 개체를 만들 수 있도록 합니다. 으로 생성자를 선언할 수도 있습니다 하지만 **보호** 하거나 **개인**합니다.

생성자는 멤버 init 목록을 걸릴 필요에 따라 수 있습니다. 이것이 생성자 본문의 값을 할당 하는 보다 클래스 멤버를 초기화 하는 보다 효율적인 방법입니다. 다음 예제에서는 클래스를 보여 줍니다. `Box` 3 개 생성자 오버 로드 합니다. 마지막 두 멤버 초기화 목록을 사용 하 여:

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

클래스의 인스턴스를 선언 하는 경우 컴파일러를 호출 하는 생성자 오버 로드 확인 규칙에 따라 선택 합니다.

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

- 생성자로 선언할 수 있습니다 **인라인**, [명시적](#explicit_constructors)를 **friend** 하거나 [constexpr](#constexpr_constructors)합니다.
- 생성자로 선언 된 개체를 초기화할 수 **상수**를 **volatile** 또는 **const volatile**합니다. 개체가 됩니다 **const** 생성자를 완료 합니다.
- 구현 파일에서 생성자를 정의 하려면 이름을 정규화 된 다른 멤버 함수와 마찬가지로: `Box::Box(){...}`합니다.

## <a name="member_init_list"></a> 멤버 이니셜라이저 목록

생성자는 멤버 이니셜라이저 목록 생성자 본문의 실행 하기 전에 클래스 멤버를 초기화 하는 경우 필요에 따라 수 있습니다. (멤버 이니셜라이저 목록을 동일 하지는 *이니셜라이저 목록* 형식의 [std:: initializer_list\<T >](../standard-library/initializer-list-class.md).)

직접 멤버 초기화 하므로 생성자의 본문에 값 할당을 통해 멤버 이니셜라이저 목록을 사용 하는 것이 좋습니다. 다음 예제에서를 보여 줍니다 멤버 이니셜라이저 목록이 모든 합니다 **identifier(argument)** 콜론 뒤 식:

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

식별자를 클래스 멤버로; 나타내야 합니다. 인수의 값으로 초기화 됩니다. 인수는 함수 호출을 생성자 매개 변수 중 하나일 수 있습니다 또는 [std:: initializer_list\<T >](../standard-library/initializer-list-class.md)합니다.

**const** 멤버 및 멤버 참조 형식의 멤버 이니셜라이저 목록에서 초기화 되어야 합니다.

기본 클래스의 파생된 생성자는 실행 전에 완전히 초기화 되도록 이니셜라이저 목록에서 매개 변수가 있는 기본 클래스 생성자에 대 한 호출을 이루어져야 합니다.

## <a name="default_constructors"></a> 기본 생성자

*기본 생성자* 일반적으로 매개 변수가 없는 없지만 기본값이 있는 매개 변수를 가질 수 있습니다.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

기본 생성자가 중 하나는 [특수 멤버 함수](special-member-functions.md)합니다. 컴파일러에서 암시적 제공 생성자 없음 클래스에서 선언 하는 경우 **인라인** 기본 생성자입니다.

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

암시적 기본 생성자를 사용 하는 경우 수 이전 예제와 같이 클래스 정의에서 멤버를 초기화 해야 합니다. 이러한 이니셜라이저 없이 멤버는 초기화 되지 않은 및 Volume() 호출 가비지 값을 생성 합니다. 일반적으로 것 암시적 기본 생성자를 사용 하지 않고도 하는 경우에이 방식으로 멤버를 초기화 하는 것이 좋습니다.

컴파일러는 암시적 기본 생성자로 정의 하 여 생성에서 방지할 수 있습니다 [삭제](#explicitly_defaulted_and_deleted_constructors):

```cpp
    // Default constructor
    Box() = delete;
```

모든 클래스 멤버에 기본 형식이 아닌 경우 삭제 된 것으로 컴파일러에서 생성 된 기본 생성자를 정의 합니다. 예를 들어, 기본 생성자 및 소멸자에 액세스할 수 있는 클래스 형식의 모든 멤버 및 해당 클래스 형식 멤버에 있어야 합니다. 참조의 모든 데이터 멤버 형식으로으로 **const** 멤버가 기본 멤버 이니셜라이저 있어야 합니다.

컴파일러에서 생성 된 기본 생성자를 호출 하 고 괄호를 사용 하려고 하는 경우 경고가 발생 합니다.

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

이는 가장 까다로운 구문 분석 문제의 한 예입니다. 예제 식을 함수 선언 또는 기본 생성자 호출로 해석할 수 있고 C++ 파서에서는 선언을 다른 항목보다 우선하므로 식이 함수 선언으로 처리됩니다. 자세한 내용은 [가장 까다로운 구문 분석](http://en.wikipedia.org/wiki/Most_vexing_parse)합니다.

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

그러나 상자 개체의 배열을 초기화할 이니셜라이저 목록 집합을 사용할 수 있습니다.

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

자세한 내용은 [이니셜라이저](initializers.md)합니다.

## <a name="copy_and_move_constructors"></a> 복사 생성자

A *복사 생성자* 동일한 유형의 개체에서 멤버 값을 복사 하 여 개체를 초기화 합니다. 클래스 멤버는 스칼라 값과 같은 모든 단순 형식에 컴파일러 생성 복사 생성자가 충분 하 고 필요가 없습니다 정의를 사용자 고유의 합니다. 클래스에 더 복잡 한 초기화가 필요한 경우 사용자 지정 복사 생성자를 구현 해야 합니다. 예를 들어, 클래스 멤버에 대 한 포인터 이면 다음 해야 새 메모리를 할당 하 고 서로의 가리키는 개체에서 값을 복사 하려면 복사 생성자를 정의 합니다. 컴파일러 생성 복사 생성자는 단순히 계속 새 포인터는 다른 메모리 위치를 가리키도록 포인터를 복사 합니다.

복사 생성자를 이러한 서명 중 하나가 있어야 있습니다.

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

복사 생성자를 정의 하는 경우 복사 할당 연산자 (=)를 정의 해야 합니다. 자세한 내용은 [할당](assignment.md) 하 고 [복사 생성자 및 복사 할당 연산자](copy-constructors-and-copy-assignment-operators-cpp.md)합니다.

삭제 된 것으로 복사 생성자를 정의 하 여 복사 작업에서 개체를 방지할 수 있습니다.

```cpp
    Box (const Box& other) = delete;
```

개체를 복사 하는 동안 오류가 *C2280: 삭제 된 함수를 참조 하려고*합니다.

## <a name="move_constructors"></a> 이동 생성자

A *이동 생성자* 는 원래 데이터를 복사 하지 않고 기존 개체의 데이터 소유권을 새 변수에 이동 하는 특수 멤버 함수입니다. 첫 번째 매개 변수로 rvalue 참조를 사용 하 고 추가 매개 변수는 기본값이 있어야 합니다. 이동 생성자는 큰 개체 주위를 전달할 때 프로그램의 효율성을 길어질 수 있습니다. 이동 생성자는 rvalue 참조 첫 번째 매개 변수로 사용 합니다. 다른 매개 변수에 기본값이 있어야 합니다.

```cpp
Box(Box&& other);
```

컴파일러 선택 이동 생성자 개체가 소멸 되려고 할 이며 더 이상 필요로 하는 동일한 형식의 다른 개체에 의해 초기화 되는 특정 상황에서는 리소스입니다. 다음 예에서는 이동 생성자 오버 로드 확인에서 선택 될 때 한 가지 경우를 보여 줍니다. 변수의 *상자* get_Box() 반환한는 *xvalue* (만료 값) 범위를 벗어나는 약입니다. 이 예제에 대 한 동기 부여를 제공 하려면 지정 보겠습니다 상자 큰 벡터의 해당 콘텐츠를 나타내는 문자열입니다. 벡터 및 해당 문자열을 복사 하는 대신 이동 생성자 "도용"이 만료 값 "box"에서 벡터는 이제 새 개체에 속해 있도록 합니다. 에 대 한 호출 `std::move` 때문에 필요한 것은 둘 다 `vector` 및 `string` 클래스 자체 이동 생성자를 구현 합니다.

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

클래스는 이동 생성자를 정의 하지 않으면, 없는 사용자가 선언한 복사 생성자, 복사 할당 연산자, 이동 할당 연산자 또는 소멸자가 없는 경우 컴파일러는 암시적 하나를 생성 합니다. 명시적 또는 암시적 이동 생성자가 없습니다.이 정의 되어 있으면 작업 그렇지 않은 경우 이동 생성자를 사용 하는 대신 복사 생성자를 사용 합니다. 클래스는 이동 생성자 또는 이동 할당 연산자를 선언 하는 경우 삭제 된 것으로 암시적으로 선언 된 복사 생성자가 정의 됩니다.

암시적으로 선언 된 이동 생성자를 않는 클래스 형식의 모든 멤버에 없는 소멸자 또는 컴파일러 이동 작업에 사용할 생성자를 결정할 수 없는 경우 삭제 된 것으로 정의 됩니다.

비 trivial 이동 생성자 작성 하는 방법에 대 한 자세한 내용은 참조 하세요. [이동 생성자 및 이동 할당 연산자 (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)합니다.

## <a name="explicitly_defaulted_and_deleted_constructors"></a> 명시적으로 기본 설정 및 삭제 된 생성자

명시적으로 할 수 있습니다 *기본* 복사 생성자, 기본 생성자, 이동 생성자, 복사 할당 연산자, 대입 연산자 및 소멸자를 이동 합니다. 명시적으로 할 수 있습니다 *삭제* 모든 특수 멤버 함수입니다.

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

자세한 내용은 [명시적으로 기본 설정 및 삭제 된 함수](../cpp/explicitly-defaulted-and-deleted-functions.md)합니다.

## <a name="constexpr_constructors"></a> constexpr 생성자

생성자로 선언할 수 있습니다 [constexpr](constexpr-cpp.md) 경우

- 기본적으로 선언 하거나 그렇지 않으면에 대 한 모든 조건을 충족 하는 것 [constexpr 함수](constexpr-cpp.md#constexpr_functions) 일반적입니다.
- 이 클래스에는 가상 기본 클래스가 없고;
- 각 매개 변수를 [리터럴 형식](trivial-standard-layout-and-pod-types.md#literal_types);
- 본문은 함수 try-블록일; 아닙니다.
- 모든 비정적 데이터 멤버 및 기본 클래스의 하위 개체 초기화 됩니다.
- 클래스 variant 멤버가 있는 공용 구조체 (a), (b) 익명 공용 구조체에 공용 구조체 멤버 중 하나에 초기화 됩니다.
- 클래스 형식의 모든 비정적 데이터 멤버 및 기본 클래스의 모든 하위 개체에 constexpr 생성자

## <a name="init_list_constructors"></a> 이니셜라이저 목록 생성자

생성자를 사용 하는 경우는 [std:: initializer_list\<T\> ](../standard-library/initializer-list-class.md) 클래스 때 해당 생성자 오버 로드 확인에 선택 됩니다 대로 해당 매개 변수 및 기타 매개 변수는 기본 인수가 포함, 직접 초기화를 통해 인스턴스화됩니다. 수락할 수 있는 모든 멤버를 초기화 하는 initializer_list를 사용할 수 있습니다. 예를 들어, 앞에서 설명한 상자 클래스에는 `std::vector<string>` 멤버 `m_contents`합니다. 다음과 같은 생성자를 제공할 수 있습니다.

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

하 고 그런 다음 다음과 같이 상자 개체를 만듭니다.

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit_constructors"></a> 명시적 생성자

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

경우에 따라 이러한 변환은 유용할 수 있지만 코드에서 미세하지만 심각한 오류를 발생시키는 경우가 더 자주 있습니다. 일반적으로 사용 해야 합니다 **명시적** 생성자 (및 사용자 정의 연산자) 이러한 종류의 암시적 형식 변환 방지 하려면 키워드:

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

생성자가 명시적인 경우 `ShippingOrder so(42, 10.8);` 줄에서 컴파일 오류가 발생합니다.  자세한 내용은 [사용자 정의 형식 변환](../cpp/user-defined-type-conversions-cpp.md)합니다.

## <a name="order_of_construction"></a> 생성 순서

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

파생 클래스 생성자는 항상 기본 클래스 생성자를 호출하므로, 완전히 생성된 기본 클래스를 통해서만 다른 작업을 수행할 수 있습니다. 기본 클래스 생성자는 파생 순서 대로 호출 됩니다-예를 들어 경우 `ClassA` 에서 파생 됩니다 `ClassB`에서 파생 된 `ClassC`의 `ClassC` 생성자가 먼저 호출 하면 `ClassB` 생성자는 `ClassA` 생성자입니다.

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

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>다중 상속을 포함 하는 클래스 생성자

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

## <a name="virtual_functions_in_constructors"></a> 생성자의 가상 함수

생성자에서 가상 함수를 호출할 경우 주의하시기 바랍니다. 기본 클래스 생성자가 파생 클래스 생성자보다 항상 먼저 호출되므로, 기본 생성자에서 호출되는 함수는 파생 클래스 버전이 아닌 기본 클래스 버전입니다. 다음 예제에서 `DerivedClass`를 생성하면 `BaseClass` 생성자에 의해 `print_it()`의 `DerivedClass` 구현이 실행되기 이전에 `DerivedClass`의 `print_it()` 구현이 실행됩니다.

```cpp
#include <iostream>
using namespace std;

class BaseClass{
public:
    BaseClass(){
        print_it();
    }
    virtual void print_it() {
        cout << "BaseClass print_it" << endl;
    }
};

class DerivedClass : public BaseClass {
public:
    DerivedClass() {
        print_it();
    }
    virtual void print_it(){
        cout << "Derived Class print_it" << endl;
    }
};

int main() {

    DerivedClass dc;
}
```

출력은 다음과 같습니다.

```Output
BaseClass print_it
Derived Class print_it
```

## <a name="delegating_constructors"></a> 위임 생성자

A *위임 생성자* 초기화 작업 중 일부를 수행 하려면 같은 클래스의 다른 생성자를 호출 합니다. 이 비슷한 작업을 수행할 수 있는 모든 생성자를 여러 개 있는 경우에 유용 합니다. 한 생성자에서 기본 논리를 작성할 수 있으며 다른 사용자 로부터 호출할 수 있습니다. 다음 간단한 예제에서는 Box(int) Box(int,int,int) 하기를 위임 합니다.

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

생성자에 의해 만들어지는 개체는 생성자가 완료되는 즉시 완전하게 초기화됩니다. 자세한 내용은 [균일 초기화 및 생성자 위임](../cpp/uniform-initialization-and-delegating-constructors.md)합니다.

## <a name="inheriting_constructors"></a> 상속 생성자 (C + + 11)

파생된 클래스를 사용 하 여 직접 기본 클래스에서 생성자를 상속할 수를 **를 사용 하 여** 다음 예제에서와 같이 선언 합니다.

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

**Visual Studio 2017 버전 15.7 이상:** 합니다 **를 사용 하 여** 문에서 **/std: c + + 17** 모드 제외 생성자와 동일한 서명이 파생된 클래스에서 기본 클래스에서 모든 생성자를 범위로 가져옵니다. 일반적으로 파생 클래스에서 새 데이터 멤버나 생성자를 선언하지 않는 경우 상속 생성자를 사용하는 것이 가장 좋습니다. 참고 항목 [Visual Studio 2017 버전 15.7의에서 개선 사항](../overview/cpp-conformance-improvements.md#improvements_157)합니다.

클래스 템플릿은 해당 형식이 기본 클래스를 지정하는 경우 형식 인수에서 모든 생성자를 상속할 수 있습니다.

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};
```

파생 클래스는 다중 기본 클래스에 동일한 서명을 사용하는 생성자가 있는 경우 해당 다중 기본 클래스에서 상속할 수 없습니다.

## <a name="constructors_in_composite_classes"></a> 생성자 및 복합 클래스

클래스 형식 멤버를 포함 하는 클래스 라고 *복합 클래스*합니다. 복합 클래스의 클래스 형식 멤버를 만들 때 생성자가 클래스의 자체 생성자보다 먼저 호출됩니다. 포함된 클래스에 기본 생성자가 없는 경우 복합 클래스의 생성자에서 초기화 목록을 사용해야 합니다. 이전 `StorageBox` 예제에서 `m_label` 멤버 변수의 형식을 새 `Label` 클래스로 변경할 경우 기본 클래스 생성자를 호출하고 `m_label` 생성자에서 `StorageBox` 변수를 초기화해야 합니다.

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
