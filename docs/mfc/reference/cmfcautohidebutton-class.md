---
title: CMFCAutoHideButton 클래스
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
ms.openlocfilehash: 15b449b4b9f9074966ac269787b1b3ca6f977f48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403891"
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton 클래스

숨기도록 구성된 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) 를 표시하거나 숨기는 단추입니다.

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

## <a name="syntax"></a>구문

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCAutoHideButton::BringToTop](#bringtotop)||
|[CMFCAutoHideButton::Create](#create)|자동 숨기기 단추를 만들고 초기화합니다.|
|[CMFCAutoHideButton::GetAlignment](#getalignment)|자동 숨기기 단추의 맞춤을 검색합니다.|
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|반환 된 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 자동 숨기기 단추와 연결 된 개체입니다.|
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton::GetRect](#getrect)||
|[CMFCAutoHideButton::GetSize](#getsize)|자동 숨기기 단추의 크기를 결정합니다.|
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|자동 숨기기 단추에 대한 텍스트 레이블의 크기를 반환합니다.|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|자동 숨기기 단추를 강조 표시합니다.|
|[CMFCAutoHideButton::IsActive](#isactive)|자동 숨기기 단추가 활성 상태인지를 나타냅니다.|
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|자동 숨기기 단추의 강조 표시 상태를 반환합니다.|
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|자동 숨기기 단추가 가로 또는 세로로 표시되는지를 결정합니다.|
|[CMFCAutoHideButton::IsTop](#istop)||
|[CMFCAutoHideButton::IsVisible](#isvisible)|단추의 표시 여부를 나타냅니다.|
|[CMFCAutoHideButton::Move](#move)||
|[CMFCAutoHideButton::OnDraw](#ondraw)|자동 숨기기 단추를 그릴 때 프레임워크에서 이 메서드를 호출합니다.|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|자동 숨기기 단추의 테두리를 그릴 때 프레임워크에서 이 메서드를 호출합니다.|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|자동 숨기기 단추의 배경을 채울 때 프레임워크에서 이 메서드를 호출합니다.|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|표시 하거나 연결 된 숨깁니다 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)합니다.|
|[CMFCAutoHideButton::ShowButton](#showbutton)|자동 숨기기 단추를 표시하거나 숨깁니다.|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>설명

을 만들면 합니다 `CMFCAutoHideButton` 개체가 연결 되는 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md). 사용자가 `CMFCAutoHideButton` 개체를 조작할 때 `CDockablePane` 개체가 숨겨지거나 표시됩니다.

기본적으로 프레임워크에서는 사용자가 자동 숨기기를 설정할 때 자동으로 `CMFCAutoHideButton`을 만듭니다. 프레임워크에서는 `CMFCAutoHideButton` 클래스 대신 사용자 지정 UI 클래스의 요소를 만들 수 있습니다. 프레임워크에서 사용해야 하는 사용자 지정 UI 클래스를 지정하려면 사용자 지정 UI 클래스와 같은 정적 멤버 변수 `CMFCAutoHideBar::m_pAutoHideButtonRTS`를 설정합니다. 기본적으로 이 변수는 `CMFCAutoHideButton`으로 설정됩니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCAutoHideButton` 개체를 생성하고 `CMFCAutoHideButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 예제에서는 `Create` 메서드를 사용하여 `CMFCAutoHideButton` 개체를 초기화하고, 연결된 `CDockablePane` 클래스를 표시하고, 자동 숨기기 단추를 표시하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>요구 사항

**헤더:** afxautohidebutton.h

##  <a name="bringtotop"></a>  CMFCAutoHideButton::BringToTop

```
void BringToTop();
```

### <a name="remarks"></a>설명

##  <a name="create"></a>  CMFCAutoHideButton::Create

만들고 자동 숨기기 단추를 초기화 합니다.

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

*pParentBar*<br/>
[in] 부모 도구 모음에 대 한 포인터입니다.

*pAutoHideWnd*<br/>
[in] 에 대 한 포인터를 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 개체입니다. 이 자동 숨기기 단추에 따르면 숨기고 `CDockablePane`합니다.

*dwAlignment*<br/>
[in] 주 프레임 창을 사용 하 여 단추의 맞춤을 지정 하는 값입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

만들 때를 `CMFCAutoHideButton` 개체를 특정 자동 숨기기 단추에 연결 해야 `CDockablePane`합니다. 사용자 자동 숨기기 단추를 사용 하 여 연결 된 표시 / 숨기기를 수 있습니다 `CDockablePane`합니다.

합니다 *dwAlignment* 자동 숨기기 단추가 응용 프로그램에 있는 매개 변수를 나타냅니다. 이 매개 변수는 다음 값 중 하나가 될 수 있습니다.

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

##  <a name="getalignment"></a>  CMFCAutoHideButton::GetAlignment

자동 숨기기 단추의 맞춤을 검색합니다.

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>반환 값

현재 자동 숨기기 단추의 맞춤을 포함 하는 DWORD 값입니다.

### <a name="remarks"></a>설명

자동 숨기기 단추의 맞춤을 응용 프로그램에 있는 단추를 나타냅니다. 다음 값 중 하나일 수 있습니다.

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

##  <a name="getautohidewindow"></a>  CMFCAutoHideButton::GetAutoHideWindow

반환 된 [CDockablePane](../../mfc/reference/cdockablepane-class.md) 자동 숨기기 단추와 연결 된 개체입니다.

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>반환 값

연결에 대 한 포인터 `CDockablePane` 개체입니다.

### <a name="remarks"></a>설명

자동 숨기기 단추를 사용 하 여 연결 하는 `CDockablePane`, 전달 합니다 `CDockablePane` 매개 변수로 [CMFCAutoHideButton::Create](#create) 메서드.

##  <a name="getparenttoolbar"></a>  CMFCAutoHideButton::GetParentToolBar

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getrect"></a>  CMFCAutoHideButton::GetRect

```
CRect GetRect() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getsize"></a>  CMFCAutoHideButton::GetSize

자동 숨기기 단추의 크기를 결정합니다.

```
CSize GetSize() const;
```

### <a name="return-value"></a>반환 값

`CSize` 단추 크기를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

계산 된 크기는 자동 숨기기 단추의 테두리의 크기를 포함 합니다.

##  <a name="gettextsize"></a>  CMFCAutoHideButton::GetTextSize

자동 숨기기 단추에 대한 텍스트 레이블의 크기를 반환합니다.

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>반환 값

A [CSize](../../atl-mfc-shared/reference/csize-class.md) 자동 숨기기 단추에 대 한 텍스트의 크기를 포함 하는 개체입니다.

##  <a name="isactive"></a>  CMFCAutoHideButton::IsActive

자동 숨기기 단추가 활성 상태인지를 나타냅니다.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>반환 값

자동 숨기기 단추가 활성 상태 이면 TRUE FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

자동 숨기기 단추는 활성 연결 된 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md) 창이 표시 됩니다.

##  <a name="ishorizontal"></a>  CMFCAutoHideButton::IsHorizontal

자동 숨기기 단추가 가로 또는 세로로 표시되는지를 결정합니다.

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>반환 값

단추가 있는 가로; 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

방향으로 설정 하는 프레임 워크를 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) 만들 때 개체입니다.  사용 하 여 방향을 제어할 수 있습니다는 *dwAlignment* 에 매개 변수를 [CMFCAutoHideButton::Create](#create) 메서드.

##  <a name="istop"></a>  CMFCAutoHideButton::IsTop

```
BOOL IsTop() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isvisible"></a>  CMFCAutoHideButton::IsVisible

자동 숨기기 단추가 표시 되는지 여부를 나타냅니다.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>반환 값

단추가 표시 되 면 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="ondraw"></a>  CMFCAutoHideButton::OnDraw

자동 숨기기 단추를 그릴 때 프레임워크에서 이 메서드를 호출합니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 자동 숨기기 단추의 모양을 사용자 지정 하려는 경우에서 파생 된 새 클래스를 만듭니다 `CMFCAutoHideButton`합니다. 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="ondrawborder"></a>  CMFCAutoHideButton::OnDrawBorder

자동 숨기기 단추의 테두리를 그릴 때 프레임워크에서 이 메서드를 호출합니다.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rectBounds*<br/>
[in] 자동 숨기기 단추의 경계 사각형입니다.

*rectBorderSize*<br/>
[in] 자동 숨기기 단추의 각 측에 대 한 테두리 두께입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 각 자동 숨기기 단추의 테두리를 사용자 지정 하려는 경우 만드는 새 클래스에서 파생 된 `CMFCAutoHideButton`합니다. 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="onfillbackground"></a>  CMFCAutoHideButton::OnFillBackground

자동 숨기기 단추의 배경을 채울 때 프레임워크에서 이 메서드를 호출합니다.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 자동 숨기기 단추의 경계 사각형입니다.

### <a name="remarks"></a>설명

응용 프로그램에서 자동 숨기기 단추의 배경을 사용자 지정 하려는 경우에서 파생 된 새 클래스를 만듭니다는 `CMFCAutoHideButton`합니다. 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="showattachedwindow"></a>  CMFCAutoHideButton::ShowAttachedWindow

표시 하거나 연결 된 숨깁니다 [CDockablePane 클래스](../../mfc/reference/cdockablepane-class.md)합니다.

```
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
[in] 이 메서드는 연결 된 표시 되는지 여부를 지정 하는 부울 `CDockablePane`합니다.

##  <a name="showbutton"></a>  CMFCAutoHideButton::ShowButton

자동 숨기기 단추를 표시하거나 숨깁니다.

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
[in] 자동 숨기기 단추를 표시할지 여부를 지정 하는 부울입니다.

##  <a name="move"></a>  CMFCAutoHideButton::Move

```
void Move(int nOffset);
```

### <a name="parameters"></a>매개 변수

[in] *nOffset*<br/>

### <a name="remarks"></a>설명

##  <a name="replacepane"></a>  CMFCAutoHideButton::ReplacePane

```
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>매개 변수

[in] *pNewBar*<br/>

### <a name="remarks"></a>설명

##  <a name="unsetautohidemode"></a>  CMFCAutoHideButton::UnSetAutoHideMode

자동 숨기기 모드를 사용하지 않도록 설정합니다.

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>매개 변수

*pFirstBarInGroup*<br/>
[in] 그룹의 첫 번째 막대에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="highlightbutton"></a>  CMFCAutoHideButton::HighlightButton

자동 숨기기 단추를 강조 표시합니다.

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>매개 변수

*bHighlight*<br/>
새 자동 숨기기 단추 상태를 지정 합니다. TRUE는 단추가 강조 표시를 나타내는 FALSE로 단추를 강조 표시 되지 않습니다.

### <a name="remarks"></a>설명

##  <a name="ishighlighted"></a>  CMFCAutoHideButton::IsHighlighted

자동 숨기기 단추의 강조 표시 상태를 반환합니다.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>반환 값

자동 숨기기 단추 있으면 TRUE를 반환 강조 표시 됩니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar 클래스](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[CAutoHideDockSite 클래스](../../mfc/reference/cautohidedocksite-class.md)
