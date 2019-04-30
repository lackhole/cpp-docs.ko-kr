---
title: 컴파일러 오류 C2065
ms.date: 09/01/2017
f1_keywords:
- C2065
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
ms.openlocfilehash: 3daf2cd532cd07225b822c80b46fc28274d4e2a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408617"
---
# <a name="compiler-error-c2065"></a>컴파일러 오류 C2065

> '*식별자*': 선언 되지 않은 식별자

컴파일러는 식별자에 대 한 선언을 찾을 수 없습니다. 이 오류에 대 한 많은 잠재적 원인이 있습니다. C2065의 가장 일반적인 원인은는 식별자를 선언 하지 않은, 철자가 잘못 된 식별자, 식별자 선언 된 위치 헤더 파일에 포함 되어 있지 않거나 식별자 범위 한정자를 예를 들어 누락 되었습니다 `cout` 대신 `std::cout`. 선언에 대 한 자세한 내용은 C++를 참조 하세요 [선언 및 정의 (C++)](../../cpp/declarations-and-definitions-cpp.md)합니다.

여기에 몇 가지 일반적인 문제 및 솔루션 보다 자세히 설명 합니다.

## <a name="the-identifier-is-undeclared"></a>식별자 선언 되지 않습니다.

식별자는 변수 또는 함수 이름의 경우 사용할 수 전에 선언 해야 합니다. 함수 선언 함수를 사용 하려면 먼저 해당 매개 변수의 형식을 포함 해야 합니다. 변수를 사용 하 여 선언 되 면 `auto`, 컴파일러는 해당 이니셜라이저에서 형식을 유추할 수 있어야 합니다.

식별자는 클래스 또는 구조체의 멤버 또는 네임 스페이스에 선언 된 경우 구조체, 클래스 또는 네임 스페이스 범위 외부에서 사용 하는 경우 클래스 또는 구조체 이름 또는 네임 스페이스 이름으로 한정 되어야 합니다. 또는 네임 스페이스 가져와야 하 여 범위를 `using` 같은 지시문 `using namespace std;`, 멤버 이름으로 범위로 가져와야 또는 `using` 선언 같은 `using std::string;`합니다. 그렇지 않으면 비 정규화 된 이름은 현재 범위에서 선언 되지 않은 식별자 간주 됩니다.

식별자가 사용자 정의 형식에 대 한 태그 예를 들어, 한 `class` 또는 `struct`, 사용할 수 있습니다 태그의 형식을 선언 해야 합니다. 예를 들어 선언 `struct SomeStruct { /*...*/ };` 변수를 선언 하기 전에 있어야 `SomeStruct myStruct;` 코드에서.

형식 식별자가 형식 별칭을 사용 하 여 선언 해야 합니다는 `using` 선언 또는 `typedef` 사용할 수 있습니다. 예를 들어 선언 해야 합니다 `using my_flags = std::ios_base::fmtflags;` 를 사용 하려면 먼저 `my_flags` 에 대 한 형식 별칭으로 `std::ios_base::fmtflags`입니다.

## <a name="example-misspelled-identifier"></a>예: 철자가 잘못 된 식별자

이 오류는 일반적으로 식별자 이름을 철자가 잘못 되었거나, 잘못 된 대문자 및 소문자 문자의 식별자를 사용 하는 경우에 발생 합니다. 선언에서 이름을 사용 하는 이름이 일치 해야 합니다.

```cpp
// C2065_spell.cpp
// compile with: cl /EHsc C2065_spell.cpp
#include <iostream>
using namespace std;
int main() {
    int someIdentifier = 42;
    cout << "Some Identifier: " << SomeIdentifier << endl;
    // C2065: 'SomeIdentifier': undeclared identifier
    // To fix, correct the spelling:
    // cout << "Some Identifier: " << someIdentifier << endl;
}
```

## <a name="example-use-an-unscoped-identifier"></a>예: 범위가 지정 되지 않은 식별자를 사용 합니다.

