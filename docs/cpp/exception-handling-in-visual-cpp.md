---
title: Visual C++에서 예외 처리
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 506ead1b6e96f59717a92b6b0c48db0270b1822f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398878"
---
# <a name="exception-handling-in-visual-c"></a>Visual C++에서 예외 처리

예외는 프로그램이 일반적인 실행 경로를 따라 계속 진행하는 것을 방해하며 프로그램의 제어를 벗어날 수 있는 오류 상태입니다. 개체 생성, 파일 입/출력 및 다른 모듈에서 함수 호출 등 특정 작업은 프로그램이 제대로 실행되는 경우에도 모두 예외의 잠재적 원인입니다. 강력한 코드는 예외를 예상하고 처리합니다.

단일 프로그램 또는 모듈 내에서 논리 오류를 감지 하려면 예외 보다는 어설션을 사용 (참조 [어설션을 사용 하 여](/visualstudio/debugger/c-cpp-assertions)).

Visual C++은 세 종류의 예외 처리를 지원합니다.

- [C++예외 처리](../cpp/cpp-exception-handling.md)

   대부분의 C++ 프로그램의 경우 형식 안전이며 스택 해제 중 개체 소멸자의 호출을 확인하는 C++ 예외 처리를 사용해야 합니다.

- [구조적된 예외 처리](../cpp/structured-exception-handling-c-cpp.md)

   Windows는 SEH라는 고유한 예외 메커니즘을 제공합니다. C++ 또는 MFC 프로그래밍에는 권장되지 않습니다. 비 MFC C 프로그램에만 SEH를 사용 합니다.

- [MFC 예외](../mfc/exception-handling-in-mfc.md)

   버전 3.0 이상에서는 MFC가 C++ 예외를 사용했으나 형식에서 C++ 예외와 유사한 이전 예외 처리 매크로를 여전히 지원합니다. 이러한 매크로는 새 프로그래밍에는 권장되지 않지만 여전히 역 호환성에 대해 지원됩니다. 매크로를 이미 사용하는 프로그램에서 자유롭게 C++ 예외를 사용할 수 있습니다. 전처리 중 매크로는 Visual C++ 버전 2.0처럼 C++ 언어의 Visual C++ 구현에서 정의된 예외 처리 키워드를 계산합니다. C++ 예외를 사용하는 동안 기존 예외 매크로를 남겨둘 수 있습니다.

사용 된 [/EH](../build/reference/eh-exception-handling-model.md) ; 프로젝트에서 사용 하는 예외 처리의 유형을 지정 하는 컴파일러 옵션 C++ 예외 처리는 기본값입니다. 오류 처리 메커니즘을 혼용하지 마십시오. 예를 들어 C++ 예외를 구조적 예외 처리와 함께 사용하지 마십시오. C++ 예외 처리를 사용하면 코드 이식 가능성이 향상되며 모든 형식의 예외를 처리할 수 있습니다. 구조적된 예외 처리의 단점에 대 한 자세한 내용은 참조 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)합니다. 에 대 한 MFC 매크로 혼합 하는 방법에 대 한 조언 하 고 C++ 예외를 참조 하세요 [예외: MFC 매크로 사용 하 고 C++ 예외](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)합니다.

CLR 응용 프로그램에서 예외 처리에 대 한 자세한 내용은 [예외 처리 (C++/CLI 및 C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)합니다.

X64에서 예외 처리에 대 한 정보에 대 한 프로세서를 참조 하세요 [x64 예외 처리](../build/exception-handling-x64.md)합니다.

## <a name="see-also"></a>참고자료

[C++ 언어 참조](../cpp/cpp-language-reference.md)