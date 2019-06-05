---
title: CEvent 클래스
ms.date: 11/04/2016
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
helpviewer_keywords:
- CEvent [MFC], CEvent
- CEvent [MFC], PulseEvent
- CEvent [MFC], ResetEvent
- CEvent [MFC], SetEvent
- CEvent [MFC], Unlock
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
ms.openlocfilehash: 54501e5ff690b855ca65652e76d45b9c6cfb6259
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503712"
---
# <a name="cevent-class"></a>CEvent 클래스

한 스레드가 다른 이벤트가 발생 했음을 알릴 수 있도록 하는 동기화 개체인 이벤트를 나타냅니다.

## <a name="syntax"></a>구문

```
class CEvent : public CSyncObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CEvent::CEvent](#cevent)|`CEvent` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CEvent::PulseEvent](#pulseevent)|집합은 이벤트를 사용할 수 있습니다 (신호)를 대기 중인 스레드를 해제 하 고 이벤트 (신호)를 사용할 수 없도록 설정 합니다.|
|[CEvent::ResetEvent](#resetevent)|이벤트 (신호)를 사용할 수 없도록 설정합니다.|
|[CEvent::SetEvent](#setevent)|사용 가능한 (신호) 이벤트를 설정 하 고 모든 대기 스레드를 해제 합니다.|
|[CEvent::Unlock](#unlock)|이벤트 개체를 해제합니다.|

## <a name="remarks"></a>설명

이벤트는 스레드는 해당 작업을 수행 하는 경우 알고 있어야 하는 경우에 유용 합니다. 예를 들어, 데이터 보관에 데이터를 복사 하는 스레드가 새 데이터를 사용할 때 알림을 받을 해야 합니다. 사용 하 여를 `CEvent` 개체를 새 데이터를 사용할 수 있는 경우 복사 스레드를 알립니다 스레드는 가능한 한 빨리 해당 태스크를 수행할 수 있습니다.

`CEvent` 개체에는 두 가지 유형: 수동 및 자동입니다.

자동 `CEvent` 개체 신호 없음 (사용할 수 없음) 상태에 하나 이상의 스레드가 해제 된 후 자동으로 반환 합니다. 기본적으로 `CEvent` 개체는 전달 하지 않은 경우 자동 `TRUE` 에 대 한 합니다 *bManualReset* 생성 중에 매개 변수입니다.

수동 `CEvent` 설정 된 상태에서 개체 유지 [SetEvent](#setevent) 또는 [ResetEvent](#resetevent) 다른 함수가 호출 될 때까지 합니다. 수동을 만들려는 `CEvent` 개체를 전달 `TRUE` 에 대 한는 `bManualReset` 생성 중에 매개 변수입니다.

사용 하는 `CEvent` 개체를 생성 합니다 `CEvent` 필요 하다 면 개체입니다. 이벤트를 대기 하 고는 응용 프로그램은 처음에 소유 하 고 지정 하려는 이름을 지정 합니다. 그런 다음 생성자는 반환 될 때 이벤트를 액세스할 수 있습니다. 호출 [SetEvent](#setevent) 신호 (가능)에 이벤트 개체와 호출 [잠금 해제](#unlock) 완료 되 면 제어 리소스에 액세스 합니다.

사용 하는 대체 방법을 `CEvent` 개체 형식의 변수를 추가 하는 것 `CEvent` 제어 하려는 클래스를 데이터 멤버로 합니다. 제어 되는 개체의 생성 하는 동안의 생성자를 호출 합니다 `CEvent` 데이터 멤버도 이벤트가 처음 신호 여부 및 specifythe 유형의 이벤트 개체를 (프로세스 전체에서 사용 하는 경우 이벤트의 이름 지정 경계) 및 원하는 모든 보안 특성.

의해 제어 되는 리소스에 액세스 하는 `CEvent` 이 방식으로 개체를 먼저 두 가지 형식의 변수를 만듭니다 [CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 형식 [CMultiLock](../../mfc/reference/cmultilock-class.md) 리소스의 액세스 방법에 있습니다. 그런 다음 호출을 `Lock` 잠금 개체의 메서드 (예를 들어 [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock)). 이 시점에서 스레드 중 하나 리소스, 리소스를 해제 하 고 액세스를 얻기 또는 출시 될 리소스에 대 한 대기에 대 한 대기 시간 초과에 대 한 액세스를 확보 되며 리소스에 액세스 하지 못했습니다. 어떤 경우 든, 스레드로부터 안전한 방식으로 리소스에 액세스 합니다. 리소스를 해제 하려면 호출 `SetEvent` 신호 이벤트 개체를 사용 하 여는 `Unlock` 잠금 개체의 메서드 (예를 들어 [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock)), 또는 범위 하지 않는 잠금 개체입니다.

사용 하는 방법에 대 한 자세한 내용은 `CEvent` 개체를 참조 하세요. [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.

## <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#45](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]

[!code-cpp[NVC_MFC_Utilities#46](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CEvent`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

##  <a name="cevent"></a>  CEvent::CEvent

명명 되거나 명명 되지 않은에서는 `CEvent` 개체입니다.

