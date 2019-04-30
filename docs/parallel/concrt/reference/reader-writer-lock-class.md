---
title: reader_writer_lock 클래스
ms.date: 11/04/2016
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
ms.openlocfilehash: 111d48b9c4a575078f2342bfaa944871bbd628f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394340"
---
# <a name="readerwriterlock-class"></a>reader_writer_lock 클래스

로컬 전용 회전을 사용한 작성기 우선 큐 기반 읽기/쓰기 잠금입니다. 잠금은 작성기에 대해 FIFO(선입 선출) 액세스 권한을 부여하며 작성기의 연속 부하 상태에서는 판독기에 제공되지 않습니다.

## <a name="syntax"></a>구문

```
class reader_writer_lock;
```

## <a name="members"></a>멤버

### <a name="public-classes"></a>public 클래스

|이름|설명|
|----------|-----------------|
|[reader_writer_lock:: scoped_lock 클래스](#scoped_lock_class)|얻는 데 사용할 수 있는 예외 안전한 RAII 래퍼입니다 `reader_writer_lock` 작성기로 개체를 잠급니다.|
|[reader_writer_lock:: scoped_lock_read 클래스](#scoped_lock_read_class)|얻는 데 사용할 수 있는 예외 안전한 RAII 래퍼입니다 `reader_writer_lock` 판독기로 개체를 잠급니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[reader_writer_lock](#ctor)|새 `reader_writer_lock` 개체를 생성합니다.|
|[~ reader_writer_lock 소멸자](#dtor)|제거 된 `reader_writer_lock` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[lock](#lock)|판독기-기록기 잠금을 기록기로 가져옵니다.|
|[lock_read](#lock_read)|판독기-기록기 잠금을 판독기로 가져옵니다. 기록기가 있는 경우 활성 판독기는 수행 될 때까지 대기 해야 합니다. 단순히 판독기가 잠금에 관심을 등록 하 고 작성기가 해제 될 때까지 기다립니다.|
|[try_lock](#try_lock)|차단 하지 않고 라이터로도 판독기-기록기 잠금을 획득 하려고 시도 합니다.|
|[try_lock_read](#try_lock_read)|차단 되지 않고 판독기로 판독기-기록기 잠금을 획득 하려고 시도 합니다.|
|[unlock](#unlock)|판독기 또는 작성기 잠근 사용자 기반 판독기 / 기록기 잠금 잠금을 해제 합니다.|

## <a name="remarks"></a>설명

자세한 내용은 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`reader_writer_lock`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="lock"></a> 잠금

판독기-기록기 잠금을 기록기로 가져옵니다.

```
void lock();
```

### <a name="remarks"></a>설명

안전한 것을 [scoped_lock](#scoped_lock_class) 구문을 확보 및 해제를 `reader_writer_lock` 예외가 작성기 개체로 안전한 방식으로 합니다.

작성기가 잠금을 가져오려고 시도하면 이후 판독기는 작성기가 잠금을 성공적으로 가져와 해제할 때까지 차단됩니다. 이 잠금은 작성기 중심 및 기록기의 연속 부하 상태에서 판독기를 사용할 수 없게 합니다.

기록기는 기록기 잠금을 끝내기 다음 작성기의에서 해제 되도록 연결 됩니다.

호출 컨텍스트에 의해 잠금이 이미 유지 되는 경우는 [improper_lock](improper-lock-class.md) 예외가 throw 됩니다.

##  <a name="lock_read"></a> lock_read

판독기-기록기 잠금을 판독기로 가져옵니다. 기록기가 있는 경우 활성 판독기는 수행 될 때까지 대기 해야 합니다. 단순히 판독기가 잠금에 관심을 등록 하 고 작성기가 해제 될 때까지 기다립니다.

```
void lock_read();
```

### <a name="remarks"></a>설명

안전한 것을 [scoped_lock_read](#scoped_lock_read_class) 구문을 확보 및 해제를 `reader_writer_lock` 예외가 판독기 개체 안전한 방식으로.

기록기 잠금을 기다리는 경우 판독기는 줄에서 모든 기록기가 획득 되 고 잠금을 해제할 때까지 기다립니다. 이 잠금은 작성기 중심 및 기록기의 연속 부하 상태에서 판독기를 사용할 수 없게 합니다.

##  <a name="ctor"></a> reader_writer_lock

새 `reader_writer_lock` 개체를 생성합니다.

```
reader_writer_lock();
```

##  <a name="dtor"></a> ~reader_writer_lock

제거 된 `reader_writer_lock` 개체입니다.

```
~reader_writer_lock();
```

### <a name="remarks"></a>설명

소멸자가 실행 하는 경우 더 이상 잠금이 유지 되는 것으로 예상 됩니다. 여전히 유지 판독기 기록기 잠금의 잠금을 함께 소멸할 수 있도록 정의 되지 않은 동작이 발생 합니다.

##  <a name="scoped_lock_class"></a>  reader_writer_lock:: scoped_lock 클래스

얻는 데 사용할 수 있는 예외 안전한 RAII 래퍼입니다 `reader_writer_lock` 작성기로 개체를 잠급니다.

```
class scoped_lock;
```

## <a name="scoped_lock_ctor"></a> scoped_lock::scoped_lock

생성을 `scoped_lock` 개체를 가져옵니다는 `reader_writer_lock` 전달 된 개체는 `_Reader_writer_lock` 작성기로 매개 변수입니다. 다른 스레드에 의해 잠금이 설정에이 호출이 차단 됩니다.

```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

#### <a name="parameters"></a>매개 변수

*_Reader_writer_lock*<br/>
`reader_writer_lock` 작성기로 가져올 개체입니다.

## <a name="scoped_lock_dtor"></a> scoped_lock::~scoped_lock

제거를 `reader_writer_lock` 개체 및 해당 생성자에 제공 된 잠금을 해제 합니다.

```
~scoped_lock();
```

##  <a name="scoped_lock_read_class"></a>  reader_writer_lock:: scoped_lock_read 클래스

얻는 데 사용할 수 있는 예외 안전한 RAII 래퍼입니다 `reader_writer_lock` 판독기로 개체를 잠급니다.

```
class scoped_lock_read;
```

##  <a name="try_lock"></a> try_lock

차단 하지 않고 라이터로도 판독기-기록기 잠금을 획득 하려고 시도 합니다.

## <a name="scoped_lock_read_ctor"></a> scoped_lock_read::scoped_lock_read

생성을 `scoped_lock_read` 개체를 가져옵니다는 `reader_writer_lock` 전달 된 개체는 `_Reader_writer_lock` 판독기로 매개 변수입니다. 작성기로 다른 스레드에 의해 잠금이 경우 보류 중인 작성기에이 호출이 차단 됩니다.

```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

#### <a name="parameters"></a>매개 변수

*_Reader_writer_lock*<br/>
`reader_writer_lock` 판독기로 가져올 개체입니다.

## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">  reader_writer_lock:: scoped_lock_read:: ~ scoped_lock_read 소멸자

제거를 `scoped_lock_read` 개체 및 해당 생성자에 제공 된 잠금을 해제 합니다.

```
~scoped_lock_read();
```

## <a name="try_lock"></a> try_lock

```
bool try_lock();
```

### <a name="return-value"></a>반환 값

잠금을 획득 하는 경우 값 **true**이 고, 그렇지 않으면 값 **false**합니다.

##  <a name="try_lock_read"></a> try_lock_read

차단 되지 않고 판독기로 판독기-기록기 잠금을 획득 하려고 시도 합니다.

```
bool try_lock_read();
```

### <a name="return-value"></a>반환 값

잠금을 획득 하는 경우 값 **true**이 고, 그렇지 않으면 값 **false**합니다.

##  <a name="unlock"></a> unlock

판독기 또는 작성기 잠근 사용자 기반 판독기 / 기록기 잠금 잠금을 해제 합니다.

```
void unlock();
```

### <a name="remarks"></a>설명

기록기 잠금을 기다리는 경우를 잠금 해제 항상 FIFO 순서에 따라 다음 쓰기도 이동 합니다. 이 잠금은 작성기 중심 및 기록기의 연속 부하 상태에서 판독기를 사용할 수 없게 합니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[critical_section 클래스](critical-section-class.md)
