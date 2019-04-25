---
title: 균일 초기화 및 생성자 위임
ms.date: 11/04/2016
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
ms.openlocfilehash: 5c5cb6421d9c8ce20f0c5e24de986ee50d9b2238
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162111"
---
# <a name="uniform-initialization-and-delegating-constructors"></a>균일 초기화 및 생성자 위임

최신 C++에서 사용할 수 있습니다 *중괄호 초기화* 등호 기호 없이 모든 형식에 대 한 합니다. 또한 비슷한 작업을 수행 하는 생성자를 여러 개 있는 경우 코드를 단순화 하기 위해 위임 생성자를 사용할 수 있습니다.

## <a name="brace-initialization"></a>중괄호 초기화

모든 클래스, 구조체 또는 공용 구조체에 대 한 중괄호 초기화를 사용할 수 있습니다. 형식에 기본 생성자를 암시적 또는 명시적으로 선언 하는 경우 (빈 중괄호)와 기본 중괄호 초기화를 사용할 수 있습니다. 예를 들어, 기본값 및 기본값이 아닌 중괄호 초기화를 사용 하 여 다음 클래스를 초기화할 수 있습니다.

```cpp
#include <string>
using namespace std;

class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}
double m_double;
string m_string;
};

int main()
{
    class_a c1{};
    class_a c1_1;

    class_a c2{ "ww" };
    class_a c2_1("xx");

    // order of parameters is the same as the constructor
    class_a c3{ "yy", 4.4 };
    class_a c3_1("zz", 5.5);
}
```

클래스 멤버 중괄호 이니셜라이저에 나타나는 순서는 해당 매개 변수를 생성자에 나타나는 순서를 멤버 선언 되는 순서가 아니라 클래스의 기본이 아닌 생성자가 하는 경우 (마찬가지로 `class_a` 에 이전 예제)입니다. 그렇지 않으면 형식에 선언 된 생성자가 없는 경우 중괄호 이니셜라이저에 나타나는 멤버의 순서가는 선언 된 순서와 동일 이 경우 원하는 대로 모든 멤버를 건너뛸 수 없습니다 public 멤버의 만큼 초기화할 수 있습니다. 다음 예제에서는 선언 된 생성자가 없는 경우 중괄호 초기화에 사용 되는 순서를 보여 줍니다.

```cpp
class class_d {
public:
    float m_float;
    string m_string;
    wchar_t m_char;
};

int main()
{
    class_d d1{};
    class_d d1{ 4.5 };
    class_d d2{ 4.5, "string" };
    class_d d3{ 4.5, "string", 'c' };

    class_d d4{ "string", 'c' }; // compiler error
    class_d d5("string", 'c', 2.0 }; // compiler error
}
```

기본 생성자를 명시적으로 선언 하지만 삭제 된 것으로 표시 하는 경우에 기본 중괄호 초기화를 사용할 수 없습니다.

```cpp
class class_f {
public:
    class_f() = delete;
    class_f(string x): m_string { x } {}
    string m_string;
};
int main()
{
    class_f cf{ "hello" };
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function
}
```

중괄호 초기화를 사용할 수 있습니다 아무 곳 이나 일반적으로 하듯이 초기화-예를 들어, 또는 함수 매개 변수 또는 반환 값으로는 **새** 키워드:

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

## <a name="initializerlist-constructors"></a>initializer_list 생성자

합니다 [initializer_list 클래스](../standard-library/initializer-list-class.md) 생성자에서 및 다른 컨텍스트에서 사용할 수 있는 지정 된 형식의 개체 목록을 나타냅니다. Initializer_list 중괄호 초기화를 사용 하 여 생성할 수 있습니다.

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
>  이 클래스를 사용 하려면 포함 해야 합니다 [ \<initializer_list >](../standard-library/initializer-list.md) 헤더입니다.

`initializer_list` 복사할 수 있습니다. 이 경우 새 그룹의 구성원은 원래 목록 멤버에 대 한 참조:

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

표준 라이브러리 컨테이너 클래스 및 `string`, `wstring`, 및 `regex`에 있는 `initializer_list` 생성자입니다. 다음 예제에서는 중괄호 이러한 생성자를 사용 하 여 초기화를 수행 하는 방법을 보여 줍니다.

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{'x', 'y', 'z'};
```

## <a name="delegating-constructors"></a>위임 생성자

많은 클래스는 비슷한 작업을 수행 하는 여러 생성자-예를 들어, 매개 변수 유효성 검사:

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c() {}
    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) {
        max = my_max > 0 ? my_max : 10;
        min = my_min > 0 && my_min < max ? my_min : 1;
        middle = my_middle < max && my_middle > min ? my_middle : 5;
    }
};
```

모든 유효성 검사에 대 한 코드를 수행 하는 함수를 추가 하 여 반복 되는 코드를 줄일 수 있습니다 `class_c` 이해 하 고 생성자가 하나 일부 다른 작업을 위임할 수 있습니다 하는 경우 유지 하는 것이 더 쉽습니다. 위임 생성자를 추가 하려면 사용 된 `constructor (. . .) : constructor (. . .)` 구문:

```cpp
class class_c {
public:
    int max;
    int min;
    int middle;

    class_c(int my_max) {
        max = my_max > 0 ? my_max : 10;
    }
    class_c(int my_max, int my_min) : class_c(my_max) {
        min = my_min > 0 && my_min < max ? my_min : 1;
    }
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){
        middle = my_middle < max && my_middle > min ? my_middle : 5;
}
};
int main() {

    class_c c1{ 1, 3, 2 };
}
```

앞의 예제를 단계별로 확인 하는 생성자 `class_c(int, int, int)` 생성자를 호출 하는 먼저 `class_c(int, int)`를 호출 하 `class_c(int)`합니다. 각 생성자에는 다른 생성자에 의해 수행 되지 않는 작업을 수행 합니다.

호출 되는 첫 번째 생성자는 모든 해당 멤버를 해당 지점에서 초기화 하는 개체를 초기화 합니다. 여기에 나와 있는 것 처럼 다른 생성자에 위임 하는 생성자 멤버 초기화를 수행할 수 없습니다.

```cpp
class class_a {
public:
    class_a() {}
    // member initialization here, no delegate
    class_a(string str) : m_string{ str } {}

    //can’t do member initialization here
    // error C3511: a call to a delegating constructor shall be the only member-initializer
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}

    // only member assignment
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string;
};
```

다음 예제에서는 비정적 데이터 멤버 이니셜라이저를 사용 하는 방법을 보여 줍니다. 생성자는 지정 된 데이터 멤버 초기화를 하는 경우 멤버 이니셜라이저 재정의 알 수 있습니다.

```cpp
class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }
    double m_double{ 1.0 };
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };
};

int main() {
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"
    int y = 4;
}
```

생성자 위임 구문 생성자 재귀 실수로 생성을 방지 하지-Constructor1 Constructor2 Constructor1를 호출 하는 호출-스택 오버플로가 발생 될 때까지 오류가 throw 됩니다. 것이 주기를 방지 해야 합니다.

```cpp
class class_f{
public:
    int max;
    int min;

    // don't do this
    class_f() : class_f(6, 3){ }
    class_f(int my_max, int my_min) : class_f() { }
};
```