---
title: CSyncObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
helpviewer_keywords:
- CSyncObject [MFC], CSyncObject
- CSyncObject [MFC], Lock
- CSyncObject [MFC], Unlock
- CSyncObject [MFC], m_hObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
ms.openlocfilehash: 842ff5f98f05425fbbb511d112ae3e4fd65ff076
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324872"
---
# <a name="csyncobject-class"></a>CSyncObject 클래스

Win32의 동기화 개체에 일반적인 기능을 제공하는 순수 가상 클래스입니다.

## <a name="syntax"></a>구문

```
class CSyncObject : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSyncObject::CSyncObject](#csyncobject)|`CSyncObject` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSyncObject::Lock](#lock)|동기화 개체에 액세스 합니다.|
|[CSyncObject::Unlock](#unlock)|동기화 개체에 액세스 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CSyncObject::operator 핸들](#operator_handle)|동기화 개체에 대 한 액세스를 제공합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CSyncObject::m_hObject](#m_hobject)|내부 동기화 개체에 대 한 핸들입니다.|

## <a name="remarks"></a>설명

파생 된 여러 클래스를 제공 하는 Microsoft Foundation Class 라이브러리를 `CSyncObject`입니다. 이들은 [CEvent](../../mfc/reference/cevent-class.md)를 [CMutex](../../mfc/reference/cmutex-class.md)합니다 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), 및 [CSemaphore](../../mfc/reference/csemaphore-class.md)합니다.

동기화 개체를 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 하세요. [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CSyncObject`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

##  <a name="csyncobject"></a>  CSyncObject::CSyncObject

제공 된 이름 사용 하 여 동기화 개체를 생성합니다.

```
explicit CSyncObject(LPCTSTR pstrName);
virtual ~CSyncObject();
```

### <a name="parameters"></a>매개 변수

*pstrName*<br/>
개체의 이름입니다. NULL 인 경우 *pstrName* null이 됩니다.

##  <a name="lock"></a>  CSyncObject::Lock

동기화 개체에 의해 제어 되는 리소스에 액세스 하려면이 함수를 호출 합니다.

```
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```

### <a name="parameters"></a>매개 변수

*dwTimeout*<br/>
동기화 개체를 사용할 수에 대 한 대기 시간 (밀리초)의 시간 지정 (신호). 무한 경우 `Lock` 개체를 반환 하기 전에 신호를 받을 때까지 기다립니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

동기화 개체가 신호를 받을 경우 `Lock` 스레드가 이제 개체를 소유 하 고 성공적으로 반환 됩니다. 동기화 개체가 신호 (사용할 수 없음), `Lock` 동기화 개체에서 지정 된 밀리초 수까지 신호를 대기 합니다 *dwTimeOut* 매개 변수입니다. 동기화 개체에서 지정 된 기간 동안 신호 되지 않은 경우 `Lock` 실패를 반환 합니다.

##  <a name="m_hobject"></a>  CSyncObject::m_hObject

내부 동기화 개체에 대 한 핸들입니다.

```
HANDLE m_hObject;
```

##  <a name="operator_handle"></a>  CSyncObject::operator HANDLE

이 연산자를 사용 하 여의 핸들을 가져올 수는 `CSyncObject` 개체입니다.

```
operator HANDLE() const;
```

### <a name="return-value"></a>반환 값

성공 하면는 동기화 개체의 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

Windows Api를 직접 호출 하는 핸들을 사용할 수 있습니다.

##  <a name="unlock"></a>  CSyncObject::Unlock

선언의 `Unlock` 순수 가상 함수 이며에서 파생 된 모든 클래스에서 재정의 되어야 매개 변수 없이 `CSyncObject`합니다.

```
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,
    LPLONG lpPrevCount = NULL);
```

### <a name="parameters"></a>매개 변수

*lCount*<br/>
기본 구현에서 사용 되지 않습니다.

*lpPrevCount*<br/>
기본 구현에서 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

기본적으로 항상 두 개의 매개 변수를 사용 하 여 선언 TRUE를 반환합니다. 이 함수는 호출 스레드에서 소유 된 동기화 개체에 대 한 액세스를 해제 하려면 호출 됩니다. 두 번째 선언 같은 제어 된 리소스의 둘 이상의 액세스할 수 있는 세마포 동기화 개체에 대 한 제공 됩니다.

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
