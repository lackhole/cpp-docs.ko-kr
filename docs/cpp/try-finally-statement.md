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
ms.openlocfilehash: d2a1c63f686b46aad4e174c86895f6f9fc00d260
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404733"
---
# <a name="try-finally-statement"></a>try-finally 문

**Microsoft 전용**

다음 구문에 설명 합니다 **try-finally** 문:

> **\_\_try**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;보호 된 코드<br/>
> }<br/>
> **\_\_finally**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;종료 코드<br/>
> }<br/>

## <a name="grammar"></a>문법

*try-finally-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**\_\_try** *compound-statement* **\_\_finally** *compound-statement*

**try finally** 문에 C에 대 한 Microsoft 확장 및 C++ 코드 블록의 실행이 중단 된 경우 정리 코드 실행을 보장 하기 위해 대상 응용 프로그램을 사용 하도록 설정 하는 언어입니다. 정리는 메모리 할당 해제, 파일 닫기 및 파일 핸들 해제와 같은 작업으로 구성됩니다. 합니다 **try-finally** 문에 루틴에서 반환 하는 위치는 검사가 수행 됩니다 오류가 발생할 수 있는 중간 많은 루틴에 특히 유용 합니다.

관련된 정보 및 코드 샘플을 참조 하세요 [시도-문을 제외 하 고](../cpp/try-except-statement.md)입니다. 구조적된 예외 처리에 대 한 자세한 내용은 참조 하세요. [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)합니다. C +를 사용 하 여 관리 되는 응용 프로그램에서 예외를 처리 하는 방법은 + CLI 참조 [/clr에서 예외 처리](../extensions/exception-handling-cpp-component-extensions.md)합니다.

> [!NOTE]
> 구조적 예외 처리는 Win32에서 C 및 C++ 소스 파일에 대해 작동하지만 특별히 C++용으로 설계되지는 않았습니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리는 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다. 에 대 한 C++ 프로그램 것이 좋습니다 사용 하는 C++ 예외 처리 메커니즘 ([try, catch 및 throw](../cpp/try-throw-and-catch-statements-cpp.md) 문).

뒤의 복합 문은 합니다 **__try** 절은 보호 된 섹션입니다. 뒤의 복합 문은 합니다 **__finally** 절에는 종료 처리기입니다. 처리기는 보호된 섹션이 예외(비정상적인 종료)로 인해 종료되건 표준 이동(정상적인 종료)으로 인해 종료되건 간에 보호된 섹션이 끝나면 실행되는 작업 집합을 지정합니다.

에 도달 하면 컨트롤을 **__try** 단순한 순차적 실행으로 이동 하 여 문입니다. 컨트롤이 전환 하는 경우는 **__try**, 해당 연결 된 처리기가 활성화 됩니다. 제어 흐름이 try 블록 끝에 도달하면 다음과 같이 실행됩니다.

1. 종료 처리기가 호출됩니다.

1. 이후 실행 진행 종료 처리기에는 다음이 완료 되 면 합니다 **__finally** 문입니다. 보호 된 섹션이 끝나는 방법에 관계 없이 (예를 통해는 **goto** 보호 된 본문 밖 또는 **반환** 문), 종료 처리기가 실행 됩니다 *하기 전에* 는 제어 흐름이 보호 된 섹션 밖으로 이동 합니다.

   A **__finally** 문이 적절 한 예외 처리기 검색을 차단 하지 않습니다.

예외가 발생 하는 경우는 **__try** 블록 프로그램이 실패 또는 운영 체제는 예외에 대 한 처리기를 찾아야 합니다. 처리기가 있으면 모든 **__finally** 블록을 실행 하 고 처리기에서 실행을 다시 시작 합니다.

예를 들어, 일련의 함수 호출 링크에서는 함수 A를 D에 연결한다고 가정합니다(아래 그림 참조). 각 함수에는 종료 처리기가 하나씩 있습니다. 예외가 D 함수에서 발생 하 고 A에서 처리를 하는 경우 시스템 지우며 스택을 해제 하는 대로 종료 처리기가이 순서 대로 호출 됩니다. D, C, B.

![종료 순서&#45;처리기 실행](../cpp/media/vc38cx1.gif "종료 순서&#45;처리기 실행") <br/>
종료 처리기 실행 순서

> [!NOTE]
> Try-finally의 동작은의 사용을 지 원하는 다른 언어에서 다른 **마지막**, C#과 같은 합니다.  단일 **__try** 하나만 하거나, 있을 수 있습니다 **__finally** 하 고 **__except**합니다.  모두 함께 사용되는 경우 외부 try-except 문은 내부 try-finally 문을 포함해야 합니다.  또한 각 블록을 실행할 때 지정되는 규칙은 서로 다릅니다.

이전 버전과 호환성에 대 한 **_try**를 **_finally**, 및 **_leave** 은 **__try**, **__ 마지막**, 및 **__leave** 하지 않으면 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 지정 됩니다.

## <a name="the-leave-keyword"></a>__leave 키워드

**__leave** 키워드는 보호 된 섹션 내 에서만 사용할 수는 **try-finally** 문과 미치는 보호 된 섹션의 끝으로 이동 하는 것입니다. 종료 처리기의 첫 번째 문에서 계속 실행됩니다.

A **goto** 문은 보호 된 섹션에서 외부로 이동할 수도 있지만 스택 해제를 호출 하기 때문에 성능이 저하 됩니다. 합니다 **__leave** 문은 스택 해제 되지는지 않습니다 때문에 더 효율적입니다.

## <a name="abnormal-termination"></a>비정상적인 종료

종료를 **try finally** 문을 사용 하는 [longjmp](../c-runtime-library/reference/longjmp.md) 런타임 함수에는 비정상적인 종료 것으로 간주 됩니다. 으로 이동 하는 것이 올바르지를 **__try** 문과 비슷하지만 밖 하나입니다. 모든 **__finally** 출발 지점 간에 활성화 된 문 (의 정상 종료를 **__try** 블록) 및 대상 (합니다 **__except** 는 차단 예외 처리)를 실행 해야 합니다. 이것을 로컬 해제라고 합니다.

경우는 **시도** 블록 중간에 종료 되는 블록 밖으로 점프를 포함 하 여 어떤 이유로, 연결 된 시스템 실행 **마지막으로** 스택 해제 과정의 일부로 차단 합니다. 이러한 경우에는 [AbnormalTermination](/windows/desktop/Debug/abnormaltermination) 함수에서 반환 **true** 내에서 호출 하는 경우는 **마지막** ;를 반환 합니다 **false**.

종료 처리기 실행 하는 도중에 프로세스가 종료 될 경우 라고는 **try-finally** 문.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[종료 처리기 작성](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[종료 처리기 구문](/windows/desktop/Debug/termination-handler-syntax)