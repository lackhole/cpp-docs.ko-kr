---
title: invalid_oversubscribe_operation 클래스
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 200743d41c1c45f2a957dba0716dd7aa07e3de76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405315"
---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation 클래스

때 throw 되는 예외를 설명 하는이 클래스는 `Context::Oversubscribe` 메서드를 호출 합니다 `_BeginOversubscription` 매개 변수 설정 **false** 를 이전에 호출 하지 않고는 `Context::Oversubscribe` 메서드를 `_BeginOversubscription` 매개 변수가 로설정**true**합니다.

## <a name="syntax"></a>구문

```
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|오버로드됨. `invalid_oversubscribe_operation` 개체를 생성합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> invalid_oversubscribe_operation

`invalid_oversubscribe_operation` 개체를 생성합니다.

```
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
