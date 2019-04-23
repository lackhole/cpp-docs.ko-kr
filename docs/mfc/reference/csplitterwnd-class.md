---
title: CSplitterWnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CSplitterWnd
- AFXEXT/CSplitterWnd
- AFXEXT/CSplitterWnd::CSplitterWnd
- AFXEXT/CSplitterWnd::ActivateNext
- AFXEXT/CSplitterWnd::CanActivateNext
- AFXEXT/CSplitterWnd::Create
- AFXEXT/CSplitterWnd::CreateScrollBarCtrl
- AFXEXT/CSplitterWnd::CreateStatic
- AFXEXT/CSplitterWnd::CreateView
- AFXEXT/CSplitterWnd::DeleteColumn
- AFXEXT/CSplitterWnd::DeleteRow
- AFXEXT/CSplitterWnd::DeleteView
- AFXEXT/CSplitterWnd::DoKeyboardSplit
- AFXEXT/CSplitterWnd::DoScroll
- AFXEXT/CSplitterWnd::DoScrollBy
- AFXEXT/CSplitterWnd::GetActivePane
- AFXEXT/CSplitterWnd::GetColumnCount
- AFXEXT/CSplitterWnd::GetColumnInfo
- AFXEXT/CSplitterWnd::GetPane
- AFXEXT/CSplitterWnd::GetRowCount
- AFXEXT/CSplitterWnd::GetRowInfo
- AFXEXT/CSplitterWnd::GetScrollStyle
- AFXEXT/CSplitterWnd::IdFromRowCol
- AFXEXT/CSplitterWnd::IsChildPane
- AFXEXT/CSplitterWnd::IsTracking
- AFXEXT/CSplitterWnd::RecalcLayout
- AFXEXT/CSplitterWnd::SetActivePane
- AFXEXT/CSplitterWnd::SetColumnInfo
- AFXEXT/CSplitterWnd::SetRowInfo
- AFXEXT/CSplitterWnd::SetScrollStyle
- AFXEXT/CSplitterWnd::SplitColumn
- AFXEXT/CSplitterWnd::SplitRow
- AFXEXT/CSplitterWnd::OnDraw
- AFXEXT/CSplitterWnd::OnDrawSplitter
- AFXEXT/CSplitterWnd::OnInvertTracker
helpviewer_keywords:
- CSplitterWnd [MFC], CSplitterWnd
- CSplitterWnd [MFC], ActivateNext
- CSplitterWnd [MFC], CanActivateNext
- CSplitterWnd [MFC], Create
- CSplitterWnd [MFC], CreateScrollBarCtrl
- CSplitterWnd [MFC], CreateStatic
- CSplitterWnd [MFC], CreateView
- CSplitterWnd [MFC], DeleteColumn
- CSplitterWnd [MFC], DeleteRow
- CSplitterWnd [MFC], DeleteView
- CSplitterWnd [MFC], DoKeyboardSplit
- CSplitterWnd [MFC], DoScroll
- CSplitterWnd [MFC], DoScrollBy
- CSplitterWnd [MFC], GetActivePane
- CSplitterWnd [MFC], GetColumnCount
- CSplitterWnd [MFC], GetColumnInfo
- CSplitterWnd [MFC], GetPane
- CSplitterWnd [MFC], GetRowCount
- CSplitterWnd [MFC], GetRowInfo
- CSplitterWnd [MFC], GetScrollStyle
- CSplitterWnd [MFC], IdFromRowCol
- CSplitterWnd [MFC], IsChildPane
- CSplitterWnd [MFC], IsTracking
- CSplitterWnd [MFC], RecalcLayout
- CSplitterWnd [MFC], SetActivePane
- CSplitterWnd [MFC], SetColumnInfo
- CSplitterWnd [MFC], SetRowInfo
- CSplitterWnd [MFC], SetScrollStyle
- CSplitterWnd [MFC], SplitColumn
- CSplitterWnd [MFC], SplitRow
- CSplitterWnd [MFC], OnDraw
- CSplitterWnd [MFC], OnDrawSplitter
- CSplitterWnd [MFC], OnInvertTracker
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
ms.openlocfilehash: 065735c13a3e763208142eb6bc989d3a496221f0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781447"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd 클래스

