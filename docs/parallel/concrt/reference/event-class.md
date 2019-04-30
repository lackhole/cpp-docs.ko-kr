---
title: event 클래스
ms.date: 11/04/2016
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
ms.openlocfilehash: aa9d46b868c1a31729a9590db3b3f67179903881
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262393"
---
# <a name="event-class"></a>event 클래스

동시성 런타임을 명시적으로 인식하는 수동 다시 설정 이벤트입니다.

## <a name="syntax"></a>구문

```
class event;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[~ event 소멸자](#dtor)|이벤트를 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[reset](#reset)|이벤트 신호 되지 않은 상태로 다시 설정합니다.|
|[set](#set)|이벤트 신호를 보냅니다.|
|[wait](#wait)|이벤트가 신호를 받을 때까지 기다립니다.|
|[wait_for_multiple](#wait_for_multiple)|여러 이벤트 신호를 받을 때까지 기다립니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[timeout_infinite](#timeout_infinite)|대기 시간이 초과되지 않아야 함을 나타내는 값입니다.|

## <a name="remarks"></a>설명

자세한 내용은 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`event`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> 이벤트

새 이벤트를 생성합니다.

```
_CRTIMP event();
```

### <a name="remarks"></a>설명

##  <a name="dtor"></a> ~event

이벤트를 제거합니다.

```
~event();
```

### <a name="remarks"></a>설명

소멸자가 실행 될 때 이벤트에서 대기 중인 스레드가 없는 것으로 예상 됩니다. 이벤트가 해당 이벤트를 계속 대기 중인 스레드와 함께 소멸할 수 있도록 허용하면 정의되지 않은 동작이 발생합니다.

##  <a name="reset"></a> 다시 설정

이벤트 신호 되지 않은 상태로 다시 설정합니다.

```
void reset();
```

##  <a name="set"></a> 설정

이벤트 신호를 보냅니다.

```
void set();
```

### <a name="remarks"></a>설명

이벤트에 신호를 보내면 이벤트를 대기하고 있는 임의 수의 컨텍스트가 실행 가능하게 됩니다.

##  <a name="timeout_infinite"></a> timeout_infinite

대기 시간이 초과되지 않아야 함을 나타내는 값입니다.

```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```

##  <a name="wait"></a> 대기

이벤트가 신호를 받을 때까지 기다립니다.

```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*_Timeout*<br/>
대기 시간이 초과 되기까지의 시간 (밀리초)의 수를 나타냅니다. 값 `COOPERATIVE_TIMEOUT_INFINITE` 제한 시간이 없음을 임을 나타냅니다.

### <a name="return-value"></a>반환 값

대기가 충족 된 경우 값 `0` 고, 그렇지 않으면 반환 값 `COOPERATIVE_WAIT_TIMEOUT` 신호 이벤트 없이 대기 시간이 초과 된 나타냅니다.

> [!IMPORTANT]
>  유니버설 Windows 플랫폼 (UWP) 앱에서 호출 하지 마십시오 `wait` ASTA에서 스레드와이 호출은 현재 스레드를 차단 하 고 응용 프로그램에서 응답 하지 않게 될 수 있습니다.

##  <a name="wait_for_multiple"></a> wait_for_multiple

여러 이벤트 신호를 받을 때까지 기다립니다.

```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>매개 변수

*_PPEvents*<br/>
배열 대기 하는 이벤트입니다. 배열 내의 이벤트 수가 나타난는 `count` 매개 변수입니다.

*count*<br/>
제공 된 배열 내에서 이벤트의 수를 `_PPEvents` 매개 변수입니다.

*_FWaitAll*<br/>
경우 값으로 설정 **true**, 매개 변수 배열 내에서 모든 이벤트에서 제공 하는 지정 된 `_PPEvents` 매개 변수는 대기를 만족 하려면 신호를 보내야 합니다. 경우 값으로 설정 **false**, 배열 내에서 모든 이벤트에 제공 하는 지정 된 `_PPEvents` 신호는 매개 변수는 대기를 만족 합니다.

*_Timeout*<br/>
대기 시간이 초과 되기까지의 시간 (밀리초)의 수를 나타냅니다. 값 `COOPERATIVE_TIMEOUT_INFINITE` 제한 시간이 없음을 임을 나타냅니다.

### <a name="return-value"></a>반환 값

배열 내의 인덱스에 제공 된 경우 대기가 충족 되었음을 합니다 `_PPEvents` 는 대기 조건을 충족 하는 매개 변수가 고, 그렇지 값 `COOPERATIVE_WAIT_TIMEOUT` 조건이 충족 될 없이 대기 시간이 초과 된 나타내려면 합니다.

### <a name="remarks"></a>설명

경우 매개 변수 `_FWaitAll` 값으로 설정 됩니다 `true` 는 모든 이벤트 신호를 보내야 하는 대기를 만족을 나타내기 위해 함수에서 반환 된 인덱스가 전달 것 값 이외의 다른 특별 한 의미가 없습니다 `COOPERATIVE_WAIT_TIMEOUT`합니다.

> [!IMPORTANT]
> 유니버설 Windows 플랫폼 (UWP) 앱에서 호출 하지 마십시오 `wait_for_multiple` ASTA에서 스레드와이 호출은 현재 스레드를 차단 하 고 응용 프로그램에서 응답 하지 않게 될 수 있습니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
