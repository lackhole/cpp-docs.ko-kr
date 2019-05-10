---
title: '방법: Parallel_invoke 병렬 작업 실행을 사용 하 여'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
ms.openlocfilehash: d618b5f202c6aaf454a60f4f37211d9000600562
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345658"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>방법: Parallel_invoke 병렬 작업 실행을 사용 하 여

사용 하는 방법을 보여 주는이 예제는 [concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) 공유 데이터 원본에 대해 여러 작업을 수행 하는 프로그램의 성능을 향상 하는 알고리즘입니다. 작업이 없는 소스를 수정 하기 때문에 실행할 수 있습니다 동시에 간단한 방법으로.

## <a name="example"></a>예제

형식의 변수를 만드는 다음 코드 예제를 고려해 야 `MyDataType`, 해당 변수를 초기화 하는 함수를 호출 하 고 그런 다음 해당 데이터에 대해 여러 시간이 오래 걸리는 작업을 수행 합니다.

[!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]

경우는 `lengthy_operation1`, `lengthy_operation2`, 및 `lengthy_operation3` 함수를 수정 하지 마십시오는 `MyDataType` 변수를 이러한 함수 실행할 수 있습니다 추가로 수정 하지 않고 병렬로 합니다.

## <a name="example"></a>예제

다음 예제에서는 이전 예제를 병렬로 실행을 수정 합니다. `parallel_invoke` 알고리즘 병렬로 각 태스크를 실행 하 고 모든 작업이 완료 된 후 반환 합니다.

[!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]

## <a name="example"></a>예제

다음 예제에서는 다운로드 *The Iliad* 여 Homer gutenberg.org에서 해당 파일에 대해 여러 작업을 수행 합니다. 예제에서는 먼저 이러한 작업을 순차적으로 수행 하 고 병렬로 동일한 작업을 수행 합니다.

[!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]

이 예제에서는 다음 샘플 출력을 생성합니다.

```Output
Downloading 'The Iliad'...

Running serial version... took 953 ms.
Running parallel version... took 656 ms.

The most common words that have five or more letters are:
    their (953)
    shall (444)
    which (431)
    great (398)
    Hector (349)
    Achilles (309)
    through (301)
    these (268)
    chief (259)
The longest sequence of words that have the same first letter is:
    through the tempest to the tented
The following palindromes appear in the text:
    spots stops
    speed deeps
    keels sleek
```

이 예제에서는 `parallel_invoke` 알고리즘 여러 호출을 동일한 데이터 소스에서 작동 하는 함수입니다. 사용할 수는 `parallel_invoke` 뿐만 아니라 동일한 데이터에서 작동 하는 동시에 모든 일련의 함수를 호출 하는 알고리즘입니다.

때문에 `parallel_invoke` 동시에 각 작업 함수를 호출 하는 알고리즘, 성능과 완료 될 때 (즉, 런타임이 각 함수는 별도 프로세서에서 처리) 가장 긴 시간이 소요 되는 함수에 의해 제한 됩니다. 사용 가능한 프로세서 수보다 병렬로 더 많은 작업을 수행 하는이 예제를 여러 태스크는 각 프로세서에서 실행할 수 있습니다. 이 경우 성능 완료 가장 긴 시간이 소요 되는 작업 그룹에 의해 제한 됩니다.

이 예제에서는 세 가지 작업이 병렬로으로 수행 하므로 세 개 이상의 프로세서가 있는 컴퓨터의 크기를 조정 하는 성능을 기대할 수 없습니다. 자세한 성능 향상을 위해 더 작은 작업으로 오래 실행 작업을 중단할 수 있으며 병렬로 해당 작업을 실행할 수 있습니다.

사용할 수는 `parallel_invoke` 대신 알고리즘 합니다 [concurrency:: task_group](reference/task-group-class.md) 및 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 취소에 대 한 지원이 필요 하지 않은 경우 클래스입니다. 사용법을 비교 하는 예제는 `parallel_invoke` 알고리즘과 작업 그룹 참조 [방법: Parallel_invoke를 사용 하 여 병렬 정렬 루틴 작성](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)합니다.

## <a name="compiling-the-code"></a>코드 컴파일

컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 넣습니다와 라는 파일에 붙여 `parallel-word-mining.cpp` Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

**cl.exe /EHsc /MD /DUNICODE /D_AFXDLL parallel-word-mining.cpp**

## <a name="see-also"></a>참고자료

[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_invoke 함수](reference/concurrency-namespace-functions.md#parallel_invoke)
