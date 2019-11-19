---
title: /Zc:noexceptTypes(C++17 noexcept 규칙)
ms.date: 11/14/2017
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 35bea7c2c629c615c60a6136f289b6b11926c054
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624860"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes(C++17 noexcept 규칙)

C + + 17 표준에서는 `noexcept`에 대 한 별칭 `throw()` 하 고, `throw(<type list>)` 및 `throw(...)`를 제거 하 고, 특정 형식에 `noexcept`을 포함 시킬 수 있습니다. 이렇게 변경 하면 c + + 14 이전 버전을 따르는 코드에서 많은 소스 호환성 문제가 발생할 수 있습니다. **/Zc: noexceptTypes** 옵션은 c + + 17 표준에 대 한 준수를 지정 합니다. **/Zc: noexceptTypes-** 코드를 c + + 17 모드로 컴파일할 때 c + + 14 및 이전 동작을 허용 합니다.

## <a name="syntax"></a>구문

> **/Zc: noexceptTypes**[-]

## <a name="remarks"></a>주의

**/Zc: noexceptTypes** 옵션을 지정 하면 컴파일러는 c + + 17 표준을 준수 하 고 [throw ()](../../cpp/exception-specifications-throw-cpp.md) 를 [noexcept](../../cpp/noexcept-cpp.md)별칭으로 처리 하 고, `throw(<type list>)` 및 `throw(...)`를 제거 하 고, 특정 형식에 `noexcept`를 포함 하도록 허용 합니다. **/Zc: noexceptTypes** 옵션은 [/prod: c + + 17](std-specify-language-standard-version.md) 또는 [/sts: 최신](std-specify-language-standard-version.md) 이 설정 된 경우에만 사용할 수 있습니다. **/Zc: noexceptTypes** 는 기본적으로 ISO c + + 17 표준을 준수 하도록 설정 됩니다. [/Permissive-](permissive-standards-conformance.md) 옵션은 **/zc: noexceptTypes**에 영향을 주지 않습니다. **NoexceptTypes** 를 지정 하 여이 옵션을 해제 합니다. **/std: c + + 17** 또는 **/sts: 최신** 이 지정 된 경우 `noexcept`의 c + + 14 동작으로 되돌립니다.

Visual Studio 2017 버전 15.5부터 컴파일러는 C++ c + + 17 모드의 선언에서 더 일치 하지 않는 예외 사양을 진단 하거나 [/permissive-](permissive-standards-conformance.md) 옵션을 지정 합니다.

이 샘플에서는 **/zc: noexceptTypes** 옵션을 설정 하거나 해제할 때 예외 지정자를 사용한 선언이 어떻게 동작 하는지를 보여 줍니다. 설정 될 때 동작을 표시 하려면 `cl /EHsc /W4 noexceptTypes.cpp`를 사용 하 여 컴파일합니다. 사용 하지 않도록 설정 된 경우 동작을 표시 하려면 `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp`를 사용 하 여 컴파일합니다.

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

기본 설정인 **/zc: noexceptTypes**를 사용 하 여 컴파일하면 샘플에서 나열 된 경고를 생성 합니다. 코드를 업데이트 하려면 대신 다음을 사용 합니다.

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

1. **구성 속성** > **C/C++**  > **명령줄** 속성 페이지를 선택합니다.

1. **/Zc: noexceptTypes** 또는 **/zc: noexceptTypes** 를 포함 하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택 합니다.

## <a name="see-also"></a>참조

[/Zc (규칙)](zc-conformance.md)\
[noexcept](../../cpp/noexcept-cpp.md)\
[예외 사양 (throw)](../../cpp/exception-specifications-throw-cpp.md)
