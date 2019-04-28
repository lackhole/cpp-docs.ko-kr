---
title: context_unblock_unbalanced 클래스
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: f4f385cde2a27665afa5eb9869eb52bc42c70111
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296218"
---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced 클래스

이 클래스는 동일한 컨텍스트에서 `Context` 개체의 `Block` 및 `Unblock` 메서드 호출 쌍이 잘못된 경우 발생하는 예외를 설명합니다.

## <a name="syntax"></a>구문

```
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|오버로드됨. `context_unblock_unbalanced` 개체를 생성합니다.|

## <a name="remarks"></a>설명

에 대 한 호출을 `Block` 및 `Unblock` 의 메서드를 `Context` 개체 항상 올바르게을 이루어야 합니다. 동시성 런타임에서 작업이 어떤 순서로 든 발생할 수 있습니다. 예를 들어 `Block` 호출 다음에 `Unblock` 호출이 오거나 그 반대가 될 수 있습니다. 예를 들어,를 두 번 호출 하는 경우이 예외가 throw 됩니다 합니다 `Unblock` 메서드는 행에 수행 되었습니다를 `Context` 차단 하지는 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> context_unblock_unbalanced

`context_unblock_unbalanced` 개체를 생성합니다.

```
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류 설명 메시지입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
