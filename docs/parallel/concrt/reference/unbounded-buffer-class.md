---
title: unbounded_buffer 클래스
ms.date: 11/04/2016
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
ms.openlocfilehash: 1474381a2d1c0947b2428ab4cf0b4683198eef84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407837"
---
# <a name="unboundedbuffer-class"></a>unbounded_buffer 클래스

`unbounded_buffer` 메시징 블록은 메시지를 개수에 제한 없이 저장할 수 있는, 순서가 지정된 다중 대상 다중 소스 `propagator_block`입니다.

## <a name="syntax"></a>구문

```
template<
   class             _Type
>
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;
```

#### <a name="parameters"></a>매개 변수

*_Type*<br/>
저장 하 고 버퍼에 의해 전파 되는 메시지의 페이로드 유형입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[unbounded_buffer](#ctor)|오버로드됨. 생성 된 `unbounded_buffer` 메시징 블록입니다.|
|[~ unbounded_buffer 소멸자](#dtor)|제거 된 `unbounded_buffer` 메시징 블록입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[dequeue](#dequeue)|항목을 제거 합니다 `unbounded_buffer` 메시징 블록입니다.|
|[enqueue](#enqueue)|항목을 추가 합니다 `unbounded_buffer` 메시징 블록입니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[accept_message](#accept_message)|이 제공 된 메시지를 수락 `unbounded_buffer` 메시징 블록을 호출자에 게 소유권을 전송 합니다.|
|[consume_message](#consume_message)|이전에 제공한 메시지를 생성 합니다 `unbounded_buffer` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.|
|[link_target_notification](#link_target_notification)|이 새 대상이 연결 된 알리는 콜백 `unbounded_buffer` 메시징 블록입니다.|
|[process_input_messages](#process_input_messages)|위치는 `message` `_PMessage` 이 `unbounded_buffer` 메시징 블록 및 모든 연결 된 대상에 제공 하려고 합니다.|
|[propagate_message](#propagate_message)|메시지를 비동기적으로 전달 된 `ISource` 이 블록 `unbounded_buffer` 메시징 블록입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.|
|[propagate_output_messages](#propagate_output_messages)|위치는 `message` `_PMessage` 이 `unbounded_buffer` 메시징 블록 및 모든 연결 된 대상에 제공 하려고 합니다. (재정의 [source_block:: propagate_output_messages](source-block-class.md#propagate_output_messages).)|
|[release_message](#release_message)|이전 메시지 예약을 해제합니다. (재정의 [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|이전에 제공한 메시지를 예약 `unbounded_buffer` 메시징 블록입니다. (재정의 [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|예약을 해제 된 후에 전파를 다시 시작 합니다. (재정의 [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|메시지를 동기적으로 전달 된 `ISource` 이 블록 `unbounded_buffer` 메시징 블록입니다. 호출한는 `send` 메서드의 소스 블록에서 호출 하는 경우.|
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다. (재정의 [itarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

자세한 내용은 [비동기 메시지 블록](../asynchronous-message-blocks.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`unbounded_buffer`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="accept_message"></a> accept_message

이 제공 된 메시지를 수락 `unbounded_buffer` 메시징 블록을 호출자에 게 소유권을 전송 합니다.

```
virtual message<_Type> * accept_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 제공 되의 `message` 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `message` 호출자에 이제 소유권을 가진 개체입니다.

##  <a name="consume_message"></a> consume_message

이전에 제공한 메시지를 생성 합니다 `unbounded_buffer` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 예약 합니다.

```
virtual message<_Type> * consume_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 사용 중인 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `message` 호출자에 이제 소유권을 가진 개체입니다.

### <a name="remarks"></a>설명

비슷합니다 `accept`를 호출 하 여 항상 선행 `reserve`합니다.

##  <a name="dequeue"></a> dequeue

항목을 제거 합니다 `unbounded_buffer` 메시징 블록입니다.

```
_Type dequeue();
```

### <a name="return-value"></a>반환 값

제거할 메시지의 페이로드에 `unbounded_buffer`합니다.

##  <a name="enqueue"></a> enqueue

항목을 추가 합니다 `unbounded_buffer` 메시징 블록입니다.

```
bool enqueue(
   _Type const&                 _Item
);
```

### <a name="parameters"></a>매개 변수

*_Item*<br/>
추가할 항목입니다.

### <a name="return-value"></a>반환 값

**true** 항목을 수락 되 면 **false** 그렇지 않은 경우.

##  <a name="link_target_notification"></a> link_target_notification

이 새 대상이 연결 된 알리는 콜백 `unbounded_buffer` 메시징 블록입니다.

```
virtual void link_target_notification(
   _Inout_ ITarget<_Type> *                 _PTarget
);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
새로 연결 된 대상에 대 한 포인터입니다.

##  <a name="propagate_message"></a> propagate_message

메시지를 비동기적으로 전달 된 `ISource` 이 블록 `unbounded_buffer` 메시징 블록입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.

```
virtual message_status propagate_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

A [message_status](concurrency-namespace-enums.md#message_status) 메시지와 함께 수행 하기로 하는 대상을 표시 합니다.

##  <a name="propagate_output_messages"></a> propagate_output_messages

위치는 `message` `_PMessage` 이 `unbounded_buffer` 메시징 블록 및 모든 연결 된 대상에 제공 하려고 합니다.

```
virtual void propagate_output_messages();
```

### <a name="remarks"></a>설명

경우 다른 메시지는 이미에서 앞의 `unbounded_buffer`, 이전 메시지가 허용 되거나 사용 될 때까지 연결 된 대상에 전파 발생 하지 것입니다. 첫 번째 대상에 연결 되었습니다 `accept` 또는 `consume` 메시지 소유권 및 다른 대상이 메시지를 가져올 수 있습니다.

##  <a name="process_input_messages"></a> process_input_messages

위치는 `message` `_PMessage` 이 `unbounded_buffer` 메시징 블록 및 모든 연결 된 대상에 제공 하려고 합니다.

```
virtual void process_input_messages(
   _Inout_ message<_Type> *                 _PMessage
);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
처리 된 메시지에 대 한 포인터입니다.

##  <a name="release_message"></a> release_message

이전 메시지 예약을 해제합니다.

```
virtual void release_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 릴리스될 개체입니다.

##  <a name="reserve_message"></a> reserve_message

이전에 제공한 메시지를 예약 `unbounded_buffer` 메시징 블록입니다.

```
virtual bool reserve_message(
   runtime_object_identity                 _MsgId
);
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

메시지를 동기적으로 전달 된 `ISource` 이 블록 `unbounded_buffer` 메시징 블록입니다. 호출한는 `send` 메서드의 소스 블록에서 호출 하는 경우.

```
virtual message_status send_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

A [message_status](concurrency-namespace-enums.md#message_status) 메시지와 함께 수행 하기로 하는 대상을 표시 합니다.

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>반환 값

**true** 블록은 연기 하지 때문에 메시지를 제공 합니다.

##  <a name="ctor"></a> unbounded_buffer

생성 된 `unbounded_buffer` 메시징 블록입니다.

```
unbounded_buffer();

unbounded_buffer(
   filter_method const&                 _Filter
);

unbounded_buffer(
   Scheduler&                 _PScheduler
);

unbounded_buffer(
   Scheduler&                 _PScheduler,
   filter_method const&                 _Filter
);

unbounded_buffer(
   ScheduleGroup&                 _PScheduleGroup
);

unbounded_buffer(
   ScheduleGroup&                 _PScheduleGroup,
   filter_method const&                 _Filter
);
```

### <a name="parameters"></a>매개 변수

*_Filter*<br/>
제공 된 메시지를 허용 해야 하는지 여부를 결정 하는 필터 함수입니다.

*_PScheduler*<br/>
`Scheduler` 메시징 블록의 전파 작업이 예약되는 `unbounded_buffer` 개체입니다.

*_PScheduleGroup*<br/>
`ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `unbounded_buffer` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

형식 `filter_method` 서명 사용 하 여 함수는 `bool (_Type const &)` 이 호출 되는 `unbounded_buffer` 메시징 블록에 제공된 된 메시지를 수락 해야 하는지 여부를 결정 합니다.

##  <a name="dtor"></a> ~unbounded_buffer

제거 된 `unbounded_buffer` 메시징 블록입니다.

```
~unbounded_buffer();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[overwrite_buffer 클래스](overwrite-buffer-class.md)<br/>
[single_assignment 클래스](single-assignment-class.md)
