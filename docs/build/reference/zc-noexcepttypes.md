---
title: /Zc:noexceptTypes (C + + 17 noexcept 규칙)
ms.date: 11/14/2017
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 28e06f54049d36262134b6be7eadb0e6e5349a45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315939"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (C + + 17 noexcept 규칙)

사용 하면 표준 C + + 17 `throw()` 별칭으로 `noexcept`, 제거 `throw(<type list>)` 및 `throw(...)`, 특정 형식을 포함할 수 있습니다 및 `noexcept`합니다. C++14 이하로 준수 하는 코드의 다양 한 소스 호환성 문제가 발생할 수 있습니다. 합니다 **/Zc:noexceptTypes** 옵션 c++17 모드에서 코드를 컴파일하면 C + + 14 및 이전 동작을 허용 하거나 표준 C + + 17 규칙을 지정할 수 있습니다.

## <a name="syntax"></a>구문

> **/Zc:noexceptTypes**[-]

## <a name="remarks"></a>설명

경우는 **/Zc:noexceptTypes** 옵션을 지정 하면 컴파일러는 C + + 17 표준을 준수 하 고 처리 [throw ()](../../cpp/exception-specifications-throw-cpp.md) 별칭으로 [noexcept](../../cpp/noexcept-cpp.md), 제거 `throw(<type list>)`하 고 `throw(...)`를 사용 하면 특정 형식을 포함 하 고 `noexcept`합니다. **/Zc:noexceptTypes** 옵션은만 사용할 수 있는 경우 [/std: c + + 17](std-specify-language-standard-version.md) 하거나 [/std:latest](std-specify-language-standard-version.md) 사용 가능 합니다. **/Zc:noexceptTypes** ISO c++17 표준에 맞게 기본적으로 사용 됩니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 옵션이 적용 되지 않습니다 **/Zc:noexceptTypes**합니다. 이 옵션을 지정 하 여 해제할 **/Zc:noexceptTypes-** 의 C + + 14 동작으로 되돌리려면 `noexcept` 때 **/std::C + + 17** 또는 **/std::latest** 지정 됩니다.

Visual Studio 2017 버전 15.5부터는 C++ 컴파일러 c++17 모드의 선언에 더 많은 불일치 예외 사양을 진단 때나 합니다 [관대 한 /-](permissive-standards-conformance.md) 옵션을 지정 합니다.

이 예제에서는 예외 지정자를 사용 하 여 선언 될 때의 동작 방식을 보여 줍니다.는 **/Zc:noexceptTypes** 옵션을 설정 하거나 사용 하지 않도록 설정 합니다. 동작으로 설정 된 경우 사용 하 여 컴파일할 `cl /EHsc /W4 noexceptTypes.cpp`합니다. 사용 하지 않도록 설정 하는 경우 동작을 보여 주기 위해 사용 하 여 컴파일할 `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`합니다.

```cpp
// noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp

void f() throw();    // equivalent to void f() noexcept;
void f() { }         // warning C5043
void g() throw(...); // warning C5040

struct A
{
    virtual void f() throw();
};

struct B : A
{
    virtual void f() { } // error C2694
};
```

기본 설정을 사용 하 여 컴파일하면 **/Zc:noexceptTypes**, 샘플이 나열 된 경고를 생성 합니다. 코드를 업데이트 하려면 다음을 대신 사용 합니다.

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A
{
    virtual void f() noexcept;
};

struct B : A
{
    virtual void f() noexcept { }
};
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/Zc:noexceptTypes** 또는 **/Zc:noexceptTypes-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[예외 사양(throw)](../../cpp/exception-specifications-throw-cpp.md)
