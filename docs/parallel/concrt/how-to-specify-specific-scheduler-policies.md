---
title: '방법: 특정 스케줄러 정책 지정'
ms.date: 11/04/2016
helpviewer_keywords:
- specifying scheduler policies [Concurrency Runtime]
- scheduler policies, specifying [Concurrency Runtime]
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
ms.openlocfilehash: 3c03ef6661ebefe0bfe9fab62938ce9987a4bca1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410034"
---
# <a name="how-to-specify-specific-scheduler-policies"></a>방법: 특정 스케줄러 정책 지정

스케줄러 정책을 스케줄러가 작업을 관리할 때 사용 하는 전략을 제어할 수 있습니다. 이 항목에서는 콘솔에 진행률 표시기를 출력 하는 작업의 스레드 우선 순위를 높이기 위해 스케줄러 정책을 사용 하는 방법을 보여 줍니다.

비동기 에이전트와 함께 사용자 지정 스케줄러 정책을 사용 하는 예제를 보려면 [방법: 특정 스케줄러 정책을 사용 하는 에이전트 만들기](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 동시에 두 가지 작업을 수행 합니다. 첫 번째 태스크에서는 n 계산<sup>th</sup> 피보나치 수 있습니다. 두 번째 작업은 콘솔에 진행률 표시기를 인쇄합니다.

첫 번째 작업 재귀 분해를 사용 하 여 피보나치 수를 계산 합니다. 즉, 각 작업 재귀적으로 전체 결과 계산 하는 하위 작업을 만듭니다. 재귀 분해를 사용 하는 작업 사용 가능한 모든 리소스를 사용 하 고 있으므로 다른 작업을 고갈 수 있습니다. 이 예제에서는 작업 진행률 표시기를 출력 하는 컴퓨팅 리소스에 대 한 시기 적절 하 게 액세스를 받지 못할 수 있습니다.

이 예제에서는 컴퓨팅 리소스에는 진행률 메시지 공정한 액세스를 출력 하는 작업을 제공 하려면에 설명 된 단계를 사용 [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) 사용자 지정 정책이 적용 된 스케줄러 인스턴스를 만들려고 합니다. 사용자 지정 정책에 가장 높은 우선 순위 클래스를 스레드 우선 순위를 지정 합니다.

이 예제에서는 합니다 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 하 고 [concurrency:: timer](../../parallel/concrt/reference/timer-class.md) 진행률 표시기를 인쇄 하는 클래스입니다. 이러한 클래스에 대 한 참조를 사용 하는 생성자의 버전에는 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 예약 하는 개체입니다. 이 예제에서는 기본 스케줄러를 사용 하 여 피보나치 수를 계산 하는 진행률 표시기를 출력 하는 작업을 예약 하려면 스케줄러 인스턴스는 작업을 예약.

사용자 지정 정책이 적용 된 스케줄러를 사용 하는 이점은 보여 주기 위해이 예제에서는 두 번 전체 작업을 수행 합니다. 이 예제에서는 먼저 기본 스케줄러를 사용 하 여 두 작업을 예약 합니다. 다음 예제에서는 첫 번째 작업을 예약 하려면 기본 스케줄러 및 두 번째 태스크를 예약 하는 사용자 지정 정책이 적용 된 스케줄러를 사용 합니다.

[!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/cpp/how-to-specify-specific-scheduler-policies_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
Default scheduler:
...........................................................................done
Scheduler that has a custom policy:
...........................................................................done
```

집합 작업을 모두 동일한 결과 생성, 사용자 지정 정책을 사용 하는 버전 반응성 동작 하 게 높은 우선 순위에서 실행 되도록 진행률 지표를 출력 하는 작업이 활성화 됩니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `scheduler-policy.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc 스케줄러-policy.cpp**

## <a name="see-also"></a>참고자료

[스케줄러 정책](../../parallel/concrt/scheduler-policies.md)<br/>
[방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[방법: 특정 스케줄러 정책을 사용하는 에이전트 만들기](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
