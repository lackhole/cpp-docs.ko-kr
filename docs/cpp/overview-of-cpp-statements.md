---
title: C++문 개요
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
ms.openlocfilehash: 9493860087331ee2d8ff05a5c0bd59c7a46ad51a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325561"
---
# <a name="overview-of-c-statements"></a>C++문 개요

C++ 문은 프로그램의 수행 순서를 변경하는 수식문, 선택문, 반복문이나 점프문을 제외하고 순차적으로 실행됩니다.

문은 다음과 같은 형식일 수 있습니다.

```
labeled-statement
expression-statement
compound-statement
selection-statement
iteration-statement
jump-statement
declaration-statement
try-throw-catch
```

대부분의 경우 C++ 문 구문은 ANSI C의 문 구문과 동일합니다. 둘 사이의 주요 차이점은 C에서는 선언이 블록의 시작에서만 허용되지만 C++에서는 *declaration-statement*가 추가되었으므로 이 제한이 사실상 제거되었다는 점입니다. 이에 따라 미리 계산된 초기화 값이 계산될 수 있는 프로그램의 지점에 변수를 도입할 수 있습니다.

블록 내에 변수를 선언하면 해당 변수의 범위와 수명을 정확하게 제어할 수 있습니다.

문에 대한 항목에서는 다음과 같은 C++ 키워드에 대해 설명합니다.

|||||
|-|-|-|-|
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[try](../cpp/try-throw-and-catch-statements-cpp.md)|
|[catch](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||
|[do](../cpp/do-while-statement-cpp.md)|[if](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||

## <a name="see-also"></a>참고자료

[문(C++)](../cpp/statements-cpp.md)