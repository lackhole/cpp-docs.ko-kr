---
title: propagator_block 클래스
ms.date: 11/04/2016
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
ms.openlocfilehash: 7f466ad8f474ddb73d2235d9999c3dbeae627672
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394366"
---
# <a name="propagatorblock-class"></a>propagator_block 클래스

`propagator_block` 클래스는 소스인 동시에 대상인 메시지 블록에 대한 추상 기본 클래스입니다. `source_block` 및 `target_block` 클래스의 기능을 결합합니다.

## <a name="syntax"></a>구문

```
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

#### <a name="parameters"></a>매개 변수

*_TargetLinkRegistry*<br/>
대상 링크를 저장에 사용 되는 링크 레지스트리입니다.

*_SourceLinkRegistry*<br/>
소스 링크를 저장에 사용 되는 링크 레지스트리입니다.

*_MessageProcessorType*<br/>
메시지 처리에 대 한 프로세서 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`source_iterator`|에 대 한 반복기의 형식 합니다 `source_link_manager` 이 `propagator_block`합니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[propagator_block](#ctor)|`propagator_block` 개체를 생성합니다.|
|[~ propagator_block 소멸자](#dtor)|`propagator_block` 개체를 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[propagate](#propagate)|소스 블록에서이 대상 블록에 메시지를 비동기적으로 전달 합니다.|
|[send](#send)|이 블록에 메시지를 동기적으로 시작합니다. 호출한는 `ISource` 블록입니다. 이 함수에는 다음이 완료 되 면 메시지 블록에 이미 전파 됩니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|새 메시지를 거부 해야 하는 블록을 나타냅니다.|
|[initialize_source_and_target](#initialize_source_and_target)|기준 개체를 초기화합니다. 구체적으로 `message_processor` 개체를 초기화 해야 합니다.|
|[link_source](#link_source)|이 지정 된 소스 블록에 연결 `propagator_block` 개체입니다.|
|[process_input_messages](#process_input_messages)|입력된 메시지를 처리합니다. Source_block에서 파생 되는 전파자 블록에만 유용 (재정의 [source_block:: process_input_messages](source-block-class.md#process_input_messages).)|
|[propagate_message](#propagate_message)|파생된 클래스에서 재정의 되 면이 메서드에서 메시지를 비동기적으로 전달 된 `ISource` 이 블록 `propagator_block` 개체입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.|
|[register_filter](#register_filter)|받은 모든 메시지에 대해 호출 되는 필터 메서드를 등록 합니다.|
|[remove_network_links](#remove_network_links)|이 모든 원본 및 대상 네트워크 링크가 제거 `propagator_block` 개체입니다.|
|[send_message](#send_message)|파생된 클래스에서 재정의 되 면이 메서드에서 메시지를 동기적으로 전달 된 `ISource` 이 블록 `propagator_block` 개체입니다. 호출한는 `send` 메서드의 소스 블록에서 호출 하는 경우.|
|[unlink_source](#unlink_source)|이 지정 된 소스 블록을 연결 해제 `propagator_block` 개체입니다.|
|[unlink_sources](#unlink_sources)|이 모든 소스 블록을 연결 해제 `propagator_block` 개체입니다. (재정의 [itarget:: Unlink_sources](itarget-class.md#unlink_sources).)|

## <a name="remarks"></a>설명

다중 상속 하지 않으려면 합니다 `propagator_block` 클래스에서 상속 합니다 `source_block` 클래스 및 `ITarget` 추상 클래스입니다. 대부분의 기능을 `target_block` 클래스 여기에 복제 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="decline_incoming_messages"></a> decline_incoming_messages

새 메시지를 거부 해야 하는 블록을 나타냅니다.

```
void decline_incoming_messages();
```

### <a name="remarks"></a>설명

이 메서드는 소멸 진행 중인 동안 새로운 메시지가 거부 되도록 소멸자에서 호출 됩니다.

##  <a name="initialize_source_and_target"></a> initialize_source_and_target

기준 개체를 초기화합니다. 구체적으로 `message_processor` 개체를 초기화 해야 합니다.

```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>매개 변수

*_PScheduler*<br/>
작업을 예약 하는 데 사용할 스케줄러입니다.

