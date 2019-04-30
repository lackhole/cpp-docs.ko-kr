---
title: message 클래스
ms.date: 11/04/2016
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
ms.openlocfilehash: 83cfdb5807581f7092709691a1839052abdd657c
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343850"
---
# <a name="message-class"></a>message 클래스

메시징 블록 간에 전달되는 데이터 페이로드를 포함하는 기본 메시지 봉투입니다.

## <a name="syntax"></a>구문

```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
메시지 페이로드의의 데이터 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`type`|에 대 한 형식 별칭을 `T`입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[message](#ctor)|오버로드됨. `message` 개체를 생성합니다.|
|[~ message 소멸자](#dtor)|제거 된 `message` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[add_ref](#add_ref)|참조 횟수에 추가 된 `message` 개체입니다. 메시지 수명 결정 하기 위해 참조 가산을 해야 하는 메시지 블록에 사용 됩니다.|
|[msg_id](#msg_id)|ID를 반환 합니다 `message` 개체입니다.|
|[remove_ref](#remove_ref)|에 대 한 참조 개수에서 뺍니다는 `message` 개체입니다. 메시지 수명 결정 하기 위해 참조 가산을 해야 하는 메시지 블록에 사용 됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[payload](#payload)|페이로드를 `message` 개체입니다.|

## <a name="remarks"></a>설명

자세한 내용은 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`message`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="add_ref"></a> add_ref

참조 횟수에 추가 된 `message` 개체입니다. 메시지 수명 결정 하기 위해 참조 가산을 해야 하는 메시지 블록에 사용 됩니다.

```
long add_ref();
```

### <a name="return-value"></a>반환 값

참조 횟수의 새 값입니다.

##  <a name="ctor"></a> 메시지

`message` 개체를 생성합니다.

```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```

### <a name="parameters"></a>매개 변수

*_P*<br/>
이 메시지의 페이로드입니다.

*_Id*<br/>
이 메시지의 고유 ID입니다.

*_Msg*<br/>
참조 또는에 대 한 포인터를 `message` 개체입니다.

### <a name="remarks"></a>설명

에 대 한 포인터를 사용 하는 생성자는 `message` 인수로 throw 개체는 [invalid_argument](../../../standard-library/invalid-argument-class.md) 예외 경우 매개 변수 `_Msg` 는 `NULL`합니다.

##  <a name="dtor"></a> ~message

제거 된 `message` 개체입니다.

```
virtual ~message();
```

##  <a name="msg_id"></a> msg_id

ID를 반환 합니다 `message` 개체입니다.

```
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>반환 값

합니다 `runtime_object_identity` 의 `message` 개체입니다.

##  <a name="payload"></a> 페이로드

페이로드를 `message` 개체입니다.

```
T const payload;
```

##  <a name="remove_ref"></a> remove_ref

에 대 한 참조 개수에서 뺍니다는 `message` 개체입니다. 메시지 수명 결정 하기 위해 참조 가산을 해야 하는 메시지 블록에 사용 됩니다.

```
long remove_ref();
```

### <a name="return-value"></a>반환 값

참조 횟수의 새 값입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
