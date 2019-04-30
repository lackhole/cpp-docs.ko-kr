---
title: default_scheduler_exists 클래스
ms.date: 11/04/2016
f1_keywords:
- default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists::default_scheduler_exists
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
ms.openlocfilehash: 326a2dfc6837665adb4d46a6aaa8780052ad2b22
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296100"
---
# <a name="defaultschedulerexists-class"></a>default_scheduler_exists 클래스

이 클래스는 프로세스 내에 기본 스케줄러가 이미 있을 때 `Scheduler::SetDefaultSchedulerPolicy` 메서드를 호출하는 경우 발생하는 예외를 설명합니다.

## <a name="syntax"></a>구문

```
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|오버로드됨. `default_scheduler_exists` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> default_scheduler_exists

`default_scheduler_exists` 개체를 생성합니다.

```
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
