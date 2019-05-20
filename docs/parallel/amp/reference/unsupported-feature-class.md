---
title: unsupported_feature 클래스
ms.date: 03/27/2019
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
ms.openlocfilehash: 451318bfbcfb9c5e002677556944e3499c0ed5fb
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525412"
---
# <a name="unsupportedfeature-class"></a>unsupported_feature 클래스

지원 되지 않는 기능을 사용 하는 경우 throw 되는 예외입니다.

## <a name="syntax"></a>구문

```
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[unsupported_feature 생성자](#unsupported_feature)|새 인스턴스를 생성 합니다 `unsupported_feature` 예외입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature"></a> unsupported_feature

  새 인스턴스를 생성 합니다 `unsupported_feature` 예외입니다.

### <a name="syntax"></a>구문

```
explicit unsupported_feature(
    const char * _Message ) throw();

unsupported_feature() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류에 대한 설명입니다.

### <a name="return-value"></a>반환 값

`unsupported_feature` 개체

## <a name="requirements"></a>요구 사항

**헤더:** amprt.h

**네임스페이스:** 동시성

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
