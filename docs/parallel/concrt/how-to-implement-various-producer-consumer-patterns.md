---
title: '방법: 다양 한 생산자-소비자 패턴 구현'
ms.date: 11/04/2016
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
ms.openlocfilehash: 113518e97b6715384b5e7b84b0d0eab63dfcfcc7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411359"
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>방법: 다양 한 생산자-소비자 패턴 구현

이 항목에서는 응용 프로그램에서 생산자-소비자 패턴을 구현 하는 방법을 설명 합니다. 이 패턴에서 *생산자*는 메시지 블록에 메시지를 보내고 *소비자*는 해당 블록에서 메시지를 읽습니다.

항목에서는 두 가지 시나리오를 보여 줍니다. 첫 번째 시나리오를 소비자 생산자를 전송 하는 각 메시지를 수신 해야 합니다. 두 번째 시나리오에서는 소비자 데이터를 정기적으로 폴링합니다 및 따라서 각 메시지를 수신 하지 않아도 됩니다.

이 항목의 두 예제 생산자는 소비자에 게 메시지를 전송할 에이전트, 메시지 블록 및 메시지 전달 함수를 사용 합니다. 공급자 에이전트를 사용 합니다 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 함수에 메시지 쓰기를 [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md) 개체입니다. 소비자 에이전트가 사용 합니다 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 메시지를 읽을 함수는 [concurrency:: isource](../../parallel/concrt/reference/isource-class.md) 개체입니다. 에이전트를 모두 처리의 끝을 조정 하는 데 센티널 값을 보유 합니다.

비동기 에이전트에 대 한 자세한 내용은 참조 하십시오 [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)합니다. 메시지 블록 및 메시지 전달 함수에 대 한 자세한 내용은 참조 하세요. [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md) 하 고 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)합니다.

## <a name="example"></a>예제

이 예제에서는 공급자 에이전트를 소비자 에이전트 일련의 숫자를 보냅니다. 소비자는 이러한 각 숫자 받고 해당 평균을 계산 합니다. 응용 프로그램 평균을 콘솔에 씁니다.

이 예에서는 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 큐 메시지 생산자를 사용 하도록 설정 하는 개체입니다. 합니다 `unbounded_buffer` 클래스 구현 `ITarget` 고 `ISource` 생산자와 소비자 보내고 공유 버퍼에서 메시지를 주고받을 수 있도록 합니다. 합니다 `send` 고 `receive` 소비자에 게 데이터 생산자를 전파 하는 작업을 조정 하는 함수입니다.

[!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
The average is 50.
```

## <a name="example"></a>예제

이 예제에서는 공급자 에이전트 소비자 에이전트에는 일련의 주식 시세를 보냅니다. 소비자 에이전트는 현재 시세 주기적으로 읽고 콘솔에 출력 합니다.

이 예제에서는 이전 예제와 유사를 사용 하는 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 개체를 하나의 메시지 소비자와 공유 하는 생산자를 사용 합니다. 이전 예에서 같이 `overwrite_buffer` 클래스 구현 `ITarget` 고 `ISource` 생산자와 소비자는 공유 메시지 버퍼에서 작동할 수 있도록 합니다.

[!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]

이 예제에서는 다음 샘플 출력을 생성합니다.

```Output
Current quote is 24.44.
Current quote is 24.44.
Current quote is 24.65.
Current quote is 24.99.
Current quote is 23.76.
Current quote is 22.30.
Current quote is 25.89.
```

와 달리 사용 하 여는 `unbounded_buffer` 개체를 `receive` 함수에서 메시지를 제거 하지 않습니다는 `overwrite_buffer` 개체입니다. 소비자는 생산자는 메시지를 덮어쓰기 전에 둘 이상의 시간 메시지 버퍼에서 읽기, 수신자가 될 때마다 동일한 메시지를 가져옵니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `producer-consumer.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc 생산자 consumer.cpp**

## <a name="see-also"></a>참고자료

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)
