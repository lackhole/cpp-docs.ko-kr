---
title: 동기화 데이터 구조와 Windows API의 비교
ms.date: 11/04/2016
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
ms.openlocfilehash: 4fa0d3fbf3457bfafab731275584d206206161dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414037"
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>동기화 데이터 구조와 Windows API의 비교

이 항목에서는 동시성 런타임을 Windows API에서 제공 하는 것에서 제공 하는 동기화 데이터 구조의 동작을 비교 합니다.

동시성 런타임에서 제공 되는 동기화 데이터 구조에 따라 합니다 *스레딩 모델 협조적*합니다. 협조적 스레딩 모델에서 동기화 기본 형식을 명시적으로 다른 스레드에 처리 리소스를 생성합니다. 이 반해 합니다 *선점형 스레딩 모델*여기서 처리 리소스 제어 스케줄러 또는 운영 체제에서 다른 스레드에 전송 됩니다.

## <a name="criticalsection"></a>critical_section

합니다 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 클래스에는 Windows와 유사 `CRITICAL_SECTION` 하나의 프로세스의 스레드에 의해만 사용할 수 있으므로 구조체입니다. Windows API에서 중요 한 섹션에 대 한 자세한 내용은 참조 하세요. [임계 영역 개체](/windows/desktop/Sync/critical-section-objects)합니다.

## <a name="readerwriterlock"></a>reader_writer_lock

합니다 [concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) Windows 슬림 판독기/기록기 (SRW) 잠금을 유사 합니다. 다음 표에서 유사점과 차이점을 설명합니다.

|기능|`reader_writer_lock`|SRW 잠금|
|-------------|--------------------------|--------------|
|재진입|예|예|
|기록기 (업그레이드 지원)에 판독기를 승격할 수 있습니다.|아니요|아니요|
|(다운 그레이드 지원) 판독기는 작성기의 수준을 내릴 수 있습니다.|아니요|아니요|
|쓰기 기본 설정|예|아니요|
|작성기에는 FIFO 액세스|예|아니요|

SRW 잠금에 대 한 자세한 내용은 참조 하십시오 [슬림 판독기/기록기 (SRW) 잠금](https://msdn.microsoft.com/library/windows/desktop/aa904937) Platform SDK에 있습니다.

## <a name="event"></a>이벤트(event)

합니다 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 클래스 명명 되지 않은 Windows 수동 재설정 이벤트와 유사 합니다. 그러나는 `event` Windows 이벤트를 선점 하 여 동작 하지만 개체는 협조적으로 동작 합니다. Windows 이벤트에 대 한 자세한 내용은 참조 하세요. [이벤트 개체](/windows/desktop/Sync/event-objects)합니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

간의 차이 파악 하는 데는 `event` 클래스 및 Windows 이벤트를 다음 예제를 살펴보세요. 이 예제에서는 스케줄러가 최대 두 개의 동시 작업을 만든 다음 호출을 사용 하는 비슷한 두 함수는 `event` 클래스와 Windows 수동 재설정 이벤트입니다. 각 함수는 먼저 공유 이벤트 신호를 대기 하는 몇 가지 작업을 만듭니다. 각 함수는 다음을 실행 중인 태스크를 생성 하 고 이벤트에 신호를 보냅니다. 그런 다음 각 함수는 신호를 받은 이벤트 기다립니다.

### <a name="code"></a>코드

[!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]

### <a name="comments"></a>설명

이 예제는 다음 예제 출력을 생성합니다.

```Output
Cooperative event:
    Context 0: waiting on an event.
    Context 1: waiting on an event.
    Context 2: waiting on an event.
    Context 3: waiting on an event.
    Context 4: waiting on an event.
    Setting the event.
    Context 5: received the event.
    Context 6: received the event.
    Context 7: received the event.
    Context 8: received the event.
    Context 9: received the event.
Windows event:
    Context 10: waiting on an event.
    Context 11: waiting on an event.
    Setting the event.
    Context 12: received the event.
    Context 14: waiting on an event.
    Context 15: received the event.
    Context 16: waiting on an event.
    Context 17: received the event.
    Context 18: waiting on an event.
    Context 19: received the event.
    Context 13: received the event.
```

때문에 `event` 클래스는 협조적으로 동작, 이벤트 신호를 받은 상태로 전환 하려고 대기 하는 경우 스케줄러 처리 리소스를 다른 컨텍스트를 다시 할당할 수 있습니다. 사용 하는 버전에서 더 많은 작업이 수행 됩니다 따라서는 `event` 클래스입니다. Windows 이벤트를 사용 하는 버전에서는 다음 태스크를 시작 하기 전에 대기 중인 각 작업 신호를 받은 상태 그대로 입력 해야 합니다.

작업에 대 한 자세한 내용은 참조 하세요. [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.

## <a name="see-also"></a>참고자료

[동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)
