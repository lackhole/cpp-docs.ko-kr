---
title: 병렬 진단 도구(동시성 런타임)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
ms.openlocfilehash: 182171bfcfbaf1476cc25fe3160114bc1d96ca7e
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66449242"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>병렬 진단 도구(동시성 런타임)

Visual Studio는 다중 스레드 애플리케이션 디버깅 및 프로파일링에 대한 광범위한 지원을 제공합니다.

## <a name="debugging"></a>디버깅

Visual Studio 디버거를 포함 합니다 **병렬 스택** 창 **병렬 태스크** 창 및 **병렬 조사식** 창입니다. 자세한 내용은 [연습: 병렬 응용 프로그램 디버깅](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) 고 [방법: 병렬 조사식 창을 사용 하 여](/visualstudio/debugger/how-to-use-the-parallel-watch-window)입니다.

## <a name="profiling"></a>프로파일링

프로 파일링 도구는 다중 스레드 응용 프로그램을 자신 및 다른 프로그램과 상호 작용 하는 방법에 대 한 그래픽, 테이블 형식 및 숫자 정보를 표시 하는 세 가지 데이터 뷰를 제공 합니다. 뷰는 관심 있는 영역을 신속 하 게 식별할 수 있도록 하 고 호출 스택, 그래픽 표시 지점에서 이동할 사이트 및 소스 코드를 호출 합니다. 자세한 내용은 [동시성 시각화 도우미](/visualstudio/profiling/concurrency-visualizer)를 참조하세요.

## <a name="event-tracing"></a>이벤트 추적

동시성 런타임을 사용 하 여 [Windows 이벤트 추적에 대 한](/windows/desktop/ETW/event-tracing-portal) (ETW)에 다양 한 이벤트가 발생할 때 프로파일러 등의 계측 도구에 알립니다. 이러한 이벤트는 병렬 알고리즘을 시작 하거나 끝날 때 스케줄러를 활성화 또는 비활성화 하는 경우, 컨텍스트를 시작, 종료, 차단, 차단 해제, 또는 생성 하는 경우 및 포함 됩니다.

와 같은 도구를 [동시성 시각화 도우미](/visualstudio/profiling/concurrency-visualizer) 이 기능을 활용; 따라서 일반적으로 필요가 없습니다 이러한 이벤트를 사용 하 여 직접 작동 하도록 합니다. 그러나 이러한 이벤트는 사용자 지정 프로파일러를 개발할 때 또는 같은 이벤트 추적 도구를 사용 하면 유용 [Xperf](https://go.microsoft.com/fwlink/p/?linkid=160628)합니다.

동시성 런타임에서 추적을 사용 하는 경우에 이러한 이벤트를 발생 시킵니다. 호출 된 [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) 이벤트 추적을 설정 하는 함수 및 [concurrency:: disabletracing](reference/concurrency-namespace-functions.md#disabletracing) 함수 추적을 사용 하지 않도록 설정 합니다.

다음 표에서 이벤트 추적을 사용 하는 경우 런타임에서 발생 하는 이벤트를 설명 합니다.

|이벤트(event)|설명|값|
|-----------|-----------------|-----------|
|[concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)|동시성 런타임에 대 한 ETW 공급자 식별자입니다.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|
|[concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)|컨텍스트와 관련 된 이벤트를 표시 합니다.|`5727a00f-50be-4519-8256-f7699871fecb`|
|[concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)|진입 및 종료에 대 한 호출을 표시 합니다 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘입니다.|`31c8da6b-6165-4042-8b92-949e315f4d84`|
|[concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)|진입 및 종료에 대 한 호출을 표시 합니다 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 알고리즘입니다.|`5cb7d785-9d66-465d-bae1-4611061b5434`|
|[concurrency::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|진입 및 종료에 대 한 호출을 표시 합니다 [concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) 알고리즘입니다.|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|
|[concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)|관련 된 이벤트를 표시 합니다 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|
|[concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)|가상 프로세서와 관련 된 이벤트를 표시 합니다.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|

동시성 런타임에서 정의 하지만 발생 하지 않으므로 현재, 다음과 같은 이벤트입니다. 런타임에서 나중에 사용 하기 위해 이러한 이벤트를 예약 합니다.

- [concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)

- [concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)

- [concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)

- [concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)

- [concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)

합니다 [concrt_eventtype](reference/concurrency-namespace-enums.md#concrt_eventtype) 열거형에는 이벤트를 추적 하는 가능한 작업을 지정 합니다. 입구에 예를 들어를 `parallel_for` 알고리즘인 런타임에서 발생 합니다 `PPLParallelForEventGuid` 이벤트 제공 `CONCRT_EVENT_START` 작업으로. 전에 `parallel_for` 알고리즘 반환, 런타임에서 다시 발생 시키는 합니다 `PPLParallelForEventGuid` 이벤트 제공 `CONCRT_EVENT_END` 작업으로.

다음 예제에 대 한 호출에 대 한 추적을 사용 하도록 설정 하는 방법을 `parallel_for`합니다. 런타임에 첫 번째 호출을 추적 하지 않습니다 `parallel_for` 추적 하도록 설정 되어 있지 때문입니다. 에 대 한 호출 `EnableTracing` 두 번째 호출을 추적 하면 공용 언어 런타임은 `parallel_for`합니다.

[!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]

호출 하는 횟수를 추적 하는 런타임 `EnableTracing` 고 `DisableTracing`입니다. 따라서 호출 하는 경우 `EnableTracing` 를 호출 해야 여러 번 `DisableTracing` 추적을 해제 하기 위해 동일한 횟수입니다.

## <a name="see-also"></a>참고자료

[동시성 런타임](../../parallel/concrt/concurrency-runtime.md)
