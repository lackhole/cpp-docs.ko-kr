---
title: CMFCTasksPaneTaskGroup 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
ms.openlocfilehash: a28f00fb732727ec1334946a9e752679307cd3a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222256"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup 클래스

합니다 `CMFCTasksPaneTaskGroup` 클래스는에서 사용 하는 도우미 클래스를 [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) 제어 합니다. `CMFCTasksPaneTaskGroup` 형식의 개체는 *작업 그룹*을 나타냅니다. 작업 그룹은 축소 단추가 포함된 별도 상자에 프레임워크가 표시하는 항목 목록입니다. 상자는 선택적 캡션(그룹 이름)을 가질 수 있습니다. 그룹을 축소하면 작업 목록이 표시되지 않습니다.

## <a name="syntax"></a>구문

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|`CMFCTasksPaneTaskGroup` 개체를 생성합니다.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|현재 작업 그룹에 대 한 내게 필요한 옵션 데이터를 결정합니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|작업 그룹의 작업 창 컨트롤의 아래쪽으로 정렬 되는지 여부를 결정 합니다.|
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|작업 그룹이 축소 되는지 여부를 결정 합니다.|
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|작업 그룹 인지 여부를 결정 *특별 한 합니다.* 다른 색으로 특수 캡션을 표시 하는 프레임 워크입니다.|
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|작업의 내부 목록을 포함합니다.|
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|그룹 캡션의 경계 사각형을 지정 합니다.|
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|그룹의 경계 사각형을 지정 합니다.|
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|그룹의 이름을 지정합니다.|

## <a name="remarks"></a>설명

다음 그림에서는 확장 된 작업 그룹을 보여 줍니다.

![작업 그룹, 확장 됨](../../mfc/reference/media/nexttaskgrpexpand.png "작업 그룹, 확장 됨")

다음 그림에서는 축소 된 작업 그룹을 보여 줍니다.

![축소 된 작업 그룹](../../mfc/reference/media/nexttaskgrpcollapse.png "축소 된 작업 그룹")

다음 그림은 캡션이 없는 작업 그룹을 보여 줍니다.

![캡션이 없는 작업 그룹](../../mfc/reference/media/nexttaskgrpnocapt.png "캡션이 없는 작업 그룹")

다음 그림에서는 두 작업 그룹을 보여 줍니다. 설정 하 여 첫 번째 작업 그룹으로 특별 한 표시는 `m_bIsSpecial` 플래그입니다. TRUE 이면 두 번째 작업 그룹을 취소 하는 동안 특별 한 합니다. 첫 번째 작업 그룹에 대 한 캡션을 두 번째 작업 그룹과 음영이 짙을 수록 성은 note:

![특수 작업 그룹](../../mfc/reference/media/nexttaskgrpspecial.png "특별 한 작업 그룹")

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxTasksPane.h

##  <a name="cmfctaskspanetaskgroup"></a>  CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup

`CMFCTasksPaneTaskGroup` 개체를 생성합니다.

```
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,
    BOOL bIsBottom,
    BOOL bIsSpecial=FALSE,
    BOOL bIsCollapsed=FALSE,
    CMFCTasksPanePropertyPage* pPage=NULL,
    HICON hIcon=NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
그룹 캡션의 그룹의 이름을 지정합니다.

*bIsBottom*<br/>
그룹 작업 창 컨트롤의 아래쪽으로 정렬 되는지 여부를 지정 합니다.

*bIsSpecial*<br/>
그룹으로 지정 되 고 있는지 여부를 지정 *특수* 그룹 캡션에 다른 색으로 채워진 여부에 따라서 및 합니다.

*bIsCollapsed*<br/>
그룹 축소 되는지 여부를 지정 합니다.

*pPage*<br/>
이 작업 그룹에 속하는 속성 페이지를 지정 합니다.

*hIcon*<br/>
그룹 캡션의 표시 되는 아이콘을 지정 합니다.

### <a name="remarks"></a>설명

##  <a name="m_bisbottom"></a>  CMFCTasksPaneTaskGroup::m_bIsBottom

작업 그룹의 작업 창 컨트롤의 아래쪽으로 정렬 되는지 여부를 결정 합니다.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>설명

작업 창 컨트롤의 아래쪽에 하나의 그룹을 정렬할 수 있습니다. 이 작업 그룹은 마지막으로 추가 되어야 합니다. 자세한 내용은 [cmfctaskspane:: Addgroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)합니다.

##  <a name="m_biscollapsed"></a>  CMFCTasksPaneTaskGroup::m_bIsCollapsed

작업 그룹이 축소 되는지 여부를 결정 합니다.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>설명

호출 하 여 작업 창에서 그룹을 축소 하는 기능을 사용 하지 않도록 설정 하거나 설정할 수 있습니다 [cmfctaskspane:: Enablegroupcollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse)합니다.

##  <a name="m_bisspecial"></a>  CMFCTasksPaneTaskGroup::m_bIsSpecial

작업 그룹 인지 여부를 결정 *특수* 다른 색으로 특별 한 작업 그룹에 대 한 캡션을 식별 하는 여부 및 합니다.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>설명

응용 프로그램이 Windows XP 시각적 테마를 사용 중인 경우와 `m_bIsSpecial` 이 false 이면, 프레임 워크 호출 `DrawThemeBackground` EBP_NORMALGROUPBACKGROUND 플래그를 사용 하 여 합니다. 하는 경우 `m_bIsSpecial` 가 TRUE 인 프레임 워크 호출 `DrawThemeBackground` EBP_SPECIALGROUPBACKGROUND 플래그를 사용 하 여 합니다.

##  <a name="m_lsttasks"></a>  CMFCTasksPaneTaskGroup::m_lstTasks

작업의 내부 목록을 포함합니다.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>설명

이 목록에 맞게, 호출 [cmfctaskspane:: Addtask](../../mfc/reference/cmfctaskspane-class.md#addtask)합니다.

##  <a name="m_rect"></a>  CMFCTasksPaneTaskGroup::m_rect

그룹 캡션의 경계 사각형을 지정 합니다.

```
CRect m_rect;
```

### <a name="remarks"></a>설명

이 값은 프레임 워크에서 자동으로 계산 됩니다.

##  <a name="m_rectgroup"></a>  CMFCTasksPaneTaskGroup::m_rectGroup

그룹의 경계 사각형을 지정 합니다.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>설명

이 값은 프레임 워크에서 자동으로 계산 됩니다.

##  <a name="m_strname"></a>  CMFCTasksPaneTaskGroup::m_strName

그룹의 이름을 지정합니다.

```
CString m_strName;
```

### <a name="remarks"></a>설명

이 값이 비어 있으면 그룹 제목을 표시 되지 않으며 그룹을 축소할 수 없습니다.

##  <a name="setaccdata"></a>  CMFCTasksPaneTaskGroup::SetACCData

현재 작업 그룹에 대 한 내게 필요한 옵션 데이터를 결정합니다.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>매개 변수

*pParent*<br/>
[in] 현재 작업 그룹의 부모 창을 나타냅니다.

*data*<br/>
[out] 형식의 개체 `CAccessibilityData` 는 현재 작업 그룹의 내게 필요한 옵션 데이터를 사용 하 여 채워집니다.

### <a name="return-value"></a>반환 값

TRUE 이면 합니다 *데이터* FALSE 매개 변수를 성공적으로 현재 작업 그룹의 내게 필요한 옵션 데이터를 사용 하 여 채워진 고, 그렇지 않으면입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTasksPane 클래스](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFCTasksPaneTask 클래스](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
