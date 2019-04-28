---
title: CAtlException 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
ms.openlocfilehash: a6ed6062be02fddc111e4eda4d26226b7a7a0c63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260677"
---
# <a name="catlexception-class"></a>CAtlException 클래스

이 클래스는 ATL 예외를 정의합니다.

## <a name="syntax"></a>구문

```
class CAtlException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlException::CAtlException](#catlexception)|생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAtlException::operator HRESULT](#operator_hresult)|현재 개체를 HRESULT 값을 캐스팅합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAtlException::m_hr](#m_hr)|형식 변수의 HRESULT 개체에 의해 생성 및 오류 조건을 저장 하는 데 사용 합니다.|

## <a name="remarks"></a>설명

`CAtlException` 개체 작업과 관련 된 ATL 예외 조건을 나타냅니다. `CAtlException` 클래스 예외 및 예외를 HRESULT 것 처럼 처리할 수 있습니다는 캐스트 연산자에 대 한 이유를 나타내는 상태 코드를 저장 하는 공용 데이터 멤버를 포함 합니다.

일반적으로 호출 `AtlThrow` 만들지 않고는 `CAtlException` 직접 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlexcept.h

##  <a name="catlexception"></a>  CAtlException::CAtlException

생성자입니다.

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>매개 변수

*hr*<br/>
HRESULT 오류 코드입니다.

##  <a name="operator_hresult"></a>  CAtlException::operator HRESULT

현재 개체를 HRESULT 값을 캐스팅합니다.

```
operator HRESULT() const throw ();
```

##  <a name="m_hr"></a>  CAtlException::m_hr

HRESULT 데이터 멤버입니다.

```
HRESULT m_hr;
```

### <a name="remarks"></a>설명

오류 조건을 저장 하는 데이터 멤버입니다. HRESULT 값을 생성자에 의해 설정 됩니다 [CAtlException::CAtlException](#catlexception)합니다.

## <a name="see-also"></a>참고자료

[AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
