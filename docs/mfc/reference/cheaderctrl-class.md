---
title: CHeaderCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
ms.openlocfilehash: 51cdfb481892ba5057d4ca26ff4d6e51665557e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160200"
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl 클래스

Windows의 공용 헤더 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|`CHeaderCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|헤더 컨트롤에 대 한 모든 필터를 지웁니다.|
|[CHeaderCtrl::ClearFilter](#clearfilter)|헤더 컨트롤에 대 한 필터를 지웁니다.|
|[CHeaderCtrl::Create](#create)|헤더 컨트롤을 만들고 연결 하는 `CHeaderCtrl` 개체입니다.|
|[CHeaderCtrl::CreateDragImage](#createdragimage)|헤더 컨트롤 내에서 항목의 이미지의 투명 한 버전을 만듭니다.|
|[CHeaderCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 헤더 컨트롤을 만들고 연결 하는 `CListCtrl` 개체입니다.|
|[CHeaderCtrl::DeleteItem](#deleteitem)|헤더 컨트롤에서 항목을 삭제합니다.|
|[CHeaderCtrl::DrawItem](#drawitem)|헤더 컨트롤의 지정된 된 항목을 그립니다.|
|[CHeaderCtrl::EditFilter](#editfilter)|헤더 컨트롤의 지정 된 필터를 편집을 시작 합니다.|
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|헤더 컨트롤의 비트맵의 여백 너비를 검색합니다.|
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|포커스가 있는 현재 헤더 컨트롤에서 항목의 식별자를 가져옵니다.|
|[CHeaderCtrl::GetImageList](#getimagelist)|헤더 컨트롤에서 그리기 헤더 항목에 사용할 이미지 목록의 핸들을 검색 합니다.|
|[CHeaderCtrl::GetItem](#getitem)|헤더 컨트롤의 항목에 대 한 정보를 검색합니다.|
|[CHeaderCtrl::GetItemCount](#getitemcount)|헤더 컨트롤의 항목 수를 검색합니다.|
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|헤더 컨트롤의 지정 된 드롭다운 단추에 대 한 경계 사각형 정보를 가져옵니다.|
|[CHeaderCtrl::GetItemRect](#getitemrect)|헤더 컨트롤의 지정 된 항목에 대 한 경계 사각형을 검색 합니다.|
|[CHeaderCtrl::GetOrderArray](#getorderarray)|헤더 컨트롤에서 항목의 왼쪽에서 오른쪽 순서를 검색합니다.|
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|현재 헤더 컨트롤에 대 한 오버플로 단추인의 경계 사각형을 가져옵니다.|
|[CHeaderCtrl::HitTest](#hittest)|헤더에 있는 경우 있는 항목을 특정 시점을 결정 합니다.|
|[CHeaderCtrl::InsertItem](#insertitem)|헤더 컨트롤에 새 항목을 삽입합니다.|
|[CHeaderCtrl::Layout](#layout)|크기와 지정 된 사각형 내에 있는 헤더 컨트롤의 위치를 검색 합니다.|
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|헤더 컨트롤에서 해당 순서에 따라 항목의 인덱스 값을 검색 합니다.|
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|헤더 컨트롤의 여백 비트맵의 너비를 설정합니다.|
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|필터 특성의 변경 내용을 수행 시간 및 게시할 시간 제한 간격을 설정는 `HDN_FILTERCHANGE` 알림.|
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|현재 헤더 컨트롤에서 지정 된 헤더 항목에 포커스를 설정합니다.|
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|수동을 나타내기 위해 헤더 항목 간의 구분선 끌어 변경 및 헤더 항목의 삭제 합니다.|
|[CHeaderCtrl::SetImageList](#setimagelist)|이미지 목록과 헤더 컨트롤에 할당합니다.|
|[CHeaderCtrl::SetItem](#setitem)|헤더 컨트롤의 지정된 된 항목의 특성을 설정합니다.|
|[CHeaderCtrl::SetOrderArray](#setorderarray)|헤더 컨트롤에서 항목의 왼쪽에서 오른쪽 순서를 설정합니다.|

## <a name="remarks"></a>설명

헤더 컨트롤에는 일반적으로 텍스트 또는 숫자 열의 집합 위에 배치 되는 창입니다. 각 열 제목을 포함 하 고 부분으로 나눌 수 있습니다. 각 열의 너비를 설정 하려면 각 부분을 구분 하는 구분선을 끌 수 있습니다. 헤더 컨트롤의 그림을 참조 하세요 [헤더 컨트롤](/windows/desktop/Controls/header-controls)합니다.

이 컨트롤 (및 따라서는 `CHeaderCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.

