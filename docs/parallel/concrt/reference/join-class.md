---
title: join 클래스
ms.date: 11/04/2016
f1_keywords:
- join
- AGENTS/concurrency::join
- AGENTS/concurrency::join::join
- AGENTS/concurrency::join::accept_message
- AGENTS/concurrency::join::consume_message
- AGENTS/concurrency::join::link_target_notification
- AGENTS/concurrency::join::propagate_message
- AGENTS/concurrency::join::propagate_to_any_targets
- AGENTS/concurrency::join::release_message
- AGENTS/concurrency::join::reserve_message
- AGENTS/concurrency::join::resume_propagation
helpviewer_keywords:
- join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
ms.openlocfilehash: d04ef90750c609d77fc8bf963bb996a90444f079
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343872"
---
# <a name="join-class"></a>join 클래스

`join` 메시징 블록은 각 소스에서 `T` 형식의 메시지를 결합하는 순서가 지정된 단일 대상 다중 소스 `propagator_block`입니다.

## <a name="syntax"></a>구문

```
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
메시지의 페이로드 유형 조인 및 블록에 의해 전파 합니다.

*_Jtype*<br/>
종류의 `join` 차단 하거나 이것이 `greedy` 또는 `non_greedy`

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[join](#ctor)|오버로드됨. `join` 메시징 블록을 생성합니다.|
|[~ join 소멸자](#dtor)|제거 된 `join` 블록입니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[accept_message](#accept_message)|이 제공 된 메시지를 수락 `join` 메시징 블록을 호출자에 게 소유권을 전송 합니다.|
|[consume_message](#consume_message)|이전에 제공한 메시지를 생성 합니다 `join` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.|
|[link_target_notification](#link_target_notification)|이 새 대상이 연결 된 알리는 콜백 `join` 메시징 블록입니다.|
|[propagate_message](#propagate_message)|메시지를 비동기적으로 전달 된 `ISource` 이 블록 `join` 메시징 블록입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.|
|[propagate_to_any_targets](#propagate_to_any_targets)|전파 될 때 이러한 있는 모든 메시지에는 각 원본에서 입력된 메시지를 포함 하는 출력 메시지를 생성 합니다. 출력 메시지가 각 대상에 보냅니다.|
|[release_message](#release_message)|이전 메시지 예약을 해제합니다. (재정의 [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|이전에 제공한 메시지를 예약 `join` 메시징 블록입니다. (재정의 [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|예약을 해제 된 후에 전파를 다시 시작 합니다. (재정의 [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`join`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="accept_message"></a> accept_message

이 제공 된 메시지를 수락 `join` 메시징 블록을 호출자에 게 소유권을 전송 합니다.

```
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 제공 되의 `message` 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `message` 호출자에 이제 소유권을 가진 개체입니다.

##  <a name="consume_message"></a> consume_message

이전에 제공한 메시지를 생성 합니다 `join` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.

```
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 사용 중인 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `message` 호출자에 이제 소유권을 가진 개체입니다.

### <a name="remarks"></a>설명

비슷합니다 `accept`를 호출 하 여 항상 선행 `reserve`합니다.

##  <a name="ctor"></a> join

`join` 메시징 블록을 생성합니다.

```
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```

### <a name="parameters"></a>매개 변수

*_NumInputs*<br/>
이 수가 입력 `join` 블록 수입니다.

*_Filter*<br/>
제공 된 메시지를 허용 해야 하는지 여부를 결정 하는 필터 함수입니다.

*_PScheduler*<br/>
`Scheduler` 메시징 블록의 전파 작업이 예약되는 `join` 개체입니다.

*_PScheduleGroup*<br/>
`ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `join` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

형식 `filter_method` 서명 사용 하 여 함수는 `bool (T const &)` 이 호출 되는 `join` 메시징 블록에 제공된 된 메시지를 수락 해야 하는지 여부를 결정 합니다.

##  <a name="dtor"></a> ~join

제거 된 `join` 블록입니다.

```
~join();
```

##  <a name="link_target_notification"></a> link_target_notification

이 새 대상이 연결 된 알리는 콜백 `join` 메시징 블록입니다.

```
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```

##  <a name="propagate_message"></a> propagate_message

메시지를 비동기적으로 전달 된 `ISource` 이 블록 `join` 메시징 블록입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.

```
message_status propagate_message(
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

전파 될 때 이러한 있는 모든 메시지에는 각 원본에서 입력된 메시지를 포함 하는 출력 메시지를 생성 합니다. 출력 메시지가 각 대상에 보냅니다.

```
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
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

이전에 제공한 메시지를 예약 `join` 메시징 블록입니다.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 제공 되의 `message` 개체입니다.

### <a name="return-value"></a>반환 값

**true 이면** 메시지를 성공적으로 예약 하는 경우 **false** 그렇지 않은 경우.

### <a name="remarks"></a>설명

후 `reserve` 반환 하는 경우 라고 **true**하거나, `consume` 또는 `release` 수행 하거나 메시지의 소유권을 해제를 호출 해야 합니다.

##  <a name="resume_propagation"></a> resume_propagation

예약을 해제 된 후에 전파를 다시 시작 합니다.

```
virtual void resume_propagation();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[choice 클래스](choice-class.md)<br/>
[multitype_join 클래스](multitype-join-class.md)
