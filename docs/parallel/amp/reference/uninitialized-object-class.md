---
title: uninitialized_object 클래스
ms.date: 03/27/2019
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: 05c24672531d50fa9bc31587e6c6733fdff21f29
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565543"
---
# <a name="uninitializedobject-class"></a>uninitialized_object 클래스

초기화 되지 않은 개체를 사용 하는 경우 throw 되는 예외입니다.

## <a name="syntax"></a>구문

```
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[uninitialized_object 생성자](#uninitialized_object)|`uninitialized_object` 클래스의 새 인스턴스를 초기화합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>요구 사항

**헤더:** amprt.h

**네임스페이스:** 동시성

## <a name="uninitializedobject"></a>uninitialized_object

새 인스턴스를 생성 합니다 `uninitialized_object` 예외입니다.

### <a name="syntax"></a>구문

```
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류에 대한 설명입니다.

### <a name="return-value"></a>반환 값

`uninitialized_object` 예외 개체입니다.

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
