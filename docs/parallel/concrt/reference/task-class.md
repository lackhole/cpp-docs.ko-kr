---
title: 작업 클래스(동시성 런타임)
ms.date: 11/04/2016
f1_keywords:
- task
- PPLTASKS/concurrency::task
- PPLTASKS/concurrency::task::task
- PPLTASKS/concurrency::task::get
- PPLTASKS/concurrency::task::is_apartment_aware
- PPLTASKS/concurrency::task::is_done
- PPLTASKS/concurrency::task::scheduler
- PPLTASKS/concurrency::task::then
- PPLTASKS/concurrency::task::wait
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
ms.openlocfilehash: 99676ac0fff9584cd8453562f8918f6cadd66666
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385208"
---
# <a name="task-class-concurrency-runtime"></a>작업 클래스(동시성 런타임)

PPL(병렬 패턴 라이브러리) `task` 클래스입니다. `task` 개체는 비동기식으로 실행할 수 있으며 동시성 런타임의 병렬 알고리즘을 통해 생성되는 기타 작업 및 병렬 작업과 동시에 실행할 수 있는 작업을 나타냅니다. 이러한 작업이 정상적으로 완료되면 `_ResultType` 형식의 결과가 생성됩니다. `task<void>` 형식의 작업에서는 결과가 생성되지 않습니다. 작업은 다른 작업과 관계없이 대기 및 취소할 수 있으며 Continuation을 사용 하 여 다른 작업을 사용 하 여 구성 될 수도 있습니다 ( `then`), 조인 ( `when_all`) 및 선택 ( `when_any`) 패턴.

## <a name="syntax"></a>구문

```
template <typename T>
class task;

template <>
class task<void>;

template<typename _ReturnType>
class task;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
태스크 개체 유형입니다.

*_ReturnType*<br/>
이 작업의 결과 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`result_type`|이 클래스의 개체가 생성하는 결과의 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[task](#ctor)|오버로드됨. `task` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[get](#get)|오버로드됨. 이 작업으로 생성된 결과를 반환합니다. 작업이 종료 상태가 아닐 경우 `get`에 대한 호출은 작업이 끝날 때까지 대기합니다. 이 메서드는 `result_type`의 `void`을 사용하는 작업에서 호출될 때는 값을 반환하지 않습니다.|
|[is_apartment_aware](#is_apartment_aware)|작업이 Windows 런타임 `IAsyncInfo` 인터페이스의 래핑을 해제하는지 여부 또는 그러한 작업의 하위 작업인지 여부를 확인합니다.|
|[is_done](#is_done)|작업 완료 여부를 확인합니다.|
|[scheduler](#scheduler)|이 작업에 대해 스케줄러를 반환합니다.|
|[then](#then)|오버로드됨. 이 작업에 연속 작업을 추가합니다.|
|[wait](#wait)|이 작업이 종료 상태에 도달할 때까지 기다립니다. `wait`은 작업 종속성을 모두 만족하며 백그라운드 작업자에 의해 이미 선택되지 않은 경우 작업을 인라인 실행할 수 있습니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator!=](#operator_neq)|오버로드됨. 두 `task` 개체가 서로 다른 내부 작업을 나타내는지 여부를 확인합니다.|
|[operator=](#operator_eq)|오버로드됨. 하나의 `task` 개체 콘텐츠를 다른 개체 콘텐츠로 바꿉니다.|
|[연산자==](#operator_eq_eq)|오버로드됨. 두 `task` 개체가 동일한 내부 작업을 나타내는지 여부를 확인합니다.|

## <a name="remarks"></a>설명

자세한 내용은 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`task`

## <a name="requirements"></a>요구 사항

**헤더:** ppltasks.h

**네임스페이스:** 동시성

##  <a name="get"></a> get

이 작업으로 생성된 결과를 반환합니다. 작업이 종료 상태가 아닐 경우 `get`에 대한 호출은 작업이 끝날 때까지 대기합니다. 이 메서드는 `result_type`의 `void`을 사용하는 작업에서 호출될 때는 값을 반환하지 않습니다.

```
_ReturnType get() const;

