---
title: 종료 처리기에 대한 제한
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 7b092ee8682dfeef0c8151c56544e36427f40da0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244491"
---
# <a name="restrictions-on-termination-handlers"></a>종료 처리기에 대한 제한

사용할 수 없습니다는 **goto** 으로 이동 하는 문에 **__try** 문 블록 또는 **__finally** 문 블록. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. 그러나 (의 외부로 이동할 수 있습니다는 **__try** 문 블록입니다.) 예외 처리기 나 종료 처리기를 중첩할 수 없습니다는 또한을 **__finally** 블록입니다.

또한 종료 처리기에 허용되는 몇 종류의 코드는 그 결과가 불확실하기 때문에 주의하여 사용해야 합니다(있는 경우). 그 중 하나는 **__finally** 문 블록 밖으로 점프하는 **goto** 문입니다. 블록이 정상적인 종료의 일부분으로 실행되는 경우 비정상적인 일이 생기지 않지만 시스템이 스택을 해제하는 경우 해제가 중지되고 비정상적인 종료가 없는 것처럼 현재 함수가 제어권을 갖습니다.

**__finally** 문 블록 안에 **return** 문을 사용해도 상황이 거의 같습니다. 종료 처리기를 포함하는 함수의 직접 실행 호출자에게 제어가 반환됩니다. 시스템이 스택을 해제 중이었으면 이 프로세스가 중단되고, 예외가 발생하지 않은 것처럼 프로그램이 계속됩니다.

## <a name="see-also"></a>참고 항목

[종료 처리기 작성](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)