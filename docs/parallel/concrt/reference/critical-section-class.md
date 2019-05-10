---
title: critical_section 클래스
ms.date: 11/04/2016
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
ms.openlocfilehash: f334b159ae39f48006a135c6e36d413b737a7344
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296165"
---
# <a name="criticalsection-class"></a>critical_section 클래스

동시성 런타임을 명시적으로 인식하는 재진입성이 아닌 뮤텍스입니다.

## <a name="syntax"></a>구문

```
class critical_section;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`native_handle_type`|`critical_section` 개체에 대한 참조입니다.|

### <a name="public-classes"></a>public 클래스

|이름|설명|
|----------|-----------------|
|[critical_section:: scoped_lock 클래스](#critical_section__scoped_lock_class)|에 대 한 예외 안전한 RAII 래퍼입니다를 `critical_section` 개체입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[critical_section](#ctor)|새 중요 섹션을 생성합니다.|
|[~ critical_section 소멸자](#dtor)|임계 영역을 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[lock](#lock)|이 중요 한 섹션을 가져옵니다.|
|[native_handle](#native_handle)|있는 경우 플랫폼 특정 네이티브 핸들을 반환 합니다.|
|[try_lock](#try_lock)|차단 하지 않고 잠금을 획득 하려고 시도 합니다.|
|[try_lock_for](#try_lock_for)|특정 기간(밀리초) 동안 차단하지 않고 잠금을 가져오려고 시도합니다.|
|[unlock](#unlock)|중요 섹션을 잠금 해제합니다.|

## <a name="remarks"></a>설명

자세한 내용은 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`critical_section`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> critical_section

새 중요 섹션을 생성합니다.

```
critical_section();
```

##  <a name="dtor"></a> ~critical_section

임계 영역을 제거합니다.

```
~critical_section();
```

### <a name="remarks"></a>설명

소멸자가 실행 하는 경우 더 이상 잠금이 유지 되는 것으로 예상 됩니다. 여전히 유지 중요 섹션의 잠금을 사용 하 여 소멸 시킬 수 있도록 정의 되지 않은 동작이 발생 합니다.

##  <a name="lock"></a> 잠금

이 중요 한 섹션을 가져옵니다.

```
void lock();
```

### <a name="remarks"></a>설명

안전한 것을 [scoped_lock](#critical_section__scoped_lock_class) 구문을 확보 및 해제를 `critical_section` 예외가 개체 안전한 방식으로 합니다.

호출 컨텍스트에 의해 잠금이 이미 유지 되는 경우는 [improper_lock](improper-lock-class.md) 예외가 throw 됩니다.

##  <a name="native_handle"></a> native_handle

있는 경우 플랫폼 특정 네이티브 핸들을 반환 합니다.

```
native_handle_type native_handle();
```

### <a name="return-value"></a>반환 값

중요 섹션에 대 한 참조입니다.

### <a name="remarks"></a>설명

`critical_section` 개체가 Windows 운영 체제에 대 한 플랫폼 특정 네이티브 핸들을 사용 하 여 연결 합니다. 메서드는 단순히 개체 자체에 대 한 참조를 반환합니다.

##  <a name="critical_section__scoped_lock_class"></a>  critical_section:: scoped_lock 클래스

에 대 한 예외 안전한 RAII 래퍼입니다를 `critical_section` 개체입니다.

```
class scoped_lock;
```

##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock

생성을 `scoped_lock` 개체를 가져옵니다는 `critical_section` 전달 된 개체는 `_Critical_section` 매개 변수입니다. 중요 섹션은 다른 스레드에 의해 유지 하는 경우이 호출은 차단 됩니다.

```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>매개 변수

*_Critical_section*<br/>
잠금에 중요 한 섹션입니다.

##  <a name="critical_section__scoped_lock_dtor"></a> scoped_lock::~scoped_lock

제거를 `scoped_lock` 개체 및 해당 생성자에서 제공 하는 중요 한 섹션을 해제 합니다.

```
~scoped_lock();
```

##  <a name="try_lock"></a> try_lock

차단 하지 않고 잠금을 획득 하려고 시도 합니다.

```
bool try_lock();
```

### <a name="return-value"></a>반환 값

잠금을 획득 하는 경우 값 **true**이 고, 그렇지 않으면 값 **false**합니다.

##  <a name="try_lock_for"></a> try_lock_for

특정 기간(밀리초) 동안 차단하지 않고 잠금을 가져오려고 시도합니다.

```
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>매개 변수

*_Timeout*<br/>
시간이 초과되기 전에 대기하는 기간(밀리초)입니다.

### <a name="return-value"></a>반환 값

잠금을 획득 하는 경우 값 **true**이 고, 그렇지 않으면 값 **false**합니다.

##  <a name="unlock"></a> unlock

중요 섹션을 잠금 해제합니다.

```
void unlock();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[reader_writer_lock 클래스](reader-writer-lock-class.md)
