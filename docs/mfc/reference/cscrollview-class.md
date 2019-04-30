---
title: CScrollView 클래스
ms.date: 11/04/2016
f1_keywords:
- CScrollView
- AFXWIN/CScrollView
- AFXWIN/CScrollView::CScrollView
- AFXWIN/CScrollView::CheckScrollBars
- AFXWIN/CScrollView::FillOutsideRect
- AFXWIN/CScrollView::GetDeviceScrollPosition
- AFXWIN/CScrollView::GetDeviceScrollSizes
- AFXWIN/CScrollView::GetScrollPosition
- AFXWIN/CScrollView::GetTotalSize
- AFXWIN/CScrollView::ResizeParentToFit
- AFXWIN/CScrollView::ScrollToPosition
- AFXWIN/CScrollView::SetScaleToFitSize
- AFXWIN/CScrollView::SetScrollSizes
helpviewer_keywords:
- CScrollView [MFC], CScrollView
- CScrollView [MFC], CheckScrollBars
- CScrollView [MFC], FillOutsideRect
- CScrollView [MFC], GetDeviceScrollPosition
- CScrollView [MFC], GetDeviceScrollSizes
- CScrollView [MFC], GetScrollPosition
- CScrollView [MFC], GetTotalSize
- CScrollView [MFC], ResizeParentToFit
- CScrollView [MFC], ScrollToPosition
- CScrollView [MFC], SetScaleToFitSize
- CScrollView [MFC], SetScrollSizes
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
ms.openlocfilehash: d60082092bd42fbe220eee08953ad5fda0ff0a85
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339590"
---
# <a name="cscrollview-class"></a>CScrollView 클래스

A [CView](../../mfc/reference/cview-class.md) 스크롤 기능이 있습니다.

## <a name="syntax"></a>구문