식별자를 제대로 범위가 지정 되지 않습니다 하는 경우이 오류가 발생할 수 있습니다. 사용 하는 경우 C2065 표시 되 면 `cout`,이 인해 발생 합니다. 때 C++ 표준 라이브러리 함수 및 연산자는 정규화 되지 않은 네임 스페이스에서 또는 하지 가져온 합니다 `std` 네임 스페이스를 사용 하 여 현재 범위에는 `using` 지시문, 컴파일러 찾을 수 없습니다. 이 문제를 해결 하려면 완전히 식별자 이름을 한정 하거나 사용 하 여 네임 스페이스를 지정 합니다 `using` 지시문입니다.

이 예제에서는 있으므로 컴파일되지 않습니다 `cout` 하 고 `endl` 에 정의 된는 `std` 네임 스페이스:

```cpp
// C2065_scope.cpp
// compile with: cl /EHsc C2065_scope.cpp
#include <iostream>
// using namespace std;   // Uncomment this line to fix

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead
    std::cout << "Hello" << std::endl;
}
```

내부에서 선언 된 식별자 `class`, `struct`, 또는 `enum class` 형식은 해당 범위 외부에서 사용 하는 경우 해당 바깥쪽 범위의 이름으로 정규화도 해야 합니다.

## <a name="example-precompiled-header-isnt-first"></a>예: 미리 컴파일된 헤더 첫 번째 없습니다.

와 같은 모든 전처리기 지시문을 추가한 경우이 오류가 발생할 수 있습니다 #include #define, 또는 #pragma, 전에 # 미리 컴파일된 헤더 파일 include 합니다. 소스 파일에 미리 컴파일된 헤더 파일을 사용 하는 경우 (즉, 사용 하 여 컴파일할 경우는 **/Yu** 컴파일러 옵션) 미리 컴파일된 헤더 파일을 전에 모든 전처리기 지시문을 무시 합니다.

이 예제에서는 있으므로 컴파일되지 않습니다 `cout` 하 고 `endl` 에 정의 된는 \<iostream > 헤더로 전에 미리 컴파일된 헤더 파일이 포함 되어 있으므로 무시 됩니다. 이 예제를 빌드하려면 모든 세 파일이 다음 만든 stdafx.cpp, 컴파일 C2065_pch.cpp 컴파일하십시오.

```cpp
// stdafx.h
#include <stdio.h>
```

```cpp
// stdafx.cpp
// Compile by using: cl /EHsc /W4 /c /Ycstdafx.h stdafx.cpp
#include <stdafx.h>
```

```cpp
// C2065_pch.cpp
// compile with: cl /EHsc /W4 /Yustdafx.h C2065_pch.cpp
#include <iostream>
#include "stdafx.h"
using namespace std;

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
}
```

이 문제를 해결 하려면 추가 #include \<iostream >는 미리 컴파일된 헤더 파일에 소스 파일에 포함 되어 미리 컴파일된 헤더 파일 후 이동 합니다.

## <a name="example-missing-header-file"></a>예: 헤더 파일이 없습니다.

식별자를 선언 하는 헤더 파일 포함 하지 않으면. 식별자에 대 한 선언을 포함 하는 파일이 사용 하는 모든 소스 파일에 포함 되어 있는지 확인 합니다.

```cpp
// C2065_header.cpp
// compile with: cl /EHsc C2065_header.cpp

//#include <stdio.h>
int main() {
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined
}
```

또 다른 가능한 원인은 포함 하지 않고 이니셜라이저 목록을 사용 하는 것은 \<initializer_list > 헤더입니다.

```cpp
// C2065_initializer.cpp
// compile with: cl /EHsc C2065_initializer.cpp

// #include <initializer_list>
int main() {
    for (auto strList : {"hello", "world"})
        if (strList == "hello") // C2065: 'strList': undeclared identifier
            return 1;
    // To fix, uncomment the #include <initializer_list> line
}
```