Windows 95/Internet Explorer 4.0 공용 컨트롤에 대 한 추가 기능은 다음과 같습니다.

- 헤더 항목 사용자 지정 정렬 합니다.

- 헤더 항목 끌어서 놓기, 헤더 항목 다시 정렬 합니다. HDS_DRAGDROP 스타일을 만들 때 사용 된 `CHeaderCtrl` 개체입니다.

- 머리글 열 텍스트 열 크기 조정 하는 동안 지속적으로 볼 수 있습니다. 만들 때 HDS_FULLDRAG 스타일을 사용 하 여를 `CHeaderCtrl` 개체입니다.

- 헤더 활성 추적을 포인터를 가리킬 때 헤더 항목을 강조 표시 합니다. 사용 하려면 HDS_HOTTRACK 스타일을 만들 때 사용 된 `CHeaderCtrl` 개체입니다.

- 이미지 목록 지원입니다. 헤더 항목에 저장 된 이미지를 포함할 수 있습니다는 `CImageList` 개체나 텍스트입니다.

사용에 대 한 자세한 내용은 `CHeaderCtrl`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md) 하 고 [CHeaderCtrl 사용 하 여](../../mfc/using-cheaderctrl.md)입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="cheaderctrl"></a>  CHeaderCtrl::CHeaderCtrl

`CHeaderCtrl` 개체를 생성합니다.

```
CHeaderCtrl();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

##  <a name="clearallfilters"></a>  CHeaderCtrl::ClearAllFilters

헤더 컨트롤에 대 한 모든 필터를 지웁니다.

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

Win32 메시지의 동작을 구현 하는이 메서드입니다 [HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter) 열 값이-1, Windows SDK에 설명 된 대로 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

##  <a name="clearfilter"></a>  CHeaderCtrl::ClearFilter

헤더 컨트롤에 대 한 필터를 지웁니다.

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>매개 변수

*nColumn*<br/>
열 값 선택을 필터링 하는 의미입니다.

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 Win32 메시지의 동작을 구현 [HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

##  <a name="create"></a>  CHeaderCtrl::Create

헤더 컨트롤을 만들고 연결 하는 `CHeaderCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
헤더 컨트롤의 스타일을 지정합니다. 헤더 컨트롤 스타일에 대 한 참조 [헤더 컨트롤 스타일](/windows/desktop/Controls/header-control-styles) Windows SDK에 있습니다.

*rect*<br/>
헤더 컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조입니다.

*pParentWnd*<br/>
일반적으로 헤더 컨트롤의 부모 창 지정을 `CDialog`입니다. NULL이 아니어야 합니다.

*nID*<br/>
헤더 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

