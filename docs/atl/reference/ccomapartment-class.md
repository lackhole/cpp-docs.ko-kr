---
title: CComApartment 클래스
ms.date: 11/04/2016
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
ms.openlocfilehash: 92db42a45a0863f8b43f7c46da9624e424d1e488
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246780"
---
# <a name="ccomapartment-class"></a>CComApartment 클래스

이 클래스는 아파트 스레드 풀링 EXE 모듈에서 관리 하는 것에 대 한 지원을 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CComApartment
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComApartment::CComApartment](#ccomapartment)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComApartment::Apartment](#apartment)|스레드의 시작 주소를 표시합니다.|
|[CComApartment::GetLockCount](#getlockcount)|스레드의 현재 잠금 수를 반환합니다.|
|[CComApartment::Lock](#lock)|스레드의 잠금 카운트를 증가 시킵니다.|
|[CComApartment::Unlock](#unlock)|스레드의 잠금 횟수를 줄입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComApartment::m_dwThreadID](#m_dwthreadid)|스레드의 식별자를 포함합니다.|
|[CComApartment::m_hThread](#m_hthread)|스레드 핸들을 포함합니다.|
|[CComApartment::m_nLockCnt](#m_nlockcnt)|스레드의 현재 잠금 수를 포함합니다.|

## <a name="remarks"></a>설명

`CComApartment` 사용해 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) 스레드 풀링 EXE 모듈의 아파트를 관리 합니다. `CComApartment` 스레드에서 계산 증가 및 감소 하는 잠금에 대 한 메서드를 제공 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="apartment"></a>  CComApartment::Apartment

스레드의 시작 주소를 표시합니다.

```
DWORD Apartment();
```

### <a name="return-value"></a>반환 값

항상 0입니다.

### <a name="remarks"></a>설명

자동으로 설정 하는 동안 [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init)합니다.

##  <a name="ccomapartment"></a>  CComApartment::CComApartment

생성자입니다.

```
CComApartment();
```

### <a name="remarks"></a>설명

초기화 된 `CComApartment` 데이터 멤버 [m_nLockCnt](#m_nlockcnt) 하 고 [m_hThread](#m_hthread)합니다.

##  <a name="getlockcount"></a>  CComApartment::GetLockCount

스레드의 현재 잠금 수를 반환합니다.

```
LONG GetLockCount();
```

### <a name="return-value"></a>반환 값

스레드의 잠금 카운트입니다.

##  <a name="lock"></a>  CComApartment::Lock

스레드의 잠금 카운트를 증가 시킵니다.

```
LONG Lock();
```

### <a name="return-value"></a>반환 값

진단에 유용 하거나 테스트 수 있는 값입니다.

### <a name="remarks"></a>설명

호출한 [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)합니다.

스레드에서 잠금 수 통계 용도로 사용 됩니다.

##  <a name="m_dwthreadid"></a>  CComApartment::m_dwThreadID

스레드의 식별자를 포함합니다.

```
DWORD m_dwThreadID;
```

##  <a name="m_hthread"></a>  CComApartment::m_hThread

스레드 핸들을 포함합니다.

```
HANDLE m_hThread;
```

##  <a name="m_nlockcnt"></a>  CComApartment::m_nLockCnt

스레드의 현재 잠금 수를 포함합니다.

```
LONG m_nLockCnt;
```

##  <a name="unlock"></a>  CComApartment::Unlock

스레드의 잠금 횟수를 줄입니다.

```
LONG Unlock();
```

### <a name="return-value"></a>반환 값

진단에 유용 하거나 테스트 수 있는 값입니다.

### <a name="remarks"></a>설명

호출한 [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock)합니다.

스레드에서 잠금 수 통계 용도로 사용 됩니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
