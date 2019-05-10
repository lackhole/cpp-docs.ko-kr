---
title: CMFCStatusBar 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
ms.openlocfilehash: 87f75769e2f400a7721a8c9089d6c5596c31a4e3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388369"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar 클래스

합니다 `CMFCStatusBar` 유사한 상태 표시줄을 구현 하는 클래스는 `CStatusBar` 클래스입니다. 그러나 `CMFCStatusBar` 클래스에는 `CStatusBar` 클래스에 의해 제공되지 않는 기능(예: 이미지, 애니메이션 및 진행률 표시줄을 표시하는 기능 및 마우스 두 번 클릭에 응답하는 기능)이 포함되어 있습니다.

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

## <a name="syntax"></a>구문

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(재정의 [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCStatusBar::CommandToIndex](#commandtoindex)||
|[CMFCStatusBar::Create](#create)|컨트롤 막대를 만들고에 연결 합니다 [CPane](../../mfc/reference/cpane-class.md) 개체입니다. (재정의 [cpane:: Create](../../mfc/reference/cpane-class.md#create).)|
|[CMFCStatusBar::CreateEx](#createex)|컨트롤 막대를 만들고에 연결 합니다 [CPane](../../mfc/reference/cpane-class.md) 개체입니다. (재정의 [cpane:: Createex](../../mfc/reference/cpane-class.md#createex).)|
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|이 창에서 상위 프레임 사이의 다른 창을 동적으로 삽입할 수 있는지 여부를 결정 합니다. (재정의 [cbasepane:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|사용 가능 / 불가능 마우스의 처리 상태 표시줄에 두 번 클릭 합니다.|
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|지정 된 창에서 진행률 표시줄을 표시 합니다.|
|[CMFCStatusBar::GetCount](#getcount)|상태 표시줄에 창 수를 반환합니다.|
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCStatusBar::GetItemID](#getitemid)||
|[CMFCStatusBar::GetItemRect](#getitemrect)||
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|창 스타일을 반환합니다. (재정의 [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|
|[CMFCStatusBar::GetPaneText](#getpanetext)||
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|상태 표시줄의 지정 된 창의 픽셀 너비를 반환합니다.|
|[CMFCStatusBar::GetTipText](#gettiptext)|상태 표시줄의 지정 된 창에 대 한 도구 설명 텍스트를 반환합니다.|
|[CMFCStatusBar::InvalidatePaneContent](#invalidatepanecontent)|지정한 창을 무효화 하 고 해당 콘텐츠를 다시 그립니다.|
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|이 연결 된 Windows 창을 만들기 전에 프레임 워크에서 호출 `CWnd` 개체입니다. (재정의 [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar::SetIndicators](#setindicators)||
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|지정 된 창에 애니메이션을 할당합니다.|
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|지정 된 창의 상태 표시줄의 배경색을 설정 합니다.|
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|상태 표시줄의 지정 된 창에 대 한 표시기 아이콘을 설정합니다.|
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|상태 표시줄의 지정 된 창에 대 한 진행률 표시줄의 현재 진행률을 설정합니다.|
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|창 스타일을입니다. (재정의 [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|
|[CMFCStatusBar::SetPaneText](#setpanetext)||
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|지정 된 창의 상태 표시줄의 텍스트 색을 설정합니다.|
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|상태 표시줄의 지정 된 창의 픽셀 너비를 설정합니다.|
|[CMFCStatusBar::SetTipText](#settiptext)|상태 표시줄의 지정 된 창에 대 한 도구 설명 텍스트를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|상태 표시줄의 창을 다시 그립니다 때 프레임 워크에서 호출 됩니다.|

## <a name="remarks"></a>설명

다음 다이어그램에서 상태 표시줄의 그림을 보여 줍니다 [상태 표시줄 데모 샘플](../../overview/visual-cpp-samples.md) 응용 프로그램입니다.

![CMFCStatusBar의 예제](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar의 예제")

## <a name="example"></a>예제

다음 예제에서는 응용 프로그램의 다양 한 메서드를 호출 하는 데 사용 하는 지역 변수는 `CMFCStatusBar` 클래스입니다. 이러한 변수는 StatusBarDemoView.h에서 선언 됩니다. 주 프레임 MainFrm.h에 선언 된, StatusBarDemoDoc.h에서 선언 된 문서 및 뷰 StatusBarDemoView.h에서 선언 됩니다. 이 코드 조각은의 일부인 합니다 [상태 표시줄 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

## <a name="example"></a>예제

다음 예제에는에 대 한 참조를 가져오는 방법을 보여 줍니다 `CMFCStatusBar` 도입 하 여 개체를 `GetStatusBar` MainFrm.h 및에서이 메서드를 호출 하는 메서드는 `GetStatusBar` StatusBarDemoView.h에서 메서드. 이 코드 조각은의 일부인 합니다 [상태 표시줄 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

## <a name="example"></a>예제

다음 예제에서는 다양 한 메서드를 호출 하는 방법에 설명 합니다 `CMFCStatusBar` StatusBarDemoView.cpp 클래스입니다. 상수는 MainFrm.h에서 선언 됩니다. 예제는 아이콘 설정, 상태 표시줄 창의 도구 설명 텍스트를 설정, 지정 된 창에서 진행률 표시줄이 표시 됩니다, 지정한 창에 애니메이션을 할당, 텍스트 및 상태 표시줄 창의 너비를 설정 및는 프로 그의 현재 진행률 표시기를 설정 하는 방법을 보여 줍니다. ess 막대 상태 표시줄 창입니다. 이 코드 조각은의 일부인 합니다 [상태 표시줄 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxstatusbar.h

##  <a name="calcfixedlayout"></a>  CMFCStatusBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

[in] *bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="commandtoindex"></a>  CMFCStatusBar::CommandToIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>매개 변수

[in] *nIDFind*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="create"></a>  CMFCStatusBar::Create

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>매개 변수

[in] *pParentWnd*<br/>
[in] *dwStyle*<br/>
[in] *nID*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="createex"></a>  CMFCStatusBar::CreateEx

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>매개 변수

[in] *pParentWnd*<br/>
[in] *dwCtrlStyle*<br/>
[in] *dwStyle*<br/>
[in] *nID*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="doesallowdyninsertbefore"></a>  CMFCStatusBar::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="enablepanedoubleclick"></a>  CMFCStatusBar::EnablePaneDoubleClick

사용 가능 / 불가능 마우스의 처리 상태 표시줄에 두 번 클릭 합니다.

```
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] TRUE 이면 마우스 두 번 클릭을 처리 하는 사용 하도록 설정 합니다. 그렇지 않으면 마우스 두 번 클릭을 처리 함

### <a name="remarks"></a>설명

상태 표시줄을 두 번 클릭을 처리 하는 데 사용 하는 경우 Windows 상태 표시줄 상태 표시줄 창에 사용자가 두 번 클릭할 때마다의 소유자를 리소스 ID와 함께 WM_COMMAND 알림을 보냅니다.

##  <a name="enablepaneprogressbar"></a>  CMFCStatusBar::EnablePaneProgressBar

지정 된 창에서 진행률 표시줄을 표시 합니다.

```
void EnablePaneProgressBar(
    int nIndex,
    long nTotal=100,
    BOOL bDisplayText=FALSE,
    COLORREF clrBar=-1,
    COLORREF clrBarDest=-1,
    COLORREF clrProgressText=-1);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 사용 하도록 설정 하려면 해당 진행률 표시줄 창의 인덱스를 지정 합니다.

*nTotal*<br/>
[in] 진행률 표시줄에 대 한 최대값을 지정 합니다.

*bDisplayText*<br/>
[in] 진행률 표시줄의 현재 진행률 값을 표시할 것인지 여부를 지정 합니다.

*clrBar*<br/>
[in] 진행률 표시줄의 배경색을 지정 합니다.

*clrBarDest*<br/>
[in] 진행률 표시줄 배경의 보조 색을 지정합니다. 다른 값을 사용 하 여 *clrBar* 색 그라데이션에 혼합 하 여 작성 하려면.

*clrProgressText*<br/>
[in] 진행률 표시줄의 텍스트 색을 지정합니다.

### <a name="remarks"></a>설명

진행률 표시줄 호출을 사용 하지 않도록 설정 하려는 경우 `EnablePaneProgressBar` 사용 하 여 *nTotal* -1로 설정 합니다. 기본적으로 *nTotal* 100으로 설정 됩니다. 따라서 백분율로 진행률을 표시 하려면 모든 추가 계산 필요 하지 않습니다.

에 대 한 다른 값을 전달 해야 *clrBar* 하 고 *clrBarDest* 진행률 표시줄의 배경색에 색 그라데이션에 혼합을 표시 되도록 합니다. .

현재 진행 상태를 설정 하려면 호출을 [CMFCStatusBar::SetPaneProgress](#setpaneprogress) 메서드.

##  <a name="getcount"></a>  CMFCStatusBar::GetCount

상태 표시줄에는 창 수를 검색합니다.

```
int GetCount() const;
```

### <a name="return-value"></a>반환 값

상태 표시줄에서 창이 횟수입니다.

##  <a name="getdrawextendedarea"></a>  CMFCStatusBar::GetDrawExtendedArea

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getextendedarea"></a>  CMFCStatusBar::GetExtendedArea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getitemid"></a>  CMFCStatusBar::GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getitemrect"></a>  CMFCStatusBar::GetItemRect

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>
[in] *lpRect*<br/>

### <a name="remarks"></a>설명

##  <a name="getpaneinfo"></a>  CMFCStatusBar::GetPaneInfo

```
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>
[in] *nID*<br/>
[in] *nStyle*<br/>
[in] *cxWidth*<br/>

### <a name="remarks"></a>설명

##  <a name="getpaneprogress"></a>  CMFCStatusBar::GetPaneProgress

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getpanestyle"></a>  CMFCStatusBar::GetPaneStyle

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getpanetext"></a>  CMFCStatusBar::GetPaneText

```
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>
[in] *s*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getpanewidth"></a>  CMFCStatusBar::GetPaneWidth

상태 표시줄의 창 너비를 검색합니다.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 상태 표시줄 창의 인덱스를 지정 합니다.

### <a name="return-value"></a>반환 값

상태 표시줄 창의 너비입니다 *nIndex* 지정, 그렇지 않으면 0 없으면 상태 표시줄 창입니다.

##  <a name="gettiptext"></a>  CMFCStatusBar::GetTipText

상태 표시줄의 창 도구 설명 텍스트를 검색 합니다.

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 창에 도구 설명 텍스트를 검색 하려는 인덱스를 지정 합니다.

### <a name="return-value"></a>반환 값

상태 표시줄 창의 도구 설명 텍스트는 *nIndex* 지정 합니다. 지정 된 상태 표시줄 창을 없으면 빈 문자열 하는 고, 그렇지 *nIndex* 이거나 해당 도구 설명 텍스트 비어 있습니다.

##  <a name="invalidatepanecontent"></a>  CMFCStatusBar::InvalidatePaneContent

상태 표시줄 창을 무효화 하 고 해당 콘텐츠를 다시 그리도록 합니다.

```
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 창의 내용이 무효화 하 고 다시 그릴 방법은 인덱스를 지정 합니다.

### <a name="remarks"></a>설명

상태 표시줄 무효화 될 때 다시 그리기에 대 한 표시 됩니다. Windows 그립니다 때 합니다 `UpdateWindow` 메서드 WM_PAINT 메시지를 보냅니다는 `OnPaint` 메서드.

##  <a name="ondrawpane"></a>  CMFCStatusBar::OnDrawPane

상태 표시줄의 창을 다시 그립니다.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 그리기에 대 한 장치 컨텍스트 포인터입니다.

*pPane*<br/>
[in] 에 대 한 포인터를 `CMFCStatusBarPaneInfo` 그려야 하는 창에 대 한 정보를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

기본적으로 `OnDrawPane` 창의 장치 컨텍스트를 사용 하 여 다시 그리면 *pDC* 의 창 스타일 및 내용에 따라 합니다.

이 메서드를 재정의 한 `CMFCStatusBar`-창의 모양을 사용자 지정 하는 클래스를 파생 합니다.

##  <a name="precreatewindow"></a>  CMFCStatusBar::PreCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>매개 변수

[in] *cs*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="setdrawextendedarea"></a>  CMFCStatusBar::SetDrawExtendedArea

```
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>매개 변수

[in] *bSet*<br/>

### <a name="remarks"></a>설명

##  <a name="setindicators"></a>  CMFCStatusBar::SetIndicators

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>매개 변수

[in] *lpIDArray*<br/>
[in] *nIDCount*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="setpaneanimation"></a>  CMFCStatusBar::SetPaneAnimation

지정 된 창에 애니메이션을 할당합니다.

```
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 창 애니메이션을 할당 하려는 인덱스를 지정 합니다.

*hImageList*<br/>
[in] 애니메이션 프레임을 포함 하는 이미지 목록에 대 한 핸들을 지정 합니다.

*nFrameRate*<br/>
[in] 애니메이션에 대 한 밀리초 프레임 속도 지정합니다.

*bUpdate*<br/>
[in] TRUE 이면 즉시 창 콘텐츠를 업데이트 합니다. 그렇지 않은 경우 창 콘텐츠 무효화 될 때 업데이트 됩니다.

### <a name="remarks"></a>설명

현재 애니메이션을 사용 하지 않도록 설정 하려는 경우 호출할 `SetPaneAnimation` 사용 하 여 `hImageList` NULL로 설정 합니다.

##  <a name="setpanebackgroundcolor"></a>  CMFCStatusBar::SetPaneBackgroundColor

상태 표시줄 창의 배경색을 설정 합니다.

```
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 창에 새 배경색을 설정 하는 인덱스를 지정 합니다.

*clrBackground*<br/>
[in] 새 배경색을 지정합니다.

*bUpdate*<br/>
[in] TRUE 이면 즉시 창 콘텐츠를 업데이트 합니다. 그렇지 않으면 창의 다른 메서드에 의해 무효화 될 때까지 창 콘텐츠를 업데이트 하지 마십시오.

##  <a name="setpaneicon"></a>  CMFCStatusBar::SetPaneIcon

상태 표시줄 창의 아이콘을 설정 합니다.

```
void SetPaneIcon(
    int nIndex,
    HICON hIcon,
    BOOL bUpdate=TRUE);

void SetPaneIcon(
    int nIndex,
    HBITMAP hBmp,
    COLORREF clrTransparent=RGB(255, 0, 255),
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 창에 이미지를 설정 하는 인덱스를 지정 합니다.

*hIcon*<br/>
[in] 창 이미지로 설정할 아이콘에 대 한 핸들을 지정 합니다.

*bUpdate*<br/>
[in] 창 콘텐츠를 즉시 업데이트할 것인지 지정 합니다.

*hBmp*<br/>
[in] 창 이미지로 설정할 비트맵에 대 한 핸들을 지정 합니다.

*clrTransparent*<br/>
[in] 비트맵의 투명 한 색을 지정 하는 *hBmp* 나타냅니다.

### <a name="remarks"></a>설명

투명 한 색을 창의 이미지를 설정 하려면 함께 HICON 또는 HBITMAP를 전달할 수 있습니다. 이미지를 더 이상 표시 하지 않을 경우 이미지 핸들을 NULL 값을 전달 합니다.

모든 실행 중인 애니메이션이 없는 경우는 [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) 에 설정 하 고, 애니메이션 중지 됩니다.

##  <a name="setpaneinfo"></a>  CMFCStatusBar::SetPaneInfo

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>
[in] *nID*<br/>
[in] *nStyle*<br/>
[in] *cxWidth*<br/>

### <a name="remarks"></a>설명

##  <a name="setpaneprogress"></a>  CMFCStatusBar::SetPaneProgress

지정한 창에 진행률 표시줄의 현재 진행률 표시기를 설정 합니다.

```
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 창에 진행률 표시기를 업데이트 하는 인덱스를 지정 합니다.

*nCurr*<br/>
[in] 진행률 표시기의 현재 값을 지정합니다.

*bUpdate*<br/>
[in] 창에 즉시 업데이트 해야 하는지 여부를 지정 합니다.

### <a name="remarks"></a>설명

지정 된 창에서 진행률 표시줄의 진행률 표시기를 업데이트 하려는 경우이 메서드를 호출 합니다.

지정 된 창에 대 한이 함수를 사용 하려면 [CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar) 첫 번째입니다.

##  <a name="setpanestyle"></a>  CMFCStatusBar::SetPaneStyle

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>
[in] *nStyle*<br/>

### <a name="remarks"></a>설명

##  <a name="setpanetext"></a>  CMFCStatusBar::SetPaneText

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>매개 변수

[in] *nIndex*<br/>
[in] *lpszNewText*<br/>
[in] *bUpdate*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="setpanetextcolor"></a>  CMFCStatusBar::SetPaneTextColor

지정 된 창의 텍스트 색을 설정 합니다.

```
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 새 텍스트 색을 할당 하려는 창의 인덱스를 지정 합니다.

*clrText*<br/>
[in] 텍스트 색을 지정 합니다.

*bUpdate*<br/>
[in] TRUE 이면 즉시 창 콘텐츠를 업데이트 합니다. 그렇지 않으면 창의 다른 메서드에 의해 무효화 될 때까지 창 콘텐츠를 업데이트 하지 마십시오.

##  <a name="setpanewidth"></a>  CMFCStatusBar::SetPaneWidth

상태 표시줄 창의 너비를 설정 합니다.

```
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 상태 표시줄 창의 새 너비를 설정할 인덱스입니다.

*cx*<br/>
[in] 픽셀에서 상태 표시줄 창의 새 너비입니다.

##  <a name="settiptext"></a>  CMFCStatusBar::SetTipText

상태 표시줄 창의 도구 설명 텍스트를 설정 합니다.

```
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
[in] 창의 도구 설명 텍스트를 할당 하려는 인덱스입니다.

*pszTipText*<br/>
[in] 새 도구 설명 텍스트입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)<br/>
[CStatusBar 클래스](../../mfc/reference/cstatusbar-class.md)
