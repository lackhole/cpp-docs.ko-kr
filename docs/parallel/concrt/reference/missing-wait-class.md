---
title: missing_wait 클래스
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: 68d24d710eec4fd602e64cc3cbde810db2b1a495
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409969"
---
# <a name="missingwait-class"></a>missing_wait 클래스

이 클래스는 개체의 소멸자를 실행할 때 `task_group` 또는 `structured_task_group` 개체에 여전히 예약된 작업이 있는 경우 발생하는 예외를 설명합니다. 예외의 결과로 스택 해제 때문에 소멸자에 도달한 경우에는 이 예외가 발생하지 않습니다.

## <a name="syntax"></a>구문

```
class missing_wait : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[missing_wait](#ctor)|오버로드됨. `missing_wait` 개체를 생성합니다.|

## <a name="remarks"></a>설명

예외 흐름 없는 담당 하는 호출을 `wait` 또는 `run_and_wait` 메서드를 `task_group` 또는 `structured_task_group` 소멸 시킬 개체를 허용 하기 전에 개체. 런타임 호출을 잊은 확인 하기 위해이 예외를 throw 합니다 `wait` 또는 `run_and_wait` 메서드.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`missing_wait`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> missing_wait

`missing_wait` 개체를 생성합니다.

```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[task_group 클래스](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group 클래스](structured-task-group-class.md)