정의 하는 경우 Windows 데스크톱 앱의 소스 파일에서이 오류가 표시 될 수 있습니다 `VC_EXTRALEAN`하십시오 `WIN32_LEAN_AND_MEAN`, 또는 `WIN32_EXTRA_LEAN`합니다. 이러한 전처리기 매크로 windows.h 및 afxv에서 일부 헤더 파일을 제외\_w32.h 속도를 컴파일합니다. Windows.h 및 afxv_w32.h에 대 한 최신 설명 제외 되는 확인 합니다.

## <a name="example-missing-closing-quote"></a>예: 닫는 따옴표가 없습니다.

이 오류는 문자열 상수 뒤 닫는 따옴표를 누락 된 경우에 발생할 수 있습니다. 컴파일러를 혼동 하기 쉬운 경우 누락 된 닫는 따옴표는 보고 된 오류 위치 앞에 여러 줄 수 있습니다 note 합니다.

```cpp
// C2065_quote.cpp
// compile with: cl /EHsc C2065_quote.cpp
#include <iostream>

int main() {
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee";
    std::cout << "Name: " << first
        << " " << last << std::endl; // C2065: 'last': undeclared identifier
}
```

## <a name="example-use-iterator-outside-for-loop-scope"></a>예제: for 루프 범위 외부 반복기 사용

반복기 변수를 선언 하는 경우이 오류가 발생할 수 있습니다는 `for` 루프 및 다음의 범위를 벗어나는 반복기 변수를 사용 하려고 합니다 `for` 루프입니다. 컴파일러 사용 하도록 설정 합니다 [/zc: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 기본적으로 컴파일러 옵션입니다. 참조 [디버그 반복기 지원](../../standard-library/debug-iterator-support.md) 자세한 내용은 합니다.

```cpp
// C2065_iter.cpp
// compile with: cl /EHsc C2065_iter.cpp
#include <iostream>
#include <string>

int main() {
    // char last = '!';
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" };
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
}
```

## <a name="example-preprocessor-removed-declaration"></a>예: 전처리기 제거 선언

이 오류는 함수 또는 변수가 현재 구성의 컴파일되지 않은 조건부로 컴파일된 코드에서 참조 하는 경우에 발생할 수 있습니다. 현재 빌드 환경에서 지원 되지 않는 헤더 파일에는 함수를 호출 하는 경우에 발생할 수 있습니다. 특정 변수 또는 함수 에서만 사용 가능한 경우 특정 전처리기 매크로 정의 된 경우에 동일한 전처리기 매크로 정의 된 경우에 이러한 함수를 호출 하는 코드를 컴파일할 수 있는지 확인 해야 합니다. 이 문제를 쉽게 파악할 IDE에서 이므로 현재 빌드 구성에 대 한 필수 전처리기 매크로 정의 하지 않은 경우 함수에 대 한 선언을 회색입니다.

코드 디버그, 빌드 있지만 소매 되지 경우에 작동 하는 예제는 다음과 같습니다.

```cpp
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate);
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```

## <a name="example-ccli-type-deduction-failure"></a>예제: C++/ CLI 형식 추론이 실패

사용 된 매개 변수에서 원하는 형식 인수를 추론할 수 없으므로 제네릭 함수를 호출 하는 경우이 오류가 발생할 수 있습니다. 자세한 내용은 [제네릭 함수 (C++/CLI)](../../extensions/generic-functions-cpp-cli.md)합니다.

```cpp
// C2065_b.cpp
// compile with: cl /clr C2065_b.cpp
generic <typename ItemType>
void G(int i) {}

int main() {
   // global generic function call
   G<T>(10);     // C2065
   G<int>(10);   // OK - fix with a specific type argument
}
```

## <a name="example-ccli-attribute-parameters"></a>예제: C++/ 특성 매개 변수 CLI

이 오류는 Visual C++ 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성될 수도 있습니다. 매개 변수에 Visual C++ 특성이 있는지 확인합니다.

```cpp
// C2065_attributes.cpp
// compile with: cl /c /clr C2065_attributes.cpp
[module(DLL, name=MyLibrary)];   // C2065
// try the following line instead
// [module(dll, name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```
