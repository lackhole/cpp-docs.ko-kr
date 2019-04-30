---
title: CMultiLock 클래스
ms.date: 11/04/2016
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
helpviewer_keywords:
- CMultiLock [MFC], CMultiLock
- CMultiLock [MFC], IsLocked
- CMultiLock [MFC], Lock
- CMultiLock [MFC], Unlock
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
ms.openlocfilehash: 107ed227c5515cbf2fcb08e957a64a4a17d8287a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366812"
---
# <a name="cmultilock-class"></a>CMultiLock 클래스

다중 스레드 프로그램에 대한 액세스를 제어할 때 사용하는 액세스 제어 메커니즘을 나타냅니다.

## <a name="syntax"></a>구문

```
class CMultiLock
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMultiLock::CMultiLock](#cmultilock)|`CMultiLock` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMultiLock::IsLocked](#islocked)|배열에 있는 특정 동기화 개체 잠겨 있는지 확인 합니다.|
|[CMultiLock::Lock](#lock)|동기화 개체의 배열에 대 한 대기 합니다.|
|[CMultiLock::Unlock](#unlock)|모든 소유 동기화 개체를 해제합니다.|

## <a name="remarks"></a>설명

`CMultiLock` 기본 클래스는 없습니다.

동기화 클래스 사용 [CSemaphore](../../mfc/reference/csemaphore-class.md)를 [CMutex](../../mfc/reference/cmutex-class.md), 및 [CEvent](../../mfc/reference/cevent-class.md)를 만들 수 있습니다를 `CMultiLock` 또는 [CSingleLock](../../mfc/reference/csinglelock-class.md)개체를 대기 하 고 동기화 개체를 해제 합니다. 사용 하 여 `CMultiLock` 특정 시간에 사용할 수 있는 개체가 여러 개 있을 경우. 사용 하 여 `CSingleLock` 때만 하면 한 번에 하나의 개체에서 대기 합니다.

사용 하는 `CMultiLock` 개체, 먼저 대기 하려는 동기화 개체의 배열을 만듭니다. 그런 다음 호출 하는 `CMultiLock` 제어 리소스 클래스에서 멤버 함수 내에서 개체의 생성자입니다. 그런 다음 호출을 [잠금](#lock) 리소스를 사용할 수 있는지 확인 하려면 멤버 함수 (신호). 하는 경우 나머지 멤버 함수를 사용 하 여 계속 합니다. 사용 가능한 리소스가 없는 경우 출시 될 리소스에 대 한 지정 된 기간에 대 한 대기 또는 실패를 반환 합니다. 리소스의 사용 하 여 완료 된 후 호출 하거나 합니다 [잠금 해제](#unlock) 경우 함수는 `CMultiLock` 개체가 다시 사용할 수 있도록 하는 `CMultiLock` 소멸 될 개체.

`CMultiLock` 개체는 많은 수의 스레드가 때 가장 유용 `CEvent` 개체 응답할 수 있습니다. 모든 포함 된 배열을 만듭니다는 `CEvent` 포인터 및 호출 `Lock`합니다. 이렇게 하면 스레드가 신호를 받는 이벤트 중 하나가 될 때까지 대기 하도록 합니다.

사용 하는 방법에 대 한 자세한 내용은 `CMultiLock` 문서를 참조 하는 개체를 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CMultiLock`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

##  <a name="cmultilock"></a>  CMultiLock::CMultiLock

`CMultiLock` 개체를 생성합니다.

```
CMultiLock(
    CSyncObject* ppObjects [ ],
    DWORD dwCount,
    BOOL bInitialLock = FALSE);
```

### <a name="parameters"></a>매개 변수

*ppObjects*<br/>
동기화 개체를 대기할 수에 대 한 포인터의 배열입니다. NULL일 수 없습니다.

*dwCount*<br/>
개체 수가 *ppObjects*합니다. 0보다 커야 합니다.

*bInitialLock*<br/>
제공 된 개체에 액세스 하려고 처음 것인지 지정 합니다.

### <a name="remarks"></a>설명

이 함수는 동기화 개체 대기 수 배열을 만든 후 호출 됩니다. 일반적으로 사용할 수 있으려면 동기화 개체 중 하나에 대 한 대기 해야 하는 스레드 내에서 호출 됩니다.

##  <a name="islocked"></a>  CMultiLock::IsLocked

지정된 된 개체 신호 인지 여부를 확인 (사용할 수 없음).

```
BOOL IsLocked(DWORD dwItem);
```

### <a name="parameters"></a>매개 변수

*dwItem*<br/>
해당 상태를 쿼리 하는 개체에 해당 하는 개체의 배열 인덱스입니다.

### <a name="return-value"></a>반환 값

0이 아닌 지정된 된 개체는 잠겨 있습니다. 그렇지 않으면 0입니다.

##  <a name="lock"></a>  CMultiLock::Lock

하나 이상의 제공 된 동기화 개체에 의해 제어 되는 리소스에 액세스 하려면이 함수를 호출 합니다 `CMultiLock` 생성자입니다.

