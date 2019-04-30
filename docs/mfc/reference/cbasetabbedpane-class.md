---
title: CBaseTabbedPane 클래스
ms.date: 11/04/2016
f1_keywords:
- CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::AddTab
- AFXBASETABBEDPANE/CBaseTabbedPane::AllowDestroyEmptyTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::ApplyRestoredTabInfo
- AFXBASETABBEDPANE/CBaseTabbedPane::CanFloat
- AFXBASETABBEDPANE/CBaseTabbedPane::CanSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::ConvertToTabbedDocument
- AFXBASETABBEDPANE/CBaseTabbedPane::DetachPane
- AFXBASETABBEDPANE/CBaseTabbedPane::EnableSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::FillDefaultTabsOrderArray
- AFXBASETABBEDPANE/CBaseTabbedPane::FindBarByTabNumber
- AFXBASETABBEDPANE/CBaseTabbedPane::FindPaneByID
- AFXBASETABBEDPANE/CBaseTabbedPane::FloatTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetDefaultTabsOrder
- AFXBASETABBEDPANE/CBaseTabbedPane::GetFirstVisibleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetMinSize
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneIcon
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneList
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabArea
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::GetUnderlyingWindow
- AFXBASETABBEDPANE/CBaseTabbedPane::GetVisibleTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::HasAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::IsHideSingleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::RecalcLayout
- AFXBASETABBEDPANE/CBaseTabbedPane::RemovePane
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoDestroy
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::ShowTab
helpviewer_keywords:
- CBaseTabbedPane [MFC], AddTab
- CBaseTabbedPane [MFC], AllowDestroyEmptyTabbedPane
- CBaseTabbedPane [MFC], ApplyRestoredTabInfo
- CBaseTabbedPane [MFC], CanFloat
- CBaseTabbedPane [MFC], CanSetCaptionTextToTabName
- CBaseTabbedPane [MFC], ConvertToTabbedDocument
- CBaseTabbedPane [MFC], DetachPane
- CBaseTabbedPane [MFC], EnableSetCaptionTextToTabName
- CBaseTabbedPane [MFC], FillDefaultTabsOrderArray
- CBaseTabbedPane [MFC], FindBarByTabNumber
- CBaseTabbedPane [MFC], FindPaneByID
- CBaseTabbedPane [MFC], FloatTab
- CBaseTabbedPane [MFC], GetDefaultTabsOrder
- CBaseTabbedPane [MFC], GetFirstVisibleTab
- CBaseTabbedPane [MFC], GetMinSize
- CBaseTabbedPane [MFC], GetPaneIcon
- CBaseTabbedPane [MFC], GetPaneList
- CBaseTabbedPane [MFC], GetTabArea
- CBaseTabbedPane [MFC], GetTabsNum
- CBaseTabbedPane [MFC], GetUnderlyingWindow
- CBaseTabbedPane [MFC], GetVisibleTabsNum
- CBaseTabbedPane [MFC], HasAutoHideMode
- CBaseTabbedPane [MFC], IsHideSingleTab
- CBaseTabbedPane [MFC], RecalcLayout
- CBaseTabbedPane [MFC], RemovePane
- CBaseTabbedPane [MFC], SetAutoDestroy
- CBaseTabbedPane [MFC], SetAutoHideMode
- CBaseTabbedPane [MFC], ShowTab
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
ms.openlocfilehash: d7ffaa7274a8ed12944cdbc5dcbbdcb8fd3fd2b9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388594"
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane 클래스

[CDockablePane Class](../../mfc/reference/cdockablepane-class.md) 의 기능을 확장하여 탭 창 만들기를 지원합니다.

## <a name="syntax"></a>구문

