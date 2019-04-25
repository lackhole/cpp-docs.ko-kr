---
title: IUMSUnblockNotification 구조체
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: bdf083e2ad418269e49e53dc164f2a60f693d5d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180220"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 구조체

차단되었으며 스케줄러의 지정된 일정 컨텍스트로의 반환을 트리거한 스레드 프록시가 차단 해제되고 예약할 준비가 되었다는 리소스 관리자의 알림을 나타냅니다. `GetContext` 메서드에서 반환된 스레드 프록시의 연결된 실행 컨텍스트가 다시 예약된 후에는 이 인터페이스가 유효하지 않습니다.

## <a name="syntax"></a>구문

```
struct IUMSUnblockNotification;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IUMSUnblockNotification::GetContext](#getcontext)|반환 된 `IExecutionContext` 차단 된 스레드 프록시를 사용 하 여 연결 된 실행 컨텍스트에 대 한 인터페이스입니다. 이 메서드가 반환 하 고 호출을 통해 기본 실행 컨텍스트가 다시 예약 되는 `IThreadProxy::SwitchTo` 메서드에서이 인터페이스 더 이상 유효 합니다.|
|[IUMSUnblockNotification::GetNextUnblockNotification](#getnextunblocknotification)|다음 반환 `IUMSUnblockNotification` 메서드에서 반환 된 체인의 인터페이스 `IUMSCompletionList::GetUnblockNotifications`합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IUMSUnblockNotification`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="getcontext"></a>  Iumsunblocknotification:: Getcontext 메서드

반환 된 `IExecutionContext` 차단 된 스레드 프록시를 사용 하 여 연결 된 실행 컨텍스트에 대 한 인터페이스입니다. 이 메서드가 반환 하 고 호출을 통해 기본 실행 컨텍스트가 다시 예약 되는 `IThreadProxy::SwitchTo` 메서드에서이 인터페이스 더 이상 유효 합니다.

```
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>반환 값

`IExecutionContext` 가 차단 해제 된 스레드 프록시 실행 컨텍스트에 대 한 인터페이스입니다.

##  <a name="getnextunblocknotification"></a>  Iumsunblocknotification:: Getnextunblocknotification 메서드

다음 반환 `IUMSUnblockNotification` 메서드에서 반환 된 체인의 인터페이스 `IUMSCompletionList::GetUnblockNotifications`합니다.

```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>반환 값

다음 `IUMSUnblockNotification` 메서드에서 반환 된 체인의 인터페이스 `IUMSCompletionList::GetUnblockNotifications`합니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[IUMSScheduler 구조체](iumsscheduler-structure.md)<br/>
[IUMSCompletionList 구조체](iumscompletionlist-structure.md)
