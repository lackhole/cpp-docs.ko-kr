---
title: SchedulerPolicy 클래스
ms.date: 11/04/2016
f1_keywords:
- SchedulerPolicy
- concrt/concurrency::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::GetPolicyValue
- concrt/concurrency::SchedulerPolicy::SetConcurrencyLimits
- concrt/concurrency::SchedulerPolicy::SetPolicyValue
helpviewer_keywords:
- SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
ms.openlocfilehash: 2eff40b11e4e9a5981ad85c37c8345abefb13fed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337331"
---
# <a name="schedulerpolicy-class"></a>SchedulerPolicy 클래스

`SchedulerPolicy` 클래스에는 정책 요소마다 하나씩, 스케줄러 인스턴스의 동작을 제어하는 키/값 쌍 집합을 포함합니다.

## <a name="syntax"></a>구문

```
class SchedulerPolicy;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[SchedulerPolicy](#ctor)|오버로드됨. 새 스케줄러 정책을 생성 하 고에 대 한 값으로 채웁니다 [정책 키](concurrency-namespace-enums.md) 동시성 런타임이 스케줄러 및 Resource Manager에서 지원 합니다.|
|[~ SchedulerPolicy 소멸자](#dtor)|스케줄러 정책을 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[GetPolicyValue](#getpolicyvalue)|제공 된 정책 키 값 검색을 `key` 매개 변수입니다.|
|[SetConcurrencyLimits](#setconcurrencylimits)|동시에 설정 합니다 `MinConcurrency` 및 `MaxConcurrency` 정책에는 `SchedulerPolicy` 개체.|
|[SetPolicyValue](#setpolicyvalue)|제공 된 정책 키 값 집합을 `key` 매개 변수가 이전 값을 반환 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator=](#operator_eq)|다른 스케줄러 정책에서 스케줄러 정책을 할당 합니다.|

## <a name="remarks"></a>설명

사용 하 여 제어할 수 있는 정책에 대 한 자세한 내용은 합니다 `SchedulerPolicy` 클래스를 참조 하십시오 [PolicyElementKey](concurrency-namespace-enums.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SchedulerPolicy`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h, concrtrm.h

**네임스페이스:** 동시성

##  <a name="getpolicyvalue"></a> GetPolicyValue

제공 된 정책 키 값 검색을 `key` 매개 변수입니다.

```
unsigned int GetPolicyValue(PolicyElementKey key) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
정책 키에 대 한 값을 검색입니다.

### <a name="return-value"></a>반환 값

으로 지정 된 키를 `key` 매개 변수는 지원, 키에 대 한 정책 값으로 캐스팅을 `unsigned int`입니다.

### <a name="remarks"></a>설명

메서드가 시킵니다 [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) 잘못 된 정책 키입니다.

##  <a name="operator_eq"></a> operator=

다른 스케줄러 정책에서 스케줄러 정책을 할당 합니다.

```
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```

### <a name="parameters"></a>매개 변수

*_RhsPolicy*<br/>
이 정책에 할당할 정책입니다.

### <a name="return-value"></a>반환 값

스케줄러 정책에 대 한 참조입니다.

### <a name="remarks"></a>설명

대부분의 경우 새로운 스케줄러 정책을 정의하는 가장 편리한 방법은 기존 정책을 복사한 후 `SetPolicyValue` 또는 `SetConcurrencyLimits` 메서드를 사용하여 수정하는 것입니다.

##  <a name="ctor"></a> SchedulerPolicy

새 스케줄러 정책을 생성 하 고에 대 한 값으로 채웁니다 [정책 키](concurrency-namespace-enums.md) 동시성 런타임이 스케줄러 및 Resource Manager에서 지원 합니다.

```
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```

### <a name="parameters"></a>매개 변수

*_PolicyKeyCount*<br/>
키/값 쌍의 수는 다음을 `_PolicyKeyCount` 매개 변수입니다.

*_SrcPolicy*<br/>
복사할 원본 정책입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 모든 정책 기본값으로 초기화 되는 경우 새로운 스케줄러 정책을 만듭니다.

두 번째 생성자는 초기화의 명명 된 매개 변수 스타일을 사용 하는 경우 새로운 스케줄러 정책을 만듭니다. 값은 `_PolicyKeyCount` 매개 변수는 키/값 쌍으로 제공 됩니다. 이 생성자에 지정 되지 않은 모든 정책 키 값이 기본값으로 해야 합니다. 이 생성자에는 예외를 throw 할 수 있었습니다 [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md)하십시오 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) 또는 [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).

세 번째 생성자는 복사 생성자가입니다. 대부분의 경우 새로운 스케줄러 정책을 정의하는 가장 편리한 방법은 기존 정책을 복사한 후 `SetPolicyValue` 또는 `SetConcurrencyLimits` 메서드를 사용하여 수정하는 것입니다.

##  <a name="dtor"></a> ~SchedulerPolicy

스케줄러 정책을 제거합니다.

```
~SchedulerPolicy();
```

##  <a name="setconcurrencylimits"></a> SetConcurrencyLimits

동시에 설정 합니다 `MinConcurrency` 및 `MaxConcurrency` 정책에는 `SchedulerPolicy` 개체.

```
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```

### <a name="parameters"></a>매개 변수

*_MinConcurrency*<br/>
에 대 한 값을 `MinConcurrency` 정책 키입니다.

*_MaxConcurrency*<br/>
에 대 한 값을 `MaxConcurrency` 정책 키입니다.

### <a name="remarks"></a>설명

메서드가 throw 됩니다 [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) 에 대 한 지정 된 값을 `MinConcurrency` 정책에 대 한 지정 된 것 보다 큽니다.는 `MaxConcurrency` 정책.

메서드가 throw 할 수도 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) 다른 잘못 된 값에 대 한 합니다.

##  <a name="setpolicyvalue"></a> SetPolicyValue

제공 된 정책 키 값 집합을 `key` 매개 변수가 이전 값을 반환 합니다.

```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
에 대 한 값을 설정 하려면 정책 키입니다.

*값*<br/>
정책 키를 설정할 값입니다.

### <a name="return-value"></a>반환 값

으로 지정 된 키를 `key` 매개 변수는 지원, 키에 대 한 오래 된 정책 값으로 캐스팅을 `unsigned int`입니다.

### <a name="remarks"></a>설명

메서드는 throw [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) 는 잘못 된 정책 키 또는 값으로 설정할 수 있는 정책 키에 대 한는 `SetPolicyValue` 메서드.

메서드가 throw 됩니다 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) 하 여 지정 된 키에 대 한 지원 되지 않는 값을 `key` 매개 변수입니다.

이 메서드는 설정할 수 없습니다는 합니다 `MinConcurrency` 또는 `MaxConcurrency` 정책입니다. 이러한 값을 설정 하려면 사용 합니다 [SetConcurrencyLimits](#setconcurrencylimits) 메서드.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[CurrentScheduler 클래스](currentscheduler-class.md)<br/>
[Scheduler 클래스](scheduler-class.md)<br/>
[작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
