---
title: '방법: 병렬 루프에서 중단을 처리 하는 예외 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
ms.openlocfilehash: 19d732d98f24172471d96cd5e2962b2a99ab0203
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409995"
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>방법: 병렬 루프에서 중단을 처리 하는 예외 사용

이 항목에서는 기본적인 트리 구조에 대 한 검색 알고리즘을 작성 하는 방법을 보여 줍니다.

항목 [취소](cancellation-in-the-ppl.md) 병렬 패턴 라이브러리에서의 취소 역할에 설명 합니다. 예외 처리의 사용은 덜 효율적인 방법 사용 보다 병렬 작업을 취소 하는 [concurrency::task_group::cancel](reference/task-group-class.md#cancel) 하 고 [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) 메서드. 그러나 적절 한 작업을 취소 하는 예외 처리 사용 되는 경우에 작업 또는 병렬 알고리즘을 사용 하지만 제공 하지 않습니다 하는 타사 라이브러리를 호출을 `task_group` 또는 `structured_task_group` 취소 하는 개체입니다.

## <a name="example"></a>예제

다음 예제에서는 기본 `tree` 데이터 요소 및 자식 노드의 목록을 포함 하는 형식입니다. 다음 섹션의 본문을 보여 줍니다.는 `for_all` 메서드, 각 자식 노드에서 작업 함수를 재귀적으로 수행 합니다.

[!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]

## <a name="example"></a>예제

다음 예제는 `for_all` 메서드. 사용 된 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 병렬로 트리의 각 노드에서 작업 함수를 수행 하는 알고리즘입니다.

[!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]

## <a name="example"></a>예제

다음 예제에서는 제공된 `tree` 개체에서 값을 검색하는 `search_for_value` 함수를 보여 줍니다. 이 함수에 전달 된 `for_all` 메서드는 제공 된 값이 포함 된 트리 노드를 발견 하면 throw 되는 작업 함수입니다.

가정 된 `tree` 클래스는 타사 라이브러리를 통해 제공 됩니다 및 수정할 수 없습니다. 이 경우 예외 처리를 사용 하 여 적합 한 때문에 합니다 `for_all` 메서드를 제공 하지 않습니다는 `task_group` 또는 `structured_task_group` 호출자에 게 개체입니다. 따라서 작업 함수를 직접 부모 작업 그룹을 취소할 수 아닙니다.

작업 그룹에 제공 하는 작업 함수에서 예외를 throw 하는 경우 런타임에서 자식 작업 그룹 등의 작업 그룹에 있는 모든 작업을 중지 하 고 아직 시작 되지 않은 모든 작업을 삭제 합니다. 합니다 `search_for_value` 함수는 `try` - `catch` 블록이 예외를 캡처하고 결과를 콘솔에 인쇄 합니다.

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]

## <a name="example"></a>예제

다음 예제에서는 `tree` 개체를 동시에 여러 값을 검색 합니다. `build_tree` 함수는이 항목의 뒷부분에 표시 됩니다.

[!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]

이 예제에서는 합니다 [concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) 병렬로 값을 검색 하는 알고리즘입니다. 이 알고리즘에 대 한 자세한 내용은 참조 하세요. [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

## <a name="example"></a>예제

다음 전체 예제는 기본적인 트리 구조에서 값을 검색 하려면 예외 처리를 사용 합니다.

[!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]

이 예제에서는 다음 샘플 출력을 생성합니다.

```Output
Found a node with value 32614.
Found a node with value 86131.
Did not find node with value 17522.
```

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `task-tree-search.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc task-tree-search.cpp**

## <a name="see-also"></a>참고자료

[PPL에서의 취소](cancellation-in-the-ppl.md)<br/>
[예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[task_group 클래스](reference/task-group-class.md)<br/>
[structured_task_group 클래스](../../parallel/concrt/reference/structured-task-group-class.md)<br/>
[parallel_for_each 함수](reference/concurrency-namespace-functions.md#parallel_for_each)
