---
title: invalid_multiple_scheduling 클래스
ms.date: 11/04/2016
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
ms.openlocfilehash: 7c8ce0aefc12097a71e79933d34a116997c8105f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252772"
---
# <a name="invalidmultiplescheduling-class"></a>invalid_multiple_scheduling 클래스

이 클래스는 `wait` 또는 `run_and_wait` 메서드에 대한 중간 호출 없이 `task_group` 또는 `structured_task_group` 개체의 `run` 메서드를 사용하여 `task_handle` 개체가 여러 번 예약하는 경우 발생하는 예외를 설명합니다.

## <a name="syntax"></a>구문

```
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|오버로드됨. `invalid_multiple_scheduling` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> invalid_multiple_scheduling

`invalid_multiple_scheduling` 개체를 생성합니다.

```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[task_handle 클래스](task-handle-class.md)<br/>
[task_group 클래스](task-group-class.md)<br/>
[run](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group 클래스](structured-task-group-class.md)
