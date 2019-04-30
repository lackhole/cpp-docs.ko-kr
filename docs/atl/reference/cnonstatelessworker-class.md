---
title: CNonStatelessWorker 클래스
ms.date: 11/04/2016
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
ms.openlocfilehash: abfd3e585c843fcc4ed4ad273c8ed217eaaccb7d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245532"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker 클래스

스레드 풀에서 요청을 받고 각 요청에 대해 생성 되 고 제거 하는 작업자 개체에 전달 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>매개 변수

*Worker*<br/>
준수 하는 작업자 스레드 클래스를 [worker 원형](../../atl/reference/worker-archetype.md) 큐에 대기 요청 처리에 대 한 적절 한 [CThreadPool](../../atl/reference/cthreadpool-class.md)합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CNonStatelessWorker::RequestType](#requesttype)|구현의 [WorkerArchetype::RequestType](worker-archetype.md#requesttype)합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CNonStatelessWorker::Execute](#execute)|구현의 [WorkerArchetype::Execute](worker-archetype.md#execute)합니다.|
|[CNonStatelessWorker::Initialize](#initialize)|구현의 [WorkerArchetype::Initialize](worker-archetype.md#initialize)합니다.|
|[CNonStatelessWorker::Terminate](#terminate)|구현의 [WorkerArchetype::Terminate](worker-archetype.md#terminate)합니다.|

## <a name="remarks"></a>설명

이 클래스는 사용에 대 한 간단한 작업자 스레드 [CThreadPool](../../atl/reference/cthreadpool-class.md)합니다. 이 클래스는 자체의 모든 요청 처리 기능을 제공 하지 않습니다. 대신 하나의 인스턴스만 인스턴스화합니다 *작업자* 요청당 및 대리자 인스턴스에 해당 메서드를 구현 합니다.

이 클래스의 장점은 기존 작업자 스레드 클래스에 대 한 상태 모델을 변경 하는 편리한 방법을 제공 합니다. `CThreadPool` 단일 작업자 스레드의 수명에 대 한 만들어집니다 상태를 보관 하는 작업자 클래스를 해당 여러 요청에서 저장할 수 있도록 합니다. 에 해당 클래스를 단순히 래핑하여 합니다 `CNonStatelessWorker` 템플릿을 사용 하 여 사용 하기 전에 `CThreadPool`, 작업자 및 단일 요청으로 제한 됩니다 보유 하 고 상태 수명입니다.

## <a name="requirements"></a>요구 사항

**헤더:** 와 atlutil.h

##  <a name="execute"></a>  CNonStatelessWorker::Execute

구현의 [WorkerArchetype::Execute](worker-archetype.md#execute)합니다.

```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>설명

이 메서드는 인스턴스를 만듭니다는 *작업자* 스택 및 호출에는 클래스 [초기화](worker-archetype.md#initialize) 해당 개체에서. 성공적으로 초기화 하는 경우이 메서드 호출 [Execute](worker-archetype.md#execute) 하 고 [Terminate](worker-archetype.md#terminate) 동일한 개체에서.

##  <a name="initialize"></a>  CNonStatelessWorker::Initialize

구현의 [WorkerArchetype::Initialize](worker-archetype.md#initialize)합니다.

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

이 클래스 초기화를 수행 하지 않습니다 `Initialize`합니다.

##  <a name="requesttype"></a>  CNonStatelessWorker::RequestType

구현의 [WorkerArchetype::RequestType](worker-archetype.md#requesttype)합니다.

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>설명

이 클래스에 사용 되는 클래스와 동일한 유형의 작업 항목을 처리 합니다 *작업자* 템플릿 매개 변수입니다. 참조 [CNonStatelessWorker 개요](../../atl/reference/cnonstatelessworker-class.md) 세부 정보에 대 한 합니다.

##  <a name="terminate"></a>  CNonStatelessWorker::Terminate

구현의 [WorkerArchetype::Terminate](worker-archetype.md#terminate)합니다.

```
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>설명

이 클래스 정리를 수행 하지 않습니다 `Terminate`합니다.

## <a name="see-also"></a>참고자료

[CThreadPool 클래스](../../atl/reference/cthreadpool-class.md)<br/>
[Worker 원형](../../atl/reference/worker-archetype.md)<br/>
[클래스](../../atl/reference/atl-classes.md)
