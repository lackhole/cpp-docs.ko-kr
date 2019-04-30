---
title: '방법: Parallel_for 루프 작성'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
ms.openlocfilehash: d6ac30a5de0ff45adad1064aeab708e6a84f5e9f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346370"
---
# <a name="how-to-write-a-parallelfor-loop"></a>방법: Parallel_for 루프 작성

이 예제에 사용 하는 방법을 보여 줍니다 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 두 행렬의 곱을 계산 합니다.

## <a name="example"></a>예제

다음 예제는 `matrix_multiply` 함수는 두 사각형 행렬의 곱을 계산 합니다.

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example"></a>예제

다음 예제에서는 합니다 `parallel_matrix_multiply` 함수를 사용 하는 `parallel_for` 외부 루프는 병렬로 수행 하는 알고리즘입니다.

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

이 예제에서는 병렬 처리에 대 한 오버 헤드의 이점을 얻기 위해 충분 한 작업을 수행 하므로만 외부 루프를 평행 화 합니다. 내부 루프를 평행 화 하는 경우 하지 받게 향상 된 성능이 있으므로 약간 내부 루프를 수행 하는 작업의 병렬 처리의 오버 헤드 보다 크지 않습니다. 따라서 외부 루프만 병렬 처리하는 것이 대부분의 시스템에서 동시성의 이점을 극대화하는 가장 좋은 방법입니다.

## <a name="example"></a>예제

다음의 성능을 비교 하는 자세한 예제는 `matrix_multiply` 비교 함수는 `parallel_matrix_multiply` 함수입니다.

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>코드 컴파일

컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 넣습니다와 라는 파일에 붙여 `parallel-matrix-multiply.cpp` Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

**cl.exe /EHsc 병렬-행렬-multiply.cpp**

## <a name="see-also"></a>참고자료

[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for 함수](reference/concurrency-namespace-functions.md#parallel_for)
