---
title: /Zc:implicitNoexcept(암시적 예외 지정자)
ms.date: 03/06/2018
f1_keywords:
- /Zc:implicitNoexcept
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
ms.openlocfilehash: ec2b8c8fb4c7730a78c4403606d6fa61c0ddc374
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315562"
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/Zc:implicitNoexcept(암시적 예외 지정자)

경우는 **/zc: implicitnoexcept** 옵션을 지정 하면 컴파일러는 암시적 추가 [noexcept](../../cpp/noexcept-cpp.md) 예외 지정자 컴파일러가 정의한 특수 멤버 함수에 사용자가 정의한 소멸자 및 비 할당자입니다. 기본적으로 **/zc: implicitnoexcept** ISO c++11 표준에 맞게 사용 가능 합니다. 이 옵션을 해제하면 사용자가 정의한 소멸자 및 비할당자와 컴파일러가 정의한 특수 멤버 함수에 암시적 `noexcept`를 사용하지 않습니다.

## <a name="syntax"></a>구문

> **/Zc:implicitNoexcept**[**-**]

## <a name="remarks"></a>설명

**/Zc: implicitnoexcept** 컴파일러가 ISO c++11 표준 15.4 항에 따라 합니다. 암시적으로 추가 된 `noexcept` 각 암시적으로 선언 되었거나 명시적으로 기본값으로 설정 된 특수 멤버 함수 예외 지정자-기본 생성자, 생성자, 이동 생성자, 소멸자, 복사 할당 연산자 복사 또는 이동 할당 연산자-및 각 사용자 정의 소멸자 또는 비 할당자 함수입니다. 사용자 정의 비할당자에는 암시적 `noexcept(true)` 예외 지정자가 있습니다. 사용자 정의 소멸자의 경우 포함된 멤버 클래스 또는 기본 클래스에 `noexcept(true)`가 아닌 소멸자가 없는 한, 암시적 예외 지정자는 `noexcept(true)`입니다. 컴파일러에서 생성된 특수 멤버 함수의 경우 이 함수에 의해 직접 호출되는 함수는 실질적으로 `noexcept(false)`이며 암시적 예외 지정자는 `noexcept(false)`입니다. 그렇지 않은 경우 암시적 예외 지정자는 `noexcept(true)`입니다.

컴파일러는 명시적인 `noexcept` 또는 `throw` 지정자나 `__declspec(nothrow)` 특성을 사용하여 선언된 함수에 대해 암시적 예외 지정자를 생성하지 않습니다.

기본적으로 **/zc: implicitnoexcept** 사용 가능 합니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 옵션이 적용 되지 않습니다 **/zc: implicitnoexcept**합니다.

옵션을 지정 하 여 비활성화 된 경우 **/zc: implicitnoexcept-**, 없습니다 암시적 예외 지정자는 컴파일러에서 생성 됩니다. 이 동작은 Visual Studio 2013과 같습니다. Visual Studio 2013에서는 예외 지정자가 없는 소멸자 및 비할당자에 `throw` 문이 있습니다. 기본적으로 시점과 **/zc: implicitnoexcept** 를 지정 하는 경우를 `throw` 암시적 함수에서 런타임 시 문이 `noexcept(true)` 지정자를 즉시 호출 하면 `std::terminate`, 및 예외 처리기의 정상적인 해제 동작이 보장 되지 않습니다. 컴파일러 생성이 상황을 식별할 [컴파일러 경고 (수준 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)합니다. 경우는 `throw` 은 의도적인 것이 좋습니다는 명시적인 하도록 함수 선언을 변경한 `noexcept(false)` 지정자를 사용 하는 대신 **/zc: implicitnoexcept-** 합니다.

이 샘플에서는 사용자 정의 소멸자 없음 명시적 예외 지정 자가 있는 경우 작동 하는 방식을 보여 줍니다.는 **/zc: implicitnoexcept** 옵션을 설정 하거나 사용 하지 않도록 설정 합니다. 동작으로 설정 된 경우 사용 하 여 컴파일할 `cl /EHsc /W4 implicitNoexcept.cpp`합니다. 사용 하지 않도록 설정 하는 경우 동작을 보여 주기 위해 사용 하 여 컴파일할 `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`합니다.

```cpp
// implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp

#include <iostream>
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS
#include <exception>    // for std::set_terminate

void my_terminate()
{
    std::cout << "Unexpected throw caused std::terminate" << std::endl;
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;
    std::exit(EXIT_FAILURE);
}

struct A {
    // Explicit noexcept overrides implicit exception specification
    ~A() noexcept(false) {
        throw 1;
    }
};

struct B : public A {
    // Compiler-generated ~B() definition inherits noexcept(false)
    ~B() = default;
};

struct C {
    // By default, the compiler generates an implicit noexcept(true)
    // specifier for this user-defined destructor. To enable it to
    // throw an exception, use an explicit noexcept(false) specifier,
    // or compile by using /Zc:implicitNoexcept-
    ~C() {
        throw 1; // C4297, calls std::terminate() at run time
    }
};

struct D : public C {
    // This destructor gets the implicit specifier of its base.
    ~D() = default;
};

int main()
{
    std::set_terminate(my_terminate);

    try
    {
        {
            B b;
        }
    }
    catch (...)
    {
        // exception should reach here in all cases
        std::cout << "~B Exception caught" << std::endl;
    }
    try
    {
        {
            D d;
        }
    }
    catch (...)
    {
        // exception should not reach here if /Zc:implicitNoexcept
        std::cout << "~D Exception caught" << std::endl;
    }
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;
    return EXIT_SUCCESS;
}
```

기본 설정을 사용 하 여 컴파일하면 **/zc: implicitnoexcept**, 샘플이이 출력을 생성 합니다.

```Output
~B Exception caught
Unexpected throw caused std::terminate
Exit returning EXIT_FAILURE
```

설정을 사용 하 여 컴파일하면 **/zc: implicitnoexcept-**, 샘플이이 출력을 생성 합니다.

```Output
~B Exception caught
~D Exception caught
Exit returning EXIT_SUCCESS
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: implicitnoexcept** 또는 **/zc: implicitnoexcept-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[예외 사양(throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[terminate](../../standard-library/exception-functions.md#terminate)<br/>
