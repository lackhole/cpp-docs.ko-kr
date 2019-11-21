---
title: Exception handling in MSVC
ms.date: 11/19/2019
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 6cf71d6e6d0519951a084ebead65003bd363395f
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246588"
---
# <a name="exception-handling-in-msvc"></a>Exception handling in MSVC

예외는 프로그램이 일반적인 실행 경로를 따라 계속 진행하는 것을 방해하며 프로그램의 제어를 벗어날 수 있는 오류 상태입니다. 개체 생성, 파일 입/출력 및 다른 모듈에서 함수 호출 등 특정 작업은 프로그램이 제대로 실행되는 경우에도 모두 예외의 잠재적 원인입니다. 강력한 코드는 예외를 예상하고 처리합니다. To detect logic errors, use assertions rather than exceptions (see [Using Assertions](/visualstudio/debugger/c-cpp-assertions)).

## <a name="kinds-of-exceptions"></a>Kinds of exceptions

The Microsoft C++ compiler (MSVC) supports three kinds of exception handling:

- [C++ exception handling](errors-and-exception-handling-modern-cpp.md)

   대부분의 C++ 프로그램의 경우 형식 안전이며 스택 해제 중 개체 소멸자의 호출을 확인하는 C++ 예외 처리를 사용해야 합니다.

- [Structured exception handling](structured-exception-handling-c-cpp.md)

   Windows는 SEH라는 고유한 예외 메커니즘을 제공합니다. C++ 또는 MFC 프로그래밍에는 권장되지 않습니다. Use SEH only in non-MFC C programs.

- [MFC exceptions](../mfc/exception-handling-in-mfc.md)

Use the [/EH](../build/reference/eh-exception-handling-model.md) compiler option to specify the type of exception handling to use in a project; C++ exception handling is the default. 오류 처리 메커니즘을 혼용하지 마십시오. 예를 들어 C++ 예외를 구조적 예외 처리와 함께 사용하지 마십시오. C++ 예외 처리를 사용하면 코드 이식 가능성이 향상되며 모든 형식의 예외를 처리할 수 있습니다. For more information about the drawbacks of structured exception handling, see [Structured Exception Handling](structured-exception-handling-c-cpp.md). For advice about mixing MFC macros and C++ exceptions, see [Exceptions: Using MFC Macros and C++ Exceptions](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="in-this-section"></a>이 섹션의 내용

- [Modern C++ best practices for exceptions and error handling](errors-and-exception-handling-modern-cpp.md)

- [How to design for exception safety](how-to-design-for-exception-safety.md)

- [How to interface between exceptional and non-exceptional code](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [The try, catch, and throw Statements](try-throw-and-catch-statements-cpp.md)

- [Catch 블록의 평가 방법](how-catch-blocks-are-evaluated-cpp.md)

- [Exceptions and Stack Unwinding](exceptions-and-stack-unwinding-in-cpp.md)

- [Exception Specifications](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [처리되지 않은 C++ 예외](unhandled-cpp-exceptions.md)

- [C(구조적) 및 C++ 예외 혼합](mixing-c-structured-and-cpp-exceptions.md)

- [Structured Exception Handling (SEH) (C/C++)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>참조

[C++ 언어 참조](cpp-language-reference.md)</br>
[x64 예외 처리](../build/exception-handling-x64.md)</br>
[Exception Handling (C++/CLI and C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)