```
class CBaseTabbedPane : public CDockablePane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CBaseTabbedPane::CBaseTabbedPane`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CBaseTabbedPane::AddTab](#addtab)|탭된 창에 새 탭을 추가합니다.|
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|빈 탭된 창 소멸 될 수 있는지 여부를 지정 합니다.|
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|레지스트리에서 탭된 창에 로드 되는 탭 설정을 적용 합니다.|
|[CBaseTabbedPane::CanFloat](#canfloat)|창 부동 상태로 있을 수 있는지 여부를 결정 합니다. (재정의 [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|탭된 창 캡션의 활성 탭으로 동일한 텍스트를 표시할 것인지 여부를 결정 합니다.|
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(재정의 [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|
|[CBaseTabbedPane::DetachPane](#detachpane)|하나 이상의 도킹 가능한 창을 MDI 탭 문서로 변환합니다.|
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|사용 하거나 활성 탭에 레이블 텍스트를 사용 하 여 캡션 텍스트를 동기화 하는 탭 창 기능을 사용 하지 않도록 설정 합니다.|
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|내부 탭 순서를 기본 상태로 복원합니다.|
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|탭의 0부터 시작 탭 인덱스에 의해 식별 되 면 탭에 있는 창에 반환 합니다.|
|||
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|창 ID로 식별 되는 창을 반환 합니다.|
|[CBaseTabbedPane::FloatTab](#floattab)|창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다.|
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|창에서 탭의 기본 순서를 반환합니다.|
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|첫 번째 표시 탭에 대 한 포인터를 검색합니다.|
|[CBaseTabbedPane::GetMinSize](#getminsize)|창의 크기에 허용 되는 최소값을 검색 합니다. (재정의 [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|창 아이콘에 대 한 핸들을 반환합니다. (재정의 [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|
|[CBaseTabbedPane::GetPaneList](#getpanelist)|탭된 창에 포함 된 창 목록을 반환 합니다.|
|[CBaseTabbedPane::GetTabArea](#gettabarea)|위쪽 및 아래쪽 탭 영역에 대 한 경계 사각형을 반환합니다.|
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|탭 창에서 탭의 수를 반환 합니다.|
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|기본 (래핑된) 탭 창을 가져옵니다.|
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|표시 된 탭의 수를 반환 합니다.|
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|탭된 창 자동 숨기기 모드로 전환할 수 있는지 여부를 결정 합니다.|
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|탭된 창 이상의 탭이 표시 되는지 숨겨져 있는지 여부를 결정 합니다.|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|직렬화 하는 동안 내부적으로 사용 합니다.|
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|창에 대 한 레이아웃 정보를 다시 계산합니다. (재정의 [cpane:: Recalclayout](../../mfc/reference/cpane-class.md#recalclayout).)|
|[CBaseTabbedPane::RemovePane](#removepane)|창이 탭된 창에서 제거합니다.|
|`CBaseTabbedPane::SaveSiblingBarIDs`|직렬화 하는 동안 내부적으로 사용 합니다.|
|`CBaseTabbedPane::Serialize`|(재정의 [cdockablepane:: Serialize](cdockablepane-class.md).)|
|`CBaseTabbedPane::SerializeTabWindow`|직렬화 하는 동안 내부적으로 사용 합니다.|
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|탭된 컨트롤 막대에는 자동으로 소멸 됩니다 있는지 여부를 결정 합니다.|
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|도킹 창 간에 표시 설정/해제 및 자동 숨기기 모드입니다. (재정의 [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|
|[CBaseTabbedPane::ShowTab](#showtab)|표시 하거나 숨깁니다을 탭 합니다.|

## <a name="remarks"></a>설명

이 클래스는 추상 클래스 이며 인스턴스화할 수 없습니다. 모든 종류의 탭된 창에 공통 되는 서비스를 구현 합니다.

현재 라이브러리 두 탭된 창 파생된 클래스가 포함 되어 있습니다. [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md) 하 고 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.

A `CBaseTabbedPane` 개체에 대 한 포인터를 래핑하는 [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md) 개체입니다. [CMFCBaseTabCtrl 클래스](../../mfc/reference/cmfcbasetabctrl-class.md) 탭 창의 자식 창이 됩니다.

탭된 창을 만드는 방법에 대 한 자세한 내용은 참조 하세요 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)를 [CTabbedPane 클래스](../../mfc/reference/ctabbedpane-class.md), 및 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

`CBaseTabbedPane`

## <a name="requirements"></a>요구 사항

**헤더:** afxBaseTabbedPane.h

##  <a name="addtab"></a>  CBaseTabbedPane::AddTab

탭된 창에 새 탭을 추가합니다.

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>매개 변수

*pNewBar*<br/>
[out에서] 추가할 창에 대 한 포인터입니다. 이 메서드를 호출한 후이 포인터를 잘못 될 수 있습니다. 자세한 내용은 설명 섹션을 참조하세요.

*bVisible*<br/>
[in] 하려면 True이 고 탭 표시 그렇지 않으면 FALSE입니다.

*bSetActive*<br/>
[in] 활성 탭; 탭을 확인. 그렇지 않으면 FALSE입니다.

*bDetachable*<br/>
[in] 하려면 True이 고; 분리 가능한 탭 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

창에 탭으로 추가 되었습니다 및 프로세스에서 제거 되지 된 경우 TRUE입니다. FALSE 이면 추가 되는 형식의 개체 `CBaseTabbedPane`합니다. 자세한 내용은 설명 섹션을 참조하세요.

### <a name="remarks"></a>설명

창이 탭된 창에 새 테이블로 추가 하려면이 메서드를 호출 합니다. 하는 경우 *pNewBar* 형식의 개체를 가리키는 `CBaseTabbedPane`, 모든 탭은 탭된 창에 복사 됩니다 차례로 *pNewBar* 소멸 됩니다. 따라서 *pNewBar* 잘못 된 포인터를 막대로 바뀌고 사용할 수 없습니다.

##  <a name="allowdestroyemptytabbedpane"></a>  CBaseTabbedPane::AllowDestroyEmptyTabbedPane

빈 탭된 창 소멸 될 수 있는지 여부를 지정 합니다.

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 빈 탭된 창 제거할 수 있습니다. 그렇지 않으면 FALSE입니다. 기본 구현에서는 항상 TRUE를 반환합니다.

### <a name="remarks"></a>설명

제거할 탭된 창인 허용 되지 않으면, 프레임 워크 대신 창을 숨깁니다.

##  <a name="applyrestoredtabinfo"></a>  CBaseTabbedPane::ApplyRestoredTabInfo

레지스트리에서 설정 탭을 로드 하 고 탭된 창에 적용 합니다.

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>매개 변수

*bUseTabIndexes*<br/>
[in] 이 매개 변수는 프레임 워크에서 내부적으로 사용 됩니다.

### <a name="remarks"></a>설명

이 메서드는 레지스트리에서 도킹 상태 정보를 다시 로드 하는 경우 프레임 워크에서 호출 됩니다. 메서드는 탭된 창에 대 한 탭 이름과 탭 순서에 대 한 정보를 가져옵니다.

##  <a name="canfloat"></a>  CBaseTabbedPane::CanFloat

탭된 창 부동 상태로 있을 수 있는지 여부를 지정 합니다.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 창 부동 상태로 있을 수 있습니다. 그렇지 않으면 FALSE입니다.

##  <a name="cansetcaptiontexttotabname"></a>  CBaseTabbedPane::CanSetCaptionTextToTabName

탭된 창 캡션의 활성 탭으로 동일한 텍스트를 표시할 것인지 여부를 결정 합니다.

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>반환 값

탭 창의 캡션 텍스트; 활성 탭의 텍스트에 설정 된 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

메서드는 텍스트에 표시할지 여부 탭된 창 캡션 중복 항목이 활성 탭의 레이블을 결정에 사용 됩니다. 호출 하 여이 기능을 사용 하지 않도록 설정 하거나 설정할 수 있습니다 [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)합니다.

##  <a name="converttotabbeddocument"></a>  CBaseTabbedPane::ConvertToTabbedDocument

하나 이상의 도킹 가능한 창을 MDI 탭 문서로 변환합니다.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>매개 변수

*bActiveTabOnly*<br/>
[in] 탭된 창으로 변환 하면 활성 탭만 변환 하려면 TRUE를 지정 합니다. 창의 모든 탭 변환 하려면 FALSE를 지정 합니다.

##  <a name="detachpane"></a>  CBaseTabbedPane::DetachPane

탭된 창에서 창을 분리합니다.

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 분리 하 고 창에 대 한 포인터입니다.

*bHide*<br/>
[in] 분리 된 후 프레임 창을 숨깁니다 여부를 지정 하는 부울 매개 변수입니다.

### <a name="return-value"></a>반환 값

프레임 워크에는 창, 성공적으로 분리 하는 경우 TRUE입니다. FALSE 이면 *pBar* 가 NULL 이거나 탭된 창에 있지 않은 창을 가리킵니다.

### <a name="remarks"></a>설명

프레임 워크는 가능한 경우 분리 된 창을 부동 합니다. 자세한 내용은 [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)합니다.

##  <a name="enablesetcaptiontexttotabname"></a>  CBaseTabbedPane::EnableSetCaptionTextToTabName

사용 하거나 활성 탭에 레이블 텍스트를 사용 하 여 캡션 텍스트를 동기화 하는 탭 창 기능을 사용 하지 않도록 설정 합니다.

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] 활성 탭 캡션에;를 사용 하 여 탭된 창 캡션을 동기화. 그렇지 않으면 FALSE입니다.

##  <a name="filldefaulttabsorderarray"></a>  CBaseTabbedPane::FillDefaultTabsOrderArray

내부 탭 순서를 기본 상태로 복원합니다.

```
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>설명

이 메서드는 프레임 워크는 Outlook 표시줄을 초기 상태로 복원 하는 경우 호출 됩니다.

##  <a name="findpanebyid"></a>  CBaseTabbedPane::FindPaneByID

창 ID로 식별 된 창을 반환 합니다.

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>매개 변수

*uBarID*<br/>
[in] 찾을 창의 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

발견 되 면 창에 대 한 포인터 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

창의 모든 탭을 비교 하 고 지정 된 ID 사용 하 여 하나를 반환 하는이 메서드는 *uBarID* 매개 변수입니다.

##  <a name="findbarbytabnumber"></a>  CBaseTabbedPane::FindBarByTabNumber

탭에 있는 창에 반환 합니다.

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>매개 변수

*nTabNum*<br/>
[in] 검색할 탭의 인덱스를 지정 합니다.

*bGetWrappedBar*<br/>
[in] 자체 창 대신 창의 기본 (래핑된) 창을 반환 하려는 경우 TRUE 그렇지 않으면 FALSE입니다. 파생 된 창에만 적용 됩니다 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)합니다.

### <a name="return-value"></a>반환 값

있으면 창의 검색 창에 대 한 유효한 포인터를 반환 됩니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

에 지정 된 탭에 있는 창을 검색 하려면이 메서드를 호출 합니다 *nTabNum* 매개 변수입니다.

##  <a name="floattab"></a>  CBaseTabbedPane::FloatTab

창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다.

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[out에서] Float로 창에 대 한 포인터입니다.

*nTabID*<br/>
[in] Float 탭의 인덱스를 지정합니다.

*dockMethod*<br/>
[in] 창 float를 사용 하는 방법을 지정 합니다. 자세한 내용은 설명 섹션을 참조하세요.

*bHide*<br/>
[in] 부동; 전에 창을 숨기려면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

창 부동 설정; 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

분리 가능한 탭에 있는 현재 창에 배치 하려면이 메서드를 호출 합니다.

창을 프로그래밍 방식으로 분리 하려는 경우에 대 한 DM_SHOW 지정 된 *dockMethod* 매개 변수입니다. 이전에 떠 있는 동일한 위치에서 창을 고정 해제 하려는 경우 DM_DBL_CLICK로 지정 합니다 *dockMethod* 매개 변수입니다.

##  <a name="getdefaulttabsorder"></a>  CBaseTabbedPane::GetDefaultTabsOrder

창에서 탭의 기본 순서를 반환합니다.

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>반환 값

`CArray` 창에서 탭의 기본 순서를 지정 하는 개체입니다.

### <a name="remarks"></a>설명

Outlook 표시줄은 초기 상태로 다시 설정 하는 경우이 메서드를 호출 하는 프레임 워크입니다.

##  <a name="getfirstvisibletab"></a>  CBaseTabbedPane::GetFirstVisibleTab

첫 번째 표시 탭에 대 한 포인터를 검색합니다.

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>매개 변수

*iTabNum*<br/>
[in] 정수에 대 한 참조입니다. 이 메서드 쓸 첫 번째 표시 탭의 인덱스가 매개이 변수 또는-1 표시 되지 않은 경우 탭이 발견 합니다.

### <a name="return-value"></a>반환 값

성공 하면 첫 번째 표시 탭;에 대 한 포인터 그렇지 않으면 NULL입니다.

##  <a name="getminsize"></a>  CBaseTabbedPane::GetMinSize

창의 크기에 허용 되는 최소값을 검색 합니다.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>매개 변수

*size*<br/>
[out] `CSize` 크기가 허용 되는 최소값으로 채워진 개체입니다.

### <a name="remarks"></a>설명

최소 창 크기의 일관 된 처리가 활성화 되는 경우 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *크기* 활성 탭에 대 한 크기에 허용 되는 최소값으로 채워집니다. 그렇지 않으면 *크기* 의 반환 값으로 채워집니다 [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)합니다.

##  <a name="getpaneicon"></a>  CBaseTabbedPane::GetPaneIcon

창의 크기에 허용 되는 최소값을 검색 합니다.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>매개 변수

*size*<br/>
[out] `CSize` 크기가 허용 되는 최소값으로 채워진 개체입니다.

### <a name="remarks"></a>설명

최소 창 크기의 일관 된 처리가 활성화 되는 경우 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *크기* 활성 탭에 대 한 크기에 허용 되는 최소값으로 채워집니다. 그렇지 않으면 *크기* 의 반환 값으로 채워집니다 [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)합니다.

##  <a name="getpanelist"></a>  CBaseTabbedPane::GetPaneList

탭된 창에 포함 된 창 목록을 반환 합니다.

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>매개 변수

*lst*<br/>
[out] `CObList` 는 탭된 창에 포함 된 창이 채워집니다.

*pRTCFilter*<br/>
[in] NULL 인 경우 반환된 된 목록에 지정된 된 런타임 클래스는 창이 있습니다만 합니다.

##  <a name="gettabarea"></a>  CBaseTabbedPane::GetTabArea

위쪽 및 아래쪽 탭 영역에 대 한 경계 사각형을 반환합니다.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>매개 변수

*rectTabAreaTop*<br/>
[out] 위 탭 영역의 화면 좌표를 받습니다.

*rectTabAreaBottom*<br/>
[out] 아래 탭 영역의 화면 좌표를 받습니다.

### <a name="remarks"></a>설명

경계 사각형에는 상한 및 하 한 탭 영역에 대 한 화면 좌표에서 확인 하려면이 메서드를 호출 합니다.

##  <a name="gettabsnum"></a>  CBaseTabbedPane::GetTabsNum

탭 창에서 탭의 수를 반환 합니다.

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>반환 값

탭된 창에서 탭 수입니다.

##  <a name="getunderlyingwindow"></a>  CBaseTabbedPane::GetUnderlyingWindow

기본 (래핑된) 탭 창을 가져옵니다.

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>반환 값

기본 탭 창에 대 한 포인터입니다.

##  <a name="getvisibletabsnum"></a>  CBaseTabbedPane::GetVisibleTabsNum

표시 탭의 수를 반환 합니다.

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>반환 값

0 보다 크거나 될 표시 탭 수입니다.

### <a name="remarks"></a>설명

탭된 창에 표시 탭의 개수를 확인 하려면이 메서드를 호출 합니다.

##  <a name="hasautohidemode"></a>  CBaseTabbedPane::HasAutoHideMode

탭 창을 자동 숨기기 모드로 전환할 수 있는지 여부를 결정합니다.

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>반환 값

창 자동 숨기기 모드를 전환할 수 있습니다 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

자동 숨기기 모드를 사용 하지 않도록 설정 하는 경우 탭된 창 캡션을에 없는 고정 단추 표시 됩니다.

##  <a name="ishidesingletab"></a>  CBaseTabbedPane::IsHideSingleTab

탭된 창 이상의 탭이 표시 되는지 숨겨져 있는지 여부를 결정 합니다.

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>반환 값

표시 탭 하나만; 때 탭 창이 표시 되지 않으면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

창 탭 하나만 열려 있기 때문에 표시 되지 않으면, 탭된 창을 제대로 작동 하는지 확인 하려면이 메서드를 호출할 수 있습니다.

##  <a name="removepane"></a>  CBaseTabbedPane::RemovePane

창이 탭된 창에서 제거합니다.

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[out에서] 탭된 창에서 제거할 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

탭 창은 여전히 유효한 경우 및 창 탭된 창에서 제거 되었으면 TRUE이 고 마지막 창이 탭된 창에서 제거 되었습니다 이며 탭된 창을 소멸 되려고 할 경우 FALSE입니다. 반환 값이 FALSE 이면 사용 하지 마십시오 탭된 창을 더 이상.

### <a name="remarks"></a>설명

지정 된 창을 제거 하려면이 메서드를 호출 합니다 *pBar* 탭된 창에서 매개 변수입니다.

##  <a name="setautodestroy"></a>  CBaseTabbedPane::SetAutoDestroy

탭된 컨트롤 막대에는 자동으로 소멸 됩니다 있는지 여부를 결정 합니다.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*bAutoDestroy*<br/>
[in] 탭된 창을 동적으로 생성 된 수명이; 제어 하지 않는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

설정 된 자동-소멸 true 모드 탭된 창을 동적으로 만들 경우 및 수명을 제어 하지 않는 경우. 하는 경우 자동 소멸 모드가 TRUE, 탭된 창 프레임 워크에서 자동으로 제거 됩니다.

##  <a name="showtab"></a>  CBaseTabbedPane::ShowTab

표시 하거나 숨깁니다을 탭 합니다.

```
virtual BOOL ShowTab(
    CWnd* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 표시 하거나 숨기려면의 창에 대 한 포인터입니다.

*bShow*<br/>
[in] TRUE; 창을 표시 하려면 창을 숨기려면 FALSE입니다.

*bDelay*<br/>
[in] 탭 레이아웃; 조정 지연 하려면 TRUE 그렇지 않으면 FALSE입니다.

*bActivate*<br/>
[in] 활성 탭; 탭을 확인. 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

탭 표시 또는 숨김 성공적으로 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 하면 창 중 하나 표시 되는지 또는 숨겨지는지를 값에 따라 합니다 *bShow* 매개 변수입니다. 탭을 숨길 수 있고 기본 탭 창의 마지막 표시 탭, 탭된 창이 사라집니다. 하는 경우에 이전에 없는 탭 표시 탭을 표시 하는 경우 탭된 창에 표시 됩니다.

##  <a name="recalclayout"></a>  CBaseTabbedPane::RecalcLayout

창에 대 한 레이아웃 정보를 다시 계산합니다.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>설명

창 부동 창인 경우이 메서드는 미니 프레임의 현재 크기를 창 크기를 조정 하기 위해 프레임 워크를 알립니다.

창이 도킹 되어 있는,이 메서드는 아무 작업도 수행 하지.

##  <a name="setautohidemode"></a>  CBaseTabbedPane::SetAutoHideMode

탭된 창에서 분리 가능한 창에 대 한 자동 숨기기 모드를 설정합니다.

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>매개 변수

*bMode*<br/>
[in] 자동 숨기기 모드를 사용 하도록 설정. 일반 도킹 모드를 사용 하도록 설정 하려면 FALSE입니다.

*dwAlignment*<br/>
[in] 만들어야 하는 자동 숨기기 창의 맞춤을 지정 합니다. 가능한 값 목록을 참조 하세요 [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment)합니다.

*pCurrAutoHideBar*<br/>
[out에서] 현재 자동 숨기기 도구 모음에 대 한 포인터입니다. NULL 일 수 있습니다.

*bUseTimer*<br/>
[in] 사용자가 창 자동 숨기기 모드로 전환할 때 자동 숨기기 효과 사용 하려면 또는 즉시 창을 숨기려면 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

없는 도구 모음을 만드는 경우 자동 숨기기 모드 또는 NULL로 전환할 때 생성 되는 자동 숨기기 도구 모음에 대 한 포인터입니다.

### <a name="remarks"></a>설명

프레임 워크는 사용자가 일반 도킹 모드에 탭된 창 자동 숨기기 모드로 전환할 수 있는 핀 단추를 선택 하는 경우이 메서드를 호출 합니다.

자동 숨기기 모드는 탭된 창에서 분리 가능한 각 창에 대 한 설정 됩니다. 분리 불가능 하 게 연결 된 창 무시 됩니다. 자세한 내용은 [cmfcbasetabctrl:: Enabletabdetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach)합니다.

프로그래밍 방식으로 탭된 창 자동 숨기기 모드로 전환 하려면이 메서드를 호출 합니다. 창 주 프레임 창으로 도킹 해야 합니다 ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) 에 대 한 유효한 포인터를 반환 해야 합니다 [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)
