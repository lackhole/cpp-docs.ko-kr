---
title: choice 클래스
ms.date: 11/04/2016
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
ms.openlocfilehash: aa4945bb5f9ef28937487ba504e23c461992b263
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337572"
---
# <a name="choice-class"></a>choice 클래스

`choice` 메시징 블록은 소스 집합과의 제어 흐름 상호 작용을 나타내는 다중 소스 단일 대상 블록입니다. 선택한 블록은 여러 소스 중 하나가 메시지를 생성할 때까지 대기하고 메시지를 생성한 소스의 인덱스를 전파합니다.

## <a name="syntax"></a>구문

```
template<
    class T
>
class choice: public ISource<size_t>;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
`tuple`-기반 입력 원본의 페이로드를 나타내는 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`type`|에 대 한 형식 별칭을 `T`입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[choice](#ctor)|오버로드됨. `choice` 메시징 블록을 생성합니다.|
|[~ choice 소멸자](#dtor)|제거 된 `choice` 메시징 블록입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[accept](#accept)|이 제공 된 메시지를 수락 `choice` 블록을 호출자에 게 소유권을 전송 합니다.|
|[acquire_ref](#acquire_ref)|이 참조 횟수를 가져옵니다 `choice` 삭제를 방지 하기 위해 메시징 블록입니다.|
|[consume](#consume)|이전에 제공한 메시지를 생성 `choice` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 합니다.|
|[has_value](#has_value)|확인 여부를이 `choice` 아직 메시징 블록 값으로 초기화 했습니다.|
|[index](#index)|에 인덱스를 반환 합니다 `tuple` 에서 선택한 요소를 나타내는 `choice` 메시징 블록입니다.|
|[link_target](#link_target)|이 대상 블록에 연결 `choice` 메시징 블록입니다.|
|[release](#release)|이전 성공적인 메시지 예약을 해제합니다.|
|[release_ref](#release_ref)|이 참조 횟수를 해제 `choice` 메시징 블록입니다.|
|[reserve](#reserve)|이전에 제공한 메시지를 예약 `choice` 메시징 블록입니다.|
|[unlink_target](#unlink_target)|이 대상 블록을 연결 해제 `choice` 메시징 블록입니다.|
|[unlink_targets](#unlink_targets)|이 모든 대상의 연결을 해제 `choice` 메시징 블록입니다. (재정의 [isource:: Unlink_targets](isource-class.md#unlink_targets).)|
|[값](#value)|인덱스를 포함 하 여 선택 된 메시지를 가져옵니다는 `choice` 메시징 블록입니다.|

## <a name="remarks"></a>설명

선택한 블록 하면 들어오는 메시지 중 하나에 사용 됩니다.

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="accept"></a> 허용

이 제공 된 메시지를 수락 `choice` 블록을 호출자에 게 소유권을 전송 합니다.

```
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 제공 되의 `message` 개체입니다.

*_PTarget*<br/>
호출 하는 대상 블록에 대 한 포인터를 `accept` 메서드.

### <a name="return-value"></a>반환 값

호출자의 소유권에는 메시지에 대 한 포인터입니다.

##  <a name="acquire_ref"></a> acquire_ref

이 참조 횟수를 가져옵니다 `choice` 삭제를 방지 하기 위해 메시징 블록입니다.

```
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 프로그램 `ITarget` 하는 동안이 원본에 연결 되는 개체는 `link_target` 메서드.

##  <a name="ctor"></a> choice

`choice` 메시징 블록을 생성합니다.

```
explicit choice(
    T _Tuple);

choice(
    Scheduler& _PScheduler,
    T _Tuple);

