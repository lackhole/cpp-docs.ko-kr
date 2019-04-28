---
title: '연습: 이미지 처리 네트워크 만들기'
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 035d73190f3596044a35cbc45681807801385eab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205837"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>연습: 이미지 처리 네트워크 만들기

이 문서에는 이미지 처리를 수행 하는 비동기 메시지 블록의 네트워크를 만드는 방법을 보여 줍니다.

네트워크의 특성을 기준으로 이미지에서 수행할 작업을 결정 합니다. 이 예제에서는 합니다 *데이터 흐름* 네트워크를 통해 이미지 경로 모델입니다. 데이터 흐름 모델에서는, 프로그램의 개별 구성 요소가 메시지를 전달하여 서로 통신합니다. 구성 요소는 메시지를 받으면 수 작업을 수행 하 고 다른 구성 요소에 해당 작업의 결과 전달 합니다. 사용 하 여이 비교 합니다 *제어 흐름* 모델, 응용 프로그램을 사용 하는 제어 구조 예를 들어, 조건문, 루프 및 제어 프로그램에서 작업 순서를 합니다.

데이터 흐름을 기반으로 하는 네트워크를 만듭니다는 *파이프라인* 작업 합니다. 파이프라인의 각 단계는 동시에 전체 작업의 일부를 수행합니다. 이는 자동차 제조 조립 라인에 비유될 수 있습니다. 각 자동차 어셈블리 라인을 통과할 때 조립 프레임, 엔진 및 등 다른 설치 합니다. 여러 대의 자동차를 동시에 조립할 수를 사용 하 여 어셈블리 라인 한 번에 한 자동차의 전체를 조립 하는 보다 더 나은 처리량을 제공 합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 시작 하기 전에 다음 문서를 읽어 보십시오.

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [방법: 메시지 블록 필터 사용](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

이 연습을 시작 하기 전에 GDI +의 기본을 이해 하는 것이 좋습니다.

##  <a name="top"></a> 섹션

이 연습에는 다음과 같은 섹션이 있습니다.

- [이미지 처리 기능을 정의 합니다.](#functionality)

- [이미지 처리 네트워크 만들기](#network)

- [전체 예제](#complete)

##  <a name="functionality"></a> 이미지 처리 기능을 정의 합니다.

이 섹션에서는 이미지 처리 네트워크를 사용 하 여 디스크에서 읽은 이미지를 사용 하 여 작업 지원 기능을 보여 줍니다.

다음 함수를 `GetRGB` 고 `MakeColor`를 추출 하 고 각각 지정된 된 색의 개별 구성 요소를 결합 합니다.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

다음 함수 `ProcessImage`, 호출을 지정 [std:: function](../../standard-library/function-class.md) GDI +의 각 픽셀의 색 값을 변환할 개체 [비트맵](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap) 개체입니다. 합니다 `ProcessImage` 함수는 합니다 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 병렬로 비트맵의 각 행을 처리 하는 알고리즘입니다.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

다음 함수를 `Grayscale`, `Sepiatone`, `ColorMask`, 및 `Darken`를 호출 합니다 `ProcessImage` 각 픽셀의 색 값을 변환 하는 함수를 `Bitmap` 개체. 이러한 각 함수는 람다 식 사용 하 여 정의 1 픽셀의 색 변환 합니다.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

다음 함수 `GetColorDominance`를 호출 합니다 `ProcessImage` 함수입니다. 그러나 각 색의 값을 변경 하는 대신이 함수를 사용 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 빨간색, 녹색 또는 파란색 구성 요소는 이미지 지배 여부를 계산 하는 개체입니다.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

다음 함수를 `GetEncoderClsid`, 인코더의 지정된 된 MIME 형식에 대 한 클래스 식별자를 검색 합니다. 이 함수를 사용 하 여 비트맵에 대 한 인코더를 검색 하는 응용 프로그램입니다.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[맨 위로 이동](#top)]

##  <a name="network"></a> 이미지 처리 네트워크 만들기

이 섹션에는 지정된 된 디렉터리에서 모든 JPEG (.jpg) 이미지에서 이미지 처리를 수행 하는 비동기 메시지 블록의 네트워크를 만드는 방법을 설명 합니다. 네트워크에는 다음 이미지 처리 작업을 수행합니다.

1. Tom이 작성 하는 모든 이미지에 대 한을 회색조로 변환 합니다.

1. 주요 색상으로 red에 있는 모든 이미지에 대 한 녹색 및 파랑 구성 요소를 제거 하 고 어둡게 만듭니다.

1. 다른 이미지에 대 한 세피아 톤을 적용 합니다.

네트워크에는 다음이 조건 중 하나가 일치 하는 첫 번째 이미지 처리 작업만 적용 됩니다. 예를 들어 이미지 Tom이 작성이 있고 해당 주요 색상으로 red, 이미지를 회색조만 변환 됩니다.

네트워크에서 각 이미지 처리 작업을 수행한 후이 이미지를 디스크에 파일로 저장 비트맵 (.bmp).

다음 단계에는이 이미지 처리 네트워크를 구현 하 고 지정된 된 디렉터리에서 모든 JPEG 이미지에 해당 네트워크를 적용 하는 함수를 만드는 방법을 보여 줍니다.

#### <a name="to-create-the-image-processing-network"></a>이미지 처리 네트워크를 만들려면

1. 함수 만들기 `ProcessImages`를 디스크에 디렉터리의 이름을 사용 하는 합니다.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. 에 `ProcessImages` 함수를 만들기는 `countdown_event` 변수입니다. `countdown_event` 클래스는이 연습의 뒷부분에서 표시 됩니다.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. 만들기는 [std:: map](../../standard-library/map-class.md) 연결 하는 개체는 `Bitmap` 원래 파일 이름으로는 개체입니다.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. 이미지 처리 네트워크의 멤버를 정의 하는 다음 코드를 추가 합니다.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. 네트워크를 연결 하는 다음 코드를 추가 합니다.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. 보낼 네트워크의 머리에 각 JPEG 파일의 전체 경로 디렉터리에 다음 코드를 추가 합니다.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. 대기는 `countdown_event` 변수를 0에 도달 합니다.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

다음 표에서는 네트워크의 멤버를 설명합니다.

|멤버|설명|
|------------|-----------------|
|`load_bitmap`|A [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) 로드 하는 개체를 `Bitmap` 디스크에서 개체 및 항목을 추가 합니다 `map` 원래 파일 이름으로 이미지를 연결 하는 개체입니다.|
|`loaded_bitmaps`|A [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 로드 된 이미지를 이미지 처리 필터에 보내는 개체입니다.|
|`grayscale`|`transformer` 회색조 tom 작성 한 이미지를 변환 하는 개체입니다. 이미지의 메타 데이터를 사용 하 여 작성자를 확인 합니다.|
|`colormask`|`transformer` 빨간색 주요 색상으로 포함 하는 이미지에서 녹색 및 파랑 색 구성 요소를 제거 하는 개체입니다.|
|`darken`|`transformer` 빨간색 주요 색상으로 포함 하는 이미지 어둡게 하는 개체입니다.|
|`sepiatone`|`transformer` 세피아 톤 Tom 작성 하지 않고 없고 주로 빨간색 되지 않은 이미지를 적용 하는 개체입니다.|
|`save_bitmap`|A `transformer` 처리를 저장 하는 개체 `image` 비트맵으로 디스크에 있습니다. `save_bitmap` 원래 파일 이름을 검색 합니다 `map` 개체 및.bmp 파일 이름 확장명이 변경 합니다.|
|`delete_bitmap`|`transformer` 이미지에 대 한 메모리를 해제 하는 개체입니다.|
|`decrement`|A [concurrency:: call](../../parallel/concrt/reference/call-class.md) 네트워크의 터미널 노드 역할을 하는 개체입니다. 이 감소는 `countdown_event` 이미지로 처리 되는 기본 응용 프로그램에 알리기 위해 개체입니다.|

합니다 `loaded_bitmaps` 메시지 버퍼는 중요 한 때문으로 `unbounded_buffer` 개체를 제공 `Bitmap` 개체를 여러 수신자입니다. 대상 블록을 허용 하는 경우는 `Bitmap` 개체를 `unbounded_buffer` 개체는 제공 하지 않습니다 `Bitmap` 다른 대상 개체입니다. 개체를 연결 하는 순서 따라서는 `unbounded_buffer` 개체는 중요 합니다. 합니다 `grayscale`, `colormask`, 및 `sepiatone` 메시지 블록에는 각 필터를 사용 하 여 적용할 특정 `Bitmap` 개체입니다. `decrement` 메시지 버퍼가의 중요 한 대상 합니다 `loaded_bitmaps` 메시지 버퍼를 모두 허용 하므로 `Bitmap` 다른 메시지 버퍼에 의해 거부 된 개체입니다. `unbounded_buffer` 개체는 순서 대로 메시지를 전파 해야 합니다. 따라서는 `unbounded_buffer` 개체를 새 대상 블록에 연결 되어 있고 해당 메시지를 수락 하는 현재 대상 블록이 없는 경우 메시지를 수락 될 때까지 차단 합니다.

응용 프로그램 메시지를 먼저 메시지를 수락 하는 하나의 메시지 블록 바로 대신 프로세스를 차단 하는 여러 메시지에 필요한 경우 사용할 수 다른 메시지 블록 형식을 같은 `overwrite_buffer`합니다. `overwrite_buffer` 클래스는 한 번에 하나의 메시지를 포함 하지만 해당 메시지를 각 대상에 전파 합니다.

다음 그림에서는 이미지 처리 네트워크를 보여줍니다.

![이미지 처리 네트워크](../../parallel/concrt/media/concrt_imageproc.png "이미지 처리 네트워크")

`countdown_event` 이 예제의 개체에에서 모든 이미지 처리 되 면 기본 응용 프로그램을 알리기 위해 이미지 처리 네트워크를 사용 하도록 설정 합니다. 합니다 `countdown_event` 클래스가 사용 하는 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 카운터 값을 0에 도달할 때 신호를 보내는 개체입니다. 주 응용 프로그램 네트워크에 파일 이름을 보낼 때마다 카운터를 증가 시킵니다. 네트워크 감소의 터미널 노드 각 이미지 처리 된 후 카운터입니다. 대기 후 지정된 된 디렉터리를 통과 하는 기본 응용 프로그램에는 `countdown_event` 해당 카운터를 0에 도달 했음을 알리기 위해 개체입니다.

다음 예제는 `countdown_event` 클래스:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[맨 위로 이동](#top)]

##  <a name="complete"></a> 전체 예제

다음 코드에서는 전체 예제를 보여 줍니다. `wmain` 함수 호출 및 GDI + 라이브러리를 관리 합니다 `ProcessImages` JPEG 처리할 함수를 파일는 `Sample Pictures` 디렉터리.

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

다음 그림은 샘플 출력을 보여 줍니다. 각 원본 이미지는 해당 수정 된 이미지 위에 있습니다.

![샘플 출력 예제](../../parallel/concrt/media/concrt_imageout.png "예제에 대 한 출력 샘플")

`Lighthouse` Tom Alphin 하 여 작성 된 하 고 따라서 회색조로 변환 됩니다. `Chrysanthemum``Desert`, `Koala`, 및 `Tulips` 빨간색 주요 색상으로 및 따라서 녹색 및 파랑 색 구성 요소를 제거 있고 짙게 됩니다. `Hydrangeas`를 `Jellyfish`, 및 `Penguins` 기본 기준과 일치 되며 따라서 toned 세피아 합니다.

[[맨 위로 이동](#top)]

### <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `image-processing-network.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /DUNICODE /EHsc image-processing-network.cpp /link gdiplus.lib**

## <a name="see-also"></a>참고자료

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
