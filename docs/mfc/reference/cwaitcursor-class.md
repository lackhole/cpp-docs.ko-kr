---
title: CWaitCursor 클래스
ms.date: 11/04/2016
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
ms.openlocfilehash: 87ac87019f127d3956caf959a28fc889fdecad50
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450812"
---
# <a name="cwaitcursor-class"></a>CWaitCursor 클래스

사용자가 장기 작업을 수행하는 동안 대기 커서를 표시하는 한 가지 방법(일반적으로 모래시계로 표시됨)을 제공합니다.

## <a name="syntax"></a>구문

```
class CWaitCursor
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CWaitCursor::CWaitCursor](#cwaitcursor)|생성 된 `CWaitCursor` 개체 및 대기 커서를 표시 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWaitCursor::Restore](#restore)|변경 된 후 대기 커서를 복원 합니다.|

## <a name="remarks"></a>설명

`CWaitCursor` 기본 클래스는 없습니다.

사례를 프로그래밍 하는 좋은 Windows는 상당한 시간을 사용 하는 작업을 수행 하는 때마다 대기 커서를 표시 하는 필요 합니다.

대기 커서를 표시 하려면 정의 `CWaitCursor` 시간이 오래 걸리는 작업을 수행 하는 코드 전에 변수입니다. 개체의 생성자는 표시할 대기 커서를 자동으로 발생 합니다.

개체 범위를 벗어날 때 (있는 블록의 끝에는 `CWaitCursor` 개체가 선언 되), 해당 소멸자 이전 커서에 커서를 설정 합니다. 즉, 개체는 자동으로 필요한 정리 수행합니다.

> [!NOTE]
>  해당 생성자와 소멸자를 작동 방식 때문 `CWaitCursor` 개체는 항상 지역 변수로 선언-전역 변수로 선언 되지 않습니다 하도 사용 하 여 이러한 할당 됩니다 **새**합니다.

메시지 상자 또는 대화 상자에서 호출을 표시 하는 등 변경 커서를 일으킬 수 있는 작업을 수행 하는 경우는 [복원](#restore) waitcursor를 복원 하려면 멤버 함수입니다. 호출 해도 되는지 `Restore` 도 경우 대기 커서를 현재 표시 됩니다.

대기 커서를 표시 하는 다른 방법의 조합을 사용 하는 것 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)하십시오 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), 및 아마도 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). 그러나 `CWaitCursor` 시간이 오래 걸리는 작업을 사용 하 여 완료 되 면 이전 커서에 커서를 설정할 필요가 없기 때문에 사용 하기 쉽습니다.

> [!NOTE]
>  MFC 설정 하 고 사용 하 여 커서를 복원 합니다 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) 가상 함수입니다. 사용자 지정 동작을 제공 하려면이 함수를 재정의할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CWaitCursor`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]

##  <a name="cwaitcursor"></a>  CWaitCursor::CWaitCursor

대기 커서를 표시 하려면 방금 선언는 `CWaitCursor` 시간이 오래 걸리는 작업을 수행 하는 코드 전에 개체입니다.

```
CWaitCursor();
```

### <a name="remarks"></a>설명

생성자는 표시할 대기 커서를 자동으로 발생 합니다.

개체 범위를 벗어날 때 (있는 블록의 끝에는 `CWaitCursor` 개체가 선언 되), 해당 소멸자 이전 커서에 커서를 설정 합니다. 즉, 개체는 자동으로 필요한 정리 수행합니다.

함수의 일부로 대기 커서를 활성화 하려면 (함수가 종료 되기 전에 일 수 있음)는 블록의 끝에 소멸자가 호출 사실 활용을 걸릴 수 있습니다. 이 기술은 아래 두 번째 예제에 표시 됩니다.

> [!NOTE]
>  해당 생성자와 소멸자를 작동 방식 때문 `CWaitCursor` 개체는 항상 지역 변수로 선언-전역 변수로 선언 되지 않습니다 하도 사용 하 여 이러한 할당 됩니다 **새**합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]

##  <a name="restore"></a>  CWaitCursor::Restore

대기 커서를 복원 하려면 메시지 상자나 대기 커서를 다른 커서에 변경 될 수 있는 대화 상자를 표시 하는 등 작업을 수행한 후이 함수를 호출 합니다.

```
void Restore();
```

### <a name="remarks"></a>설명

호출 해도 `Restore` 도 경우 대기 커서를 현재 표시 됩니다.

에 있는 것 이외의 함수에서 작업 하는 동안 대기 커서를 복원 해야 하는 경우는 `CWaitCursor` 선언 된 개체를 호출할 수 있습니다 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)<br/>
[CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)<br/>
[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)<br/>
[CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)<br/>
[어떻게 할까요 Microsoft Foundation 클래스 응용 프로그램에서 마우스 커서를 변경 합니다.](https://go.microsoft.com/fwlink/p/?linkid=128044)
