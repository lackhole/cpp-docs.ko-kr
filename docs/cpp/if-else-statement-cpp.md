---
title: if-else 문 (C++)
ms.date: 07/17/2017
f1_keywords:
- else_cpp
- if_cpp
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
ms.openlocfilehash: 16aa65ab64d9fd855ae3306da88f8eb14eec759c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183650"
---
# <a name="if-else-statement-c"></a>if-else 문 (C++)

조건부 분기를 제어 합니다. 문에서 *경우 블록* 실행 된 경우에 합니다 *if 식은* 0이 아닌 값 (또는 TRUE)으로 계산 되. 경우 값 *식* 는 0이 아니면 *문 1* 블록에 있는 다른 문이 실행 되 고 다른-블록에 있는 경우를 건너뜁니다. 경우 값 *식* 가 0 이면 다음 경우 블록을 생략 되 고 다른-블록이 있으면 실행 됩니다. 0이 아닌 값으로 계산 되는 식은

- TRUE
- null이 아닌 포인터
- 0이 아닌 산술 값, 또는
- 산술, 부울 및 포인터를 변환 하는 명확한 변환을 정의 하는 클래스 형식을 입력 합니다. (변환에 대 한 자세한 내용은 [표준 변환](../cpp/standard-conversions.md).)

## <a name="syntax"></a>구문

```cpp
if ( expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )
{
   statement1;
   ...
}
else  // optional
{
   statement2;
   ...
}

// Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
}
```

## <a name="example"></a>예제

```cpp
// if_else_statement.cpp
#include <iostream>

using namespace std;

class C
{
    public:
    void do_something(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

    // no else statement
    if (x == 10)
    {
        x = 0;
    }

    C* c;
    init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```

## <a name="if_with_init"></a> 경우는 이니셜라이저를 사용 하 여 문을

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)): **경우** 문에 선언 하 고 명명 된 변수를 초기화 하는 식을 포함 될 수도 있습니다. 변수의 경우 블록의 범위 안에서 필요한 경우 if 문이 이러한 형식의 사용 합니다.

## <a name="example"></a>예제

```cpp
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>

using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }

    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }
}
```

모든 양식에서 합니다 **하는 경우** 문을 *식*, 모든 파생 작업이 계산 되는 구조를 제외한 모든 값을 사용할 수 있는 합니다. 컨트롤에서 전달 합니다 **경우** 문에서 프로그램의 다음 문으로 하지 않는 한 중 하나는 *문을*s에는 [중단](../cpp/break-statement-cpp.md), [계속](../cpp/continue-statement-cpp.md), 또는 [goto](../cpp/goto-statement-cpp.md)합니다.

**다른** 절을 `if...else` 문은 가장 가까운 연관 된 이전 **하는 경우** 해당 없는 동일한 범위에서 문을 **다른** 문입니다.

## <a name="a-nameifconstexpr-if-constexpr-statements"></a><a name="if_constexpr"> 경우 constexpr 문

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)): 함수 템플릿을 사용할 수 있습니다는 **경우 constexpr** 문을 여러 함수 오버 로드에 의존 하지 않고 컴파일 타임 분기 결정을 내릴 수 있습니다. 예를 들어, 해당 핸들 매개 변수 압축 해제 (0-매개 변수 오버 로드가 없는 필요) 단일 함수를 작성할 수 있습니다.

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
    // handle t
    do_something(t);

    // handle r conditionally
    if constexpr (sizeof...(r))
    {
        f(r...);
    }
    else
    {
        g(r...);
    }
}
```

## <a name="see-also"></a>참고자료

[선택 문(C++)](../cpp/selection-statements-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[switch 문(C++)](../cpp/switch-statement-cpp.md)