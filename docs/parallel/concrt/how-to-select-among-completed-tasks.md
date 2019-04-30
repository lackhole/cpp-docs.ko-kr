---
title: '방법: 완료 된 작업 간 선택'
ms.date: 11/04/2016
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
ms.openlocfilehash: 0d31f9bd16aaa70cc773e60e4f1193e66ec520f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205644"
---
# <a name="how-to-select-among-completed-tasks"></a>방법: 완료 된 작업 간 선택

사용 하는 방법을 보여 주는이 예제는 [concurrency:: choice](../../parallel/concrt/reference/choice-class.md) 하 고 [concurrency:: join](../../parallel/concrt/reference/join-class.md) 검색 알고리즘을 완료 하려면 첫 번째 작업을 선택 하는 클래스입니다.

## <a name="example"></a>예제

다음 예제에서는 두 가지 검색 알고리즘을 병렬로 수행 하 고 완료 하는 첫 번째 알고리즘을 선택 합니다. 이 예제에서는 정의 된 `employee` 직원에 대 한 숫자 식별자 및 급여를 보유 하는 형식입니다. `find_employee` 함수는 제공 된 식별자가 제공 된 급여는 첫 번째 직원을 찾습니다. `find_employee` 함수도 없는 직원의 급여를 제공 된 식별자에 있는 경우를 처리 합니다. 합니다 `wmain` 함수 배열을 만들고 `employee` 개체와 여러 식별자와 급여 값을 검색 합니다.

이 예제에서는 사용 된 `choice` 다음 경우 중에서 선택할 개체:

1. 제공된 된 식별자를가지고 있는 직원 존재 합니다.

1. 제공 된 급여를가지고 있는 직원 존재 합니다.

1. 제공 된 식별자가 급여 하는 직원이 없는 존재 합니다.

예제에서는 처음 두 경우는 [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) 식별자와 다른 개체 `single_assignment` 급여를 보유 하는 개체입니다. 이 예제에서는 사용을 `join` 세 번째 경우에 대 한 개체입니다. 합니다 `join` 두 개의 추가 개체를 구성 `single_assignment` 없는 직원은 제공 된 식별자가 있는 경우 및 제공 된 급여를 포함 하는 직원이 없는 경우에 대 한 개체입니다. `join` 개체는 해당 멤버의 각 메시지를 받을 때 메시지를 보냅니다. 이 예제는 `join` 또는 급여 개체는 제공 된 식별자 직원이 없는 경우 메시지를 보냅니다.

이 예제에서는 사용을 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체가 검색 알고리즘 모두 병렬로 실행 합니다. 각 검색 작업 중 하나에 쓰는 `single_assignment` 은 지정 된 직원이 있는지 여부를 나타내는 개체입니다. 이 예제에서는 사용 합니다 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 함수는 메시지를 포함 하는 첫 번째 버퍼의 인덱스를 및 `switch` 블록 결과를 출력 합니다.

[!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
Employee with id 14758 has salary 27780.00.
Employee with salary 29150.00 has id 84345.
Employee with id 61935 has salary 29905.00.
No employee has id 899 or salary 31223.00.
```

이 예제에서는 합니다 [concurrency::make_choice](reference/concurrency-namespace-functions.md#make_choice) 도우미 함수를 만드는 `choice` 개체 및 [concurrency::make_join](reference/concurrency-namespace-functions.md#make_join) 도우미 함수를 만드는 `join` 개체입니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `find-employee.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc 찾기-employee.cpp**

## <a name="see-also"></a>참고자료

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)<br/>
[choice 클래스](../../parallel/concrt/reference/choice-class.md)<br/>
[join 클래스](../../parallel/concrt/reference/join-class.md)
