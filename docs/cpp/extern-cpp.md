---
title: extern (C++)
ms.date: 04/12/2018
f1_keywords:
- extern
- extern_CPP
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
ms.openlocfilehash: 4a3a4e158794e06f28c638e87e014ddc3fb99837
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183741"
---
# <a name="extern-c"></a>extern (C++)

합니다 **extern** 키워드가 해당 작업의 이름에 지정 하려면 전역 변수, 함수 또는 템플릿 선언에 적용 되는지 *외부 링크가*합니다. 링크 및 전역 변수 사용은 권장 되지 않습니다에 대 한 자세한 내용은 참조 하세요. [프로그램 및 링크](program-and-linkage-cpp.md)합니다.

합니다 **extern** 키워드는 컨텍스트에 따라 네 가지 의미를 갖습니다.

1. 비 const 전역 변수 선언이 **extern** 변수 또는 함수를 다른 변환 단위에서 정의 됨을 지정 합니다. 합니다 **extern** 변수가 정의 되어 있는 것을 제외한 모든 파일에 적용 해야 합니다.
1. const 변수 선언에서 변수가 외부 링크를 지정 합니다. 합니다 **extern** 모든 파일의 모든 선언에 적용 되어야 합니다. (전역 const 변수 내부 링크만 있는 기본적으로 합니다.)
1. **extern "C"** 함수가 다른 곳에 정의 하 고 언어 C 호출 규칙을 사용 하 여 지정 합니다. Extern "C" 한정자 블록의 여러 함수 선언에도 적용할 수 있습니다.
1. 템플릿 선언에서는 템플릿을 이미 인스턴스화된 다른 곳에서 지정 합니다. 현재 위치에 새로 만드는 대신 다른 인스턴스화 다시 사용할 수 있음을 컴파일러에 지시 하는 최적화입니다. 이 사용에 대 한 자세한 내용은 **extern**를 참조 하십시오 [템플릿](templates-cpp.md)합니다.

## <a name="extern-linkage-for-non-const-globals"></a>비 const 전역 extern 링크

링커 표시 하는 경우 **extern** 전역 변수 선언 하기 전에 다른 변환 단위에 정의에 표시 합니다. 기본적으로 외부는 전역 범위에서 비 const 변수 선언 에 적용 **extern** 정의 제공 하지 않는 선언에 있습니다.

```cpp
//fileA.cpp
int i = 42; // declaration and definition

//fileB.cpp
extern int i;  // declaration only. same as i in FileA

//fileC.cpp
extern int i;  // declaration only. same as i in FileA

//fileD.cpp
int i = 43; // LNK2005! 'i' already has a definition.
extern int i = 43; // same error (extern is ignored on definitions)
```

## <a name="extern-linkage-for-const-globals"></a>extern const globals 링크

A **const** 에 내부 링크는 기본적으로 전역 변수입니다. 변수 외부 링크를 원한다 면 적용 된 **extern** 키워드를 다른 파일의 다른 모든 선언에 대 한 정의:

```cpp
//fileA.cpp
extern const int i = 42; // extern const definition

//fileB.cpp
extern const int i;  // declaration only. same as i in FileA
```

## <a name="extern-constexpr-linkage"></a>extern constexpr 링크

Visual Studio 2017 버전 15.3 및 이전 버전의에서 컴파일러가 항상 지정한 constexpr 변수 내부 링크 extern 표시 된 경우에 합니다. Visual Studio 2017 15.5 버전에서 새 컴파일러 스위치([/Zc:externConstexpr](../build/reference/zc-externconstexpr.md))는 올바른 표준 준수 동작을 활성화합니다. 결국 이는 기본값이 됩니다.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

표시 된 필요한 헤더 파일 변수 선언 된 extern constexpr에 있으면 **__declspec (selectany)** 결합 하는 중복 선언을 올바르게 가지려면:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="extern-c-and-extern-c-function-declarations"></a>extern "C" 및 extern "C++" 선언을 함수

C++문자열을 사용 하는 경우 **extern** 는 다른 언어의 링크 규칙을 사용 하는 중임을 지정 합니다. C 함수 및 데이터는 이전에 C 링크가 있는 것으로 선언된 경우에만 액세스할 수 있습니다. 단, 별도로 컴파일된 변환 단위로 정의되어야 합니다.

Microsoft C++ 는 문자열을 지 원하는 **"C"** 하 고 **"C++"** 에 *문자열 리터럴* 필드. 모든 표준 포함 파일을 **extern** 에서 사용할 수 있는 런타임 라이브러리 함수를 허용 하는 "C" 구문을 C++ 프로그램입니다.

## <a name="example"></a>예제

다음 예제에서는 C 링크가 있는 이름을 선언 하는 방법을 보여 줍니다.

```cpp
// Declare printf with C linkage.
extern "C" int printf(const char *fmt, ...);

//  Cause everything in the specified
//  header files to have C linkage.
extern "C" {
    // add your #include statements here
#include <stdio.h>
}

//  Declare the two functions ShowChar
//  and GetChar with C linkage.
extern "C" {
    char ShowChar(char ch);
    char GetChar(void);
}

//  Define the two functions
//  ShowChar and GetChar with C linkage.
extern "C" char ShowChar(char ch) {
    putchar(ch);
    return ch;
}

extern "C" char GetChar(void) {
    char ch;
    ch = getchar();
    return ch;
}

// Declare a global variable, errno, with C linkage.
extern "C" int errno;
```

함수에 둘 이상의 링크 사양이 있는 경우 두 사양은 일치해야 합니다. C 및 C++ 링크가 둘 다 있는 것으로 함수를 선언하면 오류가 발생합니다. 뿐만 아니라 함수에 대한 두 선언(링크 사양이 있는 선언과 없는 선언)이 프로그램에서 발생할 경우 링크 사양이 있는 선언이 첫 번째여야 합니다. 이미 링크 사양이 있는 함수의 모든 중복 선언에는 첫 번째 선언에서 지정된 링크가 제공됩니다. 예를 들어:

```cpp
extern "C" int CFunc1();
...
int CFunc1();            // Redeclaration is benign; C linkage is
                         //  retained.

int CFunc2();
...
extern "C" int CFunc2(); // Error: not the first declaration of
                         //  CFunc2;  cannot contain linkage
                         //  specifier.
```

## <a name="see-also"></a>참고자료

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[프로그램 및 링크](program-and-linkage-cpp.md)<br/>
[extern c에서 저장소 클래스 지정자](../c-language/extern-storage-class-specifier.md)<br/>
[C에서 식별자 동작](../c-language/behavior-of-identifiers.md)<br/>
[C 링크](../c-language/linkage.md)