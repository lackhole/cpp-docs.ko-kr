---
title: cancellation_token_registration 클래스
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
ms.openlocfilehash: c6ca8061181ec057110282fa297666235e898ff6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414193"
---
# <a name="cancellationtokenregistration-class"></a>cancellation_token_registration 클래스

`cancellation_token_registration` 클래스는 `cancellation_token`의 콜백 알림을 나타냅니다. 취소 발생 시 알림을 받는 데 `register`의 `cancellation_token` 메서드를 사용하면 `cancellation_token_registration` 메서드 사용을 통해 더 이상 만들어지지 않는 특정 콜백을 호출자가 요청할 수 있도록 `deregister` 개체가 콜백에 대한 핸들로 반환됩니다.

## <a name="syntax"></a>구문

```
class cancellation_token_registration;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[~cancellation_token_registration Destructor](#dtor)||

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[operator=](#operator_eq)||
|[연산자==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`cancellation_token_registration`

## <a name="requirements"></a>요구 사항

**헤더:** pplcancellation_token.h

**네임스페이스:** 동시성

##  <a name="dtor"></a> ~cancellation_token_registration

```
~cancellation_token_registration();
```

##  <a name="ctor"></a> cancellation_token_registration

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>매개 변수

*_Src*<br/>
`cancellation_token_registration` 복사 또는 이동 합니다.

##  <a name="operator_neq"></a> operator!=

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
비교할 `cancellation_token_registration`입니다.

### <a name="return-value"></a>반환 값

##  <a name="operator_eq"></a> operator=

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>매개 변수

*_Src*<br/>
`cancellation_token_registration` 할당 합니다.

### <a name="return-value"></a>반환 값

##  <a name="operator_eq_eq"></a> operator==

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
비교할 `cancellation_token_registration`입니다.

### <a name="return-value"></a>반환 값

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
