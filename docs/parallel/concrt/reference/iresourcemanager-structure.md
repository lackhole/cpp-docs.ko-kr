---
title: IResourceManager 구조체
ms.date: 03/27/2019
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
ms.openlocfilehash: 7afb37fb35040975d6e9471a1d12465e5163fafc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301931"
---
# <a name="iresourcemanager-structure"></a>IResourceManager 구조체

동시성 런타임의 리소스 관리자에 대한 인터페이스입니다. 스케줄러가 리소스 관리자와 통신하는 데 사용되는 인터페이스입니다.

## <a name="syntax"></a>구문

```
struct IResourceManager;
```

## <a name="members"></a>멤버

### <a name="public-enumerations"></a>public 열거형

|이름|설명|
|----------|-----------------|
|[IResourceManager::OSVersion](#osversion)|운영 체제 버전을 나타내는 열거 형식입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IResourceManager::CreateNodeTopology](#createnodetopology)|런타임에서의 빌드를 디버그에만 있는,이 메서드는 테스트 후크 하드웨어 토폴로지는 구성과 일치 하는 실제 하드웨어 필요 없이 다양 한 리소스 관리자의 테스트를 용이 하 게 설계 되었습니다. 런타임의 일반 정품 빌드에이 메서드는 아무 작업도 수행 하지 않고 반환 합니다.|
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.|
|[IResourceManager::GetFirstNode](#getfirstnode)|리소스 관리자를 통해 정의된 열거 순서에서 첫 번째 노드를 반환합니다.|
|[IResourceManager::Reference](#reference)|Resource Manager 인스턴스에 대 한 참조 수를 늘립니다.|
|[IResourceManager::RegisterScheduler](#registerscheduler)|Resource Manager를 사용 하 여 스케줄러를 등록합니다. Resource Manager를 사용 하 여 통신 해야 스케줄러 등록 되 면는 `ISchedulerProxy` 반환 되는 인터페이스입니다.|
|[IResourceManager::Release](#release)|Resource Manager 인스턴스에 대 한 참조 횟수를 감소 시킵니다. Resource Manager는 해당 참조 횟수가 되 면 제거 됩니다 `0`합니다.|

## <a name="remarks"></a>설명

사용 된 [CreateResourceManager](concurrency-namespace-functions.md) 단일 Resource Manager 인스턴스에 대 한 인터페이스를 가져오려면 함수. 메서드는 Resource Manager에 대 한 참조 횟수를 증가 시키고 호출 해야 합니다 [iresourcemanager:: Release](#release) Resource Manager와 함께 완료 되 면 참조를 해제 하는 방법입니다. 일반적으로 직접 만든 각 스케줄러를 만드는 동안이 메서드를 호출 하 고 종료 후 Resource Manager에 대 한 참조를 해제 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IResourceManager`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="createnodetopology"></a>  Iresourcemanager:: Createnodetopology 메서드

런타임에서의 빌드를 디버그에만 있는,이 메서드는 테스트 후크 하드웨어 토폴로지는 구성과 일치 하는 실제 하드웨어 필요 없이 다양 한 리소스 관리자의 테스트를 용이 하 게 설계 되었습니다. 런타임의 일반 정품 빌드에이 메서드는 아무 작업도 수행 하지 않고 반환 합니다.

```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>매개 변수

*nodeCount*<br/>
시뮬레이션 되는 프로세서 노드의 수입니다.

*pCoreCount*<br/>
각 노드의 코어 수를 지정 하는 배열입니다.

*pNodeDistance*<br/>
두 노드 사이의 노드 거리를 지정 하는 매트릭스입니다. 이 매개 변수 값을 가질 수 `NULL`입니다.

*pProcessorGroups*<br/>
프로세서 그룹을 지정 하는 배열에 각 노드에 속합니다.

### <a name="remarks"></a>설명

[invalid_argument](../../../standard-library/invalid-argument-class.md) 경우 발생 하는 매개 변수 `nodeCount` 기본값이 `0` 에서는 전달 된 경우 매개 변수 `pCoreCount` 값이 `NULL`합니다.

[invalid_operation](invalid-operation-class.md) 다른 스케줄러 프로세스에 존재 하는 동안이 메서드를 호출 하면 throw 됩니다.

##  <a name="getavailablenodecount"></a>  IResourceManager::GetAvailableNodeCount Method

리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.

```
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>반환 값

Resource Manager에 사용할 수 있는 노드의 수입니다.

##  <a name="getfirstnode"></a>  Iresourcemanager:: Getfirstnode 메서드

리소스 관리자를 통해 정의된 열거 순서에서 첫 번째 노드를 반환합니다.

```
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>반환 값

리소스 관리자에 의해 정의 된 열거 순서에서 첫 번째 노드.

##  <a name="osversion"></a>  Iresourcemanager:: Osversion 열거형

운영 체제 버전을 나타내는 열거 형식입니다.

```
enum OSVersion;
```

##  <a name="reference"></a>  Iresourcemanager:: Reference 메서드

Resource Manager 인스턴스에 대 한 참조 수를 늘립니다.

```
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>반환 값

결과 참조 수입니다.

##  <a name="registerscheduler"></a>  Iresourcemanager:: Registerscheduler 메서드

Resource Manager를 사용 하 여 스케줄러를 등록합니다. Resource Manager를 사용 하 여 통신 해야 스케줄러 등록 되 면는 `ISchedulerProxy` 반환 되는 인터페이스입니다.

```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>매개 변수

*pScheduler*<br/>
`IScheduler` 스케줄러 등록에 대 한 인터페이스입니다.

*version*<br/>
통신 인터페이스의 버전 스케줄러 Resource Manager와의 통신에 사용 됩니다. 버전을 사용 하 여 Resource Manager 스케줄러에 오래 된 기능 권한을 얻을 수 있도록 하는 동안 통신 인터페이스를 발전 시킬 수 있습니다. 버전을 사용 해야 하는 Visual Studio 2010에 Resource Manager 기능을 사용 하려는 스케줄러 `CONCRT_RM_VERSION_1`합니다.

### <a name="return-value"></a>반환 값

`ISchedulerProxy` Resource Manager 스케줄러와 연결 된 인터페이스입니다. 스케줄러에서이 지점에서 Resource Manager와 통신 하기 위해이 인터페이스를 사용 해야 합니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 Resource Manager와의 통신을 시작 합니다. 메서드를 연결 합니다 `IScheduler` 사용 하 여 스케줄러에 대 한 인터페이스를 `ISchedulerProxy` 인터페이스 및 사용자에 게 전달 합니다. 스케줄러를 사용 하는 실행 리소스를 요청 하거나 Resource Manager를 사용 하 여 스레드를 구독할 반환 되는 인터페이스를 사용할 수 있습니다. 리소스 관리자가 반환한 스케줄러 정책에서 정책 요소를 사용 하 여는 [ischeduler:: Getpolicy](ischeduler-structure.md#getpolicy) 스케줄러 스레드 형식을 결정 하는 메서드를 작업을 실행 해야 합니다. 경우에 `SchedulerKind` 정책 키에 값 `UmsThreadDefault` 값을 값으로 정책을 읽고 `UmsThreadDefault`의 `IScheduler` 메서드에 전달 하는 인터페이스 여야 합니다는 `IUMSScheduler` 인터페이스입니다.

메서드에서 throw를 `invalid_argument` 예외 경우 매개 변수 `pScheduler` 기본값이 `NULL` 이거나 매개 변수 `version` 통신 인터페이스에 대 한 유효한 버전이 아닙니다.

##  <a name="release"></a>  Iresourcemanager:: Release 메서드

Resource Manager 인스턴스에 대 한 참조 횟수를 감소 시킵니다. Resource Manager는 해당 참조 횟수가 되 면 제거 됩니다 `0`합니다.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>반환 값

결과 참조 수입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[ISchedulerProxy 구조체](ischedulerproxy-structure.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)
