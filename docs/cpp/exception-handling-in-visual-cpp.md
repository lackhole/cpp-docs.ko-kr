---
title: MSVC의 예외 처리
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
# <a name="exception-handling-in-msvc"></a>MSVC의 예외 처리

예외는 프로그램이 일반적인 실행 경로를 따라 계속 진행하는 것을 방해하며 프로그램의 제어를 벗어날 수 있는 오류 상태입니다. 개체 생성, 파일 입/출력 및 다른 모듈에서 함수 호출 등 특정 작업은 프로그램이 제대로 실행되는 경우에도 모두 예외의 잠재적 원인입니다. 강력한 코드는 예외를 예상하고 처리합니다. 논리 오류를 검색 하려면 예외 대신 어설션을 사용 합니다 ( [어설션 사용](/visualstudio/debugger/c-cpp-assertions)참조).

## <a name="kinds-of-exceptions"></a>예외 종류

Microsoft C++ 컴파일러 (MSVC)는 세 가지 예외 처리를 지원 합니다.

- [C++예외 처리](errors-and-exception-handling-modern-cpp.md)

   대부분의 C++ 프로그램의 경우 형식 안전이며 스택 해제 중 개체 소멸자의 호출을 확인하는 C++ 예외 처리를 사용해야 합니다.

- [구조적 예외 처리](structured-exception-handling-c-cpp.md)

   Windows는 SEH라는 고유한 예외 메커니즘을 제공합니다. C++ 또는 MFC 프로그래밍에는 권장되지 않습니다. 비 MFC C 프로그램 에서만 SEH를 사용 합니다.

- [MFC 예외](../mfc/exception-handling-in-mfc.md)

[/Eh](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용 하 여 프로젝트에서 사용할 예외 처리 유형을 지정 합니다. C++ 기본값은 예외 처리입니다. 오류 처리 메커니즘을 혼용하지 마십시오. 예를 들어 C++ 예외를 구조적 예외 처리와 함께 사용하지 마십시오. C++ 예외 처리를 사용하면 코드 이식 가능성이 향상되며 모든 형식의 예외를 처리할 수 있습니다. 구조적 예외 처리의 단점에 대 한 자세한 내용은 [구조적 예외 처리](structured-exception-handling-c-cpp.md)를 참조 하세요. MFC 매크로 및 C++ 예외를 혼합 하는 방법에 대 한 조언을 보려면 [예외: C++ mfc 매크로 및 예외 사용](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)을 참조 하세요.

## <a name="in-this-section"></a>단원 내용

- [예외 C++ 및 오류 처리에 대 한 최신 모범 사례](errors-and-exception-handling-modern-cpp.md)

- [예외 안전을 위한 설계 방법](how-to-design-for-exception-safety.md)

- [예외 코드와 비 예외 코드 간의 상호 작용 방법](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [Try, catch 및 throw 문](try-throw-and-catch-statements-cpp.md)

- [Catch 블록의 평가 방법](how-catch-blocks-are-evaluated-cpp.md)

- [예외 및 스택 해제](exceptions-and-stack-unwinding-in-cpp.md)

- [예외 사양](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [처리되지 않은 C++ 예외](unhandled-cpp-exceptions.md)

- [C(구조적) 및 C++ 예외 혼합](mixing-c-structured-and-cpp-exceptions.md)

- [SEH (구조적 예외 처리) (C/C++)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>참고 항목

[C++ 언어 참조](cpp-language-reference.md)</br>
[x64 예외 처리](../build/exception-handling-x64.md)</br>
[예외 처리 (C++/Cli 및 C++/cx)](../extensions/exception-handling-cpp-component-extensions.md)