```
class CScrollView : public CView
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[CScrollView::CScrollView](#cscrollview)|`CScrollView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CScrollView::CheckScrollBars](#checkscrollbars)|스크롤 보기에 가로 및 세로 스크롤 막대가 있는지 여부를 나타냅니다.|
|[CScrollView::FillOutsideRect](#filloutsiderect)|뷰 스크롤 영역 외부의 영역을 채웁니다.|
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|장치 단위로 현재 스크롤 위치를 가져옵니다.|
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|현재 매핑 모드, 총 크기 및 스크롤 가능한 보기의 줄 및 페이지 크기를 가져옵니다. 크기는 장치 단위에서입니다.|
|[CScrollView::GetScrollPosition](#getscrollposition)|논리 단위에서 현재 스크롤 위치를 가져옵니다.|
|[CScrollView::GetTotalSize](#gettotalsize)|논리적 단위로 스크롤 보기의 총 크기를 가져옵니다.|
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|해당 프레임의 크기를 결정 하려면 보기의 크기를 하면 됩니다.|
|[CScrollView::ScrollToPosition](#scrolltoposition)|뷰를 논리 단위로 지정 하 여 주어진된 지점에 스크롤합니다.|
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|스크롤 뷰를 확장-맞춤 모드로 전환 합니다.|
|[CScrollView::SetScrollSizes](#setscrollsizes)|스크롤 뷰 매핑 모드, 총 크기 및 가로 및 세로 스크롤 크기를 설정합니다.|

## <a name="remarks"></a>설명

표준에서 파생 된 클래스에서 직접 스크롤을 처리할 수 있습니다 `CView` 메시지 매핑된 재정의 하 여 [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 하 고 [OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll) 멤버 함수입니다. 하지만 `CScrollView` 는 다음과 같은 기능이 추가 해당 `CView` 기능:

- 창과 뷰포트 크기 및 매핑 모드를 관리합니다.

- 자동 스크롤 막대 메시지에 응답 중 스크롤됩니다.

- 이 키보드, 스크롤되지 않는 마우스 또는 IntelliMouse 휠에서 메시지에 따라에서 자동으로 스크롤합니다.

키보드에서 메시지에 따라에서 자동으로 스크롤할 WM_KEYDOWN 메시지를 추가 하 고 VK_DOWN, VK_PREV 및 호출에 대 한 테스트 [SetScrollPos](/windows/desktop/api/winuser/nf-winuser-setscrollpos)합니다.

메시지 매핑 재정의 하 여 직접 스크롤 휠을 처리할 수 있습니다 [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) 하 고 [OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel) 멤버 함수입니다. 에 않기 `CScrollView`, 이러한 멤버 함수에 대 한 권장 되는 동작을 지원 [WM_MOUSEWHEEL](/windows/desktop/inputdev/wm-mousewheel), 휠 회전 메시지.

자동 스크롤을 활용 하려면 보기에서 파생 `CScrollView` of에서 `CView`합니다. 뷰의 처음 만들어질 때, 호출 문서의 크기를 기준으로 스크롤할 수 있는 보기의 크기를 계산 하려는 경우는 `SetScrollSizes` 의 재정의에서 멤버 함수 [cview:: Oninitialupdate](../../mfc/reference/cview-class.md#oninitialupdate) 또는 [ CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)합니다. (문서 크기를 쿼리 하는 사용자 고유의 코드를 작성 해야 합니다. 예를 들어 참조 된 [Scribble 샘플](../../overview/visual-cpp-samples.md).)

에 대 한 호출을 `SetScrollSizes` 뷰의 매핑 모드, 스크롤 뷰 및 가로 또는 세로로 스크롤할 수 있는 메모리 양은 총 차원 멤버 함수를 설정 합니다. 모든 크기 논리 단위에서는입니다. 보기의 논리적 크기는 일반적으로 문서에 저장 된 데이터에서 계산 됩니다 있지만 고정된 크기를 지정 하려는 경우도 있습니다. 두 방법의 예제를 참조 하세요 [CScrollView::SetScrollSizes](#setscrollsizes)합니다.

논리 단위에서 가로 및 세로로 스크롤할 수 있는 메모리 양은 지정 합니다. 기본적으로 사용자가 스크롤 상자 외부의 스크롤 막대 손잡이 `CScrollView` 스크롤 하는 "페이지입니다." 스크롤 막대의 한쪽 끝에서 스크롤 화살표를 클릭 하면 `CScrollView` 스크롤 하는 "선입니다." 기본적으로 페이지는 1/10; 뷰의 전체 크기 줄은 페이지 크기의 1/10입니다. 사용자 지정 크기를 전달 하 여 이러한 기본값을 재정의 합니다 `SetScrollSizes` 멤버 함수입니다. 예를 들어, 현재 글꼴로 줄의 높이를 세로 크기와 총 크기의 너비의 일부분을 가로 크기를 설정할 수 있습니다.

스크롤 하는 대신 `CScrollView` 뷰 현재 창 크기를 조정할 수 있습니다. 이 모드에서는 보기에 스크롤 막대가 없습니다 및 논리적 보기 늘어나거나 창의 클라이언트 영역에 정확히 맞게 합니다. 이 눈금에 맞춤 기능을 사용 하려면 호출 [CScrollView::SetScaleToFitSize](#setscaletofitsize)합니다. (호출 `SetScaleToFitSize` 또는 `SetScrollSizes`, 하지만 둘 다 합니다.)

전에 `OnDraw` 파생 된 뷰 클래스의 멤버 함수를 호출 `CScrollView` 뷰포트 원본에 대 한 자동으로 조정 합니다 `CPaintDC` 디바이스 컨텍스트 개체에 전달 하는 `OnDraw`합니다.

스크롤 창의 뷰포트 원본에 맞게 `CScrollView` 재정의 [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)합니다. 이 조정을 자동으로 설정 됩니다는 `CPaintDC` 장치 컨텍스트는 `CScrollView` 전달 `OnDraw`를 호출 해야 하지만 `CScrollView::OnPrepareDC` 직접 다른 장치 컨텍스트를 사용과 같은 `CClientDC`합니다. 재정의할 수 있습니다 `CScrollView::OnPrepareDC` 펜, 배경색 및 다른 그리기 특성을 설정 하지만 크기 조정 작업을 수행 하는 기본 클래스를 호출 합니다.

스크롤 막대는 다음과 같은 경우에 표시 된 것 처럼 뷰를 기준으로 다음 세 위치에 나타날 수 있습니다.

- WS_VSCROLL 고 WS_HSCROLL를 사용 하 여 뷰에 대 한 표준 창 스타일 스크롤 막대를 설정할 수 있습니다[Windows 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.

- 스크롤 막대 컨트롤 뷰를 포함 하는 프레임에도 추가할 수 있습니다, 그리고이 경우 프레임 워크를 전달 하 고 wm_hscroll 및 WM_VSCROLL 메시지 프레임 창에서 현재 활성 뷰를 합니다.

- 프레임 워크에도 전달 스크롤에서 메시지를 `CSplitterWnd` splitter 컨트롤을 현재 활성 분할자 창 (뷰). 에 배치 하는 경우는 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) 공유 스크롤 막대를 사용 하 여는 `CScrollView` 자체 만들기 보다는 공유 된 개체를 사용 합니다.

사용 하 여 대 한 자세한 내용은 `CScrollView`를 참조 하세요 [문서/뷰 아키텍처](../../mfc/document-view-architecture.md) 하 고 [파생 된 뷰 클래스에서에서 사용할 수 있는 MFC](../../mfc/derived-view-classes-available-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="checkscrollbars"></a>  CScrollView::CheckScrollBars

스크롤 보기에 가로 및 세로 막대에 있는지 확인 하려면이 멤버 함수를 호출 합니다.

```
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>매개 변수

*bHasHorzBar*<br/>
응용 프로그램에 가로 스크롤 막대를 나타냅니다.

*bHasVertBar*<br/>
응용 프로그램에 세로 스크롤 막대를 나타냅니다.

##  <a name="cscrollview"></a>  CScrollView::CScrollView

`CScrollView` 개체를 생성합니다.

```
CScrollView();
```

### <a name="remarks"></a>설명

호출 해야 하면 `SetScrollSizes` 또는 `SetScaleToFitSize` 스크롤 하기 전에 뷰를 사용할 수 있습니다.

##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect

호출 `FillOutsideRect` 스크롤 영역 외부에 표시 되는 뷰의 영역을 채웁니다.

```
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
장치 컨텍스트를 채우기를 수행 합니다.

*pBrush*<br/>
영역을 채울 된 브러시입니다.

### <a name="remarks"></a>설명

사용 하 여 `FillOutsideRect` 스크롤 보기의 `OnEraseBkgnd` 과도 하 게 백그라운드 다시 표시 하지 않으려면 처리기 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition

호출 `GetDeviceScrollPosition` 현재 가로 및 세로 스크롤 상자에에서 위치 스크롤 막대 해야 합니다.

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>반환 값

가로 및 세로 위치 (장치 단위)로 스크롤 상자는 `CPoint` 개체입니다.

### <a name="remarks"></a>설명

좌표 쌍이 뷰의 왼쪽 위 모퉁이 스크롤 된 문서의 위치에 해당 합니다. 스크롤 뷰 장치 위치로 마우스 장치 위치 오프셋 때 유용 합니다.

`GetDeviceScrollPosition` 장치 단위에서 값을 반환합니다. 사용 하 여 논리 단위를 원한다 면 `GetScrollPosition` 대신 합니다.

##  <a name="getdevicescrollsizes"></a>  CScrollView::GetDeviceScrollSizes

`GetDeviceScrollSizes` 현재 매핑 모드, 총 크기 및 스크롤 가능한 보기의 줄 및 페이지 크기를 가져옵니다.

```
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>매개 변수

*nMapMode*<br/>
이 보기에 대 한 현재 매핑 모드를 반환합니다. 가능한 값 목록을 참조 하세요. `SetScrollSizes`합니다.

*sizeTotal*<br/>
장치 단위로 스크롤 보기의 현재 총 크기를 반환합니다.

*sizePage*<br/>
스크롤 막대 손잡이 클릭 마우스에 대 한 응답의 각 방향으로 스크롤이 현재 가로 및 세로 거리를 반환 합니다. `cx` 멤버 가로 크기를 포함 합니다. `cy` 멤버 세로 크기를 포함 합니다.

*sizeLine*<br/>
스크롤 화살표를 클릭 마우스에 대 한 응답의 각 방향으로 스크롤이 현재 가로 및 세로 거리를 반환 합니다. `cx` 멤버 가로 크기를 포함 합니다. `cy` 멤버 세로 크기를 포함 합니다.

### <a name="remarks"></a>설명

크기는 장치 단위에서입니다. 이 멤버 함수는 거의 호출 되지 않습니다.

##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition

호출 `GetScrollPosition` 현재 가로 및 세로 스크롤 상자에에서 위치 스크롤 막대 해야 합니다.

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>반환 값

가로 및 세로 위치 (논리 단위)으로 스크롤 상자는 `CPoint` 개체입니다.

### <a name="remarks"></a>설명

좌표 쌍이 뷰의 왼쪽 위 모퉁이 스크롤 된 문서의 위치에 해당 합니다.

`GetScrollPosition` 논리 단위에서 값을 반환합니다. 사용 하 여 장치 단위 원한다 면 `GetDeviceScrollPosition` 대신 합니다.

##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize

호출 `GetTotalSize` 스크롤 보기의 현재 가로 및 세로 크기를 검색 하려면.

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>반환 값

논리적 단위로 스크롤 보기의 총 크기입니다. 가로 크기에는 `cx` 의 멤버는 `CSize` 값을 반환 합니다. 세로 크기에는 `cy` 멤버입니다.

##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit

호출 `ResizeParentToFit` 프레임 창의 크기를 지정 하는 보기의 크기에 있도록 합니다.

```
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>매개 변수

*bShrinkOnly*<br/>
크기를 조정 하는 데 종류입니다. TRUE 값을 기본값으로 해당 하는 경우 프레임 창을 축소 합니다. 스크롤 막대 큰 뷰나 작은 프레임 창에 표시 됩니다. FALSE 값 이면 항상 정확 하 게 프레임 창의 크기를 조정 하는 보기. 이 프레임 창 내에서 여러 문서 MDI (인터페이스) 프레임 창이 나 화면에 맞게 너무 가져올 수 있으므로 다소 위험할 수 있습니다.

### <a name="remarks"></a>설명

이 MDI 자식 프레임 창의 뷰에 대해서만 권장 됩니다. 사용 하 여 `ResizeParentToFit` 에 `OnInitialUpdate` 처리기 함수가 파생 된 `CScrollView` 클래스입니다. 이 멤버 함수는 예제를 보려면 [CScrollView::SetScrollSizes](#setscrollsizes)합니다.

`ResizeParentToFit` 뷰 창의 크기를이 설정 되어 있다고 가정 합니다. 경우 보기 창 크기가 설정 되지 않은 경우 `ResizeParentToFit` 가 호출 하면 어설션 합니다. 이 발생 하지 않습니다는 있도록 호출 하기 전에 다음 호출은 `ResizeParentToFit`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition

호출 `ScrollToPosition` 뷰에서 지정된 된 지점으로 스크롤해야 합니다.

```
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
논리 단위에서를 스크롤하여 가리킵니다. `x` 멤버 (보다 크거나 0으로 보기의 총 크기까지) 양수 값 이어야 합니다. 같은 기준이 `y` 매핑 모드가 MM_TEXT 일 때 멤버입니다. `y` 멤버의 매핑 모드가 MM_TEXT 이외의 음수입니다.

### <a name="remarks"></a>설명

이 점은 창의 왼쪽 위 모퉁이에 있도록 뷰를 스크롤할 수 됩니다. 보기에 맞게 크기가 조정 되는 경우이 멤버 함수를 호출할 수 있어야 합니다.

##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize

호출 `SetScaleToFitSize` 뷰포트 크기를 현재 창 크기를 자동으로 확장 하려는 경우.

```
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>매개 변수

*sizeTotal*<br/>
뷰를 조정할 수를 가로 및 세로 크기입니다. 스크롤 보기의 크기는 논리적 단위로 측정 됩니다. 에 포함 된 가로 크기를 `cx` 멤버입니다. 에 포함 된 세로 크기를 `cy` 멤버입니다. 둘 다 `cx` 고 `cy` 0 보다 크거나 이어야 합니다.

### <a name="remarks"></a>설명

스크롤 막대를 사용 하 여 언제 든 지 논리 보기의 일부만 표시 될 수 있습니다. 눈금에 맞춤 기능을 사용 하 여 보기에 스크롤 막대가 없습니다 있고 논리적인 관점에서 늘어나거나 창의 클라이언트 영역에 정확히 맞게 합니다. 창의 크기를 조정할 때 보기 창의 크기를 기준으로 새 규모로 데이터를 그립니다.

에 대 한 호출을 일반적으로 배치할 `SetScaleToFitSize` 뷰의의 재정의 `OnInitialUpdate` 멤버 함수입니다. 원하지 않는 자동 크기 조정, 호출 된 `SetScrollSizes` 멤버 함수를 대신 합니다.

`SetScaleToFitSize` "맞추기 확대/축소" 작업을 구현 하려면 사용할 수 있습니다. 사용 하 여 `SetScrollSizes` 스크롤을 다시 초기화 합니다.

`SetScaleToFitSize` 뷰 창의 크기를이 설정 되어 있다고 가정 합니다. 경우 보기 창 크기가 설정 되지 않은 경우 `SetScaleToFitSize` 가 호출 하면 어설션 합니다. 이 발생 하지 않습니다는 있도록 호출 하기 전에 다음 호출은 `SetScaleToFitSize`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="setscrollsizes"></a>  CScrollView::SetScrollSizes

호출 `SetScrollSizes` 때 뷰를 업데이트할 수 있습니다.

```
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>매개 변수

*nMapMode*<br/>
이 보기에 대해 설정할 매핑 모드입니다. 가능한 값은 다음과 같습니다.

|매핑 모드|논리 단위|양의 y-축 확장 하는 중...|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 픽셀|아래쪽|
|MM_HIMETRIC|0.01 mm|상향|
|MM_TWIPS|1/1440에서|상향|
|MM_HIENGLISH|0.001에서|상향|
|MM_LOMETRIC|0.1 mm|상향|
|MM_LOENGLISH|0.01에서|상향|

이러한 모드의 모든 Windows에서 정의 됩니다. MM_ISOTROPIC 및 MM_ANISOTROPIC, 다음 두 가지 표준 매핑 모드에 사용 되지 않는 `CScrollView`합니다. 클래스 라이브러리에서 제공 된 `SetScaleToFitSize` 뷰 창 크기를 확장 하는 것에 대 한 멤버 함수입니다. 위의 테이블에 열 3 좌표 방향을 설명합니다.

*sizeTotal*<br/>
스크롤 보기의 총 크기입니다. `cx` 멤버 가로 범위를 포함 합니다. `cy` 멤버 세로 범위를 포함 합니다. 크기는 논리 단위에서입니다. 둘 다 `cx` 고 `cy` 0 보다 크거나 이어야 합니다.

*sizePage*<br/>
마우스에 대 한 응답의 각 방향으로 스크롤이 가로 및 세로 거리는 스크롤 막대 손잡이 클릭 합니다. `cx` 멤버 가로 크기를 포함 합니다. `cy` 멤버 세로 크기를 포함 합니다.

*sizeLine*<br/>
마우스에 대 한 응답의 각 방향으로 스크롤이 가로 및 세로 거리 스크롤 화살표를 클릭 합니다. `cx` 멤버 가로 크기를 포함 합니다. `cy` 멤버 세로 크기를 포함 합니다.

### <a name="remarks"></a>설명

재정의에서 호출을 `OnUpdate` 멤버 함수 또는 크기가 변경 되 면 예를 들어 문서를 처음 표시할 때 스크롤 특성을 조정 합니다.

일반적으로 가져와야 크기 정보 보기의 관련된 문서에서 아마도 라는 문서 멤버 함수를 호출 하 여 `GetMyDocSize`, 파생된 문서 클래스를 사용 하 여 제공 하는 합니다. 다음 코드에서는이 방법을 보여 줍니다.

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

또는 다음 코드와 같이 고정된 크기를 설정 해야 경우가 있습니다.

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

MM_ISOTROPIC 또는 MM_ANISOTROPIC를 제외한 Windows 매핑 모드 중 하나를 매핑 모드를 설정 해야 합니다. 무제한 매핑 모드를 사용 하려는 경우 호출 된 `SetScaleToFitSize` 대신 멤버 함수 `SetScrollSizes`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd 클래스](../../mfc/reference/csplitterwnd-class.md)
