---
title: unique_lock 클래스
ms.date: 11/04/2016
f1_keywords:
- mutex/std::unique_lock
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
ms.openlocfilehash: 784969bea25bfff49a21c23b350afbfc8bdab59a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383518"
---
# <a name="uniquelock-class"></a>unique_lock 클래스

`mutex`의 잠금 및 잠금 해제를 관리하는 개체를 만들기 위해 인스턴스화할 수 있는 템플릿을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>설명

템플릿 인수 `Mutex`는 *뮤텍스 형식*의 이름을 지정해야 합니다.

내부적으로 `unique_lock` 연결에 대 한 포인터를 저장 `mutex` 개체와 **bool** 현재 스레드가 소유 하는지 여부를 나타내는 `mutex`합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`mutex_type`|템플릿 인수 `Mutex`에 대한 동의어입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[unique_lock](#unique_lock)|`unique_lock` 개체를 생성합니다.|
|[~unique_lock 소멸자](#dtorunique_lock_destructor)|`unique_lock` 개체와 연결된 모든 리소스를 해제합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[lock](#lock)|스레드가 연결된 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.|
|[mutex](#mutex)|연결된 `mutex`에 대해 저장된 포인터를 검색합니다.|
|[owns_lock](#owns_lock)|호출 스레드가 연결된 `mutex`를 소유하는지를 지정합니다.|
|[release](#release)|연결된 `mutex` 개체에서 `unique_lock` 개체의 연결을 끊습니다.|
|[swap](#swap)|연결된 `mutex` 및 소유권 상태를 지정된 개체의 mutex 및 소유권 상태로 바꿉니다.|
|[try_lock](#try_lock)|차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.|
|[try_lock_for](#try_lock_for)|차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.|
|[try_lock_until](#try_lock_until)|차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.|
|[unlock](#unlock)|연결된 `mutex`의 소유권을 해제합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator bool](#op_bool)|연결된 `mutex`의 소유권이 호출 스레드에 있는지를 지정합니다.|
|[operator=](#op_eq)|저장된 `mutex` 포인터 및 연결된 소유권 상태를 지정한 개체에서 복사합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

*unique_lock*<br/>

## <a name="requirements"></a>요구 사항

**헤더:** \<뮤텍스 >

**네임스페이스:** std

## <a name="lock"></a>  lock

스레드가 연결된 `mutex`의 소유권을 가져올 때까지 호출 스레드를 차단합니다.

```cpp
void lock();
```

### <a name="remarks"></a>설명

경우 저장 된 `mutex` 포인터가 NULL 이면이 메서드에서 throw 한 [system_error](../standard-library/system-error-class.md) 는 오류 코드가 있는 `operation_not_permitted`합니다.

호출 스레드가 연결된 `mutex`를 이미 소유하고 있으면 이 메서드는 오류 코드가 `resource_deadlock_would_occur`인 `system_error`를 throw합니다.

이 메서드를 호출이 고, 그렇지 `lock` 연결 된 `mutex` 내부 스레드 소유권 플래그를 설정 하 고 **true**합니다.

## <a name="mutex"></a>  mutex

연결된 `mutex`에 대해 저장된 포인터를 검색합니다.

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="op_bool"></a>  operator bool

연결된 뮤텍스의 소유권이 호출 스레드에 있는지를 지정합니다.

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>반환 값

**true 이면** 스레드가; 뮤텍스를 소유 하는 경우이 고, 그렇지 **false**합니다.

## <a name="op_eq"></a>  operator=

저장된 `mutex` 포인터 및 연결된 소유권 상태를 지정한 개체에서 복사합니다.

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>매개 변수

*기타*<br/>
`unique_lock` 개체입니다.

### <a name="return-value"></a>반환 값

`*this`

### <a name="remarks"></a>설명

이 메서드가 `mutex`에 대해 `unlock`을 호출하기 전에 호출 스레드가 이전에 연결된 `mutex`를 소유하고 있었다면 새 값이 할당됩니다.

복사 후이 메서드는 다음과 같이 설정 됩니다. *다른* 기본 생성 상태로 합니다.

## <a name="owns_lock"></a>  owns_lock

호출 스레드가 연결된 `mutex`를 소유하는지를 지정합니다.

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>반환 값

**true** 스레드가 소유 하는 경우는 `mutex`이 고, 그렇지 않으면 **false**합니다.

## <a name="release"></a>  release

연결된 `mutex` 개체에서 `unique_lock` 개체의 연결을 끊습니다.

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>반환 값

저장된 `mutex` 포인터의 이전 값입니다.

### <a name="remarks"></a>설명

이 메서드는 저장 된 값을 설정 `mutex` 내부 집합과 0에 대 한 포인터 `mutex` 소유권 플래그를 **false**합니다.

## <a name="swap"></a>  swap

연결된 `mutex` 및 소유권 상태를 지정된 개체의 mutex 및 소유권 상태로 바꿉니다.

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>매개 변수

*기타*<br/>
`unique_lock` 개체입니다.

## <a name="try_lock"></a>  try_lock

차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>반환 값

**true** 메서드는 성공적으로의 소유권을 가져올 경우 합니다 `mutex`이 고, 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

경우 저장 된 `mutex` 포인터가 NULL 이면 메서드에서 throw 된 [system_error](../standard-library/system-error-class.md) 는 오류 코드가 있는 `operation_not_permitted`합니다.

호출 스레드가 `mutex`를 이미 소유하고 있으면 이 메서드는 오류 코드가 `resource_deadlock_would_occur`인 `system_error`를 throw합니다.

## <a name="try_lock_for"></a>  try_lock_for

차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>매개 변수

*Rel_time*<br/>
메서드가 `mutex`의 소유권을 가져오려고 시도하는 최대 시간을 지정하는 [chrono::duration](../standard-library/duration-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

**true** 메서드는 성공적으로의 소유권을 가져올 경우 합니다 `mutex`이 고, 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

경우 저장 된 `mutex` 포인터가 NULL 이면 메서드에서 throw 된 [system_error](../standard-library/system-error-class.md) 는 오류 코드가 있는 `operation_not_permitted`합니다.

호출 스레드가 `mutex`를 이미 소유하고 있으면 이 메서드는 오류 코드가 `resource_deadlock_would_occur`인 `system_error`를 throw합니다.

## <a name="try_lock_until"></a>  try_lock_until

차단되지 않고 연결된 `mutex`의 소유권을 가져오려고 시도합니다.

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>매개 변수

*Abs_time*<br/>
임계값을 지정하는 특정 시점으로, 이 시간 경과 후에는 메서드가 더 이상 `mutex`의 소유권을 가져오려고 시도하지 않습니다.

### <a name="return-value"></a>반환 값

**true** 메서드는 성공적으로의 소유권을 가져올 경우 합니다 `mutex`이 고, 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

경우 저장 된 `mutex` 포인터가 NULL 이면 메서드에서 throw 된 [system_error](../standard-library/system-error-class.md) 는 오류 코드가 있는 `operation_not_permitted`합니다.

호출 스레드가 `mutex`를 이미 소유하고 있으면 이 메서드는 오류 코드가 `resource_deadlock_would_occur`인 `system_error`를 throw합니다.

## <a name="unique_lock"></a>  unique_lock 생성자

`unique_lock` 개체를 생성합니다.

```cpp
unique_lock() noexcept;
unique_lock(unique_lock&& Other) noexcept;
explicit unique_lock(mutex_type& Mtx);

unique_lock(mutex_type& Mtx, adopt_lock_t Adopt);

unique_lock(mutex_type& Mtx, defer_lock_t Defer) noexcept;
unique_lock(mutex_type& Mtx, try_to_lock_t Try);

template <class Rep, class Period>
unique_lock(mutex_type& Mtx,
    const chrono::duration<Rep, Period>
Rel_time);

template <class Clock, class Duration>
unique_lock(mutex_type& Mtx,
    const chrono::time_point<Clock, Duration>
Abs_time);

unique_lock(mutex_type& Mtx,
    const xtime* Abs_time) noexcept;
```

### <a name="parameters"></a>매개 변수

*Mtx*<br/>
뮤텍스 형식 개체입니다.

*Rel_time*<br/>
메서드가 `mutex`의 소유권을 가져오려고 시도하는 최대 시간을 지정하는 [chrono::duration](../standard-library/duration-class.md) 개체입니다.

*Abs_time*<br/>
임계값을 지정하는 특정 시점으로, 이 시간 경과 후에는 메서드가 더 이상 `mutex`의 소유권을 가져오려고 시도하지 않습니다.

*기타*<br/>
`unique_lock` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 연결된 뮤텍스 포인터 값 0이 포함된 개체를 생성합니다.

두 번째 생성자는 연결 된 뮤텍스 상태에서 이동 *다른*합니다. 이동 후 *다른* 뮤텍스와 함께 연결 되어 있지 않습니다.

나머지 생성자 저장소 & *Mtx* 으로 저장 된 `mutex` 포인터입니다. `mutex`의 소유권은 두 번째 인수(있는 경우)에 의해 결정됩니다.

|||
|-|-|
|`No argument`|연결된 `mutex` 개체에 대해 `lock` 메서드를 호출하여 소유권을 가져옵니다.|
|`Adopt`|이때 소유권이 있는 것으로 가정합니다. 생성자를 호출할 때 `Mtx`가 잠겨 있어야 합니다.|
|`Defer`|호출 스레드는 `mutex` 개체를 소유하지 않는다고 가정합니다. 생성자를 호출할 때는 `Mtx`가 잠겨 있지 않아야 합니다.|
|`Try`|연결된 `mutex` 개체에 대해 `try_lock`을 호출하여 소유권을 가져옵니다. 생성자는 아무 항목도 throw하지 않습니다.|
|`Rel_time`|`try_lock_for(Rel_time)`를 호출하여 소유권을 결정합니다.|
|`Abs_time`|`try_lock_until(Abs_time)`을 호출하여 소유권을 결정합니다.|

## <a name="dtorunique_lock_destructor"></a>  ~unique_lock 소멸자

`unique_lock` 개체와 연결된 모든 리소스를 해제합니다.

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>설명

호출 스레드가 연결된 `mutex`를 소유하는 경우 소멸자는 `mutex` 개체에 대해 unlock을 호출하여 소유권을 해제합니다.

## <a name="unlock"></a>  unlock

연결된 `mutex`의 소유권을 해제합니다.

```cpp
void unlock();
```

### <a name="remarks"></a>설명

호출 스레드가 연결된 `mutex`를 소유하고 있지 않으면 이 메서드는 오류 코드가 `operation_not_permitted`인 [system_error](../standard-library/system-error-class.md)를 throw합니다.

이 메서드를 호출이 고, 그렇지 `unlock` 연결 된 `mutex` 내부 스레드 소유권 플래그를 설정 하 고 **false**합니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
