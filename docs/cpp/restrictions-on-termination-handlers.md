---
title: 종료 처리기에 대한 제한
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 6c39407270037756c55dc42aed80e1d04616c9ee
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246378"
---
# <a name="restrictions-on-termination-handlers"></a>종료 처리기에 대한 제한

You cannot use a **goto** statement to jump into a **__try** statement block or a **__finally** statement block. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. (You can, however, jump out of a **__try** statement block.) Also, you cannot nest an exception handler or termination handler inside a **__finally** block.

또한 종료 처리기에 허용되는 몇 종류의 코드는 그 결과가 불확실하기 때문에 주의하여 사용해야 합니다(있는 경우). One is a **goto** statement that jumps out of a **__finally** statement block. 블록이 정상적인 종료의 일부분으로 실행되는 경우 비정상적인 일이 생기지 않지만 시스템이 스택을 해제하는 경우 해제가 중지되고 비정상적인 종료가 없는 것처럼 현재 함수가 제어권을 갖습니다.

A **return** statement inside a **__finally** statement block presents roughly the same situation. 종료 처리기를 포함하는 함수의 직접 실행 호출자에게 제어가 반환됩니다. 시스템이 스택을 해제 중이었으면 이 프로세스가 중단되고, 예외가 발생하지 않은 것처럼 프로그램이 계속됩니다.

## <a name="see-also"></a>참조

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)