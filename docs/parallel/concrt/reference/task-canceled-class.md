---
title: task_canceled 클래스
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: caef1c62ff09ffb76f74d4a1453e9d59dcb7d45b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385247"
---
# <a name="taskcanceled-class"></a>task_canceled 클래스

이 클래스는 현재 작업을 강제 취소하도록 PPL 작업 레이어에서 throw된 예외를 설명합니다. 이 throw 됩니다는 `get()` 메서드를 [태스크](/visualstudio/extensibility/debugger/task-class-internal-members), 취소 된 작업에 대 한 합니다.

## <a name="syntax"></a>구문

```
class task_canceled : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[task_canceled](#ctor)|오버로드됨. `task_canceled` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`task_canceled`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> task_canceled

`task_canceled` 개체를 생성합니다.

```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