```
CEvent(
    BOOL bInitiallyOwn = FALSE,
    BOOL bManualReset = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>매개 변수

*bInitiallyOwn*<br/>
TRUE 인 경우에 대 한 스레드는 `CMultilock` 또는 `CSingleLock` 개체를 사용할 수 있습니다. 그렇지 않은 경우 리소스에 액세스 하려는 모든 스레드가 대기 해야 합니다.

*bManualReset*<br/>
TRUE 이면 이벤트 개체는 수동 이벤트에 이벤트 개체는 자동 이벤트 그렇지 않은 경우를 지정 합니다.

*lpszName*<br/>
`CEvent` 개체의 이름입니다. 프로세스 경계를 넘어 개체를 사용할 경우에 제공 되어야 합니다. 생성자 빌드 새 이름이 기존 이벤트와 일치 하는 경우 `CEvent` 해당 이름의 이벤트를 참조 하는 개체입니다. 이름이 일치 이벤트를 발생 하지 않은 기존 동기화 개체를 생성 하지 못합니다. NULL 인 경우 이름이 null이 됩니다.

*lpsaAttribute*<br/>
이벤트 개체에 대 한 보안 특성입니다. 에 대 한 전체 설명은이 구조를 참조 하세요 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) Windows SDK에 있습니다.

### <a name="remarks"></a>설명

액세스 하거나 릴리스를 `CEvent` 개체를 만듭니다를 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체와 호출 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 하 고 [잠금 해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수입니다.

상태를 변경 하는 `CEvent` 개체가 신호를 (스레드가 없는 경우 대기), 호출 [SetEvent](#setevent) 또는 [PulseEvent](#pulseevent)합니다. 상태를 설정 하는 `CEvent` 신호를 개체 (스레드가 대기 해야 합니다), 호출 [ResetEvent](#resetevent)합니다.

> [!IMPORTANT]
>  만든 후는 `CEvent` 개체를 사용 하 여 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) 뮤텍스 이미 존재 하지 않는지 확인 합니다. 뮤텍스 예기치 않게가 불량 프로세스 무단 점유 이며 뮤텍스를 악의적으로 사용 하려는 수 수를 나타낼 수 있습니다. 이 경우 권장 되는 보안에 민감한 프로시저 핸들을 닫고 개체를 만드는 오류가 발생 하는 경우에 따라 계속입니다.

##  <a name="pulseevent"></a>  CEvent::PulseEvent

(사용 가능) 신호를 이벤트의 상태를 설정 하 고 모든 대기 스레드를 해제 하 고, nonsignaled (사용할 수 없음)를 자동으로 다시 설정 합니다.

```
BOOL PulseEvent();
```

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이벤트 수동, 모든 대기 스레드가 해제 되 면 이벤트를 신호 없음으로 설정 됩니다 및 `PulseEvent` 반환 합니다. 이벤트 자동 인 경우 단일 스레드가 해제 됩니다, 이벤트가 신호 없음으로 설정 되었는지 및 `PulseEvent` 반환 합니다.

대기 중인 스레드가 없는 경우 스레드가 즉시 해제할 수 `PulseEvent` 신호 이벤트의 상태를 설정 하 고 반환 합니다.

`PulseEvent` 기본 Win32를 사용 하 여 `PulseEvent` 함수는 커널 모드 비동기 프로시저 호출 하 여 대기 상태에서 일시적으로 제거할 수 있습니다. 따라서 `PulseEvent` 안정적이 지 않습니다 하 고 새 응용 프로그램으로 쓰일 수 없습니다. 자세한 내용은 참조는 [PulseEvent 함수](/windows/desktop/api/winbase/nf-winbase-pulseevent)합니다.

##  <a name="resetevent"></a>  CEvent::ResetEvent

설정 이벤트의 상태 신호 될 때까지 명시적으로 여를 신호 받음으로 설정할지를 [SetEvent](#setevent) 멤버 함수입니다.

```
BOOL ResetEvent();
```

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이렇게 하면 모든 스레드가 대기할이 이벤트에 액세스 하려는.

이 멤버 함수 자동 이벤트에 의해 사용 되지 않습니다.

##  <a name="setevent"></a>  CEvent::SetEvent

모든 대기 스레드가 해제 신호를 받을 이벤트의 상태를 설정 합니다.

```
BOOL SetEvent();
```

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이벤트 수동 인 경우 이벤트 신호 될 때까지 남아 [ResetEvent](#resetevent) 라고 합니다. 이 경우 둘 이상의 스레드를 릴리스할 수 있습니다. 이 이벤트는 자동이 단일 스레드가 해제 될 때까지 이벤트 신호를 받은 상태로 유지 됩니다. 시스템은 이벤트의 상태를 신호 설정한 됩니다. 대기 중인 스레드가 없는 경우에 한 스레드가 해제 될 때까지 상태 신호를 받은 상태로 유지 됩니다.

##  <a name="unlock"></a>  CEvent::Unlock

이벤트 개체를 해제합니다.

```
BOOL Unlock();
```

### <a name="return-value"></a>반환 값

스레드의 이벤트 개체 및 이벤트를 소유 하는 경우 0이 아닌 값은 자동 이벤트; 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 현재 해당 잠금 개체를 다시 사용할 경우 작업이 완료 되 면 해제는 자동 이벤트를 소유한 스레드에 의해 호출 됩니다. 잠금 개체를 다시 사용 하지 않는 경우이 함수에서 잠금 개체의 소멸자가 호출 됩니다.

## <a name="see-also"></a>참고자료

[CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
