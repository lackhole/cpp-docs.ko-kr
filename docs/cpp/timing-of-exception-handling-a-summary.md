---
title: '예외 처리에서의 타이밍: 요약'
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
ms.openlocfilehash: cbff7c4153646fcb3471e18d20a0e633fbd1307f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330455"
---
# <a name="timing-of-exception-handling-a-summary"></a>예외 처리에서의 타이밍: 요약

종료 처리기가 실행 하는 방법과 관계 없이 **__try** 문 블록 종료 됩니다. 원인의 점프,는 **__try** 블록을 `longjmp` 블록 및 예외 처리로 인 한 스택 해제 밖으로 제어를 전송 하는 문.

> [!NOTE]
>  Visual C++는 `setjmp` 및 `longjmp` 문의 두 가지 형태를 지원합니다. 빠른 버전은 종료 처리를 건너뛰지만 더 효율적입니다. 이 버전을 사용 하려면 파일을 포함 \<setjmp.h >. 다른 버전은 이전 단락에 설명된 대로 종료 처리를 지원합니다. 이 버전을 사용 하려면 파일을 포함 \<setjmpex.h >. 빠른 버전의 성능 향상 정도는 하드웨어 구성에 따라 달라집니다.

운영 체제는 다른 코드를 실행하기 전에 예외 처리기의 본문을 포함한 모든 종료 처리기를 적절한 순서대로 실행합니다.

예외로 인해 중단된 경우 시스템은 먼저 예외 처리기 하나 이상의 필터 부분을 실행한 다음 무엇을 종료할지 결정해야 합니다. 이벤트의 순서는 다음과 같습니다.

1. 예외가 발생합니다.

1. 시스템이 활성 예외 처리기의 계층 구조를 보고 우선 순위가 가장 높은 처리기(블록 및 함수 호출과 관련하여 가장 최근에 설치되고 가장 깊게 중첩된 예외 처리기)의 필터를 실행합니다.

1. 이 필터가 제어를 전달하는 경우(0을 반환함) 제어를 전달하지 않는 필터가 발견될 때까지 프로세스가 계속됩니다.

1. 이 필터-1이 반환 하는 경우 예외가 발생 했습니다 종료가 발생 하지 않았고 계속 실행.

1. 필터가 1을 반환하는 경우 다음 이벤트가 발생합니다.

   - 시스템이 현재 실행 중인 코드(예외가 발생한 코드)와 제어를 획득하는 예외 처리기가 포함된 스택 프레임 사이의 모든 스택 프레임을 지우며 스택을 해제합니다.

   - 스택이 해제되면서 스택의 각 종료 처리기가 실행됩니다.

   - 예외 처리기 자체가 실행됩니다.

   - 코드 줄에서 이 예외 처리기 끝 다음으로 제어가 전달됩니다.

## <a name="see-also"></a>참고자료

[종료 처리기 작성](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)