```
DWORD Lock(
    DWORD dwTimeOut = INFINITE,
    BOOL bWaitForAll = TRUE,
    DWORD dwWakeMask = 0);
```

### <a name="parameters"></a>매개 변수

*dwTimeOut*<br/>
동기화 개체를 사용할 수에 대 한 대기 시간 지정 (신호). 무한 경우 `Lock` 개체를 반환 하기 전에 신호를 받을 때까지 기다립니다.

*bWaitForAll*<br/>
대기 하는 모든 개체 반환 하기 전에 동시 신호 해야 하는지 여부를 지정 합니다. FALSE 이면 `Lock` 중 하나라도 대기 개체에 신호가 전달 될 때 반환 됩니다.

*dwWakeMask*<br/>
대기를 중단 하려면 허용 되는 다른 조건을 지정 합니다. 이 매개 변수에 대 한 사용 가능한 옵션의 전체 목록을 참조 하세요 [MsgWaitForMultipleObjects](/windows/desktop/api/winuser/nf-winuser-msgwaitformultipleobjects) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

경우 `Lock` 실패 하면 반환-1입니다. 성공 하면 다음 값 중 하나가 반환 됩니다.

- WAIT_OBJECT_0, WAIT_OBJECT_0 + (1 개체 개수)

   하는 경우 *bWaitForAll* 가 TRUE 인 모든 개체 (사용 가능) 신호입니다. 하는 경우 *bWaitForAll* 가 FALSE를 반환 값-WAIT_OBJECT_0 신호를 받는 (사용 가능) 하는 개체의 개체 배열의 인덱스입니다.

- WAIT_OBJECT_0 + (개체 개수)

   에 지정 된 이벤트 *dwWakeMask* 스레드의 입력된 큐에서 사용할 수 있습니다.

- WAIT_ABANDONED_0, WAIT_ABANDONED_0 + (1 개체 개수)

   하는 경우 *bWaitForAll* 가 TRUE이 고, 신호는 모든 개체는 개체 중 하나 이상이 중단 된 뮤텍스 개체입니다. 하는 경우 *bWaitForAll* 가 FALSE를 반환 값-WAIT_ABANDONED_0 대기를 만족 하는 중단 된 뮤텍스 개체의 개체 배열의 인덱스입니다.

- WAIT_TIMEOUT

   에 지정 된 시간 제한 간격 *dwTimeOut* 그 다음 대기 하지 않고 만료 되었습니다.

### <a name="remarks"></a>설명

하는 경우 *bWaitForAll* 가 TRUE 인 `Lock` 동기화 개체를 모두 동시에 신호 하는 즉시 성공적으로 반환 됩니다. 하는 경우 *bWaitForAll* 은 FALSE `Lock` 하나 이상의 동기화 개체가 신호를 받게 되는 즉시 반환 됩니다.

하는 경우 `Lock` 에 지정 된 밀리초 이하의 대기 즉시 반환할 수 없는 합니다 *dwTimeOut* 반환 하기 전에 매개 변수입니다. 하는 경우 *dwTimeOut* 은 무제한을 `Lock` 개체에 대 한 액세스는 또는 구성 요소에 지정 된 조건이 될 때까지 반환 하지 것입니다 *dwWakeMask* 충족 되었습니다. 그렇지 않은 경우, `Lock` 된 동기화 개체를 획득할 수를 반환 했습니다. 않으면 그렇지 않은 경우 오류가 반환 됩니다.

##  <a name="unlock"></a>  CMultiLock::Unlock

소유 하는 동기화 개체를 해제 `CMultiLock`합니다.

```
BOOL Unlock();

BOOL Unlock(
    LONG lCount,
    LPLONG lPrevCount = NULL);
```

### <a name="parameters"></a>매개 변수

*lCount*<br/>
참조 개수 계산 릴리스 합니다. 0보다 커야 합니다. 지정된 된 크기는 개체의 수가 최대값을 초과 하으로 인해에 수는 변경 되지 않으며 함수가 FALSE를 반환 합니다.

*lPrevCount*<br/>
동기화 개체에 대 한 이전 카운트를 수신 하는 변수를 가리킵니다. NULL 인 경우 이전 카운트를 반환 되지 않습니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수를 호출 하 `CMultiLock`의 소멸자입니다.

첫 번째 형태 `Unlock` 에서 관리 하는 동기화 개체의 잠금을 해제 하려고 `CMultiLock`합니다. 두 번째 형태 `Unlock` 잠금을 해제 하려고 합니다 `CSemaphore` 소유한 개체 `CMultiLock`합니다. 하는 경우 `CMultiLock` 소유 하지 않는 잠긴 `CSemaphore` 개체 함수가 FALSE를 반환 합니다; 그리고 그렇지 않으면 TRUE를 반환 합니다. *lCount* 하 고 *lpPrevCount* 동일 매개 변수로 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)합니다. 두 번째 형식의 `Unlock` 거의 multilock 상황에 적용 됩니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)
