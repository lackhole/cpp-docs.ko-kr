---
title: /Zc:strictStrings(문자열 리터럴 형식 변환 사용 안 함)
ms.date: 03/06/2018
f1_keywords:
- /Zc:strictStrings
- strictStrings
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
ms.openlocfilehash: 954088955a3f1530bb298aadbc35c7dd74150b7a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315666"
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>/Zc:strictStrings(문자열 리터럴 형식 변환 사용 안 함)

지정한 경우 컴파일러에는 문자열 리터럴을 사용하여 초기화한 포인터에 대한 엄격한 `const` 한정 규칙이 필요합니다.

## <a name="syntax"></a>구문

> **/Zc:strictStrings**[**-**]

## <a name="remarks"></a>설명

경우 **/zc: strictstrings** 지정 된 경우 컴파일러가 표준 적용 C++ `const` 형식으로 문자열 리터럴에 대 한 조건을 ' 배열을 `const char`' 또는 ' 배열을 `const wchar_t`' 선언에 따라 . 문자열 리터럴은 변경 불가능하고 문자열 리터럴 중 하나의 내용을 수정하려고 하면 런타임에 액세스 위반 오류가 발생합니다. 문자열 포인터를 `const`로 선언하여 문자열 리터럴을 사용하여 초기화하거나 명시적 `const_cast`를 사용하여 비`const` 포인터를 초기화해야 합니다. 기본적으로 이거나 **/Zc:strictStrings-** 지정 된 경우 컴파일러가 표준 적용 하지 않습니다 C++ `const` 문자열 리터럴을 사용 하 여 초기화 된 문자열 포인터에 대 한 자격 요건입니다.

합니다 **/zc: strictstrings** 옵션은 기본적으로 해제 되어 있습니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 컴파일러 옵션에는 암시적으로이 옵션을 설정 하지만 사용 하 여 재정의할 수 있습니다 **/Zc:strictStrings-** 합니다.

사용 된 **/zc: strictstrings** 잘못 된 코드의 컴파일을 방지 하는 옵션입니다. 다음 예제에서는 간단한 선언 오류가 런타임에 충돌을 어떻게 발생시키는지 보여줍니다. 

```cpp
// strictStrings_off.cpp
// compile by using: cl /W4 strictStrings_off.cpp
int main() {
   wchar_t* str = L"hello";
   str[2] = L'a'; // run-time error: access violation
}
```

때 **/zc: strictstrings** 는 동일한 코드의 선언에서 오류를 보고 사용 하도록 설정 `str`합니다.

```cpp
// strictStrings_on.cpp
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp
int main() {
   wchar_t* str = L"hello"; // error: Conversion from string literal
   // loses const qualifier
   str[2] = L'a';
}
```

`auto`를 사용하여 문자열 포인터를 선언하면 컴파일러에서는 올바른 `const` 포인터 형식 선언을 만듭니다. `const` 포인터의 내용을 수정하려는 시도는 컴파일러에서 오류로 보고합니다.

> [!NOTE]
> C++ Visual Studio 2013에서 표준 라이브러리를 지원 하지 않습니다 합니다 **/zc: strictstrings** 컴파일러 옵션에서 디버그 빌드입니다. 여러 보이면 [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) 빌드에서 오류 출력을이 원인일 수 있습니다.

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: strictstrings** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](zc-conformance.md)<br/>
