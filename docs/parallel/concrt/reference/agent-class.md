---
title: 에이전트 클래스
ms.date: 11/04/2016
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
ms.openlocfilehash: 98ad5f817361d8410e5a60648fb23baec06c42d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337754"
---
# <a name="agent-class"></a>에이전트 클래스

모든 독립 에이전트에 대한 기본 클래스로 사용되는 클래스입니다. 다른 에이전트로부터 상태를 숨기고 메시지 전달을 사용하여 상호 작용하는 데 사용됩니다.

## <a name="syntax"></a>구문

```
class agent;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[agent](#ctor)|오버로드됨. 에이전트를 생성합니다.|
|[~ agent 소멸자](#dtor)|에이전트를 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[cancel](#cancel)|에이전트에서 이동 합니다 `agent_created` 또는 `agent_runnable` 에 상태를 `agent_canceled` 상태입니다.|
|[start](#start)|에이전트를 이동 합니다 `agent_created` 상태는 `agent_runnable` 상태 및 실행을 예약 합니다.|
|[status](#status)|동기 하는 원본 에이전트에서 상태 정보입니다.|
|[status_port](#status_port)|비동기 원본 에이전트에서 상태 정보입니다.|
|[wait](#wait)|에이전트 작업을 완료를 대기 합니다.|
|[wait_for_all](#wait_for_all)|모든 태스크를 완료 하려면 지정 된 에이전트에 대 한 대기 합니다.|
|[wait_for_one](#wait_for_one)|해당 작업을 완료 하려면 지정 된 에이전트 중 하나가 될 때까지 기다립니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[done](#done)|이동에 에이전트를 `agent_done` 에이전트가 완료 되었음을 나타내는 상태입니다.|
|[run](#run)|에이전트의 기본 태스크를 나타냅니다. `run` 파생된 클래스에서 재정의 하 고 에이전트가 수행할 동작 지정이 시작 된 후입니다.|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 에이전트](../../../parallel/concrt/asynchronous-agents.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`agent`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> 에이전트

에이전트를 생성합니다.

```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```

### <a name="parameters"></a>매개 변수

*_PScheduler*<br/>
`Scheduler` 개체 내 에이전트의 실행 작업이 예약 됩니다.

*_PGroup*<br/>
`ScheduleGroup` 개체 내 에이전트의 실행 작업이 예약 됩니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

##  <a name="dtor"></a> ~agent

에이전트를 제거합니다.

```
virtual ~agent();
```

### <a name="remarks"></a>설명

터미널 상태에 있지 않은 에이전트를 제거 하는 오류 (중 하나 `agent_done` 또는 `agent_canceled`). 이 에이전트에서 상속 되는 클래스의 소멸자에 있는 터미널 상태가 될 때까지 대기 하 여 방지할 수는 `agent` 클래스입니다.

##  <a name="cancel"></a> 취소

에이전트에서 이동 합니다 `agent_created` 또는 `agent_runnable` 에 상태를 `agent_canceled` 상태입니다.

```
bool cancel();
```

### <a name="return-value"></a>반환 값

**true 이면** 에이전트가 취소 된 경우 **false** 그렇지 않은 경우. 이미 실행을 시작 하거나 이미 완료 된 경우 에이전트를 취소할 수 없습니다.

##  <a name="done"></a> 작업 수행

이동에 에이전트를 `agent_done` 에이전트가 완료 되었음을 나타내는 상태입니다.

```
bool done();
```

### <a name="return-value"></a>반환 값

**true** 에이전트는 이동 하는 경우는 `agent_done` 상태 **false** 그렇지 않은 경우. 에이전트 취소 되었습니다.를 이동할 수 없습니다는 `agent_done` 상태입니다.

### <a name="remarks"></a>설명

끝에이 메서드를 호출 해야 합니다 `run` 에이전트의 실행을 알고 있는 경우 메서드를 완료 합니다.

##  <a name="run"></a> 실행

에이전트의 기본 태스크를 나타냅니다. `run` 파생된 클래스에서 재정의 하 고 에이전트가 수행할 동작 지정이 시작 된 후입니다.

```
virtual void run() = 0;
```

### <a name="remarks"></a>설명

에이전트 상태가으로 변경 됩니다 `agent_started` 직전이 메서드가 호출 됩니다. 메서드를 호출 해야 `done` 적절 한 상태로 반환 되기 전에 에이전트 및 예외를 throw 할 수 있습니다.

##  <a name="start"></a> 시작

에이전트를 이동 합니다 `agent_created` 상태는 `agent_runnable` 상태 및 실행을 예약 합니다.

```
bool start();
```

### <a name="return-value"></a>반환 값

**true 이면** 에이전트가 올바르게 시작 하는 경우 **false** 그렇지 않은 경우. 취소 되었습니다. 에이전트를 시작할 수 없습니다.

##  <a name="status"></a> 상태

동기 하는 원본 에이전트에서 상태 정보입니다.

```
agent_status status();
```

### <a name="return-value"></a>반환 값

에이전트의 현재 상태를 반환합니다. 이 반환 되는 상태 반환할 직후 변경할 수는 참고 합니다.

##  <a name="status_port"></a> status_port

비동기 원본 에이전트에서 상태 정보입니다.

```
ISource<agent_status>* status_port();
```

### <a name="return-value"></a>반환 값

에이전트의 현재 상태에 대 한 메시지를 보낼 수 있는 메시지 원본을 반환 합니다.

##  <a name="wait"></a> 대기

에이전트 작업을 완료를 대기 합니다.

```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*_PAgent*<br/>
에이전트에 대 한 대기에 대 한 포인터입니다.