void get() const;
```

### <a name="return-value"></a>반환 값

작업의 결과입니다.

### <a name="remarks"></a>설명

작업이 취소 되 면 호출 `get` 시킵니다를 [task_canceled](task-canceled-class.md) 예외입니다. 작업에서 다른 예외가 발생하거나 예외가 선행 작업에서 전파된 경우 `get`에 대한 호출은 해당 예외를 throw합니다.

> [!IMPORTANT]
>  유니버설 Windows 플랫폼 (UWP) 앱에서 호출 하지 마세요 [concurrency::task::wait](#wait) 하거나 `get` ( `wait` 호출 `get`) 사용자 인터페이스 스레드에서 실행 되는 코드에서. 그렇지 않으면 런타임에서 throw [concurrency:: invalid_operation](invalid-operation-class.md) 있으므로 이러한 메서드는 현재 스레드를 차단 하 고 응용 프로그램에서 응답 하지 않게 될 수 있습니다. 그러나 호출할 수는 `get` 결과 즉시 사용할 수 있으므로 작업 기반 연속에서 선행 작업의 결과 수신 하는 방법입니다.

##  <a name="is_apartment_aware"></a> is_apartment_aware

작업이 Windows 런타임 `IAsyncInfo` 인터페이스의 래핑을 해제하는지 여부 또는 그러한 작업의 하위 작업인지 여부를 확인합니다.

```
bool is_apartment_aware() const;
```

### <a name="return-value"></a>반환 값

**true** 작업의 래핑을 해제 하는 경우는 `IAsyncInfo` 인터페이스 또는 그러한 작업의 하위 **false** 그렇지 않은 경우.

##  <a name="is_done"></a>  task:: is_done 메서드 (동시성 런타임)

작업 완료 여부를 확인합니다.

```
bool is_done() const;
```

### <a name="return-value"></a>반환 값

작업이 완료 된 경우 false이 고, 그렇지 true입니다.

### <a name="remarks"></a>설명

작업이 완료 되거나 (사용자 예외 없이 또는)를 취소 하는 경우 true를 반환 합니다.

##  <a name="operator_neq"></a> operator!=

두 `task` 개체가 서로 다른 내부 작업을 나타내는지 여부를 확인합니다.

```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
작업 비교입니다.

### <a name="return-value"></a>반환 값

**true** 서로 다른 기본 작업 개체가 참조 하는 경우 및 **false** 그렇지 않은 경우.

##  <a name="operator_eq"></a> operator=

하나의 `task` 개체 콘텐츠를 다른 개체 콘텐츠로 바꿉니다.

