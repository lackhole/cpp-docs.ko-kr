---
title: Worker 원형
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 790cf064fcffe1f0cd3c191c28ed0a0614062406
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274501"
---
# <a name="worker-archetype"></a>Worker 원형

따르는 클래스를 *작업자* archetype 스레드 풀에서 대기 중인 작업 항목을 처리 하는 코드를 제공 합니다.

**구현**

이 원형에 맞는 클래스를 구현 하려면 클래스는 다음과 같은 기능을 제공 해야 합니다.

|메서드|설명|
|------------|-----------------|
|[Initialize](#initialize)|모든 요청에 전달 되기 전에 작업자 개체를 초기화 하기 위해 호출할 [Execute](#execute)합니다.|
|[Execute](#execute)|작업 항목을 처리 하기 위해 호출 됩니다.|
|[Terminate](#terminate)|모든 요청에 전달 된 후 작업자 개체 초기화를 호출 [Execute](#execute)합니다.|

|Typedef|설명|
|-------------|-----------------|
|[RequestType](#requesttype)|작업자 클래스에 의해 처리 될 수 있는 작업 항목 형식에 대 한 typedef입니다.|

일반적인 *작업자* 클래스는 다음과 같습니다.

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**기존 구현**

이러한 클래스는이 원형을 따릅니다.

|클래스|설명|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|스레드 풀의 요청을 받고으로 생성 되 고 각 요청에 대 한 제거 하는 작업자 개체를 전달 합니다.|

**사용 하 여**

이러한 템플릿 매개 변수 예상이 원형에 맞게 클래스:

|매개 변수 이름|사용 주체|
|--------------------|-------------|
|*Worker*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*Worker*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>요구 사항

**헤더:** 와 atlutil.h

## <a name="execute"></a>WorkerArchetype::Execute

작업 항목을 처리 하기 위해 호출 됩니다.

```
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>매개 변수

*request*<br/>
작업 항목을 처리할 수입니다. 동일한 형식의 작업 항목은 `RequestType`합니다.

*pvWorkerParam*<br/>
작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달 `WorkerArchetype::Initialize` 고 `Terminate`입니다.

*pOverlapped*<br/>
에 대 한 포인터를 [OVERLAPPED](/windows/desktop/api/minwinbase/ns-minwinbase-_overlapped) 구조는 작업 항목이 대기 중인 큐를 만드는 데 사용 합니다.

## <a name="initialize"></a> WorkerArchetype::Initialize

모든 요청에 전달 되기 전에 작업자 개체를 초기화 하기 위해 호출 `WorkerArchetype::Execute`합니다.
```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>매개 변수

*pvParam*<br/>
작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달 `WorkerArchetype::Terminate` 고 `WorkerArchetype::Execute`입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

## <a name="requesttype"></a> WorkerArchetype::RequestType

작업자 클래스에 의해 처리 될 수 있는 작업 항목 형식에 대 한 typedef입니다.

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>설명

이 형식은의 첫 번째 매개 변수로 사용 해야 `WorkerArchetype::Execute` 및는 ULONG_PTR에서 캐스팅 될 수 있어야 합니다.

## <a name="terminate"></a> WorkerArchetype::Terminate

모든 요청에 전달 된 후 작업자 개체의 초기화를 취소 하기 위해 호출 `WorkerArchetype::Execute`).

```
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>매개 변수

*pvParam*<br/>
작업자 클래스에 의해 인식 사용자 지정 매개 변수입니다. 또한 전달 `WorkerArchetype::Initialize` 고 `WorkerArchetype::Execute`입니다.

## <a name="see-also"></a>참고자료

[개념](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)
