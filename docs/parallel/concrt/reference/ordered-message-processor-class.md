---
title: ordered_message_processor 클래스
ms.date: 11/04/2016
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
ms.openlocfilehash: b88544f399031a5f770fa39aa1f3300306158511
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394431"
---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor 클래스

`ordered_message_processor`는 메시지 블록이 수신된 순서대로 메시지를 처리할 수 있도록 하는 `message_processor`입니다.

## <a name="syntax"></a>구문

```
template<class T>
class ordered_message_processor : public message_processor<T>;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
프로세서에 의해 처리 되는 메시지의 페이로드 유형입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`type`|에 대 한 형식 별칭을 `T`입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[ordered_message_processor](#ctor)|`ordered_message_processor` 개체를 생성합니다.|
|[~ordered_message_processor Destructor](#dtor)|제거 된 `ordered_message_processor` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[async_send](#async_send)|비동기적으로 메시지를 큐에 대기 하 고 이미 수행 하지 않은 경우 처리 작업을 시작 합니다. (재정의 [message_processor:: async_send](message-processor-class.md#async_send).)|
|[initialize](#initialize)|초기화는 `ordered_message_processor` 적절 한 콜백 함수, 스케줄러 및 일정 그룹을 사용 하 여 개체입니다.|
|[initialize_batched_processing](#initialize_batched_processing)|일관 처리된 메시지 처리 초기화|
|[sync_send](#sync_send)|동기적으로 메시지를 큐에 대기 하 고 이미 수행 하지 않은 경우 처리 작업을를 시작 합니다. (재정의 [message_processor:: sync_send](message-processor-class.md#sync_send).)|
|[wait](#wait)|모든 비동기 처리 작업 블록을 제거 하기 전에 시간이 있는지 확인 하려면 메시지 블록의 소멸자에 사용 되는 특정 프로세서 관련 스핀 대기 합니다. (재정의 [message_processor:: wait](message-processor-class.md#wait).)|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|비동기적으로 호출 되는 처리 함수입니다. 메시지를 큐에서 제거 하 고 처리를 시작 합니다. (재정의 [message_processor:: process_incoming_message](message-processor-class.md#process_incoming_message).)|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[message_processor](message-processor-class.md)

`ordered_message_processor`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="async_send"></a> async_send

비동기적으로 메시지를 큐에 대기 하 고 이미 수행 하지 않은 경우 처리 작업을 시작 합니다.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>매개 변수

*_Msg*<br/>
메시지에 대 한 포인터입니다.

##  <a name="initialize"></a> 초기화

초기화는 `ordered_message_processor` 적절 한 콜백 함수, 스케줄러 및 일정 그룹을 사용 하 여 개체입니다.

```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```

### <a name="parameters"></a>매개 변수

*_PScheduler*<br/>
간단한 작업을 예약 하는 데 사용할 스케줄러에 대 한 포인터입니다.

*_PScheduleGroup*<br/>
간단한 작업을 예약 하는 데 사용할 일정 그룹에 대 한 포인터입니다.

*_Handler*<br/>
콜백 중에 호출 처리기 함수입니다.

##  <a name="initialize_batched_processing"></a> initialize_batched_processing

일관 처리된 메시지 처리 초기화

```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```

### <a name="parameters"></a>매개 변수

*_Processor*<br/>
콜백 중에 호출 처리기 함수입니다.

*_Propagator*<br/>
콜백 중에 호출 전파자 함수입니다.

##  <a name="ctor"></a> ordered_message_processor

`ordered_message_processor` 개체를 생성합니다.

```
ordered_message_processor();
```

### <a name="remarks"></a>설명

이 `ordered_message_processor` 될 때까지 동기 또는 비동기 처리기를 예약 하지 것입니다는 `initialize` 함수를 호출 합니다.

##  <a name="dtor"></a> ~ordered_message_processor

제거 된 `ordered_message_processor` 개체입니다.

```
virtual ~ordered_message_processor();
```

### <a name="remarks"></a>설명

프로세서를 제거 하기 전에 모든 대기 중인 비동기 작업을 기다립니다.

##  <a name="process_incoming_message"></a> process_incoming_message

비동기적으로 호출 되는 처리 함수입니다. 메시지를 큐에서 제거 하 고 처리를 시작 합니다.

```
virtual void process_incoming_message();
```

##  <a name="sync_send"></a> sync_send

동기적으로 메시지를 큐에 대기 하 고 이미 수행 하지 않은 경우 처리 작업을를 시작 합니다.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>매개 변수

*_Msg*<br/>
메시지에 대 한 포인터입니다.

##  <a name="wait"></a> 대기

모든 비동기 처리 작업 블록을 제거 하기 전에 시간이 있는지 확인 하려면 메시지 블록의 소멸자에 사용 되는 특정 프로세서 관련 스핀 대기 합니다.

```
virtual void wait();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
