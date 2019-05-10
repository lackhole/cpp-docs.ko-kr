---
title: CMFCDropDownToolBar 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
ms.openlocfilehash: f2c4135d2a27928dbde4299fa1f8eda42237d893
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238073"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar 클래스

사용자가 최상위 도구 모음 단추를 누르고 있을 때 나타나는 도구 모음입니다.

   더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.
## <a name="syntax"></a>구문

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|( `CPane::AllowShowOnPaneMenu`을 재정의합니다.)|
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(재정의 [CMFCToolBar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(재정의 [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar).)|
|[CMFCDropDownToolBar::OnLButtonUp](#onlbuttonup)||
|[CMFCDropDownToolBar::OnMouseMove](#onmousemove)||
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|( `CMFCToolBar::OnSendCommand`을 재정의합니다.)|
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(재정의 [CMFCToolBar::OnUpdateCmdUI](cmfctoolbar-class.md)합니다.|

### <a name="remarks"></a>설명

`CMFCDropDownToolBar` 팝업 메뉴의 동작을 사용 하 여 도구 모음의 시각적 모양을 결합 하는 개체입니다. 때 사용자를 누르고 드롭다운 도구 모음 단추 (참조 [CMFCDropDownToolbarButton 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), 드롭다운 도구 모음이 나타나고 사용자에 스크롤 및 마우스를 해제 하 여 드롭다운 도구 모음에서 단추에 선택할 수 단추입니다. 사용자가 드롭다운 도구 모음에서 단추를 선택, 최상위 도구 모음에서 현재 단추와 해당 단추가 표시 됩니다.

드롭다운 도구 모음 사용자 지정 하거나 창을 도킹 하면 없습니다 및 분리 상태 없습니다.

다음 그림에 표시 된 `CMFCDropDownToolBar` 개체:

![CMFCDropDownToolbar의 예제](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDownToolbar의 예제")

만든를 `CMFCDropDownToolBar` 는 일반 도구 모음을 만든 동일한 방식으로 개체 (참조 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)).

드롭다운 도구 모음에 부모 도구 모음 삽입할:

1. 부모 도구 모음 리소스의 단추에 대한 더미 리소스 ID를 예약합니다.

2. 만들기는 `CMFCDropDownToolBarButton` 드롭다운 도구 모음을 포함 하는 개체 (자세한 내용은 참조 하십시오 [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).

3. 사용 하 여 더미 단추 바꾸기 합니다 `CMFCDropDownToolBarButton` 개체를 사용 하 여 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)합니다.

도구 모음 단추에 대 한 자세한 내용은 참조 하세요. [연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)합니다. 드롭다운 도구 모음의 예로, VisualStudioDemo 샘플 프로젝트를 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `Create` 의 메서드는 `CMFCDropDownToolBar` 클래스입니다. 이 코드 조각은의 일부인 합니다 [Visual Studio 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdropdowntoolbar.h

##  <a name="allowshowonpanemenu"></a>  CMFCDropDownToolBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="loadbitmap"></a>  CMFCDropDownToolBar::LoadBitmap

애플리케이션 리소스에서 도구 모음 이미지를 로드합니다.

```
virtual BOOL LoadBitmap(
    UINT uiResID,
    UINT uiColdResID=0,
    UINT uiMenuResID=0,
    BOOL bLocked=FALSE,
    UINT uiDisabledResID=0,
    UINT uiMenuDisabledResID=0);
```

### <a name="parameters"></a>매개 변수

*uiResID*<br/>
[in] 핫 도구 모음 이미지를 참조 하는 비트맵의 리소스 ID입니다.

*uiColdResID*<br/>
[in] 콜드 도구 모음 이미지를 참조 하는 비트맵의 리소스 ID입니다.

*uiMenuResID*<br/>
[in] 일반 메뉴 이미지를 참조 하는 비트맵의 리소스 ID입니다.

*bLocked*<br/>
[in] 도구 모음을 잠그려면 그렇지 않으면 FALSE입니다.

*uiDisabledResID*<br/>
[in] 비활성화 된 도구 모음 이미지를 참조 하는 비트맵의 리소스 ID입니다.

*uiMenuDisabledResID*<br/>
[in] 비활성화 된 메뉴 이미지를 참조 하는 비트맵의 리소스 ID입니다.

### <a name="return-value"></a>반환 값

메서드가 성공하면 0이 아니고, 실패하면 0입니다.

### <a name="remarks"></a>설명

[CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) 메서드는 이 메서드를 호출하여 도구 모음과 관련된 이미지를 로드합니다. 이미지 리소스의 사용자 지정 로드를 수행하려면 이 메서드를 재정의합니다.

`LoadBitmapEx` 메서드를 호출하여 도구 모음을 만든 후 추가 이미지를 로드합니다.

##  <a name="loadtoolbar"></a>  CMFCDropDownToolBar::LoadToolBar

```
virtual BOOL LoadToolBar(
    UINT uiResID,
    UINT uiColdResID = 0,
    UINT uiMenuResID = 0,
    BOOL = FALSE,
    UINT uiDisabledResID = 0,
    UINT uiMenuDisabledResID = 0,
    UINT uiHotResID = 0);
```

### <a name="parameters"></a>매개 변수

[in] *uiResID*<br/>

[in] *uiColdResID*<br/>

[in] *uiMenuResID*<br/>

[in] *BOOL*<br/>

[in] *uiDisabledResID*<br/>

[in] *uiMenuDisabledResID*<br/>

[in] *uiHotResID*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="onlbuttonup"></a>  CMFCDropDownToolBar::OnLButtonUp

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

[in] *nFlags*<br/>

[in] *point*<br/>

### <a name="remarks"></a>설명

##  <a name="onmousemove"></a>  CMFCDropDownToolBar::OnMouseMove

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>매개 변수

[in] *nFlags*<br/>

[in] *point*<br/>

### <a name="remarks"></a>설명

##  <a name="onsendcommand"></a>  CMFCDropDownToolBar::OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>매개 변수

[in] *pButton*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="onupdatecmdui"></a>  CMFCDropDownToolBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>매개 변수

[in] *pTarget*<br/>

[in] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CMFCDropDownToolbarButton 클래스](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
