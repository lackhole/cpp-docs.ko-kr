---
title: '방법: 일정 한 간격으로 메시지 보내기'
ms.date: 11/04/2016
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
ms.openlocfilehash: 0bf5f93e2a570761874232a88a23289e59e58d94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321964"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>방법: 일정 한 간격으로 메시지 보내기

이 예제에서는 concurrency::[timer 클래스](../../parallel/concrt/reference/timer-class.md)를 사용하여 일정한 간격으로 메시지를 보내려고 합니다.

## <a name="example"></a>예제

다음 예제에서 `timer`는 시간이 오래 걸리는 작업을 하는 동안 진행률을 보고하는 개체입니다. 이 예제의 링크된 `timer` 개체는 [concurrency::call](../../parallel/concrt/reference/call-class.md)개체입니다. `call` 개체는 일정한 간격으로 진행률 표시기를 콘솔에 출력합니다. [concurrency::timer::start](reference/timer-class.md#start) 메서드는 별도 컨텍스트에서 타이머를 실행합니다. `perform_lengthy_operation` 함수에서 호출하는 [concurrency::wait](reference/concurrency-namespace-functions.md#wait) 함수는 주 컨텍스트에서 시간이 많이 걸리는 작업을 시뮬레이션합니다.

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

이 예제는 다음 예제 출력을 생성합니다.

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `report-progress.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc report-progress.cpp**

## <a name="see-also"></a>참고자료

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)