*_PScheduleGroup*<br/>
일정 그룹 작업을 예약 하는 데 사용할 수입니다.

##  <a name="link_source"></a> link_source

이 지정 된 소스 블록에 연결 `propagator_block` 개체입니다.

```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PSource*<br/>
에 대 한 포인터를 `ISource` 블록 연결 되어야 하는 것입니다.

##  <a name="process_input_messages"></a> process_input_messages

입력된 메시지를 처리합니다. source_block에서 파생되는 전파자 블록에만 유용합니다.

```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
처리 된 메시지에 대 한 포인터입니다.

##  <a name="propagate"></a> propagate

소스 블록에서이 대상 블록에 메시지를 비동기적으로 전달 합니다.

```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

A [message_status](concurrency-namespace-enums.md) 메시지와 함께 수행 하기로 하는 대상을 표시 합니다.

### <a name="remarks"></a>설명

`propagate` 메서드는 연결 된 소스 블록에 의해 대상 블록에서 호출 됩니다. 큐에 하나는 이미 큐에 들어가지 않았습니다 하는 경우 메시지를 처리 하는 비동기 작업 또는 실행 합니다.

메서드에서 throw를 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우는 예외를 `_PMessage` 또는 `_PSource` 매개 변수는 `NULL`합니다.

##  <a name="propagate_message"></a> propagate_message

파생된 클래스에서 재정의 되 면이 메서드에서 메시지를 비동기적으로 전달 된 `ISource` 이 블록 `propagator_block` 개체입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.

```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

A [message_status](concurrency-namespace-enums.md) 메시지와 함께 수행 하기로 하는 대상을 표시 합니다.

##  <a name="ctor"></a> propagator_block

`propagator_block` 개체를 생성합니다.

```
propagator_block();
```

##  <a name="dtor"></a> ~propagator_block

`propagator_block` 개체를 제거합니다.

```
virtual ~propagator_block();
```

##  <a name="register_filter"></a> register_filter

받은 모든 메시지에 대해 호출 되는 필터 메서드를 등록 합니다.

```
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>매개 변수

*_Filter*<br/>
필터 메서드입니다.

##  <a name="remove_network_links"></a> remove_network_links

이 모든 원본 및 대상 네트워크 링크가 제거 `propagator_block` 개체입니다.

```
void remove_network_links();
```

##  <a name="send"></a> 보내기

이 블록에 메시지를 동기적으로 시작합니다. 호출한는 `ISource` 블록입니다. 이 함수에는 다음이 완료 되 면 메시지 블록에 이미 전파 됩니다.

```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
`message` 개체에 대한 포인터입니다.

*_PSource*<br/>
메시지를 제공 하는 소스 블록에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

A [message_status](concurrency-namespace-enums.md) 메시지와 함께 수행 하기로 하는 대상을 표시 합니다.

### <a name="remarks"></a>설명

이 메서드가 throw를 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우는 예외를 `_PMessage` 또는 `_PSource` 매개 변수는 `NULL`합니다.

##  <a name="send_message"></a> send_message

파생된 클래스에서 재정의 되 면이 메서드에서 메시지를 동기적으로 전달 된 `ISource` 이 블록 `propagator_block` 개체입니다. 호출한는 `send` 메서드의 소스 블록에서 호출 하는 경우.

```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>반환 값

A [message_status](concurrency-namespace-enums.md) 메시지와 함께 수행 하기로 하는 대상을 표시 합니다.

### <a name="remarks"></a>설명

기본적으로이 블록 반환 `declined` 파생된 클래스에서 재정의 되지 않는 경우.

##  <a name="unlink_source"></a> unlink_source

이 지정 된 소스 블록을 연결 해제 `propagator_block` 개체입니다.

```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>매개 변수

*_PSource*<br/>
에 대 한 포인터를 `ISource` 블록 연결을 끊어야 하는 것입니다.

##  <a name="unlink_sources"></a> unlink_sources

이 모든 소스 블록을 연결 해제 `propagator_block` 개체입니다.

```
virtual void unlink_sources();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[source_block 클래스](source-block-class.md)<br/>
[ITarget 클래스](itarget-class.md)
