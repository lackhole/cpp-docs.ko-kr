---
title: timer 클래스
ms.date: 11/04/2016
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
ms.openlocfilehash: e36441f53c9b53c9826ee92b2892142a522d7243
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180123"
---
# <a name="timer-class"></a>timer 클래스

`timer` 메시징 블록은 지정된 기간이 경과한 후 또는 특정 간격마다 대상에 메시지를 보낼 수 있는 단일 대상 `source_block`입니다.

## <a name="syntax"></a>구문

```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
이 블록의 출력 메시지의 페이로드 유형입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[timer](#ctor)|오버로드됨. 생성 된 `timer` 지정된 된 간격 후 지정된 된 메시지를 발생 시키는 메시징 블록입니다.|
|[~ timer 소멸자](#dtor)|제거를 `timer` 메시징 블록입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[pause](#pause)|중지 된 `timer` 메시징 블록입니다. 반복 되는 경우 `timer` 메시징 블록 것을 다시 시작할 수 이후의 `start()` 호출 합니다. -반복 되지 않는 타이머,이 것과 동일한 효과가 `stop` 호출 합니다.|
|[start](#start)|시작 된 `timer` 메시징 블록입니다. 지정 된 시간 (밀리초) 후이 수가 호출 되 면 지정 된 값이 전파 됩니다으로 다운스트림을 `message`입니다.|
|[stop](#stop)|중지 된 `timer` 메시징 블록입니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[accept_message](#accept_message)|이 제공 된 메시지를 수락 `timer` 메시징 블록을 호출자에 게 소유권을 전송 합니다.|
|[consume_message](#consume_message)|이전에 제공한 메시지를 생성 합니다 `timer` 및 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 된 합니다.|
|[link_target_notification](#link_target_notification)|이 새 대상이 연결 된 알리는 콜백 `timer` 메시징 블록입니다.|
|[propagate_to_any_targets](#propagate_to_any_targets)|생성 하는 메시지를 제공 하려고 합니다 `timer` 모든 연결 된 대상 블록입니다.|
|[release_message](#release_message)|이전 메시지 예약을 해제합니다. (재정의 [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|이전에 제공한 메시지를 예약 `timer` 메시징 블록입니다. (재정의 [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|예약을 해제 된 후에 전파를 다시 시작 합니다. (재정의 [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ISource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="accept_message"></a> accept_message

이 제공 된 메시지를 수락 `timer` 메시징 블록을 호출자에 게 소유권을 전송 합니다.

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 제공 되의 `message` 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `message` 호출자에 이제 소유권을 가진 개체입니다.

##  <a name="consume_message"></a> consume_message

이전에 제공한 메시지를 생성 합니다 `timer` 및 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 된 합니다.

```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 사용 중인 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `message` 호출자에 이제 소유권을 가진 개체입니다.

### <a name="remarks"></a>설명

비슷합니다 `accept`를 호출 하 여 항상 선행 `reserve`합니다.

##  <a name="link_target_notification"></a> link_target_notification

이 새 대상이 연결 된 알리는 콜백 `timer` 메시징 블록입니다.

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
새로 연결 된 대상에 대 한 포인터입니다.

##  <a name="pause"></a> 일시 중지

중지 된 `timer` 메시징 블록입니다. 반복 되는 경우 `timer` 메시징 블록 것을 다시 시작할 수 이후의 `start()` 호출 합니다. -반복 되지 않는 타이머,이 것과 동일한 효과가 `stop` 호출 합니다.

```
void pause();
```

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

생성 하는 메시지를 제공 하려고 합니다 `timer` 모든 연결 된 대상 블록입니다.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```

##  <a name="release_message"></a> release_message

이전 메시지 예약을 해제합니다.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 릴리스될 개체입니다.

##  <a name="reserve_message"></a> reserve_message

이전에 제공한 메시지를 예약 `timer` 메시징 블록입니다.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 받고 있는 개체입니다.

### <a name="return-value"></a>반환 값

**true 이면** 메시지를 성공적으로 예약 하는 경우 **false** 그렇지 않은 경우.

### <a name="remarks"></a>설명

후 `reserve` 반환 하는 경우 라고 **true**하거나, `consume` 또는 `release` 수행 하거나 메시지의 소유권을 해제를 호출 해야 합니다.

##  <a name="resume_propagation"></a> resume_propagation

예약을 해제 된 후에 전파를 다시 시작 합니다.

```
virtual void resume_propagation();
```

##  <a name="start"></a> 시작

시작 된 `timer` 메시징 블록입니다. 지정 된 시간 (밀리초) 후이 수가 호출 되 면 지정 된 값이 전파 됩니다으로 다운스트림을 `message`입니다.

```
void start();
```

##  <a name="stop"></a> stop

중지 된 `timer` 메시징 블록입니다.

```
void stop();
```

##  <a name="ctor"></a> 타이머

생성 된 `timer` 지정된 된 간격 후 지정된 된 메시지를 발생 시키는 메시징 블록입니다.

```
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```

### <a name="parameters"></a>매개 변수

*_Ms*<br/>
다운스트림 전파 될 지정된 된 메시지에 대 한 시작 하는 호출 후 경과 해야 하는 시간 (밀리초)의 수입니다.

*값*<br/>
타이머 경과 하면 다운스트림 전파 되어야 하는 값입니다.

*_PTarget*<br/>
타이머는 해당 메시지를 전파할 대상입니다.

*_Repeating*<br/>
True 이면 타이머가 정기적으로 실행 됩니다 모든 `_Ms` 시간 (밀리초)입니다.

*_Scheduler*<br/>
`Scheduler` 개체에 대 한 작업 전파 되는 `timer` 메시징 블록은 예약 된 예약 됩니다.

*_ScheduleGroup*<br/>
`ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `timer` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

### <a name="remarks"></a>설명

런타임은 `_Scheduler` 또는 `_ScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

##  <a name="dtor"></a> ~timer

제거를 `timer` 메시징 블록입니다.

```
~timer();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
