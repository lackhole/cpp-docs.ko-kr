---
title: 생성자 위임 (C++)
description: 에서 C++ 위임 생성자를 사용 하 여 다른 생성자를 호출 하 고 코드 반복을 줄입니다.
ms.date: 11/19/2019
ms.openlocfilehash: 533cdfbeb882f3770cc554b0633611a4ffc2cfbd
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74250699"
---
# <a name="delegating-constructors"></a>위임 생성자

많은 클래스에는 비슷한 작업을 수행 하는 여러 생성자 (예: 매개 변수 유효성 검사)가 있습니다.

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

모든 유효성 검사를 수행 하는 함수를 추가 하 여 반복적인 코드를 줄일 수 있지만, 한 생성자가 일부 작업을 다른 생성자에 위임할 수 있는 경우 `class_c` 코드를 이해 하 고 유지 관리 하기가 더 쉽습니다. 위임 생성자를 추가 하려면 `constructor (. . .) : constructor (. . .)` 구문을 사용 합니다.

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

이전 예제를 단계별로 진행 하면서 생성자는 먼저 `class_c(int)`를 호출 하는 생성자 `class_c(int, int)`를 호출 `class_c(int, int, int)` 합니다. 각 생성자는 다른 생성자에서 수행 되지 않는 작업만 수행 합니다.

호출 되는 첫 번째 생성자는 개체를 초기화 하 여 해당 지점에서 모든 멤버가 초기화 되도록 합니다. 다음과 같이 다른 생성자에 위임 하는 생성자에서 멤버를 초기화할 수 없습니다.

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

다음 예제에서는 비정적 데이터 멤버 이니셜라이저를 사용 하는 방법을 보여 줍니다. 생성자가 지정 된 데이터 멤버를 초기화 하는 경우에도 멤버 이니셜라이저가 재정의 됩니다.

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

생성자 위임 구문은 실수로 생성자 재귀를 만들도록 방지 하지 않습니다. Constructor1는 Constructor1를 호출 하는 Constructor2를 호출 하 고 스택 오버플로가 발생할 때까지 오류가 throw 되지 않습니다. 주기를 방지 하는 것은 사용자의 책임입니다.

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
