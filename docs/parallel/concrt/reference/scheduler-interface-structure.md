---
title: scheduler_interface 구조체
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: 99a3ea8b6ad1f23b4f3d54b7f2f406a3d115b374
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392442"
---
# <a name="schedulerinterface-structure"></a>scheduler_interface 구조체

Scheduler 인터페이스

## <a name="syntax"></a>구문

```
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[scheduler_interface::schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`scheduler_interface`

## <a name="requirements"></a>요구 사항

**헤더:** pplinterface.h

**네임스페이스:** 동시성

##  <a name="schedule"></a>  scheduler_interface:: schedule 메서드

```
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