*_Timeout*<br/>
대기할 시간 (밀리초)는 최대 시간입니다.

### <a name="return-value"></a>반환 값

`agent_status` 대기가 완료 되 면 에이전트입니다. 일 수 있습니다 `agent_canceled` 또는 `agent_done`합니다.

### <a name="remarks"></a>설명

에이전트에 들어가면 에이전트 작업이 완료 되는 `agent_canceled` 또는 `agent_done` 상태입니다.

경우 매개 변수 `_Timeout` 상수가 아닌 값이 `COOPERATIVE_TIMEOUT_INFINITE`, 예외 [operation_timed_out](operation-timed-out-class.md) 지정된 기간 동안에는 에이전트에서 해당 작업이 완료 전에 만료 되 면 throw 됩니다.

##  <a name="wait_for_all"></a> wait_for_all

모든 태스크를 완료 하려면 지정 된 에이전트에 대 한 대기 합니다.

```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*count*<br/>
배열에 있는 에이전트 포인터 수 `_PAgents`입니다.

*_PAgents*<br/>
에이전트에 대 한 대기에 대 한 포인터의 배열입니다.

*_PStatus*<br/>
에이전트 상태 배열에 대 한 포인터입니다. 메서드는 반환 될 때 각 상태 값은 해당 에이전트의 상태를 나타냅니다.

*_Timeout*<br/>
대기할 시간 (밀리초)는 최대 시간입니다.

### <a name="remarks"></a>설명

에이전트에 들어가면 에이전트 작업이 완료 되는 `agent_canceled` 또는 `agent_done` 상태입니다.

경우 매개 변수 `_Timeout` 상수가 아닌 값이 `COOPERATIVE_TIMEOUT_INFINITE`, 예외 [operation_timed_out](operation-timed-out-class.md) 지정된 기간 동안에는 에이전트에서 해당 작업이 완료 전에 만료 되 면 throw 됩니다.

##  <a name="wait_for_one"></a> wait_for_one

해당 작업을 완료 하려면 지정 된 에이전트 중 하나가 될 때까지 기다립니다.

```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*count*<br/>
배열에 있는 에이전트 포인터 수 `_PAgents`입니다.

*_PAgents*<br/>
에이전트에 대 한 대기에 대 한 포인터의 배열입니다.

*_Status*<br/>
에이전트 상태를 저장할 변수 참조입니다.

*_Index*<br/>
에이전트 인덱스 배치 될 위치는 변수에 대 한 참조입니다.

*_Timeout*<br/>
대기할 시간 (밀리초)는 최대 시간입니다.

### <a name="remarks"></a>설명

에이전트에 들어가면 에이전트 작업이 완료 되는 `agent_canceled` 또는 `agent_done` 상태입니다.

경우 매개 변수 `_Timeout` 상수가 아닌 값이 `COOPERATIVE_TIMEOUT_INFINITE`, 예외 [operation_timed_out](operation-timed-out-class.md) 지정된 기간 동안에는 에이전트에서 해당 작업이 완료 전에 만료 되 면 throw 됩니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