```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
소스 `task` 개체입니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

`task`가 스마트 포인터와 같이 작동할 경우, 복사 할당 후 이 `task` 개체는 `_Other`와 동일한 실제 작업을 나타냅니다.

##  <a name="operator_eq_eq"></a> operator==

두 `task` 개체가 동일한 내부 작업을 나타내는지 여부를 확인합니다.

```
bool operator== (const task<_ReturnType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
작업 비교입니다.

### <a name="return-value"></a>반환 값

**true** 개체가 참조는 같은 기본 작업을 하는 경우 및 **false** 그렇지 않은 경우.

##  <a name="scheduler"></a>  task:: scheduler 메서드 (동시성 런타임)

이 작업에 대해 스케줄러를 반환합니다.

```
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>반환 값

스케줄러에 대 한 포인터

##  <a name="ctor"></a> 작업

`task` 개체를 생성합니다.

```
task();

template<typename T>
__declspec(
    noinline) explicit task(T _Param);

template<typename T>
__declspec(
    noinline) explicit task(T _Param, const task_options& _TaskOptions);

task(
    const task& _Other);

task(
    task&& _Other);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
작업이 생성되는 매개 변수 형식입니다.

*_Param*<br/>
작업이 생성되는 매개 변수입니다. 람다, 함수 개체 수를 `task_completion_event<result_type>` 개체 또는 Windows 런타임 앱에서 작업을 사용 하는 경우 Windows::Foundation::IAsyncInfo 합니다. 람다 또는 함수 개체는 동일한 형식 이어야 합니다 `std::function<X(void)>`여기서 X 형식 변수의 수, `result_type`, `task<result_type>`, 또는 Windows 런타임 앱에서 Windows::Foundation::IAsyncInfo 합니다.

*_TaskOptions*<br/>
작업 옵션에는 취소 토큰, 스케줄러 등이 포함됩니다.

*_Other*<br/>
소스 `task` 개체입니다.

### <a name="remarks"></a>설명

`task`에 대한 기본 생성자는 컨테이너 내에서 사용할 수 있는 작업을 허용하기 위해서만 존재합니다. 유효한 작업을 할당할 때까지 기본 생성 작업을 사용할 수 없습니다. 와 같은 메서드 `get`, `wait` 또는 `then` 시킵니다를 [invalid_argument](../../../standard-library/invalid-argument-class.md) 는 기본 생성 작업에서 호출 하는 동안 예외가 발생 합니다.

`task_completion_event`에서 만든 작업은 작업 완료 이벤트가 설정되면 완료됩니다(연속 실행되도록 예약되어 있음).

취소 토큰을 사용하는 생성자의 버전은 이 토큰을 가져온 `cancellation_token_source`를 사용하여 취소할 수 있는 작업을 만듭니다. 취소 토큰 없이 만든 작업은 취소할 수 없습니다.

`Windows::Foundation::IAsyncInfo` 인터페이스에서 생성되었거나 `IAsyncInfo` 인터페이스를 반환하는 람다에서 생성된 작업은 포함된 Windows 런타임 비동기 작업 또는 동작이 완료될 때 종료 상태에 도달합니다. 마찬가지로 `task<result_type>`을 반환하는 람다에서 생성된 작업은 내부 작업이 종료 상태에 도달하고 람다가 반환되지 않을 때 종료 상태에 도달합니다.

`task`는 스마트 포인터처럼 작동하고 값으로 안전하게 전달됩니다. 또한 잠글 필요 없이 여러 스레드에서 액세스할 수 있습니다.

Windows::Foundation::IAsyncInfo 인터페이스 또는 그러한 인터페이스를 반환 하는 람다를 사용 하는 생성자 오버 로드만 Windows 런타임 앱에 사용할 수 있습니다.

자세한 내용은 [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.

##  <a name="then"></a> 그런 다음

이 작업에 연속 작업을 추가합니다.

```
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions = task_options()) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;
```

### <a name="parameters"></a>매개 변수

*_Function*<br/>
이 작업으로 호출될 함수 개체의 형식입니다.

*_Func*<br/>
이 작업이 완료될 때 실행되는 연속 함수입니다. 이 연속 함수는 `result_type` 또는 `task<result_type>`을 입력 변수로 사용해야 하며, 여기서 `result_type`은 이 작업에서 생성하는 결과의 형식입니다.

*_TaskOptions*<br/>
작업 옵션에는 취소 토큰, 스케줄러 및 연속 컨텍스트가 포함됩니다. 기본적으로 앞의 세 가지 옵션은 선행 작업에서 상속됩니다.

*_CancellationToken*<br/>
연속 작업에 연결할 취소 토큰입니다. 취소 토큰 없이 만든 연속 작업은 선행 작업의 토큰을 상속합니다.

*_ContinuationContext*<br/>
연속이 실행되어야 하는 위치를 지정하는 변수입니다. 이 변수는만 UWP 앱에서 사용 하는 경우에 유용 합니다. 자세한 내용은 참조 하세요. [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>반환 값

새로 만든 연속 작업입니다. 반환된 작업의 결과 형식은 `_Func`가 반환하는 것에 따라 결정됩니다.

### <a name="remarks"></a>설명

오버 로드 `then` 람다 또는 함수 Windows::Foundation::IAsyncInfo 인터페이스를 반환 하는, Windows 런타임 앱에서 사용할 개만 있습니다.

작업 연속을 사용 하 여 비동기 작업을 작성 하는 방법에 대 한 자세한 내용은 참조 하세요. [작업 병렬 처리](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다.

##  <a name="wait"></a> 대기

이 작업이 종료 상태에 도달할 때까지 기다립니다. `wait`은 작업 종속성을 모두 만족하며 백그라운드 작업자에 의해 이미 선택되지 않은 경우 작업을 인라인 실행할 수 있습니다.

```
task_status wait() const;
```

### <a name="return-value"></a>반환 값

`task_status` 또는 `completed`가 될 수 있는 `canceled` 값입니다. 작업 실행 중에 예외가 발생하거나 예외가 선행 작업에서 전파된 경우 `wait`은 해당 예외를 throw합니다.

### <a name="remarks"></a>설명

> [!IMPORTANT]
>  유니버설 Windows 플랫폼 (UWP) 앱에서 호출 하지 마십시오 `wait` 사용자 인터페이스 스레드에서 실행 되는 코드에 있습니다. 호출하는 경우 이 메서드가 현재 스레드를 차단하고 앱이 응답하지 않게 만들 수 있기 때문에 런타임에서 [concurrency::invalid_operation](invalid-operation-class.md) 을 throw합니다. 그러나 [concurrency::task::get](#get) 메서드를 호출하여 작업 기반 연속에서 선행 작업의 결과를 받을 수 있습니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