초기화에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CHeaderCtrl` 두 단계에서 개체입니다. 먼저 생성자를 호출 하 고 호출 `Create`, 헤더 컨트롤을 만들고 연결 하는 `CHeaderCtrl` 개체입니다.

헤더 컨트롤 스타일 외에도 헤더 컨트롤 배치 하 고 크기를 조정 하는 방법을 확인 하려면 다음과 같은 일반적인 컨트롤 스타일을 사용할 수 있습니다 (참조 [공용 컨트롤 스타일](/windows/desktop/Controls/common-control-styles) 자세한):

- 컨트롤이 부모 창의 클라이언트 영역의 맨 아래에 배치 하는 자체 창의 너비 부모와 동일한 너비를 설정 하는 CCS_BOTTOM 합니다.

- 컨트롤의 맨 위에 있는 그려지지 강조 표시는 두 픽셀 CCS_NODIVIDER 방지 합니다.

- CCS_NOMOVEY 컨트롤이 조정 하 고 WM_SIZE 메시지에 대 한 응답에서 가로로 하지만 하지 세로 방향으로 자체 이동 합니다. CCS_NORESIZE 스타일을 사용 하는 경우에이 스타일 적용 되지 않습니다. 헤더 컨트롤 기본적으로이 스타일을 갖습니다.

- CCS_NOPARENTALIGN 위쪽 이나 아래쪽 부모 창에 자동으로 이동 컨트롤을 방지 합니다. 대신 컨트롤의 부모 창 크기를 변경 되더라도 부모 창 내에서 위치를 유지합니다. CCS_TOP 또는 CCS_BOTTOM 스타일도 사용 되는 경우 기본적으로 높이 조정 됩니다 있지만 위치와 너비를 그대로 유지 됩니다.

- CCS_NORESIZE 초기 크기 또는 새 크기를 설정 하는 경우 기본 너비와 높이 사용 하 여 컨트롤을 방지 합니다. 대신, 너비와 높이 만들거나 크기 조정에 대 한 요청에 지정 된 컨트롤에서 사용 합니다.

- 컨트롤이 부모 창의 클라이언트 영역의 위쪽에 배치 하는 자체 창의 너비 부모와 동일한 너비를 설정 하는 CCS_TOP 합니다.

헤더 컨트롤에 창 스타일을 적용할 수도 있습니다 (참조 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 자세한):

- WS_CHILD 자식 창을 만듭니다. WS_POPUP 스타일을 사용 하 여 사용할 수 없습니다.

- WS_VISIBLE에 처음 표시 되는 창을 만듭니다.

- WS_DISABLED 처음부터 사용할 수 있는 창을 만듭니다.

- WS_GROUP는 이동할 수 한 컨트롤에서 다음 화살표 키를 사용 하 여 컨트롤의 그룹의 첫 번째 컨트롤을 지정 합니다. 모든 컨트롤을 동일한 그룹에 속하는 첫 번째 컨트롤 후 WS_GROUP 스타일을 사용 하 여 정의 합니다. WS_GROUP 스타일을 사용 하 여 다음 컨트롤의 스타일 그룹을 종료 하 고 그룹 (즉, 하나의 그룹 끝 다음 시작 되는 위치)를 시작 합니다.

- WS_TABSTOP 중 하나를 지정 수 있는 사용자가 TAB 키를 사용 하 여 이동할 수는 컨트롤입니다. TAB 키를 WS_TABSTOP 스타일에 의해 지정 된 다음 컨트롤로 이동 합니다.

컨트롤을 사용 하 여 확장된 창 스타일을 사용 하려는 경우 호출할 [CreateEx](#createex) 대신 `Create`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

##  <a name="createex"></a>  CHeaderCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 된 `CHeaderCtrl` 개체입니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
만들려는 컨트롤의 확장된 스타일을 지정 합니다. 확장 된 Windows 스타일의 목록은 참조 하세요. 합니다 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK의 합니다.

*dwStyle*<br/>
헤더 컨트롤의 스타일입니다. 헤더 컨트롤 스타일에 대 한 참조 [헤더 컨트롤 스타일](/windows/desktop/Controls/header-control-styles) Windows SDK에 있습니다. 참조 [만들기](#create) 추가 스타일의 목록은 합니다.

*rect*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 크기와의 클라이언트 좌표에서 만든 창의 위치를 설명 하는 구조 *pParentWnd*합니다.

*pParentWnd*<br/>
컨트롤의 부모 창에 대 한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 하 여 `CreateEx` of `Create` Windows 확장된 스타일 앞으로 지정 된 Windows 확장된 스타일을 적용할 **WS_EX_** 합니다.

##  <a name="createdragimage"></a>  CHeaderCtrl::CreateDragImage

헤더 컨트롤 내에서 항목의 이미지의 투명 한 버전을 만듭니다.

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
헤더 컨트롤에서 항목의 0부터 시작 하는 인덱스입니다. 이 항목에 할당 된 이미지는 투명 한 이미지의 기반입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CImageList](../../mfc/reference/cimagelist-class.md) 성공 하면 NULL 개체입니다. 반환된 된 목록에는 하나의 이미지만을 포함합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_CREATEDRAGIMAGE](/windows/desktop/Controls/hdm-createdragimage)Windows SDK에 설명 된 대로 합니다. 헤더 항목 끌어서 놓기 지원 하기 위해 제공 됩니다.

`CImageList` 개체는 반환 된 포인터가 가리키는 임시 개체 이며 다음 유휴 시간 처리에서 삭제 됩니다.

##  <a name="deleteitem"></a>  CHeaderCtrl::DeleteItem

헤더 컨트롤에서 항목을 삭제합니다.

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
삭제할 항목의 0부터 시작 인덱스를 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

##  <a name="drawitem"></a>  CHeaderCtrl::DrawItem

소유자 그리기 헤더 컨트롤의 시각적 측면이 때 프레임 워크에서 호출 됩니다.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>매개 변수

*lpDrawItemStruct*<br/>
에 대 한 포인터를 [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) 그릴 항목을 설명 하는 구조입니다.

### <a name="remarks"></a>설명

합니다 `itemAction` 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업 수행 수입니다.

이 멤버 함수는 기본적으로 아무 작업도 수행 하지. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수를 재정의 `CHeaderCtrl` 개체입니다.

응용 프로그램에 제공 된 디스플레이 컨텍스트를 위해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 *lpDrawItemStruct* 전에이 멤버 함수를 종료 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

##  <a name="editfilter"></a>  CHeaderCtrl::EditFilter

헤더 컨트롤의 지정 된 필터를 편집 하기 시작 합니다.

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>매개 변수

*nColumn*<br/>
열 편집입니다.

*bDiscardChanges*<br/>
필터를 편집 하는 동안 사용자가 사용자를 처리 하는 방법을 지정 하는 값의 편집 변경 때 합니다 [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter) 전송 됩니다.

지정 하는 경우 사용자가 변경한 내용을 적용 하려면 FALSE 또는 사용자가 변경한 내용을 무시합니다

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 Win32 메시지의 동작을 구현 [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

##  <a name="getbitmapmargin"></a>  CHeaderCtrl::GetBitmapMargin

헤더 컨트롤의 비트맵의 여백 너비를 검색합니다.

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>반환 값

픽셀에서 비트맵 여백의 너비입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_GETBITMAPMARGIN](/windows/desktop/Controls/hdm-getbitmapmargin)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

##  <a name="getfocuseditem"></a>  CHeaderCtrl::GetFocusedItem

현재 헤더 컨트롤에 포커스를가지고 있는 항목의 인덱스를 가져옵니다.

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>반환 값

포커스가 있는 헤더 항목의 0부터 시작 하는 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [HDM_GETFOCUSEDITEM](/windows/desktop/Controls/hdm-getfocuseditem) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제는 `SetFocusedItem` 고 `GetFocusedItem` 메서드. 코드의 이전 단원에서 다섯 개의 열을 사용 하 여 헤더 컨트롤을 생성 합니다. 그러나는 열에 표시 되지 않도록 열 구분 기호를 끌 수 있습니다. 다음 예제에서는 설정 하 고 포커스 항목으로 마지막 열 머리글을 확인 합니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="getimagelist"></a>  CHeaderCtrl::GetImageList

헤더 컨트롤에서 그리기 헤더 항목에 사용할 이미지 목록의 핸들을 검색 합니다.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_GETIMAGELIST](/windows/desktop/Controls/hdm-getimagelist)Windows SDK에 설명 된 대로 합니다. `CImageList` 개체는 반환 된 포인터가 가리키는 임시 개체 이며 다음 유휴 시간 처리에서 삭제 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

##  <a name="getitem"></a>  CHeaderCtrl::GetItem

헤더 컨트롤 항목에 대 한 정보를 검색합니다.

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
검색할 항목의 0부터 시작 인덱스를 지정 합니다.

*pHeaderItem*<br/>
에 대 한 포인터를 [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) 새 항목을 수신 하는 구조입니다. 이 구조체를 사용 합니다 `InsertItem` 및 `SetItem` 멤버 함수입니다. 플래그 설정는 `mask` 요소 반환 될 때 해당 요소에 값을 제대로 입력을 확인 합니다. 경우는 `mask` 요소 0으로 설정 되 면 다른 구조 요소 값은 의미가 없습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

##  <a name="getitemcount"></a>  CHeaderCtrl::GetItemCount

헤더 컨트롤의 항목 수를 검색합니다.

```
int GetItemCount() const;
```

### <a name="return-value"></a>반환 값

성공할 경우 헤더 컨트롤 항목의 수 그렇지 않으면-1입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CHeaderCtrl::DeleteItem](#deleteitem)합니다.

##  <a name="getitemdropdownrect"></a>  CHeaderCtrl::GetItemDropDownRect

현재 헤더 컨트롤의 머리글 항목에 대 한 드롭다운 단추의 경계 사각형을 가져옵니다.

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iItem*|[in] 해당 스타일은 HDF_SPLITBUTTON 헤더 항목의 0부터 시작 인덱스입니다. 자세한 내용은 참조 하세요. 합니다 `fmt` 의 멤버는 [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) 구조입니다.|
|*lpRect*|[out] 에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조 경계 사각형 정보를 얻습니다.|

### <a name="return-value"></a>반환 값

이 함수에 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [HDM_GETITEMDROPDOWNRECT](/windows/desktop/Controls/hdm-getitemdropdownrect) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제는 `GetItemDropDownRect` 메서드. 코드의 이전 단원에서 다섯 개의 열을 사용 하 여 헤더 컨트롤을 생성 합니다. 다음 코드 예제에서는 헤더 드롭다운 단추에 대해 예약 된 첫 번째 열의 위치 주변 3 차원 사각형을 그립니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

##  <a name="getitemrect"></a>  CHeaderCtrl::GetItemRect

헤더 컨트롤의 지정 된 항목에 대 한 경계 사각형을 검색 합니다.

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
헤더 컨트롤 항목의 0부터 시작 하는 인덱스입니다.

*lpRect*<br/>
주소에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 경계 사각형 정보를 수신 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드는 Win32 메시지의 동작을 구현 [HDM_GETITEMRECT](/windows/desktop/Controls/hdm-getitemrect)Windows SDK에 설명 된 대로 합니다.

##  <a name="getorderarray"></a>  CHeaderCtrl::GetOrderArray

헤더 컨트롤에서 항목의 왼쪽에서 오른쪽 순서를 검색합니다.

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>매개 변수

*piArray*<br/>
왼쪽에서 오른쪽으로 나타나는 순서로 헤더 컨트롤에서 항목의 인덱스 값을 수신 하는 버퍼의 주소에 대 한 포인터입니다.

*iCount*<br/>
헤더 컨트롤 항목의 수입니다. 음수가 아닌 있어야 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_GETORDERARRAY](/windows/desktop/Controls/hdm-getorderarray)Windows SDK에 설명 된 대로 합니다. 헤더 항목 순서 지정을 지원 하기 위해 제공 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

##  <a name="getoverflowrect"></a>  CHeaderCtrl::GetOverflowRect

현재 헤더 컨트롤의 오버플로 단추의 경계 사각형을 가져옵니다.

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*lpRect*|[out] 에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 경계 사각형 정보를 수신 하는 구조입니다.|

### <a name="return-value"></a>반환 값

이 함수에 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

헤더 컨트롤에 동시에 표시할 수 있는 것 보다 더 많은 항목이 있으면 컨트롤 표시 되지 않는 항목 스크롤 하는 오버플로 단추를 표시할 수 있습니다. 헤더 컨트롤에는 오버플로 단추를 표시 하려면 HDF_SPLITBUTTON 및 HDS_OVERFLOW 스타일 있어야 합니다. 경계 사각형을 오버플로 단추를 포함 하 고 오버플로 단추가 표시 하는 경우에 존재 합니다. 자세한 내용은 [헤더 컨트롤 스타일](/windows/desktop/Controls/header-control-styles)합니다.

이 메서드는 전송 된 [HDM_GETOVERFLOWRECT](/windows/desktop/Controls/hdm-getoverflowrect) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제는 `GetOverflowRect` 메서드. 코드의 이전 단원에서 다섯 개의 열을 사용 하 여 헤더 컨트롤을 생성 합니다. 그러나는 열에 표시 되지 않도록 열 구분 기호를 끌 수 있습니다. 일부 열이 표시 되지 않는 경우 오버플로 단추가 헤더 컨트롤을 그립니다. 다음 코드 예제에서는 오버플로 단추의 위치 주변 3 차원 사각형을 그립니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

##  <a name="hittest"></a>  CHeaderCtrl::HitTest

헤더에 있는 경우 있는 항목을 특정 시점을 결정 합니다.

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*phdhti*|[out에서] 에 대 한 포인터를 [HDHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_hd_hittestinfo) 테스트 하는 시점을 지정 하 고 테스트의 결과 받는 구조체입니다.|

### <a name="return-value"></a>반환 값

지정 된 위치에 있는 경우 헤더 항목의 0부터 시작 인덱스 그렇지 않으면-1입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [HDM_HITTEST](/windows/desktop/Controls/hdm-hittest) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제는 `HitTest` 메서드. 이 코드 예제에서는 이전 단원에서 다섯 개의 열을 사용 하 여 헤더 컨트롤을 생성 합니다. 그러나는 열에 표시 되지 않도록 열 구분 기호를 끌 수 있습니다. 이 예제에서는 표시 된 경우 열의 인덱스를 보고 하 고 해당 열이 표시 되지 않으면-1입니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

##  <a name="insertitem"></a>  CHeaderCtrl::InsertItem

지정된 된 인덱스에 헤더 컨트롤에 새 항목을 삽입합니다.

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
삽입할 항목의 인덱스(0부터 시작)입니다. 값이 0 이면 항목 헤더 컨트롤의 시작 부분에 삽입 됩니다. 값이 최대값 보다 크면 항목 헤더 컨트롤의 끝에 삽입 됩니다.

*phdi*<br/>
에 대 한 포인터를 [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) 삽입할 항목에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공할 경우 새 항목의 인덱스 그렇지 않으면-1입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

##  <a name="layout"></a>  CHeaderCtrl::Layout

크기와 지정 된 사각형 내에 있는 헤더 컨트롤의 위치를 검색 합니다.

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>매개 변수

*pHeaderLayout*<br/>
에 대 한 포인터를 [HDLAYOUT](/windows/desktop/api/commctrl/ns-commctrl-_hd_layout) 크기와 헤더 컨트롤의 위치를 설정 하는 데 사용 되는 정보가 포함 된 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 지정된 된 사각형을 차지 하는 새 헤더 컨트롤에 대 한 적절 한 크기 결정에 사용 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

##  <a name="ordertoindex"></a>  CHeaderCtrl::OrderToIndex

헤더 컨트롤에서 해당 순서에 따라 항목의 인덱스 값을 검색 합니다.

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>매개 변수

*nOrder*<br/>
왼쪽에서 오른쪽 헤더 컨트롤에 항목이 표시 되는 0부터 시작 순서입니다.

### <a name="return-value"></a>반환 값

헤더 컨트롤에서 해당 순서에 따라 항목의 인덱스입니다. 인덱스를 왼쪽에서 오른쪽으로 0부터 셉니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 매크로의 동작을 구현 [HDM_ORDERTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb775355)Windows SDK에 설명 된 대로 합니다. 헤더 항목 순서 지정을 지원 하기 위해 제공 됩니다.

##  <a name="setbitmapmargin"></a>  CHeaderCtrl::SetBitmapMargin

헤더 컨트롤의 여백 비트맵의 너비를 설정합니다.

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
기존 헤더 컨트롤 내에서 비트맵을 둘러싸는 여백 (픽셀)에 지정 된 너비입니다.

### <a name="return-value"></a>반환 값

픽셀에서 비트맵 여백의 너비입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_SETBITMAPMARGIN](/windows/desktop/Controls/hdm-setbitmapmargin)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

##  <a name="setfilterchangetimeout"></a>  CHeaderCtrl::SetFilterChangeTimeout

필터 특성의 변경 내용을 수행 시간 및 게시할 시간 제한 간격을 설정 합니다는 [HDN_FILTERCHANGE](/windows/desktop/Controls/hdn-filterchange) 알림.

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>매개 변수

*dwTimeOut*<br/>
시간 제한 값 (밀리초)입니다.

### <a name="return-value"></a>반환 값

수정 중인 필터 컨트롤의 인덱스입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_SETFILTERCHANGETIMEOUT](/windows/desktop/Controls/hdm-setfilterchangetimeout)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

##  <a name="setfocuseditem"></a>  CHeaderCtrl::SetFocusedItem

현재 헤더 컨트롤에서 지정 된 헤더 항목에 포커스를 설정합니다.

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iItem*|[in] 헤더 항목의 인덱스가 0부터 시작 합니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [HDM_SETFOCUSEDITEM](/windows/desktop/Controls/hdm-setfocuseditem) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>예제

다음 코드 예제는 `SetFocusedItem` 고 `GetFocusedItem` 메서드. 코드의 이전 단원에서 다섯 개의 열을 사용 하 여 헤더 컨트롤을 생성 합니다. 그러나는 열에 표시 되지 않도록 열 구분 기호를 끌 수 있습니다. 다음 예제에서는 설정 하 고 포커스 항목으로 마지막 열 머리글을 확인 합니다.

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="sethotdivider"></a>  CHeaderCtrl::SetHotDivider

수동을 나타내기 위해 헤더 항목 간의 구분선 끌어 변경 및 헤더 항목의 삭제 합니다.

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
포인터의 위치입니다. 헤더 컨트롤에 대 한 포인터의 위치에 따라 적절 한 구분선 강조 표시 합니다.

*nIndex*<br/>
강조 표시 된 구분선의 인덱스입니다.

### <a name="return-value"></a>반환 값

강조 표시 된 구분선의 인덱스입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_SETHOTDIVIDER](/windows/desktop/Controls/hdm-sethotdivider)Windows SDK에 설명 된 대로 합니다. 헤더 항목 끌어서 놓기 지원 하기 위해 제공 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

##  <a name="setimagelist"></a>  CHeaderCtrl::SetImageList

이미지 목록과 헤더 컨트롤에 할당합니다.

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*pImageList*<br/>
에 대 한 포인터를 `CImageList` 헤더 컨트롤에 할당할 이미지 목록을 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CImageList](../../mfc/reference/cimagelist-class.md) 헤더 컨트롤에 이전에 할당 된 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_SETIMAGELIST](/windows/desktop/Controls/hdm-setimagelist)Windows SDK에 설명 된 대로 합니다. `CImageList` 개체는 반환 된 포인터가 가리키는 임시 개체 이며 다음 유휴 시간 처리에서 삭제 됩니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CHeaderCtrl::GetImageList](#getimagelist)합니다.

##  <a name="setitem"></a>  CHeaderCtrl::SetItem

헤더 컨트롤의 지정된 된 항목의 특성을 설정합니다.

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
조작 될 항목의 0부터 시작 하는 인덱스입니다.

*pHeaderItem*<br/>
에 대 한 포인터를 [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) 새 항목에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CHeaderCtrl::GetItem](#getitem)합니다.

##  <a name="setorderarray"></a>  CHeaderCtrl::SetOrderArray

헤더 컨트롤에서 항목의 왼쪽에서 오른쪽 순서를 설정합니다.

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>매개 변수

*iCount*<br/>
헤더 컨트롤 항목의 수입니다.

*piArray*<br/>
왼쪽에서 오른쪽으로 나타나는 순서로 헤더 컨트롤에서 항목의 인덱스 값을 수신 하는 버퍼의 주소에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 매크로의 동작을 구현 [HDM_SETORDERARRAY](/windows/desktop/Controls/hdm-setorderarray)Windows SDK에 설명 된 대로 합니다. 헤더 항목 순서 지정을 지원 하기 위해 제공 됩니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CHeaderCtrl::GetOrderArray](#getorderarray)합니다.

## <a name="see-also"></a>참고자료

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl 클래스](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList 클래스](../../mfc/reference/cimagelist-class.md)
