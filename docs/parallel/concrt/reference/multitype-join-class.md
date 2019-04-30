---
title: multitype_join 클래스
ms.date: 11/04/2016
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
ms.openlocfilehash: 7a0c68c2c017eedfa23548bee1d17177e8eaaa1e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409949"
---
# <a name="multitypejoin-class"></a>multitype_join 클래스

`multitype_join` 메시징 블록은 각 소스에서 다양한 형식의 메시지를 결합하고 결합된 메시지의 튜플을 대상에 제공하는 다중 소스, 단일 대상 메시징 블록입니다.

## <a name="syntax"></a>구문

```
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
`tuple` 조인 되 고 블록에 의해 전파 메시지의 페이로드 형식입니다.

*_Jtype*<br/>
종류의 `join` 차단 하거나 이것이 `greedy` 또는 `non_greedy`

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`type`|에 대 한 형식 별칭을 `T`입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[multitype_join](#ctor)|오버로드됨. `multitype_join` 메시징 블록을 생성합니다.|
|[~multitype_join Destructor](#dtor)|제거 된 `multitype_join` 메시징 블록입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[accept](#accept)|이 제공 된 메시지를 수락 `multitype_join` 블록을 호출자에 게 소유권을 전송 합니다.|
|[acquire_ref](#acquire_ref)|이 참조 횟수를 가져옵니다 `multitype_join` 삭제를 방지 하기 위해 메시징 블록입니다.|
|[consume](#consume)|이전에 제공 하는 메시지를 생성 합니다 `multitype_join` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 합니다.|
|[link_target](#link_target)|이 대상 블록에 연결 `multitype_join` 메시징 블록입니다.|
|[release](#release)|이전 성공적인 메시지 예약을 해제합니다.|
|[release_ref](#release_ref)|이 참조 횟수를 해제 `multiple_join` 메시징 블록입니다.|
|[reserve](#reserve)|이전에 제공한 메시지를 예약 `multitype_join` 메시징 블록입니다.|
|[unlink_target](#unlink_target)|이 대상 블록을 연결 해제 `multitype_join` 메시징 블록입니다.|
|[unlink_targets](#unlink_targets)|이 모든 대상의 연결을 해제 `multitype_join` 메시징 블록입니다. (재정의 [isource:: Unlink_targets](isource-class.md#unlink_targets).)|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[ISource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="accept"></a> 허용

이 제공 된 메시지를 수락 `multitype_join` 블록을 호출자에 게 소유권을 전송 합니다.

```
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 제공 되의 `message` 개체입니다.

*_PTarget*<br/>
호출 하는 대상 블록에 대 한 포인터를 `accept` 메서드.

### <a name="return-value"></a>반환 값

호출자의 소유권에는 메시지에 대 한 포인터입니다.

##  <a name="acquire_ref"></a> acquire_ref

이 참조 횟수를 가져옵니다 `multitype_join` 삭제를 방지 하기 위해 메시징 블록입니다.

```
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 프로그램 `ITarget` 하는 동안이 원본에 연결 되는 개체는 `link_target` 메서드.

##  <a name="consume"></a> consume

이전에 제공 하는 메시지를 생성 합니다 `multitype_join` 메시징 블록이 고 호출자에 게 소유권을 전송 하 여 대상에 의해 성공적으로 예약 합니다.

```
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
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

##  <a name="link_target"></a> link_target

이 대상 블록에 연결 `multitype_join` 메시징 블록입니다.

```
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
에 대 한 포인터를 `ITarget` 이 연결할 블록 `multitype_join` 메시징 블록입니다.

##  <a name="ctor"></a> multitype_join

`multitype_join` 메시징 블록을 생성합니다.

```
explicit multitype_join(
    T _Tuple);

multitype_join(
    Scheduler& _PScheduler,
    T _Tuple);

multitype_join(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

multitype_join(
    multitype_join&& _Join);
```

### <a name="parameters"></a>매개 변수

*_Tuple*<br/>
이 `tuple` 메시징 블록에 대한 소스의 `multitype_join` 입니다.

*_PScheduler*<br/>
`Scheduler` 메시징 블록의 전파 작업이 예약되는 `multitype_join` 개체입니다.

*_PScheduleGroup*<br/>
`ScheduleGroup` 메시징 블록의 전파 작업이 예약되는 `multitype_join` 개체입니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.

*_Join*<br/>
복사할 `multitype_join` 메시징 블록입니다. 원래 개체는 고아로 표시되어 생성자가 이동하도록 합니다.

### <a name="remarks"></a>설명

런타임은 `_PScheduler` 또는 `_PScheduleGroup` 매개 변수를 지정하지 않는 경우 기본 스케줄러를 사용합니다.

잠금이 있는 경우 이동 생성은 수행되지 않습니다. 즉, 이동하는 중에 간단한 작업이 실행되고 있지 않은지 확인할 책임은 사용자에게 있습니다. 그러지 않으면 수많은 레이스가 발생하여 예외가 발생하거나 일관성 없는 상태가 될 수 있습니다.

##  <a name="dtor"></a> ~multitype_join

제거 된 `multitype_join` 메시징 블록입니다.

```
~multitype_join();
```

##  <a name="release"></a> 릴리스

이전 성공적인 메시지 예약을 해제합니다.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 릴리스될 개체입니다.

*_PTarget*<br/>
호출 하는 대상 블록에 대 한 포인터를 `release` 메서드.

##  <a name="release_ref"></a> release_ref

이 참조 횟수를 해제 `multiple_join` 메시징 블록입니다.

```
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 메서드를 호출 하는 대상 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 `ITarget` 이 원본에서 연결이 해제 되는 개체입니다. 소스 블록 대상 블록에 대 한 예약 된 리소스를 해제할 수 있습니다.

##  <a name="reserve"></a> 예약

이전에 제공한 메시지를 예약 `multitype_join` 메시징 블록입니다.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_MsgId*<br/>
합니다 `runtime_object_identity` 의 `message` 받고 있는 개체입니다.

*_PTarget*<br/>
호출 하는 대상 블록에 대 한 포인터를 `reserve` 메서드.

### <a name="return-value"></a>반환 값

`true` 메시지를 성공적으로 예약 하는 경우 `false` 그렇지 않은 경우. 예약은 메시지를 이미 다른 대상이 예약했거나 수락한 경우, 소스에서 예약을 거부한 경우 등과 같은 다양한 이유로 실패할 수 있습니다.

### <a name="remarks"></a>설명

호출한 후 `reserve`를 호출 해야 성공 하면 `consume` 또는 `release` 수행 하거나 각각 메시지의 소유를 포기 하기 위해.

##  <a name="unlink_target"></a> unlink_target

이 대상 블록을 연결 해제 `multitype_join` 메시징 블록입니다.

```
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
에 대 한 포인터를 `ITarget` 블록에서이 연결을 끊을 `multitype_join` 메시징 블록입니다.

##  <a name="unlink_targets"></a> unlink_targets

이 모든 대상의 연결을 해제 `multitype_join` 메시징 블록입니다.

```
virtual void unlink_targets();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[choice 클래스](choice-class.md)<br/>
[join 클래스](join-class.md)
