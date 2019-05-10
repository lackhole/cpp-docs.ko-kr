---
title: call 클래스
ms.date: 11/04/2016
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
ms.openlocfilehash: 9651a74fdb07ad96d6f01edb6818ea48d697c37c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337910"
---
# <a name="call-class"></a>call 클래스

`call` 메시징 블록은 메시지를 받을 때 지정된 함수를 호출하는 순서가 지정된 다중 소스 `target_block`입니다.

## <a name="syntax"></a>구문

```
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
이 블록에 전파 하는 메시지의 페이로드 유형입니다.

*_FunctorType*<br/>
이 블록을 받아들일 수 있는 함수의 서명입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[call](#ctor)|오버로드됨. `call` 메시징 블록을 생성합니다.|
|[~ call 소멸자](#dtor)|제거 된 `call` 메시징 블록입니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[process_input_messages](#process_input_messages)|입력된 메시지에 대해 호출 함수를 실행합니다.|
|[process_message](#process_message)|이 허용 된 메시지를 처리 `call` 메시징 블록입니다.|
|[propagate_message](#propagate_message)|메시지를 비동기적으로 전달 된 `ISource` 이 블록 `call` 메시징 블록입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.|
|[send_message](#send_message)|메시지를 동기적으로 전달 된 `ISource` 이 블록 `call` 메시징 블록입니다. 호출한는 `send` 메서드의 소스 블록에서 호출 하는 경우.|
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다. (재정의 [itarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ITarget](itarget-class.md)

[target_block](target-block-class.md)

`call`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> 호출

`call` 메시징 블록을 생성합니다.

```
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```

### <a name="parameters"></a>매개 변수

*_Func*<br/>
수락 된 각 메시지에 대 한 호출 되는 함수입니다.

*_Filter*<br/>
제공 된 메시지를 허용 해야 하는지 여부를 결정 하는 필터 함수입니다.

*_PScheduler*<br/>
`Scheduler` 메시징 블록의 전파 작업이 예약되는 `call` 개체입니다.

*_PScheduleGroup*<br/>
`ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `call` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

형식 `_Call_method` 서명 사용 하 여 함수는 `void (T const &)` 이 호출 되는 `call` 메시징 블록 메시지를 처리 합니다.

형식 `filter_method` 서명 사용 하 여 함수는 `bool (T const &)` 이 호출 되는 `call` 메시징 블록에 제공된 된 메시지를 수락 해야 하는지 여부를 결정 합니다.

##  <a name="dtor"></a> ~call

제거 된 `call` 메시징 블록입니다.

```
~call();
```

##  <a name="process_input_messages"></a> process_input_messages

입력된 메시지에 대해 호출 함수를 실행합니다.

```
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
처리 된 메시지에 대 한 포인터입니다.

##  <a name="process_message"></a> process_message

이 허용 된 메시지를 처리 `call` 메시징 블록입니다.

```
virtual void process_message(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>매개 변수

*_PMessage*<br/>
처리 된 메시지에 대 한 포인터입니다.

##  <a name="propagate_message"></a> propagate_message

메시지를 비동기적으로 전달 된 `ISource` 이 블록 `call` 메시징 블록입니다. 호출한는 `propagate` 메서드의 소스 블록에서 호출 하는 경우.

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

##  <a name="send_message"></a> send_message

메시지를 동기적으로 전달 된 `ISource` 이 블록 `call` 메시징 블록입니다. 호출한는 `send` 메서드의 소스 블록에서 호출 하는 경우.

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

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

`supports_anonymous_source` 메서드를 재정의하여 이 블록이 연결되지 않은 소스에서 제공하는 메시지를 수락할 수 있음을 나타냅니다.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>반환 값

**true** 블록은 연기 하지 때문에 메시지를 제공 합니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[transformer 클래스](transformer-class.md)