여러 개의 창이 포함된 창인 분할자 창 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CSplitterWnd : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|생성 하는 호출을 `CSplitterWnd` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSplitterWnd::ActivateNext](#activatenext)|다음 창] 또는 [이전 창 명령을 수행합니다.|
|[CSplitterWnd::CanActivateNext](#canactivatenext)|다음 창] 또는 [이전 창 명령을 현재 사용할 수 있는지 확인 합니다.|
|[CSplitterWnd::Create](#create)|동적 분할 창을 만들고에 연결 하는 호출 된 `CSplitterWnd` 개체입니다.|
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|공유 scroll bar 컨트롤을 만듭니다.|
|[CSplitterWnd::CreateStatic](#createstatic)|정적 분할 창은 만들고 연결 하는 호출 된 `CSplitterWnd` 개체입니다.|
|[CSplitterWnd::CreateView](#createview)|분할기 창에서 창을 만드는 호출 합니다.|
|[CSplitterWnd::DeleteColumn](#deletecolumn)|분할기 창에서 열을 삭제합니다.|
|[CSplitterWnd::DeleteRow](#deleterow)|분할기 창에서 행을 삭제 합니다.|
|[CSplitterWnd::DeleteView](#deleteview)|분할기 창에서 뷰를 삭제합니다.|
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|키보드 분할 명령을, 일반적으로 "창 분할 합니다."를 수행 합니다.|
|[CSplitterWnd::DoScroll](#doscroll)|분할 창을 동기화 스크롤을 수행 합니다.|
|[CSplitterWnd::DoScrollBy](#doscrollby)|픽셀의 지정 된 수 만큼 분할 창을 스크롤합니다.|
|[CSplitterWnd::GetActivePane](#getactivepane)|포커스 또는 활성 보기 프레임에서 활성 창을 결정합니다.|
|[CSplitterWnd::GetColumnCount](#getcolumncount)|현재 창을 열 수를 반환합니다.|
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|지정한 열에 정보를 반환합니다.|
|[CSplitterWnd::GetPane](#getpane)|지정 된 행과 열에 있는 창을 반환합니다.|
|[CSplitterWnd::GetRowCount](#getrowcount)|현재 창 행 개수를 반환합니다.|
|[CSplitterWnd::GetRowInfo](#getrowinfo)|지정된 된 행에 정보를 반환합니다.|
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|공유 스크롤 막대 스타일을 반환합니다.|
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|자식 창의 지정 된 행과 열에 있는 창 ID를 반환합니다.|
|[CSplitterWnd::IsChildPane](#ischildpane)|현재 창이 분할자 창의 자식 창 되는지 확인 하려면 호출 합니다.|
|[CSplitterWnd::IsTracking](#istracking)|분할 막대는 현재 이동 중인 경우를 결정 합니다.|
|[CSplitterWnd::RecalcLayout](#recalclayout)|분할기 창 행 또는 열 크기를 조정한 후 다시 표시 하기 위해 호출 합니다.|
|[CSplitterWnd::SetActivePane](#setactivepane)|현재 있는 프레임 창을 설정 합니다.|
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|지정 된 열 정보를 설정 하려면 호출 합니다.|
|[CSplitterWnd::SetRowInfo](#setrowinfo)|지정 된 행 정보를 설정 하려면 호출 합니다.|
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|분할기 창에 대 한 새 스크롤 막대 스타일 스크롤 막대 지원 공유를 지정 합니다.|
|[CSplitterWnd::SplitColumn](#splitcolumn)|프레임 창이 세로로 분할 하는 지점을 나타냅니다.|
|[CSplitterWnd::SplitRow](#splitrow)|프레임 창이 가로로 분할 하는 지점을 나타냅니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CSplitterWnd::OnDraw](#ondraw)|분할기 창 그리기 위해 프레임 워크에서 호출 됩니다.|
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|분할 창의 이미지를 렌더링합니다.|
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|동일한 크기 및 모양을 프레임 창으로 분할 창의 이미지를 렌더링 합니다.|

## <a name="remarks"></a>설명

창에서 파생 된 응용 프로그램 관련 개체는 일반적으로 [CView](../../mfc/reference/cview-class.md), 모든 수 있지만 [CWnd](../../mfc/reference/cwnd-class.md) 적절 한 자식 창 ID를 가진 개체를

A `CSplitterWnd` 개체를 부모에 일반적으로 포함 되어 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 하거나 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 개체입니다. 만들기는 `CSplitterWnd` 다음 단계를 사용 하 여 개체:

1. 포함 된 `CSplitterWnd` 부모 프레임의 멤버 변수입니다.

2. 상위 프레임의 재정의 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) 멤버 함수입니다.

3. 재정의 된 내 `OnCreateClient`를 호출 합니다 [만들기](#create) 또는 [CreateStatic](#createstatic) 의 멤버 함수 `CSplitterWnd`합니다.

호출 된 `Create` 멤버 함수는 동적 분할 창을 만들 수 있습니다. 동적 분할 창은 일반적으로 만들고 여러 개별 창 또는 같은 문서 보기를 스크롤하여 사용 됩니다. 프레임 워크에 분할자;에 대 한 초기 창에는 자동으로 만듭니다. 다음 프레임 워크 만듭니다 크기 조정, 고 분할기 창 컨트롤을 작동 하는 사용자 처럼 추가 창의 삭제 합니다.

호출 하는 경우 `Create`, 창 너무 작아서 완벽 하 게 표시할 수 없는 경우를 결정 하는 최소 행 높이 및 열 너비를 지정 합니다. 호출한 후 `Create`를 호출 하 여 이러한 최소값을 조정할 수 있습니다 합니다 [SetColumnInfo](#setcolumninfo) 및 [SetRowInfo](#setrowinfo) 멤버 함수입니다.

또한 사용 하 여 합니다 `SetColumnInfo` 및 `SetRowInfo` 는 "이상적" 열 너비와 행에 대 한 "이상적" 높이 설정 하는 멤버 함수입니다. 프레임 워크 창에 표시 하는 경우 먼저 분할기 창 다음 부모 프레임을 표시 합니다. 다음 프레임 워크의 창 분할기 창 클라이언트 영역의 오른쪽 아래 모퉁이에서 왼쪽 위 하기 이상적인 해당 차원에 따라 행과 열에 배치 합니다.

동적 분할기 창에서 모든 창은 동일한 클래스 이어야 합니다. 동적 분할 창을 지 원하는 친숙 한 응용 프로그램에는 Microsoft Word 및 Microsoft Excel 포함 됩니다.

사용 된 `CreateStatic` 정적 분할 창은 만들려는 멤버 함수입니다. 사용자가 창, 하지 해당 번호 또는 주문 정적 분할의 창 크기에만 변경할 수 있습니다.

정적 분할을 만들 때 고정 된 분할자의 모든 창 구체적으로 만들어야 합니다. 상위 프레임의 하기 전에 모든 창 만들어야 `OnCreateClient` 멤버 함수가 반환 또는 프레임 워크는 창이 제대로 표시 되지 합니다.

`CreateStatic` 멤버 함수가 자동으로 0의 최소 행 높이 및 열 너비를 사용 하 여 정적 분할을 초기화 합니다. 호출한 후 `Create`를 호출 하 여 이러한 최소값을 조정 합니다 [SetColumnInfo](#setcolumninfo) 및 [SetRowInfo](#setrowinfo) 멤버 함수입니다. 또한 사용 하 여 `SetColumnInfo` 하 고 `SetRowInfo` 호출한 후 `CreateStatic` 원하는 이상적인 창 크기를 나타내는입니다.

정적 분할의 개별 창을 종종 서로 다른 클래스에 속합니다. 정적 분할 창은의 예는 그래픽 편집기 및 Windows 파일 관리자를 참조 하십시오.

분할 창 (외에도 창 수 있는 스크롤 막대) 특수 한 스크롤 막대를 지원 합니다. 이러한 스크롤 막대의 자식인는 `CSplitterWnd` 개체 하 고 창을 사용 하 여 공유 됩니다.

분할기 창을 만든 경우 이러한 특별 한 스크롤 막대를 만듭니다. 예를 들어, 한 `CSplitterWnd` 행이 하나씩, 두 개의 열을가지고 있으며 WS_VSCROLL 스타일에는 두 창에서 공유 되는 세로 스크롤 막대가 표시 됩니다. 사용자가 스크롤 막대를 움직이면 WM_VSCROLL 메시지 창 모두에 전송 됩니다. 창 스크롤 막대 위치를 설정 하는 경우 공유 스크롤 막대 설정 됩니다.

참조에 대 한 자세한 내용은 분할 창 [기술 참고 29](../../mfc/tn029-splitter-windows.md)합니다.

동적 분할 창을 만드는 방법에 대 한 자세한 내용은 다음을 참조 하세요.

- MFC 샘플 [Scribble](../../overview/visual-cpp-samples.md)

- MFC 샘플 [VIEWEX](../../overview/visual-cpp-samples.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSplitterWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="activatenext"></a>  CSplitterWnd::ActivateNext

다음 창] 또는 [이전 창 명령을 수행 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void ActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>매개 변수

*bPrev*<br/>
활성화 하는 창을 나타냅니다. **TRUE** 에 대 한 이전; **FALSE** 다음에 대 한 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 사용 되는 높은 수준의 명령 합니다 [CView](../../mfc/reference/cview-class.md) 클래스에 대 한 위임는 `CSplitterWnd` 구현 합니다.

##  <a name="canactivatenext"></a>  CSplitterWnd::CanActivateNext

다음 창] 또는 [이전 창 명령을 현재 사용할 수 있는지 확인 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```

### <a name="parameters"></a>매개 변수

*bPrev*<br/>
활성화 하는 창을 나타냅니다. **TRUE** 에 대 한 이전; **FALSE** 다음에 대 한 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 사용 되는 높은 수준의 명령 합니다 [CView](../../mfc/reference/cview-class.md) 클래스에 대 한 위임는 `CSplitterWnd` 구현 합니다.

##  <a name="create"></a>  CSplitterWnd::Create

동적 분할 창을 만들기 위해 호출 된 `Create` 멤버 함수입니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    int nMaxRows,
    int nMaxCols,
    SIZE sizeMin,
    CCreateContext* pContext,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_HSCROLL | WS_VSCROLL | SPLS_DYNAMIC_SPLIT,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
부모 프레임 창 분할기 창입니다.

*nMaxRows*<br/>
분할기 창에서 행의 최대 수입니다. 이 값 2를 초과할 수 없습니다.

*nMaxCols*<br/>
분할기 창에 있는 열의 최대 수입니다. 이 값 2를 초과할 수 없습니다.

*sizeMin*<br/>
창을 표시 될 수 있습니다 최소 크기를 지정 합니다.

*pContext*<br/>
에 대 한 포인터를 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조입니다. 대부분의 경우이 수 합니다 *pContext* 부모 프레임 창에 전달 합니다.

*dwStyle*<br/>
창 스타일을 지정합니다.

*nID*<br/>
창의 자식 창 ID입니다. 분할기 창에 다른 분할자 창 내에서 중첩 된 아니면 ID AFX_IDW_PANE_FIRST을 수 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

포함할 수 있습니다는 `CSplitterWnd` 부모의 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 하거나 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 다음 단계를 수행 하 여 개체:

1. 포함 된 `CSplitterWnd` 부모 프레임의 멤버 변수입니다.

1. 상위 프레임의 재정의 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) 멤버 함수입니다.

1. 호출 된 `Create` 재정의 된 내에서 멤버 함수 `OnCreateClient`합니다.

부모 프레임 내에서 분할자 창을 만들면 부모 프레임의 전달 *pContext* 분할기 창에 매개 변수입니다. 그렇지 않으면이 매개 변수는 NULL 일 수 있습니다.

설정 하는 동적 분할 창은의 초기 최소 행 높이 및 열 너비를 *sizeMin* 매개 변수입니다. 창은 너무 작아서 전체에 표시 될 수 있는지 여부를 결정을 하는 이러한 최소값을 사용 하 여 변경할 수 있습니다 합니다 [SetRowInfo](#setrowinfo) 하 고 [SetColumnInfo](#setcolumninfo) 멤버 함수입니다.

에 동적 분할 창을 대 한 자세한 문서에 "분할자 Windows"를 참조 하세요 [여러 문서 형식, 뷰 및 프레임 Windows](../../mfc/multiple-document-types-views-and-frame-windows.md)를 [기술 참고 29](../../mfc/tn029-splitter-windows.md), 및 `CSplitterWnd` 클래스 개요입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]

##  <a name="createscrollbarctrl"></a>  CSplitterWnd::CreateScrollBarCtrl

공유 scroll bar 컨트롤을 만들기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
창 스타일을 지정합니다.

*nID*<br/>
창의 자식 창 ID입니다. 분할기 창에 다른 분할자 창 내에서 중첩 된 아니면 ID AFX_IDW_PANE_FIRST을 수 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

재정의 `CreateScrollBarCtrl` 스크롤 막대 옆에 있는 추가 컨트롤을 포함 합니다. 기본 동작은 일반 Windows 스크롤 막대 컨트롤을 만들려면입니다.

##  <a name="createstatic"></a>  CSplitterWnd::CreateStatic

정적 분할 창은 만들려면 호출을 `CreateStatic` 멤버 함수입니다.

```
virtual BOOL CreateStatic(
    CWnd* pParentWnd,
    int nRows,
    int nCols,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
부모 프레임 창 분할기 창입니다.

*nRows*<br/>
행의 수입니다. 이 값은 16을 초과할 수 없습니다.

*nCols*<br/>
열의 수입니다. 이 값은 16을 초과할 수 없습니다.

*dwStyle*<br/>
창 스타일을 지정합니다.

*nID*<br/>
창의 자식 창 ID입니다. 분할기 창에 다른 분할자 창 내에서 중첩 된 아니면 ID AFX_IDW_PANE_FIRST을 수 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

A `CSplitterWnd` 부모에 일반적으로 포함 되어 `CFrameWnd` 하거나 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 다음 단계를 수행 하 여 개체:

1. 포함 된 `CSplitterWnd` 부모 프레임의 멤버 변수입니다.

1. 상위 프레임의 재정의 `OnCreateClient` 멤버 함수입니다.

1. 호출 된 `CreateStatic` 재정의 된 내에서 멤버 함수 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)합니다.

정적 분할 창은 고정된 된 수의 서로 다른 클래스에서 종종 창이 포함 되어 있습니다.

정적 분할 창은 만들 때 동시에 만들어야 모든 창. 합니다 [CreateView](#createview) 멤버 함수가이 목적을 위해 일반적으로 사용 되지만 다른 nonview 클래스를 만들 수 있습니다.

정적 분할 창은 대 한 초기 최소 행 높이 및 열 너비는 0입니다. 창이 너무 작아서 전체에 표시 될 수 없는 경우를 결정 하는 이러한 최소값을 사용 하 여 변경할 수 있습니다 합니다 [SetRowInfo](#setrowinfo) 하 고 [SetColumnInfo](#setcolumninfo) 멤버 함수입니다.

스크롤 막대에 정적 분할 창은를 추가 하려면 WS_HSCROLL 및 WS_VSCROLL 스타일을 추가 *dwStyle*합니다.

문서의 "분할자 Windows"를 참조 하세요 [여러 문서 형식, 뷰 및 프레임 Windows](../../mfc/multiple-document-types-views-and-frame-windows.md)를 [기술 참고 29](../../mfc/tn029-splitter-windows.md), 및 `CSplitterWnd` 정적 분할 창은 대 한 자세한 내용은 클래스 개요입니다.

##  <a name="createview"></a>  CSplitterWnd::CreateView

정적 분할 창은 사용할 창을 만듭니다.

```
virtual BOOL CreateView(
    int row,
    int col,
    CRuntimeClass* pViewClass,
    SIZE sizeInit,
    CCreateContext* pContext);
```

### <a name="parameters"></a>매개 변수

*row*<br/>
새 보기를 배치 하는 분할자 창 행을 지정 합니다.

*col*<br/>
새 보기를 배치 하는 분할자 창을 열을 지정 합니다.

*pViewClass*<br/>
지정 된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 새 뷰의 합니다.

*sizeInit*<br/>
새 보기의 초기 크기를 지정합니다.

*pContext*<br/>
뷰를 만드는 데 생성 컨텍스트에 대 한 포인터 (일반적으로 *pContext* 부모 프레임의 재정의 된 전달할 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) 분할기 창의 멤버 함수 생성 되 고).

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

모든 정적 분할 창은 창 프레임 워크는 분할자를 표시 하기 전에 만들어야 합니다.

프레임 워크는 또한 동적 분할 창은 사용자 창, 행 또는 열을 분할 하는 경우 새 창을 만들려면이 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]

##  <a name="csplitterwnd"></a>  CSplitterWnd::CSplitterWnd

생성 하는 호출을 `CSplitterWnd` 개체입니다.

```
CSplitterWnd();
```

### <a name="remarks"></a>설명

생성 된 `CSplitterWnd` 두 단계로 개체입니다. 먼저 만드는 생성자를 호출 합니다 `CSplitterWnd` 개체를 호출는 [만들기](#create) 분할기 창 만들고에 연결 하는 멤버 함수는 `CSplitterWnd` 개체.

##  <a name="deletecolumn"></a>  CSplitterWnd::DeleteColumn

분할기 창에서 열을 삭제합니다.

```
virtual void DeleteColumn(int colDelete);
```

### <a name="parameters"></a>매개 변수

*colDelete*<br/>
삭제할 열을 지정 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 (즉, 분할 창에 있는 경우 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창은의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 이 지정할 수는 가상 함수를 함께 [CreateView](#createview), 고급 동적 분할 창을 구현 합니다.

##  <a name="deleterow"></a>  CSplitterWnd::DeleteRow

분할기 창에서 행을 삭제 합니다.

```
virtual void DeleteRow(int rowDelete);
```

### <a name="parameters"></a>매개 변수

*rowDelete*<br/>
삭제할 행을 지정 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 (즉, 분할 창에 있는 경우 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창은의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 이 지정할 수는 가상 함수를 함께 [CreateView](#createview), 고급 동적 분할 창을 구현 합니다.

##  <a name="deleteview"></a>  CSplitterWnd::DeleteView

분할기 창에서 뷰를 삭제합니다.

```
virtual void DeleteView(
    int row,
    int col);
```

### <a name="parameters"></a>매개 변수

*row*<br/>
보기를 삭제 하는 분할자 창 행을 지정 합니다.

*col*<br/>
보기를 삭제 하는 분할자 창을 열을 지정 합니다.

### <a name="remarks"></a>설명

활성 뷰를 삭제 하는 경우 다음 뷰로 활성화 됩니다. 기본 구현은 보기 자동 가정에서 삭제할 [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)합니다.

이 멤버 함수는 (즉, 분할 창에 있는 경우 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창은의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 이 지정할 수는 가상 함수를 함께 [CreateView](#createview), 고급 동적 분할 창을 구현 합니다.

##  <a name="dokeyboardsplit"></a>  CSplitterWnd::DoKeyboardSplit

키보드 분할 명령을, 일반적으로 "창 분할 합니다."를 수행 합니다.

```
virtual BOOL DoKeyboardSplit();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 사용 되는 높은 수준의 명령 합니다 [CView](../../mfc/reference/cview-class.md) 클래스에 대 한 위임는 `CSplitterWnd` 구현 합니다.

##  <a name="doscroll"></a>  CSplitterWnd::DoScroll

분할 창을 동기화 스크롤을 수행 합니다.

```
virtual BOOL DoScroll(
    CView* pViewFrom,
    UINT nScrollCode,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*pViewFrom*<br/>
뷰 스크롤 메시지의 원본에 대 한 포인터입니다.

*nScrollCode*<br/>
사용자를 나타내는 스크롤 막대 코드를 요청을 스크롤의입니다. 이 매개 변수는 두 부분으로 구성 됩니다: 가로 스크롤 발생의 형식을 결정을 낮은 순서 바이트 및 세로로 스크롤 발생의 형식을 결정 하는 상위 바이트:

    - 아래로 SB_BOTTOM 스크롤입니다.

    - 한 줄 아래로 SB_LINEDOWN 스크롤합니다.

    - 한 줄 위로 SB_LINEUP 스크롤합니다.

    - 한 페이지 아래로 SB_PAGEDOWN 스크롤합니다.

    - 한 페이지 위로 SB_PAGEUP 스크롤합니다.

    - 맨 위로 이동 SB_TOP 스크롤입니다.

*bDoScroll*<br/>
지정된 된 스크롤 동작이 발생 하는지 여부를 결정 합니다. 하는 경우 *bDoScroll* 가 TRUE (즉, 있으면 자식 창 및 분할 창을 범위가 스크롤 하는 경우), 지정 된 스크롤 작업을 수행할 수 있습니다; 다음 경우 *bDoScroll* FALSE 이면 (즉, 자식 창이 없습니다 가 분할 보기에는 스크롤 범위가 없습니다. 또는), 스크롤 발생 하지 않습니다.

### <a name="return-value"></a>반환 값

동기화 하는 경우 0이 아닌 스크롤 발생 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 뷰 스크롤 메시지를 받을 때 분할 창을 동기화 스크롤이 수행 하기 위해 프레임 워크에서 호출 됩니다. 동기화 된 스크롤을 허용 하기 전에 사용자가 작업을 요구 하도록 재정의 합니다.

##  <a name="doscrollby"></a>  CSplitterWnd::DoScrollBy

픽셀의 지정 된 수 만큼 분할 창을 스크롤합니다.

```
virtual BOOL DoScrollBy(
    CView* pViewFrom,
    CSize sizeScroll,
    BOOL bDoScroll = TRUE);
```

### <a name="parameters"></a>매개 변수

*pViewFrom*<br/>
뷰 스크롤 메시지의 원본에 대 한 포인터입니다.

*sizeScroll*<br/>
가로 및 세로로 스크롤할 수 픽셀 수입니다.

*bDoScroll*<br/>
지정된 된 스크롤 동작이 발생 하는지 여부를 결정 합니다. 하는 경우 *bDoScroll* 가 TRUE (즉, 있으면 자식 창 및 분할 창을 범위가 스크롤 하는 경우), 지정 된 스크롤 작업을 수행할 수 있습니다; 다음 경우 *bDoScroll* FALSE 이면 (즉, 자식 창이 없습니다 가 분할 보기에는 스크롤 범위가 없습니다. 또는), 스크롤 발생 하지 않습니다.

### <a name="return-value"></a>반환 값

동기화 하는 경우 0이 아닌 스크롤 발생 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 스크롤 메시지에 대 한 응답으로 프레임 워크에서 호출 됩니다, 픽셀에 나타난 양만큼 스크롤 분할 창을 동기화 하는 데 *sizeScroll*합니다. 양수를 오른쪽 아래로 스크롤 지정 음수 값 및를 왼쪽으로 스크롤을 나타냅니다.

스크롤을 허용 하기 전에 사용자가 작업을 요구 하도록 재정의 합니다.

##  <a name="getactivepane"></a>  CSplitterWnd::GetActivePane

포커스 또는 활성 보기 프레임에서 활성 창을 결정합니다.

```
virtual CWnd* GetActivePane(
    int* pRow = NULL,
    int* pCol = NULL);
```

### <a name="parameters"></a>매개 변수

*pRow*<br/>
에 대 한 포인터를 **int** 활성 창의 행 수를 검색할 수 있습니다.

*pCol*<br/>
에 대 한 포인터를 **int** 활성 창의 열 수를 검색할 수 있습니다.

### <a name="return-value"></a>반환 값

활성 창에 대 한 포인터입니다. 활성 창 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 활성 창 분할기 창에서 확인 하기 위해 프레임 워크에서 호출 됩니다. 활성 창 가져오기 전에 사용자가 작업을 요구 하도록 재정의 합니다.

##  <a name="getcolumncount"></a>  CSplitterWnd::GetColumnCount

현재 창을 열 수를 반환합니다.

```
int GetColumnCount() const;
```

### <a name="return-value"></a>반환 값

분할자의 현재 열 개수를 반환합니다. 정적 분할에 대 한이 또한 됩니다 열의 최대 수 있습니다.

##  <a name="getcolumninfo"></a>  CSplitterWnd::GetColumnInfo

지정한 열에 정보를 반환합니다.

```
void GetColumnInfo(
    int col,
    int& cxCur,
    int& cxMin) const;
```

### <a name="parameters"></a>매개 변수

*col*<br/>
열을 지정 합니다.

*cxCur*<br/>
에 대 한 참조를 **int** 열의 현재 너비를 설정 해야 합니다.

*cxMin*<br/>
에 대 한 참조를 **int** 열의 현재 최소 너비를 설정 해야 합니다.

##  <a name="getpane"></a>  CSplitterWnd::GetPane

지정 된 행과 열에 있는 창을 반환합니다.

```
CWnd* GetPane(
    int row,
    int col) const;
```

### <a name="parameters"></a>매개 변수

*row*<br/>
행을 지정합니다.

*col*<br/>
열을 지정 합니다.

### <a name="return-value"></a>반환 값

지정 된 행과 열에 있는 창을 반환합니다. 반환 된 창은 일반적으로 [CView](../../mfc/reference/cview-class.md)-클래스를 파생 합니다.

##  <a name="getrowcount"></a>  CSplitterWnd::GetRowCount

현재 창 행 개수를 반환합니다.

```
int GetRowCount() const;
```

### <a name="return-value"></a>반환 값

분할기 창에서 현재 행의 수를 반환합니다. 정적 분할 창에 대 한 최대 행 수도이 합니다.

##  <a name="getrowinfo"></a>  CSplitterWnd::GetRowInfo

지정된 된 행에 정보를 반환합니다.

```
void GetRowInfo(
    int row,
    int& cyCur,
    int& cyMin) const;
```

### <a name="parameters"></a>매개 변수

*row*<br/>
행을 지정합니다.

*cyCur*<br/>
에 대 한 참조 **int** 픽셀에서 행의 현재 높이를 설정 해야 합니다.

*cyMin*<br/>
에 대 한 참조 **int** 픽셀에서 행의 현재 최소 높이를 설정 해야 합니다.

### <a name="remarks"></a>설명

지정된 된 행에 대 한 정보를 가져오려면이 함수를 호출 합니다. 합니다 *cyCur* 매개 변수는 지정된 된 행의 현재 높이 채워집니다 및 *cyMin* 행의 최소 높이 사용 하 여 채워집니다.

##  <a name="getscrollstyle"></a>  CSplitterWnd::GetScrollStyle

분할기 창에 대 한 공유 스크롤 막대 스타일을 반환합니다.

```
DWORD GetScrollStyle() const;
```

### <a name="return-value"></a>반환 값

성공 하면 다음 창 중 하나 이상의 스타일 플래그:

    - WS_HSCROLL 분할자 현재 관리 하는 경우 가로 스크롤 막대를 공유 합니다.

    - WS_VSCROLL 분할자 현재 관리 하는 경우 세로 스크롤 막대를 공유 합니다.

0 이면 분할기 창 모든 공유 스크롤 막대를 현재 관리 하지 않습니다.

##  <a name="idfromrowcol"></a>  CSplitterWnd::IdFromRowCol

자식 창의 지정 된 행과 열에 있는 창 ID를 가져옵니다.

```
int IdFromRowCol(
    int row,
    int col) const;
```

### <a name="parameters"></a>매개 변수

*row*<br/>
분할기 창 행을 지정합니다.

*col*<br/>
분할기 창 열을 지정 합니다.

### <a name="return-value"></a>반환 값

창의 자식 창 ID입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 창으로 nonviews를 만드는 데 사용 됩니다 하 고 창에 존재 하기 전에 호출할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]

##  <a name="ischildpane"></a>  CSplitterWnd::IsChildPane

확인 여부 *pWnd* 는 현재이 분할자 창의 자식 창.

```
BOOL IsChildPane(
    CWnd* pWnd,
    int* pRow,
    int* pCol);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 테스트할 개체입니다.

*pRow*<br/>
에 대 한 포인터를 **int** 행 번호를 저장 하는 합니다.

*pCol*<br/>
에 대 한 포인터를 **int** 저장할 열 번호입니다.

### <a name="return-value"></a>반환 값

0이 아니면 *pWnd* 는 현재이 분할자 창의 자식 창 및 *pRow* 하 고 *pCol* 분할기 창에서 창의 위치로 채워집니다. 하는 경우 *pWnd* 자식 창이 없는이 분할기 창의 0이 반환 됩니다.

### <a name="remarks"></a>설명

시각적 개체의 C++ 6.0 이전 버전에서는이 함수는로 정의 된

`BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`

이 버전은 이제 사용 되지 않습니다 및 사용할 수 없습니다.

##  <a name="istracking"></a>  CSplitterWnd::IsTracking

창의 분할 막대는 현재 이동 중인 경우를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL IsTracking();
```

### <a name="return-value"></a>반환 값

분할 작업을이 진행에서 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="ondrawsplitter"></a>  CSplitterWnd::OnDrawSplitter

분할 창의 이미지를 렌더링합니다.

```
virtual void OnDrawSplitter(
    CDC* pDC,
    ESplitType nType,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
그릴 장치 컨텍스트에 대 한 포인터입니다. 하는 경우 *pDC* NULL 이면 [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) 라고 창 프레임 워크 및 없습니다 분할 하 여 그려집니다.

*nType*<br/>
값은 `enum ESplitType`, 다음 중 하나일 수 있습니다.

    - `splitBox` 분할자 끌기 상자입니다.

    - `splitBar` 두 개의 분할 창 간에 표시 되는 막대입니다.

    - `splitIntersection` 분할 창의 교차 합니다. Windows 95/98에서 실행 하는 경우이 요소는 호출할 수 없습니다.

    - `splitBorder` 분할 창 테두리입니다.

*rect*<br/>
에 대 한 참조를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 크기 및 분할 창을 모양을 지정 하는 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 그리고 분할자 창의 정확한 특징을 지정 하는 프레임 워크에서 호출 됩니다. 재정의 `OnDrawSplitter` 분할자 창에 다양 한 그래픽 구성 요소에 대 한 이미지의 고급 사용자 지정 합니다. 기본 이미지는 분할 막대의 교차점 함께 혼합 되는 Windows 또는 Microsoft Windows 95 98에 대 한 Microsoft의 분할자와 비슷합니다.

에 동적 분할 창을 대 한 자세한 문서에 "분할자 Windows"를 참조 하세요 [여러 문서 형식, 뷰 및 프레임 Windows](../../mfc/multiple-document-types-views-and-frame-windows.md)를 [기술 참고 29](../../mfc/tn029-splitter-windows.md), 및 `CSplitterWnd` 클래스 개요입니다.

##  <a name="oninverttracker"></a>  CSplitterWnd::OnInvertTracker

동일한 크기 및 모양을 프레임 창으로 분할 창의 이미지를 렌더링 합니다.

```
virtual void OnInvertTracker(const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
에 대 한 참조를 `CRect` 추적 사각형을 지정 하는 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 분할자의 크기를 조정 하는 동안 프레임 워크에서 호출 됩니다. 재정의 `OnInvertTracker` 분할 창의 이미지의 고급 사용자 지정 합니다. 기본 이미지는 분할 막대의 교차점 함께 혼합 되는 Windows 또는 Microsoft Windows 95 98에 대 한 Microsoft의 분할자와 비슷합니다.

에 동적 분할 창을 대 한 자세한 문서에 "분할자 Windows"를 참조 하세요 [여러 문서 형식, 뷰 및 프레임 Windows](../../mfc/multiple-document-types-views-and-frame-windows.md)를 [기술 참고 29](../../mfc/tn029-splitter-windows.md), 및 `CSplitterWnd` 클래스 개요입니다.

##  <a name="recalclayout"></a>  CSplitterWnd::RecalcLayout

분할기 창 행 또는 열 크기를 조정한 후 다시 표시 하기 위해 호출 합니다.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>설명

올바르게 사용 하 여 행 및 열 크기를 조정한 분할기 창 다시 표시 하려면이 멤버 함수를 호출 합니다 [SetRowInfo](#setrowinfo) 하 고 [SetColumnInfo](#setcolumninfo) 멤버 함수입니다. 분할기 창 표시 되기 전에 생성 프로세스의 일부로 행 및 열 크기 변경 하면이 멤버 함수를 호출할 필요는 없습니다.

프레임 워크 사용자 분할기 창 크기를 조정 하거나 분할을 이동할 때마다이 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CSplitterWnd::SetColumnInfo](#setcolumninfo)합니다.

##  <a name="setactivepane"></a>  CSplitterWnd::SetActivePane

현재 있는 프레임 창을 설정 합니다.

```
virtual void SetActivePane(
    int row,
    int col,
    CWnd* pWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*row*<br/>
하는 경우 *pWnd* NULL 이면 활성화 됩니다 창에 행을 지정 합니다.

*col*<br/>
하는 경우 *pWnd* NULL 이면 활성화 됩니다는 창에서 열을 지정 합니다.

*pWnd*<br/>
`CWnd` 개체에 대한 포인터입니다. 창에서 지정한 값이 null 이면 *행* 하 고 *col* 활성 설정 됩니다. NULL이 아닌 경우에 활성 설정 되는 창을 지정 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 사용자 프레임 창 내에서 창으로 포커스를 변경 하는 경우 창을 활성 상태로 설정 하기 위해 프레임 워크에서 호출 됩니다. 명시적으로 호출할 수 있습니다 `SetActivePane` 지정된 된 보기에 포커스를 변경 합니다.

행 및 열 중 하나를 제공 하 여 창 지정 **나** 함으로써 *pWnd*합니다.

##  <a name="setcolumninfo"></a>  CSplitterWnd::SetColumnInfo

지정 된 열 정보를 설정 하려면 호출 합니다.

```
void SetColumnInfo(
    int col,
    int cxIdeal,
    int cxMin);
```

### <a name="parameters"></a>매개 변수

*col*<br/>
분할기 창 열을 지정 합니다.

*cxIdeal*<br/>
분할자 창 열의 이상적인 너비를 픽셀 단위로 지정합니다.

*cxMin*<br/>
분할기 창 열의 최소 너비를 픽셀 단위로 지정 합니다.

### <a name="remarks"></a>설명

새 최소 너비 및 열에 대 한 이상적인 너비를 설정 하려면이 멤버 함수를 호출 합니다. 열의 최소값 시기를 결정 열 너무 작아서 완벽 하 게 표시할 수 있습니다.

분할자 창을 표시 하는 프레임 워크, 열 및 이상적인 차원 분할기 창 클라이언트 영역의 오른쪽 아래 모퉁이를 왼쪽 위에서에서 작업에 따라 행의 창 레이아웃 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]

##  <a name="setrowinfo"></a>  CSplitterWnd::SetRowInfo

지정 된 행 정보를 설정 하려면 호출 합니다.

```
void SetRowInfo(
    int row,
    int cyIdeal,
    int cyMin);
```

### <a name="parameters"></a>매개 변수

*row*<br/>
분할기 창 행을 지정합니다.

*cyIdeal*<br/>
분할기 창 행의 이상적인 높이 픽셀 단위로 지정합니다.

*cyMin*<br/>
분할자 창 행의 최소 높이 픽셀 단위로 지정합니다.

### <a name="remarks"></a>설명

새 최소 높이 행의 이상적인 높이 설정 하려면이 멤버 함수를 호출 합니다. 행 최 솟 값 행 되 너무 작아서 표시할 완벽 하 게 결정 합니다.

분할자 창을 표시 하는 프레임 워크, 열 및 이상적인 차원 분할기 창 클라이언트 영역의 오른쪽 아래 모퉁이를 왼쪽 위에서에서 작업에 따라 행의 창 레이아웃 합니다.

##  <a name="setscrollstyle"></a>  CSplitterWnd::SetScrollStyle

분할기 창에 대 한 새 스크롤 스타일 스크롤 막대 지원 공유를 지정 합니다.

```
void SetScrollStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
분할기 창에 대 한 새 스크롤 스타일 공유 다음 값 중 하나일 수 있는 스크롤 막대 지원:

- WS_HSCROLL 표시 만들기/공유 가로 스크롤 막대입니다.

- WS_VSCROLL 표시 만들기/공유 세로 스크롤 막대입니다.

### <a name="remarks"></a>설명

스크롤 막대를 만든 후이 소멸 되지 것입니다 경우에 `SetScrollStyle` 해당 스타일 하지 않고 호출 되었으며 이러한 스크롤 막대 대신 숨겨집니다. 이렇게 하면은 숨겨진 경우에 해당 상태를 유지 하려면 스크롤 막대. 호출한 후 `SetScrollStyle` 를 호출 하는 데 필요한 것 [RecalcLayout](#recalclayout) 모든 변경 내용을 적용 하려면.

##  <a name="splitcolumn"></a>  CSplitterWnd::SplitColumn

프레임 창이 세로로 분할 하는 지점을 나타냅니다.

```
virtual BOOL SplitColumn(int cxBefore);
```

### <a name="parameters"></a>매개 변수

*cxBefore*<br/>
분할이 발생 하는 하기 전 까지의 픽셀에서 위치입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 세로 분할자 창을 만들 때 호출 됩니다. `SplitColumn` 분할 발생 하는 기본 위치를 나타냅니다.

`SplitColumn` (즉, 분할 창에 있는 경우 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창은의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 이 지정할 수는 가상 함수를 함께 [CreateView](#createview), 고급 동적 분할 창을 구현 합니다.

##  <a name="splitrow"></a>  CSplitterWnd::SplitRow

프레임 창이 가로로 분할 하는 지점을 나타냅니다.

```
virtual BOOL SplitRow(int cyBefore);
```

### <a name="parameters"></a>매개 변수

*cyBefore*<br/>
분할이 발생 하는 하기 전 까지의 픽셀에서 위치입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 가로 분할자 창을 만들 때 호출 됩니다. `SplitRow` 분할 발생 하는 기본 위치를 나타냅니다.

`SplitRow` (즉, 분할 창에 있는 경우 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창은의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 이 지정할 수는 가상 함수를 함께 [CreateView](#createview), 고급 동적 분할 창을 구현 합니다.

##  <a name="ondraw"></a>  CSplitterWnd::OnDraw

분할기 창 그리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
장치 컨텍스트에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[MFC 샘플 VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)
