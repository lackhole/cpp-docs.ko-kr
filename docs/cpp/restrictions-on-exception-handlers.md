---
title: 예외 처리기에 대한 제한
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 030d444443b3a6e3e2e0ac0e015619046a76d562
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245154"
---
# <a name="restrictions-on-exception-handlers"></a>예외 처리기에 대한 제한

The principal limitation to using exception handlers in code is that you cannot use a **goto** statement to jump into a **__try** statement block. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. You can jump out of a **__try** statement block and nest exception handlers as you choose.

## <a name="see-also"></a>참조

[예외 처리기 작성](../cpp/writing-an-exception-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)