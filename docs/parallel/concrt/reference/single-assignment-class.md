---
title: single_assignment 클래스
ms.date: 11/04/2016
f1_keywords:
- single_assignment
- AGENTS/concurrency::single_assignment
- AGENTS/concurrency::single_assignment::single_assignment
- AGENTS/concurrency::single_assignment::has_value
- AGENTS/concurrency::single_assignment::value
- AGENTS/concurrency::single_assignment::accept_message
- AGENTS/concurrency::single_assignment::consume_message
- AGENTS/concurrency::single_assignment::link_target_notification
- AGENTS/concurrency::single_assignment::propagate_message
- AGENTS/concurrency::single_assignment::propagate_to_any_targets
- AGENTS/concurrency::single_assignment::release_message
- AGENTS/concurrency::single_assignment::reserve_message
- AGENTS/concurrency::single_assignment::resume_propagation
- AGENTS/concurrency::single_assignment::send_message
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
ms.openlocfilehash: 436d0d4cc16ee18449178782b775a25bb1d8592a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159914"
---
# <a name="singleassignment-class"></a>single_assignment 클래스

`single_assignment` 메시징 블록은 하나의 한 번 쓰기 `message`를 저장할 수 있는, 순서가 지정된 다중 대상 다중 소스 `propagator_block`입니다.

## <a name="syntax"></a>구문

```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
저장 하 고 버퍼에 의해 전파 되는 메시지의 페이로드 유형입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[single_assignment](#ctor)|오버로드됨. `single_assignment` 메시징 블록을 생성합니다.|
|[~ single_assignment 소멸자](#dtor)|제거 된 `single_assignment` 메시징 블록입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[has_value](#has_value)|확인 여부를이 `single_assignment` 아직 메시징 블록 값으로 초기화 했습니다.|
|[값](#value)|현재 페이로드의에 저장 되는 메시지에 대 한 참조를 가져옵니다는 `single_assignment` 메시징 블록입니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[accept_message](#accept_message)|이 제공 된 메시지를 수락 `single_assignment` 메시징 블록을 호출자에 게는 메시지의 복사본을 반환 합니다.|
|[consume_message](#consume_message)|이전에 제공한 메시지를 생성 합니다 `single_assignment` 및 호출자에 게는 메시지의 복사본을 반환 하 여 대상에 의해 예약 된 합니다.|
|[link_target_notification](#link_target_notification)|이 새 대상이 연결 된 알리는 콜백 `single_assignment` 메시징 블록입니다.|
|[propagate_message](#propagate_message)|메시지를 비동기적으로 전달 된 `ISource` 이 블록 `single_assignment` 메시징 블록입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.|
|[propagate_to_any_targets](#propagate_to_any_targets)|위치는 `message _PMessage` 이 `single_assignment` 메시징 블록 및 모든 연결 된 대상에 제공 합니다.|
|[release_message](#release_message)|이전 메시지 예약을 해제합니다. (재정의 [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|이전에 제공한 메시지를 예약 `single_assignment` 메시징 블록입니다. (재정의 [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|예약을 해제 된 후에 전파를 다시 시작 합니다. (재정의 [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|메시지를 동기적으로 전달 된 `ISource` 이 블록 `single_assignment` 메시징 블록입니다. 호출한는 `send` 메서드의 소스 블록에서 호출 하는 경우.|

## <a name="remarks"></a>설명

`single_assignment` 메시징 블록 복사본 각 대상으로 메시지를 전파 합니다.

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`single_assignment`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="accept_message"></a> accept_message

이 제공 된 메시지를 수락 `single_assignment` 메시징 블록을 호출자에 게는 메시지의 복사본을 반환 합니다.

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 제공 되의 `message` 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `message` 호출자에 이제 소유권을 가진 개체입니다.

### <a name="remarks"></a>설명

`single_assignment` 현재 보유 한 메시지의 소유권을 전송 하는 것이 아니라 블록 반환 복사본을 대상으로 메시지를 메시징입니다.

##  <a name="consume_message"></a> consume_message

이전에 제공한 메시지를 생성 합니다 `single_assignment` 및 호출자에 게는 메시지의 복사본을 반환 하 여 대상에 의해 예약 된 합니다.

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

##  <a name="has_value"></a> has_value

확인 여부를이 `single_assignment` 아직 메시징 블록 값으로 초기화 했습니다.

```
bool has_value() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 블록에 값을 받은 경우 **false** 그렇지 않은 경우.

##  <a name="link_target_notification"></a> link_target_notification

이 새 대상이 연결 된 알리는 콜백 `single_assignment` 메시징 블록입니다.

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
새로 연결 된 대상에 대 한 포인터입니다.

##  <a name="propagate_message"></a> propagate_message

메시지를 비동기적으로 전달 된 `ISource` 이 블록 `single_assignment` 메시징 블록입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.

```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

A [message_status](concurrency-namespace-enums.md) 메시지와 함께 수행 하기로 하는 대상을 표시 합니다.

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

위치는 `message` `_PMessage` 이 `single_assignment` 메시징 블록 및 모든 연결 된 대상에 제공 합니다.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
에 대 한 포인터를 `message` 이 `single_assignment` 메시징 블록의 소유권을 획득 했습니다.

##  <a name="release_message"></a> release_message

이전 메시지 예약을 해제합니다.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 릴리스될 개체입니다.

##  <a name="reserve_message"></a> reserve_message

이전에 제공한 메시지를 예약 `single_assignment` 메시징 블록입니다.

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

##  <a name="send_message"></a> send_message

메시지를 동기적으로 전달 된 `ISource` 이 블록 `single_assignment` 메시징 블록입니다. 호출한는 `send` 메서드의 소스 블록에서 호출 하는 경우.

```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

A [message_status](concurrency-namespace-enums.md) 메시지와 함께 수행 하기로 하는 대상을 표시 합니다.

##  <a name="ctor"></a> single_assignment

`single_assignment` 메시징 블록을 생성합니다.

```
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>매개 변수

*_Filter*<br/>
제공 된 메시지를 허용 해야 하는지 여부를 결정 하는 필터 함수입니다.

*_PScheduler*<br/>
`Scheduler` 메시징 블록의 전파 작업이 예약되는 `single_assignment` 개체입니다.

*_PScheduleGroup*<br/>
`ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `single_assignment` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

형식 `filter_method` 서명 사용 하 여 함수는 `bool (T const &)` 이 호출 되는 `single_assignment` 메시징 블록에 제공된 된 메시지를 수락 해야 하는지 여부를 결정 합니다.

##  <a name="dtor"></a> ~single_assignment

제거 된 `single_assignment` 메시징 블록입니다.

```
~single_assignment();
```

##  <a name="value"></a> 값

현재 페이로드의에 저장 되는 메시지에 대 한 참조를 가져옵니다는 `single_assignment` 메시징 블록입니다.

```
T const& value();
```

### <a name="return-value"></a>반환 값

저장된 된 메시지의 페이로드입니다.

### <a name="remarks"></a>설명

이 메서드는 메시지에 현재 저장 된 경우 메시지가 도착할 때까지 대기 합니다 `single_assignment` 메시징 블록입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[overwrite_buffer 클래스](overwrite-buffer-class.md)<br/>
[unbounded_buffer 클래스](unbounded-buffer-class.md)
