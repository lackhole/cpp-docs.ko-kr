---
title: CComCriticalSection 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
ms.openlocfilehash: f3a4b50f8dd9bc460a209c47497e720529c40e58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246646"
---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection 클래스

이 클래스는 가져오기 및 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class CComCriticalSection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComCriticalSection::Init](#init)|만들고 임계 영역 개체를 초기화 합니다.|
|[CComCriticalSection::Lock](#lock)|임계 영역 개체의 소유권을 가져옵니다.|
|[CComCriticalSection::Term](#term)|임계 영역 개체에서 사용 하는 시스템 리소스를 해제 합니다.|
|[CComCriticalSection::Unlock](#unlock)|임계 영역 개체의 소유권을 해제 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComCriticalSection::m_sec](#m_sec)|CRITICAL_SECTION 개체입니다.|

## <a name="remarks"></a>설명

`CComCriticalSection` 클래스와 유사한 [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)단, 명시적으로 초기화 하 고 중요 섹션을 해제 해야 합니다.

일반적으로 사용 `CComCriticalSection` 를 통해 합니다 **typedef** 이름 [CriticalSection](ccommultithreadmodel-class.md#criticalsection)합니다. 이 이름을 참조 `CComCriticalSection` 때 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 사용 되 고 있습니다.

참조 [CComCritSecLock 클래스](../../atl/reference/ccomcritseclock-class.md) 호출 보다이 클래스를 사용 하는 안전한 방법을 `Lock` 고 `Unlock` 직접.

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

##  <a name="ccomcriticalsection"></a>  CComCriticalSection::CComCriticalSection

생성자입니다.

```
CComCriticalSection() throw();
```

### <a name="remarks"></a>설명

설정 된 [m_sec](#m_sec) NULL 데이터 멤버입니다.

##  <a name="init"></a>  CComCriticalSection::Init

Win32 함수 호출 [InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection)에 포함 된 임계 영역 개체를 초기화 하는 합니다 [m_sec](#m_sec) 데이터 멤버입니다.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 E_OUTOFMEMORY 또는 실패 시 E_FAIL S_OK를 반환합니다.

##  <a name="lock"></a>  CComCriticalSection::Lock

Win32 함수를 호출 [EnterCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-entercriticalsection)에 대기 스레드가 있는 임계 영역 개체의 소유권을 가져올 수 있습니다 때까지 합니다 [m_sec](#m_sec) 데이터 멤버.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 E_OUTOFMEMORY 또는 실패 시 E_FAIL S_OK를 반환합니다.

### <a name="remarks"></a>설명

임계 영역 개체를 호출 하 여 먼저 초기화 해야 합니다 [Init](#init) 메서드. 보호 되는 코드의 실행이 완료 스레드에서 호출 해야 합니다 [잠금 해제](#unlock) 중요 섹션의 소유권을 해제 합니다.

##  <a name="m_sec"></a>  CComCriticalSection::m_sec

모든 사용 되는 임계 영역 개체를 포함 `CComCriticalSection` 메서드.

```
CRITICAL_SECTION m_sec;
```

##  <a name="term"></a>  CComCriticalSection::Term

Win32 함수를 호출 [DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection)에 포함 된 임계 영역 개체에서 사용 하는 모든 리소스를 해제 합니다 [m_sec](#m_sec) 데이터 멤버입니다.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

한 번 `Term` 가 호출 된 중요 한 섹션 동기화에 더 이상 사용 될 수 없습니다.

##  <a name="unlock"></a>  CComCriticalSection::Unlock

Win32 함수를 호출 [LeaveCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-leavecriticalsection)에 포함 된 임계 영역 개체의 소유권을 해제 하는 [m_sec](#m_sec) 데이터 멤버입니다.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

스레드 소유권을 가져오려면 먼저 호출 해야 합니다 [잠금](#lock) 메서드. 호출할 때마다 `Lock` 해당 호출을 `Unlock` 중요 섹션의 소유권을 해제 합니다.

## <a name="see-also"></a>참고자료

[CComFakeCriticalSection 클래스](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComCritSecLock 클래스](../../atl/reference/ccomcritseclock-class.md)