choice(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

choice(
    choice&& _Choice);
```

### <a name="parameters"></a>매개 변수

*_Tuple*<br/>
선택을 위한 소스의 `tuple` 입니다.

*_PScheduler*<br/>
`Scheduler` 메시징 블록의 전파 작업이 예약되는 `choice` 개체입니다.

*_PScheduleGroup*<br/>
`ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `choice` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

*_Choice*<br/>
복사할 `choice` 메시징 블록입니다. 원래 개체는 고아로 표시되어 생성자가 이동하도록 합니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

잠금이 있는 경우 이동 생성은 수행되지 않습니다. 즉, 이동하는 중에 간단한 작업이 실행되고 있지 않은지 확인할 책임은 사용자에게 있습니다. 그러지 않으면 수많은 레이스가 발생하여 예외가 발생하거나 일관성 없는 상태가 될 수 있습니다.

##  <a name="dtor"></a> ~choice

제거 된 `choice` 메시징 블록입니다.

```
~choice();
```

##  <a name="consume"></a> consume

이전에 제공한 메시지를 생성 `choice` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 합니다.

```
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 예약 된의 `message` 개체입니다.

*_PTarget*<br/>
호출 하는 대상 블록에 대 한 포인터를 `consume` 메서드.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `message` 호출자에 이제 소유권을 가진 개체입니다.

### <a name="remarks"></a>설명

`consume` 메서드와 비슷합니다 `accept`를 항상 호출을 통해 야 하지만 `reserve` 반환 **true**합니다.

##  <a name="has_value"></a> has_value

확인 여부를이 `choice` 아직 메시징 블록 값으로 초기화 했습니다.

```
bool has_value() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 블록에 값을 받은 경우 **false** 그렇지 않은 경우.

##  <a name="index"></a> index

에 인덱스를 반환 합니다 `tuple` 에서 선택한 요소를 나타내는 `choice` 메시징 블록입니다.

```
size_t index();
```

### <a name="return-value"></a>반환 값

메시지 인덱스입니다.

### <a name="remarks"></a>설명

사용 하 여 메시지 페이로드를 추출할 수 있습니다는 `get` 메서드.

##  <a name="link_target"></a> link_target

이 대상 블록에 연결 `choice` 메시징 블록입니다.

```
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
에 대 한 포인터를 `ITarget` 이 연결할 블록 `choice` 메시징 블록입니다.

##  <a name="release"></a> 릴리스

이전 성공적인 메시지 예약을 해제합니다.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 릴리스될 개체입니다.

*_PTarget*<br/>
호출 하는 대상 블록에 대 한 포인터를 `release` 메서드.

##  <a name="release_ref"></a> release_ref

이 참조 횟수를 해제 `choice` 메시징 블록입니다.

```
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 `ITarget` 이 원본에서 연결이 해제 되는 개체입니다. 소스 블록 대상 블록에 대 한 예약 된 리소스를 해제할 수 있습니다.

##  <a name="reserve"></a> 예약

이전에 제공한 메시지를 예약 `choice` 메시징 블록입니다.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 받고 있는 개체입니다.

*_PTarget*<br/>
호출 하는 대상 블록에 대 한 포인터를 `reserve` 메서드.

### <a name="return-value"></a>반환 값

**true 이면** 메시지를 성공적으로 예약 하는 경우 **false** 그렇지 않은 경우. 예약은 메시지를 이미 다른 대상이 예약했거나 수락한 경우, 소스에서 예약을 거부한 경우 등과 같은 다양한 이유로 실패할 수 있습니다.

### <a name="remarks"></a>설명

호출한 후 `reserve`를 호출 해야 성공 하면 `consume` 또는 `release` 수행 하거나 각각 메시지의 소유를 포기 하기 위해.

##  <a name="unlink_target"></a> unlink_target

이 대상 블록을 연결 해제 `choice` 메시징 블록입니다.

```
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
에 대 한 포인터를 `ITarget` 블록에서이 연결을 끊을 `choice` 메시징 블록입니다.

##  <a name="unlink_targets"></a> unlink_targets

이 모든 대상의 연결을 해제 `choice` 메시징 블록입니다.

```
virtual void unlink_targets();
```

### <a name="remarks"></a>설명

이 메서드는 때문에 소멸자에서 호출 하지 않아도 내부에 대 한 소멸자 `single_assignment` 블록을 올바르게 연결 해제 합니다.

##  <a name="value"></a> 값

인덱스를 포함 하 여 선택 된 메시지를 가져옵니다는 `choice` 메시징 블록입니다.

```
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>매개 변수

*_Payload_type*<br/>
메시지 페이로드의 형식입니다.

### <a name="return-value"></a>반환 값

메시지의 페이로드입니다.

### <a name="remarks"></a>설명

`choice` 메시징 블록은 페이로드 형식이 서로 다른 입력을 사용할 수 있기 때문에 검색 시 페이로드의 형식을 지정해야 합니다. 결과에 따라 형식을 확인할 수 있습니다는 `index` 메서드.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[join 클래스](join-class.md)<br/>
[single_assignment 클래스](single-assignment-class.md)
