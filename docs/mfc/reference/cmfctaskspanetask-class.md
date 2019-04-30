---
title: CMFCTasksPaneTask 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
helpviewer_keywords:
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
ms.openlocfilehash: 95a2e4f2a1f2e3344936af33fb2258b496b1be93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218708"
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask 클래스

합니다 `CMFCTasksPaneTask` 클래스는 작업 창 컨트롤에 대 한 작업을 나타내는 도우미 클래스 ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)). 작업 개체의 작업 그룹에서 항목을 나타냅니다 ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). 각 작업은 사용자가 작업을 클릭할 때 프레임워크가 실행하는 명령과 작업 이름의 왼쪽에 나타내는 아이콘을 포함할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|만들고 초기화는 `CMFCTasksPaneTask` 개체입니다.|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|현재 작업에 대 한 내게 필요한 옵션 데이터를 결정합니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|작업 창이 자동으로 소멸 되 고 있는지 여부를 결정 합니다.|
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|프레임 워크를 굵은 텍스트로 작업 레이블을 그릴지 여부를 결정 합니다.|
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|프레임 워크 작업을 사용 하 여 연결 하는 사용자 정의 데이터를 포함 합니다. 작업에 연결 된 데이터가 없는 경우 0으로 설정 합니다.|
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|작업 창의 핸들입니다.|
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|프레임 워크 태스크 옆에 표시 되는 이미지의 이미지 목록 인덱스입니다.|
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|작업 창의 높이입니다. 작업 없음 작업 창에 있는 경우이 값이 0입니다.|
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|에 대 한 포인터를 `CMFCTasksPaneTaskGroup` 이 작업에 속하는 합니다.|
|[CMFCTasksPaneTask::m_rect](#m_rect)|태스크의 경계 사각형을 지정 합니다.|
|[CMFCTasksPaneTask::m_strName](#m_strname)|태스크의 이름입니다.|
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|프레임 워크 작업을 마우스 오른쪽 단추로 클릭할 때 실행 되는 명령의 명령 ID를 지정 합니다. 이 값이 유효한 명령 ID가 없는 경우 작업은 단순한 레이블입니다로 처리 됩니다.|

## <a name="remarks"></a>설명

다음 그림에서는 세 가지 작업을 포함 하는 작업 그룹을 보여 줍니다.

![작업 그룹, 확장 됨](../../mfc/reference/media/nexttaskgrpexpand.png "작업 그룹, 확장 됨")

> [!NOTE]
> 작업에 유효한 명령 ID를 찾을 수 없는 경우 단순 레이블로 처리 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxTasksPane.h

##  <a name="cmfctaskspanetask"></a>  CMFCTasksPaneTask::CMFCTasksPaneTask

만들고 초기화는 `CMFCTasksPaneTask` 개체입니다.

```
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,
    LPCTSTR lpszName,
    int nIcon,
    UINT uiCommandID,
    DWORD dwUserData = 0,
    HWND hwndTask = NULL,
    BOOL bAutoDestroyWindow = FALSE,
    int nWindowHeight = 0);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
지정 된 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 작업이 속한 합니다.

*lpszName*<br/>
태스크의 이름을 지정합니다.

*nIcon*<br/>
이미지 목록에서 작업의 이미지의 인덱스를 지정합니다.

*uiCommandID*<br/>
작업을 클릭할 때 실행 되는 명령의 명령 ID를 지정 합니다.

*dwUserData*<br/>
사용자 정의 데이터입니다.

*hwndTask*<br/>
작업 창에 대 한 핸들을 지정합니다.

*bAutoDestroyWindow*<br/>
True 이면 작업 창이 자동으로 제거 됩니다.

*nWindowHeight*<br/>
작업 창의 높이 지정합니다.

### <a name="remarks"></a>설명

##  <a name="m_bautodestroywindow"></a>  CMFCTasksPaneTask::m_bAutoDestroyWindow

작업 창이 자동으로 소멸 되 고 있는지 여부를 결정 합니다.

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>설명

작업 기간을 지정 하려면 TRUE로 설정 ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) 자동으로, 그렇지 않으면 FALSE 제거 해야 합니다.

##  <a name="m_bisbold"></a>  CMFCTasksPaneTask::m_bIsBold

작업 레이블 굵은 텍스트로 그릴지 여부를 결정 합니다.

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>설명

True로 설정 하면 작업 레이블 텍스트를 굵게 표시 된이 멤버를 설정 합니다.

##  <a name="m_dwuserdata"></a>  CMFCTasksPaneTask::m_dwUserData

작업과 연결 된 사용자 정의 데이터를 포함 합니다. 작업과 관련 된 데이터가 없는 경우 0으로 설정 합니다.

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>설명

##  <a name="m_hwndtask"></a>  CMFCTasksPaneTask::m_hwndTask

작업 창의 핸들입니다.

```
HWND m_hwndTask;
```

### <a name="remarks"></a>설명

작업 창에 추가 하려면 [CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow)합니다.

##  <a name="m_nicon"></a>  CMFCTasksPaneTask::m_nIcon

지정 된 태스크 옆에 표시 되는 이미지를 식별 하는 이미지 목록에서 인덱스 위치입니다.

```
int m_nIcon;
```

### <a name="remarks"></a>설명

이미지 목록으로 설정 됩니다 [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist)합니다.

설정 `m_nIcon` 이미지 없는 작업을 표시 하려는 경우-1입니다.

##  <a name="m_nwindowheight"></a>  CMFCTasksPaneTask::m_nWindowHeight

작업 창의 높이입니다. 작업 없음 작업 창에 있는 경우이 값이 0입니다.

```
int m_nWindowHeight;
```

### <a name="remarks"></a>설명

##  <a name="m_pgroup"></a>  CMFCTasksPaneTask::m_pGroup

에 대 한 포인터를 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 이 작업이 속한 합니다.

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>설명

모든 작업에는 상위 그룹이 있어야 합니다. 호출 하 여 작업 창에 그룹을 추가한 [cmfctaskspane:: Addgroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)합니다.

##  <a name="m_rect"></a>  CMFCTasksPaneTask::m_rect

태스크의 경계 사각형을 지정 합니다.

```
CRect m_rect;
```

### <a name="remarks"></a>설명

이 값은 태스크를 그릴 때 프레임 워크에 의해 계산 됩니다.

##  <a name="m_strname"></a>  CMFCTasksPaneTask::m_strName

태스크의 이름입니다.

```
CString m_strName;
```

### <a name="remarks"></a>설명

##  <a name="m_uicommandid"></a>  CMFCTasksPaneTask::m_uiCommandID

작업을 마우스 오른쪽 단추로 클릭할 때 실행 되는 명령의 명령 ID를 지정 합니다. 이 값이 유효한 명령 ID가 없는 경우 작업은 단순한 레이블입니다로 처리 됩니다.

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>설명

##  <a name="setaccdata"></a>  CMFCTasksPaneTask::SetACCData

현재 작업에 대 한 내게 필요한 옵션 데이터를 결정합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
[in] 현재 태스크의 부모 창을 나타냅니다.

*data*<br/>
[out] 형식의 개체 `CAccessibilityData` 는 현재 태스크의 내게 필요한 옵션 데이터를 사용 하 여 채워집니다.

### <a name="return-value"></a>반환 값

TRUE 이면 합니다 *데이터* FALSE 매개 변수를 성공적으로 현재 태스크의 내게 필요한 옵션 데이터를 사용 하 여 채워진 고, 그렇지 않으면입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
