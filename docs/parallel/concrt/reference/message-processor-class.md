---
title: message_processor 클래스
ms.date: 11/04/2016
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
ms.openlocfilehash: be6cb1c614a41919663a4cc063da66679556e498
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409956"
---
# <a name="messageprocessor-class"></a>message_processor 클래스

`message_processor` 클래스는 `message` 개체 처리를 위한 추상 기본 클래스입니다. 메시지 순서에 대한 보장은 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class message_processor;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
이 데이터 형식의 메시지 페이로드의 처리 `message_processor` 개체입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`type`|에 대 한 형식 별칭을 `T`입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[async_send](#async_send)|파생된 클래스에서 재정의 하는 경우 메시지를 비동기적으로 블록에 넣습니다.|
|[sync_send](#sync_send)|파생된 클래스에서 재정의 되 면 메시지를 동기적으로 된 블록에 넣습니다.|
|[wait](#wait)|파생된 클래스에서 재정의 되 면 모든 비동기 작업이 완료 될 때까지 기다립니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|파생된 클래스에서 재정의 되 면 블록으로 전달 메시지 처리를 수행 합니다. 새 메시지가 추가 되 고 큐가 비워 둘 수 때마다 한 번 호출 됩니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`message_processor`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="async_send"></a> async_send

파생된 클래스에서 재정의 하는 경우 메시지를 비동기적으로 블록에 넣습니다.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>매개 변수

*_Msg*<br/>
`message` 비동기적으로 보낼 개체입니다.

### <a name="remarks"></a>설명

프로세서 구현에서는이 메서드를 재정의 해야 합니다.

##  <a name="process_incoming_message"></a> process_incoming_message

파생된 클래스에서 재정의 되 면 블록으로 전달 메시지 처리를 수행 합니다. 새 메시지가 추가 되 고 큐가 비워 둘 수 때마다 한 번 호출 됩니다.

```
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>설명

메시지 블록 구현은이 메서드를 재정의 해야 합니다.

##  <a name="sync_send"></a> sync_send

파생된 클래스에서 재정의 되 면 메시지를 동기적으로 된 블록에 넣습니다.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>매개 변수

*_Msg*<br/>
`message` 동기적으로 보낼 개체입니다.

### <a name="remarks"></a>설명

프로세서 구현에서는이 메서드를 재정의 해야 합니다.

##  <a name="wait"></a> 대기

파생된 클래스에서 재정의 되 면 모든 비동기 작업이 완료 될 때까지 기다립니다.

```
virtual void wait() = 0;
```

### <a name="remarks"></a>설명

프로세서 구현에서는이 메서드를 재정의 해야 합니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[ordered_message_processor 클래스](ordered-message-processor-class.md)
