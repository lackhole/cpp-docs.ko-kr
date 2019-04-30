---
title: '방법: 동시성 런타임을 사용 하 여 예외 처리를 사용 하는 OpenMP 루프 변환'
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
ms.openlocfilehash: 118cf3e485fa78ae3eaa5efe34708924b89d6588
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296386"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>방법: 동시성 런타임을 사용 하 여 예외 처리를 사용 하는 OpenMP 루프 변환

이 예제에는 OpenMP를 변환 하는 방법을 보여 줍니다 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 동시성 런타임에서 예외 처리 메커니즘을 사용 하는 예외 처리를 수행 하는 루프입니다.

Openmp에서는 병렬 영역에서 throw 되는 예외를 포착 하 고 동일한 스레드에서 동일한 지역에서 처리 합니다. 병렬 영역을 벗어나는 예외는 기본적으로 프로세스를 종료 하는 처리 되지 않은 예외 처리기에 의해 발견 되었습니다.

와 같은 작업 그룹에 전달 하는 작업 함수의 본문에서 예외를 throw 하는 경우 동시성 런타임에서 [concurrency:: task_group](reference/task-group-class.md) 하거나 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체 또는 와 같은 병렬 알고리즘 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for), 런타임에서 해당 예외를 저장 하 고 작업 그룹을 완료 하는 알고리즘에 대 한 대기 하는 컨텍스트에 마샬링합니다. 작업 그룹에 대 한 대기 컨텍스트가 호출 하는 컨텍스트로 [concurrency::task_group::wait](reference/task-group-class.md#wait)하십시오 [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait), [concurrency::task_group::run_and _wait](reference/task-group-class.md#run_and_wait), 또는 [concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait)합니다. 병렬 알고리즘에 대 한 대기 중인 컨텍스트는 해당 알고리즘을 호출 하는 컨텍스트입니다. 런타임에서 또한 자식 작업 그룹을 포함 하 여 작업 그룹에 있는 모든 활성 작업을 중지 하 고 아직 시작 되지 않은 모든 작업을 무시 합니다.

## <a name="example"></a>예제

이 예제에서는 OpenMP에서 예외를 처리 하는 방법을 보여 줍니다 `parallel` 지역에 대 한 호출 `parallel_for`합니다. 합니다 `do_work` 함수가 성공 하지 못하고 따라서 형식의 예외를 throw 하는 메모리 할당 요청을 수행 [std:: bad_alloc](../../standard-library/bad-alloc-class.md)합니다. OpenMP를 사용 하는 버전에서는 예외를 throw 하는 스레드 해야도 catch 합니다. 즉, OpenMP 병렬 루프 반복 될 때마다 예외를 처리 해야 합니다. 동시성 런타임을 사용 하는 버전을 주 스레드가 다른 스레드에 의해 throw 되는 예외를 catch 합니다.

[!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-exception-handling_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
Using OpenMP...
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
An error of type 'class std::bad_alloc' occurred.
Using the Concurrency Runtime...
An error of type 'class std::bad_alloc' occurred.
```

OpenMP를 사용 하는이 예제의 버전에서는 예외에서 발생 하 고 각 루프 반복에서 처리 됩니다. 동시성 런타임을 사용 하는 버전에서 런타임 예외를 저장, 모든 활성 작업을 중지, 작업을 시작 하 고, 아직 처리 하지 않은 취소 및 예외를 호출 하는 컨텍스트에 마샬링합니다 `parallel_for`합니다.

OpenMP를 사용 하는 버전 예외 발생 후 종료 되는, 필요한 경우에 오류가 발생 한 다른 루프 반복을 알리기 위해 부울 플래그를 사용할 수 있습니다. 항목의 예제와 같이 [방법: 동시성 런타임을 사용 하 여 사용 하 여 취소를 사용 하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), 후속 루프 반복 플래그를 설정 하는 경우 아무 작업도 하지 않습니다. 반대로, 예외 발생 후 동시성 런타임을 사용 하는 루프가 계속 되는, 필요한 경우 자체 병렬 루프 본문에서 예외를 처리 합니다.

동시성 런타임에서 비동기 에이전트 및 간단한 작업 등의 다른 구성 요소는 예외를 전송 하지 않습니다. 대신, 처리 되지 않은 예외는 기본적으로 프로세스를 종료 하는 처리 되지 않은 예외 처리기를 합니다. 예외 처리에 대 한 자세한 내용은 참조 하세요. [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.

에 대 한 자세한 내용은 `parallel_for` 및 기타 병렬 알고리즘을 참조 하십시오 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `concrt-omp-exceptions.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc /openmp concrt-omp-exceptions.cpp**

## <a name="see-also"></a>참고자료

[OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)
