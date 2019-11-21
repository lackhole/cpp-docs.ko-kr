---
title: try-finally 문
ms.date: 11/19/2018
f1_keywords:
- __try
- _try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
- _finally
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
ms.openlocfilehash: 045d2bf5617c81bcc4d7a202f36b112d5f0142a6
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246296"
---
# <a name="try-finally-statement"></a>try-finally 문

**Microsoft 전용**

The following syntax describes the **try-finally** statement:

> **\_\_try**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;// guarded code<br/>
> }<br/>
> **\_\_finally**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;// termination code<br/>
> }

## <a name="grammar"></a>문법

*try-finally-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **\_\_try** *compound-statement* **\_\_finally** *compound-statement*

The **try-finally** statement is a Microsoft extension to the C and C++ languages that enables target applications to guarantee execution of cleanup code when execution of a block of code is interrupted. 정리는 메모리 할당 해제, 파일 닫기 및 파일 핸들 해제와 같은 작업으로 구성됩니다. The **try-finally** statement is especially useful for routines that have several places where a check is made for an error that could cause premature return from the routine.

For related information and a code sample, see [try-except Statement](../cpp/try-except-statement.md). For more information on structured exception handling in general, see [Structured Exception Handling](../cpp/structured-exception-handling-c-cpp.md). For more information on handling exceptions in managed applications with C++/CLI, see [Exception Handling under /clr](../extensions/exception-handling-cpp-component-extensions.md).

> [!NOTE]
> 구조적 예외 처리는 Win32에서 C 및 C++ 소스 파일에 대해 작동하지만 특별히 C++용으로 설계되지는 않았습니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리는 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다. For C++ programs, it is recommended that you use the C++ exception-handling mechanism ([try, catch, and throw](../cpp/try-throw-and-catch-statements-cpp.md) statements).

The compound statement after the **__try** clause is the guarded section. The compound statement after the **__finally** clause is the termination handler. 처리기는 보호된 섹션이 예외(비정상적인 종료)로 인해 종료되건 표준 이동(정상적인 종료)으로 인해 종료되건 간에 보호된 섹션이 끝나면 실행되는 작업 집합을 지정합니다.

Control reaches a **__try** statement by simple sequential execution (fall through). When control enters the **__try**, its associated handler becomes active. 제어 흐름이 try 블록 끝에 도달하면 다음과 같이 실행됩니다.

1. 종료 처리기가 호출됩니다.

1. When the termination handler completes, execution continues after the **__finally** statement. Regardless of how the guarded section ends (for example, via a **goto** out of the guarded body or a **return** statement), the termination handler is executed *before* the flow of control moves out of the guarded section.

   A **__finally** statement does not block searching for an appropriate exception handler.

If an exception occurs in the **__try** block, the operating system must find a handler for the exception or the program will fail. If a handler is found, any and all **__finally** blocks are executed and execution resumes in the handler.

예를 들어, 일련의 함수 호출 링크에서는 함수 A를 D에 연결한다고 가정합니다(아래 그림 참조). 각 함수에는 종료 처리기가 하나씩 있습니다. 예외가 D 함수에서 발생하고 A에서 처리될 경우 시스템이 스택 D, C, B를 해제하면 그 순서대로 종료 처리기가 호출됩니다.

![Order of termination&#45;handler execution](../cpp/media/vc38cx1.gif "Order of termination&#45;handler execution") <br/>
종료 처리기 실행 순서

> [!NOTE]
> The behavior of try-finally is different from some other languages that support the use of **finally**, such as C#.  A single **__try** may have either, but not both, of **__finally** and **__except**.  모두 함께 사용되는 경우 외부 try-except 문은 내부 try-finally 문을 포함해야 합니다.  또한 각 블록을 실행할 때 지정되는 규칙은 서로 다릅니다.

For compatibility with previous versions, **_try**, **_finally**, and **_leave** are synonyms for **__try**, **__finally**, and **__leave** unless compiler option [/Za \(Disable language extensions)](../build/reference/za-ze-disable-language-extensions.md) is specified.

## <a name="the-__leave-keyword"></a>__leave 키워드

The **__leave** keyword is valid only within the guarded section of a **try-finally** statement, and its effect is to jump to the end of the guarded section. 종료 처리기의 첫 번째 문에서 계속 실행됩니다.

A **goto** statement can also jump out of the guarded section, but it degrades performance because it invokes stack unwinding. The **__leave** statement is more efficient because it does not cause stack unwinding.

## <a name="abnormal-termination"></a>비정상적인 종료

Exiting a **try-finally** statement using the [longjmp](../c-runtime-library/reference/longjmp.md) run-time function is considered abnormal termination. It is illegal to jump into a **__try** statement, but legal to jump out of one. All **__finally** statements that are active between the point of departure (normal termination of the **__try** block) and the destination (the **__except** block that handles the exception) must be run. 이것을 로컬 해제라고 합니다.

If a **try** block is prematurely terminated for any reason, including a jump out of the block, the system executes the associated **finally** block as a part of the process of unwinding the stack. In such cases, the [AbnormalTermination](/windows/win32/Debug/abnormaltermination) function returns **true** if called from within the **finally** block; otherwise, it returns **false**.

The termination handler is not called if a process is killed in the middle of executing a **try-finally** statement.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[Termination-Handler Syntax](/windows/win32/Debug/termination-handler-syntax)