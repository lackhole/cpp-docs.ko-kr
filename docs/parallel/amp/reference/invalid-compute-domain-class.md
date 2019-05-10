---
title: invalid_compute_domain 클래스
ms.date: 11/04/2016
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
ms.openlocfilehash: 51fcd9e42bc4497131da5adb3dff72efb46537b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351721"
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain 클래스

런타임에서에서 지정 된 계산 도메인을 사용 하 여 커널을 시작할 수 없는 경우 throw 되는 예외를 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) 호출 사이트입니다.

## <a name="syntax"></a>구문

```
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[invalid_compute_domain 생성자](#ctor)|`invalid_compute_domain` 클래스의 새 인스턴스를 초기화합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>요구 사항

**헤더:** amprt.h

**네임스페이스:** 동시성

## <a name="ctor"></a> invalid_compute_domain

클래스의 새 인스턴스를 초기화합니다.

## <a name="syntax"></a>구문

```
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>매개 변수

*_Message*<br/>
오류에 대한 설명입니다.

### <a name="return-value"></a>반환 값

인스턴스는 `invalid_compute_domain` 클래스

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
