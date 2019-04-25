---
title: 헤더 파일 (C++)
ms.date: 04/20/2018
helpviewer_keywords:
- header files [C++]
ms.openlocfilehash: ea163f4d47022d886e40a09c47c252ffa186aee0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153610"
---
# <a name="header-files-c"></a>헤더 파일 (C++)

변수, 함수, 클래스 등 프로그램 요소의 이름은 사용할 수 있으려면 먼저 선언 되어야 합니다. 예를 들어 입력할 수 없으며 방금 `x = 42` 첫 번째 'x'를 선언 하지 않고 합니다.

```cpp
int x; // declaration
x = 42; // use x
```

선언 하는지 여부를 컴파일러에 지시 되는 **int**, **double**, **함수**, **클래스** 또는 일부 다른 작업입니다.  또한 각 이름 선언 되어야 합니다 (직접 또는 간접적으로)가 사용 되는 모든.cpp 파일에서. 프로그램을 컴파일할 때 각.cpp 파일 컴파일될 하지 독립적으로 컴파일 단위입니다. 컴파일러는 어떤 이름이 다른 컴파일 단위에서 선언 된 알지 못합니다. 즉, 클래스 또는 함수 또는 전역 변수를 정의 하는 경우 사용 하는 각 추가.cpp 파일에서 해당 항목의 선언을 제공 해야 합니다. 모든 파일을 각 선언 정확 하 게 일치 이어야 합니다. 약간의 불일치를 링커 라는 하나의 프로그램으로 모든 컴파일 단위를 병합 하려고 할 때 오류 또는 의도 하지 않은 동작을 하면 합니다.

오류에 대 한 가능성을 최소화 하려면 C++ 에서 사용 하 여 규칙을 채택 *헤더 파일* 선언을 포함 합니다. 선언이 헤더 파일에서 확인을 사용 하 여를 #include 지시문 모든.cpp 파일에서 또는 다른 헤더 파일에 해당 선언이 필요 합니다. # 컴파일 전에.cpp 파일에 직접 지시문 삽입 헤더 파일의 복사본을 include 합니다.

## <a name="example"></a>예제

다음 예제에서는 클래스를 선언 하 고는 다른 소스 파일에 사용 하는 일반적인 방법은 보여 줍니다. 헤더 파일을 사용 하 여 먼저 `my_class.h`합니다. 클래스 정의 포함 하지만 정의 불완전 합니다. 멤버 함수 `do_something` 정의 되어 있지 않습니다.

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

다음으로 (일반적으로 사용 하 여.cpp 또는 유사한 확장) 구현 파일을 만듭니다. 파일 my_class.cpp를 호출 하 고 멤버 선언에 대 한 정의 제공 합니다. 추가 `#include` 삽입 my_class 선언 하기 위해 "my_class.h" 파일에 대 한 지시문이 시점에서.cpp 파일을 고 포함 `<iostream>` 의 선언에 가져오려고 `std::cout`합니다. 따옴표는 소스 파일과 동일한 디렉터리에 대 한 헤더 파일에 대 한 사용 및 꺾쇠 괄호는 표준 라이브러리 헤더에 사용 되는 note 합니다. 또한 여러 표준 라이브러리 헤더 없는.h 또는 다른 파일 확장명입니다.

구현 파일에서는 필요에 따라 사용할 수는 **를 사용 하 여** 문을 사용 하 여 "my_class" 또는 "cout"의 모든 멘 션 한 정하는 것을 방지 하려면 "n::" 또는 "std::".  넣지 마세요 **를 사용 하 여** 헤더 파일의 문을!

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

사용 하 여 이제 `my_class` 다른.cpp 파일에 있습니다. 에서는 # 컴파일러는 선언에서 있도록 헤더 파일 include 합니다. 모든 컴파일러 요구 알아야은 해당 my_class 라는 public 멤버 함수가 포함 된 클래스 `do_something()`합니다.

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

컴파일러는 각.cpp 파일을.obj 파일로 컴파일 완료 되 면.obj 파일을 링커에 전달 합니다. 찾으면 my_class;에 대 한 정의 정확히 하나만 링커에서 개체 파일을 병합 하는 경우 my_class.cpp에 대 한 생성 된.obj 파일에 하 고 빌드 성공 합니다.

## <a name="include-guards"></a>가드를 포함 합니다.

일반적으로 헤더 파일에는 *include 가드* 또는 `#pragma once` 지시문을 단일.cpp 파일에 여러 번 없습니다 삽입할 수 있는지 확인 합니다.

```cpp
// my_class.h
#ifndef MY_CLASS_H // include guard
#define MY_CLASS_H

namespace N
{
    class my_class
    {
    public:
        void do_something();
    };
}

#endif /* MY_CLASS_H */
```

## <a name="what-to-put-in-a-header-file"></a>헤더 파일에 삽입할 항목에

헤더 파일은 여러 파일에 의해 잠재적으로 포함 될 수 있습니다, 되므로 동일한 이름의 여러 정의 생성할 수 있습니다는 정의 포함할 수 없습니다. 다음 허용 되지 않거나 매우 바람직하지 것으로 간주 됩니다.

- 네임 스페이스 또는 전역 범위에서 기본 제공 형식 정의
- 인라인이 아닌 함수 정의
- 비 const 변수 정의
- 집계 정의
- 명명되지 않은 네임스페이스
- using 지시문

사용 합니다 **를 사용 하 여** 지시문 오류가 반드시 발생 하지는 않지만 네임 스페이스를 범위로 직접 또는 간접적으로 해당 헤더를 포함 하는 모든.cpp 파일에서 제공 하는 것 때문에 문제가 발생할 수 있습니다.

## <a name="sample-header-file"></a>샘플 헤더 파일

다음 예제에서는 선언 및 정의 헤더 파일에 허용 되는 다양 한 종류를 보여 줍니다.

```cpp
#pragma once
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{
    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };

    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif

    class my_class   // regular class definition,
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;
}
```