---
title: DispatchState 구조체
ms.date: 11/04/2016
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
ms.openlocfilehash: c755675a69ce86bc03a3fdb59fa7d43a20676495
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295918"
---
# <a name="dispatchstate-structure"></a>DispatchState 구조체

`DispatchState` 구조체는 `IExecutionContext::Dispatch` 메서드에 상태를 전송하는 데 사용됩니다. `IExecutionContext` 인터페이스에 대해 `Dispatch` 메서드가 호출되는 상황을 설명합니다.

## <a name="syntax"></a>구문

```
struct DispatchState;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[DispatchState::DispatchState](#ctor)|새 `DispatchState` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|버전 관리에 사용 되는이 구조체의 크기입니다.|
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|이 컨텍스트에서 시작 했는지 여부를 알려 줍니다는 `Dispatch` 메서드 이전 컨텍스트로 비동기적으로 차단 합니다. UMS 일정 컨텍스트에서만 사용 되 고 값으로 설정 되어이 `0` 다른 모든 실행 컨텍스트에 대 한 합니다.|
|[DispatchState::m_reserved](#m_reserved)|향후 정보 전달에 대 한 예약 된 비트입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`DispatchState`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="ctor"></a>  Dispatchstate:: Dispatchstate 생성자

새 `DispatchState` 개체를 생성합니다.

```
DispatchState();
```

##  <a name="m_dispatchstatesize"></a>  Dispatchstate:: M_dispatchstatesize 데이터 멤버

버전 관리에 사용 되는이 구조체의 크기입니다.

```
unsigned long m_dispatchStateSize;
```

##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  Dispatchstate:: M_fispreviouscontextasynchronouslyblocked 데이터 멤버

이 컨텍스트에서 시작 했는지 여부를 알려 줍니다는 `Dispatch` 메서드 이전 컨텍스트로 비동기적으로 차단 합니다. UMS 일정 컨텍스트에서만 사용 되 고 값으로 설정 되어이 `0` 다른 모든 실행 컨텍스트에 대 한 합니다.

```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

##  <a name="m_reserved"></a>  Dispatchstate:: M_reserved 데이터 멤버

향후 정보 전달에 대 한 예약 된 비트입니다.

```
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
