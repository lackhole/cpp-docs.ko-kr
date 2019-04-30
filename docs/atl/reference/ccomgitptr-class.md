---
title: CComGITPtr 클래스
ms.date: 11/04/2016
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
ms.openlocfilehash: bf509d027833610e4251c009d4e444dad3fdd5ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246475"
---
# <a name="ccomgitptr-class"></a>CComGITPtr 클래스

이 클래스는 인터페이스 포인터를 처리 하기 위한 메서드 및 전역 인터페이스 테이블 (GIT)를 제공합니다.

## <a name="syntax"></a>구문

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
GIT에 저장 될 인터페이스 포인터의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComGITPtr::CComGITPtr](#ccomgitptr)|생성자입니다.|
|[CComGITPtr::~CComGITPtr](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComGITPtr::Attach](#attach)|인터페이스 포인터를 전역 인터페이스 테이블 (GIT)에 등록 하려면이 메서드를 호출 합니다.|
|[CComGITPtr::CopyTo](#copyto)|전달 된 포인터에 대 한 전역 인터페이스 테이블 (GIT)에서 인터페이스를 복사 하려면이 메서드를 호출 합니다.|
|[CComGITPtr::Detach](#detach)|해당 인터페이스를 분리 하려면이 메서드는 `CComGITPtr` 개체입니다.|
|[CComGITPtr::GetCookie](#getcookie)|쿠키를 반환 하려면이 메서드를 호출 합니다 `CComGITPtr` 개체입니다.|
|[CComGITPtr::Revoke](#revoke)|전역 인터페이스 테이블 (GIT)에서 인터페이스를 제거 하려면이 메서드를 호출 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CComGITPtr::operator DWORD](#operator_dword)|쿠키를 반환 합니다 `CComGITPtr` 개체입니다.|
|[CComGITPtr::operator =](#operator_eq)|대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComGITPtr::m_dwCookie](#m_dwcookie)|쿠키입니다.|

## <a name="remarks"></a>설명

자유 스레드된 마샬러를 집계 하 고 다른 개체에서 가져온 인터페이스 포인터를 사용 해야 하는 개체 인터페이스를 올바르게 마샬링되는 게 하려면 추가 단계를 수행 해야 합니다. 일반적으로 GIT에서 인터페이스 포인터를 저장 하 고 포인터 GIT에서 사용 될 때마다 시작 해야 합니다. 클래스 `CComGITPtr` GIT에 저장 하는 인터페이스 포인터를 사용할 수 있도록 제공 됩니다.

> [!NOTE]
>  전역 인터페이스 테이블 시설만 DCOM 버전 1.1 사용 하 여 Windows 95 이상 Windows 98, Windows NT 4.0 서비스 팩 3 이상 및 Windows 2000에서 제공 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="attach"></a>  CComGITPtr::Attach

인터페이스 포인터를 전역 인터페이스 테이블 (GIT)에 등록 하려면이 메서드를 호출 합니다.

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
GIT에 추가 될 인터페이스 포인터입니다.

*dwCookie*<br/>
인터페이스 포인터를 식별 하는 데 사용 되는 쿠키입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 GIT 유효 하지 않은 경우 또는 쿠키 NULL과 동일한 경우 어설션 오류가 발생 합니다.

##  <a name="ccomgitptr"></a>  CComGITPtr::CComGITPtr

생성자입니다.

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>매개 변수

*p*<br/>
[in] (GIT) 전역 인터페이스 테이블에 저장 하는 인터페이스 포인터입니다.

*git*<br/>
[in] 기존에 대 한 참조 `CComGITPtr` 개체입니다.

*dwCookie*<br/>
[in] 인터페이스 포인터를 식별 하는 데 사용 되는 쿠키입니다.

*rv*<br/>
[in] 원본 `CComGITPtr` 개체 데이터를 이동 합니다.

### <a name="remarks"></a>설명

새로 만듭니다 `CComGITPtr` 개체를 필요에 따라 기존 사용 하 여 `CComGITPtr` 개체입니다.

사용 하 여 생성자 *rv* 이동 생성자입니다. 원본에서 데이터를 이동할 *rv*를 차례로 *rv* 지워집니다.

##  <a name="dtor"></a>  CComGITPtr::~CComGITPtr

소멸자입니다.

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>설명

전역 인터페이스 테이블 (GIT)에서 인터페이스를 제거를 사용 하 여 [CComGITPtr::Revoke](#revoke)합니다.

##  <a name="copyto"></a>  CComGITPtr::CopyTo

전달 된 포인터에 대 한 전역 인터페이스 테이블 (GIT)에서 인터페이스를 복사 하려면이 메서드를 호출 합니다.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>매개 변수

*pp*<br/>
인터페이스를 수신 하는 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

GIT에서 해당 인터페이스는 전달 된 포인터에 복사 됩니다. 포인터가 더 이상 필요한 경우 호출자에 의해 해제 되어야 합니다.

##  <a name="detach"></a>  CComGITPtr::Detach

해당 인터페이스를 분리 하려면이 메서드는 `CComGITPtr` 개체입니다.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>반환 값

쿠키를 반환 합니다 `CComGITPtr` 개체입니다.

### <a name="remarks"></a>설명

Git에서 인터페이스를 제거 하려면 호출자에 게 달려를 사용 하 여 [CComGITPtr::Revoke](#revoke)합니다.

##  <a name="getcookie"></a>  CComGITPtr::GetCookie

쿠키를 반환 하려면이 메서드를 호출 합니다 `CComGITPtr` 개체입니다.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>반환 값

쿠키를 반환합니다.

### <a name="remarks"></a>설명

쿠키는 인터페이스 및 해당 위치를 식별 하는 데는 변수입니다.

##  <a name="m_dwcookie"></a>  CComGITPtr::m_dwCookie

쿠키입니다.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>설명

쿠키는 인터페이스 및 해당 위치를 식별 하는 데는 멤버 변수입니다.

##  <a name="operator_eq"></a>  CComGITPtr::operator =

대입 연산자입니다.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>매개 변수

*p*<br/>
[in] 인터페이스 포인터입니다.

*git*<br/>
[in] `CComGITPtr` 개체에 대한 참조입니다.

*dwCookie*<br/>
[in] 인터페이스 포인터를 식별 하는 데 사용 되는 쿠키입니다.

*rv*<br/>
[in] `CComGITPtr` 데이터를 이동 합니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CComGITPtr` 개체입니다.

### <a name="remarks"></a>설명

에 새 값을 할당 한 `CComGITPtr` 전역 인터페이스 테이블에 대 한 참조 또는 기존 개체에서 개체입니다.

##  <a name="operator_dword"></a>  CComGITPtr::operator DWORD

연결 된 쿠키를 반환 합니다 `CComGITPtr` 개체입니다.

```
operator DWORD() const;
```

### <a name="remarks"></a>설명

쿠키는 인터페이스 및 해당 위치를 식별 하는 데는 변수입니다.

##  <a name="revoke"></a>  CComGITPtr::Revoke

전역 인터페이스 테이블 (GIT)에서 현재 인터페이스를 제거 하려면이 메서드를 호출 합니다.

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

GIT에서 인터페이스를 제거합니다.

## <a name="see-also"></a>참고자료

[자유 스레드된 마샬러](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[아파트 간 인터페이스 액세스](/windows/desktop/com/accessing-interfaces-across-apartments)<br/>
[전역 인터페이스 테이블을 사용 하는 경우](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
