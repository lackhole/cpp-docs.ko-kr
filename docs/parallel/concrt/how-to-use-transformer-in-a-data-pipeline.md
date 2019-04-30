---
title: '방법: 데이터 파이프라인에서 transformer 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
ms.openlocfilehash: 59c4854eea985b3c91fad6e7dc6c47ca9b07d333
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375589"
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>방법: 데이터 파이프라인에서 transformer 사용

이 항목에서는 사용 하는 방법을 보여 주는 기본 예제가 포함 된 [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) 데이터 파이프라인에 클래스입니다. 이미지 처리를 수행 하는 데이터 파이프라인을 사용 하는 자세한 예제를 참조 하세요. [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)합니다.

*데이터 파이프라인* 동시 프로그래밍의 일반적인 패턴입니다. 데이터 파이프라인은 일련의 단계로, 여기서 각 단계 작업을 수행 하 고 다음 단계로 해당 작업의 결과 전달 합니다 이루어져 있습니다. `transformer` 클래스 데이터의 핵심 구성 요소는 파이프라인 입력된 값을 수신 하기 때문에 해당 값의 작업을 수행 하 고 후 결과 사용 하는 다른 구성 요소에 대해 생성 합니다.

## <a name="example"></a>예제

이 예제에서는 일련의 초기 입력된 값을 지정 하는 변환 수행 하려면 다음 데이터 파이프라인을 사용 합니다.

1. 첫 번째 단계는 해당 입력의 절대값을 계산합니다.

1. 두 번째 단계는 해당 입력의 제곱근을 계산합니다.

1. 세 번째 단계는 해당 입력의 제곱을 계산합니다.

1. 단계에서 입력을 부정 하는 명시 합니다.

1. 다섯 번째 단계는 메시지 버퍼를 최종 결과 씁니다.

마지막으로 콘솔에 파이프라인의 결과 출력합니다.

[!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]

이 예제는 다음과 같은 출력을 생성합니다.

```Output
The result is -42.
```

입력 값에서과 형식이 다른 값을 출력 데이터 파이프라인의 단계에 대 한 것이 일반적입니다. 이 예제에서 두 번째 단계는 형식의 값입니다 `int` 입력으로 해당 값의 제곱근을 생성 하 고 (을 `double`) 출력으로 합니다.

> [!NOTE]
>  이 예제에서 데이터 파이프라인은 그림입니다. 각 변환 작업에서 약간의 작업으로 수행 하므로 메시지 전달 하는 데 오버 헤드가 필요한 수의 이점을 능가 데이터 파이프라인을 사용 하 여 합니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `data-pipeline.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc data-pipeline.cpp**

## <a name="see-also"></a>참고자료

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)
