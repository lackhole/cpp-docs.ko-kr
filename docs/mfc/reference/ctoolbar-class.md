---
title: CToolBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
ms.openlocfilehash: aa49ebed2d48d9818c2d39ae4894d8caf1fbbf81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323650"
---
# <a name="ctoolbar-class"></a>CToolBar 클래스

비트맵 단추의 행과 구분 기호(선택 사항)가 있는 컨트롤 막대입니다.

## <a name="syntax"></a>구문

```
class CToolBar : public CControlBar
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CToolBar::CToolBar](#ctoolbar)|`CToolBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CToolBar::CommandToIndex](#commandtoindex)|지정 된 명령 ID 사용 하 여 단추의 인덱스를 반환합니다.|
|[CToolBar::Create](#create)|Windows 도구 모음을 만들고에 연결 된 `CToolBar` 개체입니다.|
|[CToolBar::CreateEx](#createex)|만듭니다는 `CToolBar` 포함 된 항목에 대 한 추가 스타일을 사용 하 여 개체 `CToolBarCtrl` 개체입니다.|
|[CToolBar::GetButtonInfo](#getbuttoninfo)|ID, 스타일 및 단추의 이미지 수를 검색합니다.|
|[CToolBar::GetButtonStyle](#getbuttonstyle)|단추에 대 한 스타일을 검색 합니다.|
|[CToolBar::GetButtonText](#getbuttontext)|단추에 나타나는 텍스트를 검색 합니다.|
|[CToolBar::GetItemID](#getitemid)|단추 또는 구분 기호 지정된 된 인덱스에서의 명령 ID를 반환합니다.|
|[CToolBar::GetItemRect](#getitemrect)|지정된 된 인덱스에 있는 항목의 표시 사각형을 검색합니다.|
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|기본 공용 컨트롤에 직접 액세스할 수 있습니다.|
|[CToolBar::LoadBitmap](#loadbitmap)|비트맵 단추 이미지를 포함 하는 비트맵을 로드 합니다.|
|[CToolBar::LoadToolBar](#loadtoolbar)|리소스 편집기를 사용 하 여 만든 도구 모음 리소스를 로드 합니다.|
|[CToolBar::SetBitmap](#setbitmap)|비트맵 이미지를 설정합니다.|
|[CToolBar::SetButtonInfo](#setbuttoninfo)|ID, 스타일 및 단추의 이미지 수를 설정합니다.|
|[CToolBar::SetButtons](#setbuttons)|단추 스타일 및 비트맵 내 단추 이미지의 인덱스를 설정 합니다.|
|[CToolBar::SetButtonStyle](#setbuttonstyle)|단추에 스타일을 설정 합니다.|
|[CToolBar::SetButtonText](#setbuttontext)|단추에 나타나는 텍스트를 설정 합니다.|
|[CToolBar::SetHeight](#setheight)|도구 모음의 높이 설정합니다.|
|[CToolBar::SetSizes](#setsizes)|단추와 해당 비트맵의 크기를 설정합니다.|

## <a name="remarks"></a>설명

단추는 누름 단추, 확인란 단추 또는 라디오 단추 처럼 작동할 수 있습니다. `CToolBar` 개체는 일반적으로 포함 된 멤버 클래스에서 파생 된 프레임 창 개체 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 하거나 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)합니다.

[CToolBar::GetToolBarCtrl](#gettoolbarctrl), 멤버 함수는 새 MFC 4.0 허용 도구 모음 사용자 지정 및 추가 기능에 대 한 Windows 공용 컨트롤 지원 기능을 사용할 수 있습니다. `CToolBar` 멤버 함수는 대부분의 Windows 공용 컨트롤;의 기능 제공. 그러나 호출 하는 경우 `GetToolBarCtrl`, 도구 모음 도구 모음 Windows 95/98의 특징 중 더 지정할 수 있습니다. 호출 하는 경우 `GetToolBarCtrl`에 대 한 참조를 반환 합니다를 `CToolBarCtrl` 개체입니다. 참조 [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) Windows 공용 컨트롤을 사용 하 여 도구 모음을 디자인 하는 방법에 대 한 자세한 내용은 합니다. 공용 컨트롤에 대 한 자세한 내용은 참조 하세요. [공용 컨트롤](/windows/desktop/Controls/common-controls-intro) Windows SDK에 있습니다.

Visual C++ 도구 모음을 만들려면 두 가지 방법으로 제공 합니다. 리소스 편집기를 사용 하 여 도구 모음 리소스를 만들려면 다음이 단계를 수행 합니다.

1. 도구 모음 리소스를 만듭니다.

1. `CToolBar` 개체를 생성합니다.

1. 호출 된 [만들기](#create) (또는 [CreateEx](#createex)) Windows 도구 모음을 만들고 연결 하는 함수는 `CToolBar` 개체입니다.

1. 호출 [LoadToolBar](#loadtoolbar) 도구 모음 리소스를 로드 합니다.

그렇지 않은 경우 다음이 단계를 따르세요.

1. `CToolBar` 개체를 생성합니다.

1. 호출 된 [만들기](#create) (또는 [CreateEx](#createex)) Windows 도구 모음을 만들고 연결 하는 함수는 `CToolBar` 개체입니다.

1. 호출 [LoadBitmap](#loadbitmap) 도구 모음 단추 이미지를 포함 하는 비트맵을 로드 합니다.

1. 호출 [SetButtons](#setbuttons) 단추 스타일을 설정 하는 비트맵의 이미지를 사용 하 여 각 단추를 연결 합니다.

도구 모음에서 모든 단추 이미지 각 단추에 대 한 하나의 이미지를 포함 해야 하는 하나의 비트맵에서 가져옵니다. 모든 이미지에 동일한 크기를 해야 합니다. 기본값인 16 너비가 픽셀이 고 높이가 15 픽셀인 사용 됩니다. 비트맵 이미지 나란히 여야 합니다.

`SetButtons` 함수는 컨트롤 Id 및 배열의 요소 수를 지정 하는 정수 배열에 대 한 포인터를 사용 합니다. 배열의 해당 요소를 값으로 각 단추의 ID를 설정 하 고 각 단추 비트맵에 있는 단추의 이미지의 위치를 지정 하는 이미지 인덱스를 할당 합니다. 배열 요소에 값이 있는 ID_SEPARATOR 이미지 인덱스가 없는 할당 됩니다.

비트맵의 이미지는 일반적으로 순서는 화면에 그릴 하지만 사용할 수 있습니다 합니다 [SetButtonInfo](#setbuttoninfo) 이미지 순서 및 그리기 순서 간의 관계를 변경 하는 함수입니다.

도구 모음에서 모든 단추 크기는 같습니다. 따라 기본값은 24 x 22 픽셀 *소프트웨어 디자인에 대 한 Windows 인터페이스 지침*합니다. 이미지 및 단추 차원 사이의 추가 공백 이미지 주위에 테두리를 만드는 데 사용 됩니다.

각 단추에는 하나의 이미지를 있습니다. 여러 단추 상태 및 스타일 (누름된 up, down, 사용 안 함, 사용 안 함 및 비활성화) 하나 해당 이미지에서 생성 됩니다. 비트맵 색을 사용할 수 있지만 검정 및 회색 음영으로 이미지를 사용 하 여 최상의 결과 얻을 수 있습니다.

> [!WARNING]
> `CToolBar` 최대 16 개의 색 비트맵을 지원합니다. 도구 모음 편집기에 이미지를 로드 하면 Visual Studio 자동으로 필요한 경우는 16 색 비트맵에 이미지를 변환 하 고 이미지 변환 된 경우 경고 메시지가 표시 됩니다. (이미지를 편집 하려면 외부 편집기를 사용) 하는 16 개 색을 사용 하 여 이미지를 사용 하는 경우 응용 프로그램이 예기치 않게 동작할 수 있습니다.

도구 모음 단추는 기본적으로 누름 단추를 모방 합니다. 그러나 단추 확인란 또는 라디오 단추 도구 모음 단추 모방 수도 있습니다. 확인란 단추는 세 가지 상태: checked 지워지고 비활성화 합니다. 라디오 단추 두 가지 상태: 확인 하 고 선택을 취소 합니다.

배열을 가리키는 없이 개별 단추 또는 구분 기호 스타일을 설정 하려면 호출 [GetButtonStyle](#getbuttonstyle) 스타일을 가져오고 호출 [SetButtonStyle](#setbuttonstyle) 대신 `SetButtons`합니다. `SetButtonStyle` 런타임에 단추의 스타일을 변경 하려는 경우에 가장 유용 합니다.

단추에 표시할 텍스트를 할당, 호출 [GetButtonText](#getbuttontext) 단추를 표시 한 다음 호출 하는 텍스트를 검색할 [SetButtonText](#setbuttontext) 텍스트를 설정 합니다.

확인란 단추 만들기, 스타일 TBBS_CHECKBOX 할당 또는 사용을 `CCmdUI` 개체의 `SetCheck` ON_UPDATE_COMMAND_UI 처리기에서 멤버 함수입니다. 호출 `SetCheck` 확인란 단추 누름 바뀝니다. 전달 `SetCheck` 인수를 0 선택 또는 2에 대 한 옵션을 선택 취소 1에 대 한 비활성화 합니다.

라디오 단추를 만들려면 호출을 [CCmdUI](../../mfc/reference/ccmdui-class.md) 개체의 [SetRadio](../../mfc/reference/ccmdui-class.md#setradio) ON_UPDATE_COMMAND_UI 처리기에서 멤버 함수입니다. 전달 `SetRadio` 않은 상태 또는 검사에 대 한 0이 아닌 값에 대 한 인수로 0입니다. 라디오 그룹을 함께 동작을 제공 하기 위해 모든 단추에 대 한 ON_UPDATE_COMMAND_UI 처리기 그룹에 있어야 합니다.

사용 하 여 대 한 자세한 내용은 `CToolBar`, 문서를 참조 하세요 [MFC 도구 모음 구현](../../mfc/mfc-toolbar-implementation.md) 고 [Technical Note 31: 컨트롤 막대](../../mfc/tn031-control-bars.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="commandtoindex"></a>  CToolBar::CommandToIndex

이 멤버 함수는 첫 번째 도구 모음 단추, 0 위치에서 시작 명령 ID와 일치 인덱스를 반환 `nIDFind`합니다.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>매개 변수

*nIDFind*<br/>
도구 모음 단추의 명령 ID입니다.

### <a name="return-value"></a>반환 값

단추 또는 단추가 지정 된 명령 id입니다. 없는 경우-1의 인덱스

##  <a name="create"></a>  CToolBar::Create

이 멤버 함수는 Windows 도구 모음 (자식 창)를 만들고 사용 하 여 연결 된 `CToolBar` 개체입니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
도구 모음의 부모 창에 대 한 포인터입니다.

*dwStyle*<br/>
도구 모음 스타일입니다. 지원 되는 추가 도구 모음 스타일은

- CBRS_TOP 컨트롤 막대 프레임 창의 위쪽에 있는 경우

- CBRS_BOTTOM 컨트롤 막대 프레임 창의 맨 아래에 있는 경우

- CBRS_NOALIGN 컨트롤 막대 부모 크기를 조정할 때 관계를 변경할 수 없습니다.

- CBRS_TOOLTIPS 컨트롤 막대에는 도구 설명을 표시합니다.

- CBRS_SIZE_DYNAMIC 컨트롤 막대는 동적입니다.

- CBRS_SIZE_FIXED 컨트롤 막대 고정 되어 있습니다.

- CBRS_FLOATING 컨트롤 막대는 부동입니다.

- CBRS_FLYBY 상태 표시줄 단추에 대 한 정보를 표시합니다.

- CBRS_HIDE_INPLACE 컨트롤 막대를 사용자에 게 표시 되지 않습니다.

*nID*<br/>
도구 모음의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

또한 도구 모음 높이 기본값으로 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

##  <a name="createex"></a>  CToolBar::CreateEx

Windows 도구 모음 (자식 창)을 만들고 사용 하 여 연결 하려면이 함수를 호출 합니다 `CToolBar` 개체입니다.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,
    CRect rcBorders = CRect(
    0,
    0,
    0,
    0),
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
도구 모음의 부모 창에 대 한 포인터입니다.

*dwCtrlStyle*<br/>
포함된 된 생성에 대 한 추가 스타일 [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) 개체입니다. 기본적으로이 값은 TBSTYLE_FLAT에 설정 됩니다. 도구 모음 스타일의 전체 목록은 참조 하세요 *dwStyle*합니다.

*dwStyle*<br/>
도구 모음 스타일입니다. 참조 [도구 모음 컨트롤 및 단추 스타일](/windows/desktop/Controls/toolbar-control-and-button-styles) 적절 한 스타일의 목록은 Windows SDK에 있습니다.

*rcBorders*<br/>
A [CRect](../../atl-mfc-shared/reference/crect-class.md) 도구 모음 창 테두리의 너비를 정의 하는 개체입니다. 이러한 테두리는 기본적으로 테두리가 없는 도구 모음 창에서 그 결과로 0,0,0,0으로 설정 됩니다.

*nID*<br/>
도구 모음의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

또한 도구 모음 높이 기본값으로 설정합니다.

사용 하 여 `CreateEx`, 대신 [만들기](#create)특정 스타일을 포함 된 도구 모음 컨트롤을 만드는 동안 제공 해야 하는 경우. 예를 들어, 설정 *dwCtrlStyle* TBSTYLE_FLAT를 &#124; Internet Explorer 4 도구 모음 유사한 도구 모음을 만들려면 TBSTYLE_TRANSPARENT 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

##  <a name="ctoolbar"></a>  CToolBar::CToolBar

이 멤버 함수 생성을 `CToolBar` 개체 및 기본 크기를 설정 합니다.

```
CToolBar();
```

### <a name="remarks"></a>설명

호출 된 [만들기](#create) 도구 모음 창을 만들기 위해 멤버 함수입니다.

##  <a name="getbuttoninfo"></a>  CToolBar::GetButtonInfo

이 멤버 함수는 컨트롤 ID, 스타일 및 도구 모음 단추 또는 구분 기호에서 지정한 위치에서의 이미지 인덱스를 검색 합니다. *nIndex 합니다.*

```
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
도구 모음 단추 또는 구분 기호 검색 해야 하는 정보를 가져올 인덱스입니다.

*nID*<br/>
UINT 단추의 명령 ID로 설정 되어 있는지에 대 한 참조입니다.

*nStyle*<br/>
UINT 단추의 스타일으로 설정 되어 있는지에 대 한 참조입니다.

*iImage*<br/>
비트맵 내 단추의 이미지의 인덱스에 설정 된 정수에 대 한 참조입니다.

### <a name="remarks"></a>설명

해당 값에서 참조 하는 변수에 할당 됩니다 *nID*하십시오 *nStyle*, 및 *iImage*합니다. 이미지 인덱스에 있는 모든 도구 모음 단추에 대 한 이미지를 포함 하는 비트맵 내 이미지의 위치입니다. 첫 번째 이미지는 위치 0입니다.

하는 경우 *nIndex* 구분 기호를 지정 *iImage* 구분 기호 너비 (픽셀 단위)로 설정 됩니다.

##  <a name="getbuttonstyle"></a>  CToolBar::GetButtonStyle

단추 또는 도구 모음의 구분 기호 스타일을 검색 하려면이 멤버 함수를 호출 합니다.

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스를 검색할 도구 모음 단추 또는 구분 기호 스타일입니다.

### <a name="return-value"></a>반환 값

단추 또는 지정 된 구분 기호 스타일 *nIndex*합니다.

### <a name="remarks"></a>설명

단추의 스타일 단추를 표시 하는 방법 및 사용자 입력에 응답 하는 방법을 결정 합니다. 참조 [SetButtonStyle](#setbuttonstyle) 단추 스타일의 예입니다.

##  <a name="getbuttontext"></a>  CToolBar::GetButtonText

단추에 표시 되는 텍스트를 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 텍스트의 인덱스입니다.

*rString*<br/>
에 대 한 참조를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 는 검색할 텍스트가 들어 있는 개체입니다.

### <a name="return-value"></a>반환 값

`CString` 단추 텍스트를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

이 멤버의 두 번째 폼 채우기 함수를 `CString` 문자열 텍스트를 사용 하 여 개체입니다.

##  <a name="getitemid"></a>  CToolBar::GetItemID

단추 또는 구분 기호에서 지정한 명령 ID를 반환 하는이 멤버 함수 *nIndex*합니다.

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
ID를 가진 검색할 항목의 인덱스입니다.

### <a name="return-value"></a>반환 값

단추 또는 구분 기호에서 지정한 명령 ID *nIndex*합니다.

### <a name="remarks"></a>설명

구분 기호 ID_SEPARATOR를 반환합니다.

##  <a name="getitemrect"></a>  CToolBar::GetItemRect

이 멤버 함수는 채웁니다 합니다 `RECT` 구조에 포함 된 주소의 *lpRect* 단추 또는 구분 기호에서 지정 된 좌표를 사용 하 여 *nIndex*합니다.

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 인 사각형 좌표는 (단추 또는 구분 기호) 항목의 인덱스입니다.

*lpRect*<br/>
주소를 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 항목의 좌표를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

도구 모음의 왼쪽 위 모퉁이 기준으로 픽셀 좌표는입니다.

사용 하 여 `GetItemRect` 콤보 상자나 기타 컨트롤을 사용 하 여 대체 하려는 구분 기호의 좌표를 가져오려고 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CToolBar::SetSizes](#setsizes)합니다.

##  <a name="gettoolbarctrl"></a>  CToolBar::GetToolBarCtrl

이 멤버 함수에는 기본 공용 컨트롤에 직접 액세스할 수 있습니다.

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>반환 값

`CToolBarCtrl` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

사용 하 여 `GetToolBarCtrl` Windows 도구 모음 공용 컨트롤의 기능을 활용 하 고 지원 활용 하기 위해 [CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md) 도구 모음 사용자 지정을 제공 합니다.

공용 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 [컨트롤](../../mfc/controls-mfc.md) 하 고 [공용 컨트롤](/windows/desktop/Controls/common-controls-intro) Windows SDK에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

##  <a name="loadbitmap"></a>  CToolBar::LoadBitmap

지정 된 비트맵을 로드 하려면이 멤버 함수 호출 `lpszResourceName` 또는 `nIDResource`합니다.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
로드할 비트맵의 리소스 이름에 대 한 포인터입니다.

*nIDResource*<br/>
로드할 비트맵의 리소스 ID입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

비트맵 각 도구 모음 단추에 대 한 하나의 이미지를 포함 해야 합니다. 이미지 없는 경우 표준 크기 (16 픽셀 및 15 픽셀인)의 호출 [SetSizes](#setsizes) 단추 크기와 해당 이미지를 설정 합니다.

> [!WARNING]
> `CToolBar` 최대 16 개의 색 비트맵을 지원합니다. 도구 모음 편집기에 이미지를 로드 하면 Visual Studio 자동으로 필요한 경우는 16 색 비트맵에 이미지를 변환 하 고 이미지 변환 된 경우 경고 메시지가 표시 됩니다. (이미지를 편집 하려면 외부 편집기를 사용) 하는 16 개 색을 사용 하 여 이미지를 사용 하는 경우 응용 프로그램이 예기치 않게 동작할 수 있습니다.

##  <a name="loadtoolbar"></a>  CToolBar::LoadToolBar

지정 된 도구 모음을 로드 하려면이 멤버 함수 호출 *lpszResourceName* 하거나 *nIDResource*합니다.

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
도구 모음의 로드할 리소스 이름에 대 한 포인터입니다.

*nIDResource*<br/>
로드할 리소스 ID는 도구 모음입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

참조 [도구 모음 편집기](../../windows/toolbar-editor.md) 의 도구 모음 리소스를 만드는 방법에 대 한 자세한 내용은 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CToolBar::CreateEx](#createex)합니다.

##  <a name="setbitmap"></a>  CToolBar::SetBitmap

도구 모음 비트맵 이미지를 설정 하려면이 멤버 함수를 호출 합니다.

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>매개 변수

*hbmImageWell*<br/>
도구 모음을 사용 하 여 연결 된 비트맵 이미지의 핸들입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

예를 들어 호출 `SetBitmap` 단추의 동작을 변경 하는 문서에서 작업을 수행 하는 사용자 후 비트맵 이미지를 변경할 수 있습니다.

##  <a name="setbuttoninfo"></a>  CToolBar::SetButtonInfo

단추의 명령 ID, 스타일 및 이미지 수를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
단추 또는 구분 기호 정보를 설정할의 0부터 시작 인덱스입니다.

*nID*<br/>
단추의 명령 ID에 설정 된 값입니다.

*nStyle*<br/>
새 단추 스타일입니다. 다음 단추 스타일 지원 됩니다.

- TBBS_BUTTON 표준 누름 단추 (기본값)

- TBBS_SEPARATOR 구분 기호

- TBBS_CHECKBOX 자동 확인란 단추

- TBBS_GROUP 단추 그룹의 시작을 표시

- TBBS_CHECKGROUP은 확인란 단추 그룹의 시작을 표시

- TBBS_DROPDOWN은 드롭다운 목록에서 단추를 만듭니다.

- 이미지의 크기에 없는 단추의 텍스트를 기반으로 TBBS_AUTOSIZE 단추의 너비를 계산 합니다.

- TBBS_NOPREFIX 단추 텍스트는 연관 된 액셀러레이터 키 접두사가 없습니다.

*iImage*<br/>
비트맵 내 단추의 이미지에 대 한 새 인덱스입니다.

### <a name="remarks"></a>설명

스타일 TBBS_SEPARATOR 있는 구분 기호에 대해이 함수는 구분 기호 너비를 픽셀 단위로 설정에 저장 된 값 *iImage*합니다.

> [!NOTE]
>  단추 상태를 사용 하 여 설정할 수도 있습니다는 *nStyle* 매개 변수 이지만 단추 상태에 의해 제어 됩니다 때문에 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) 처리기 상태가 사용 하 여 설정한 `SetButtonInfo` 손실 됩니다 다음 중 유휴 처리 합니다. 참조 [사용자 인터페이스 개체를 업데이트 하는 방법](../../mfc/how-to-update-user-interface-objects.md) 고 [TN031: 컨트롤 막대](../../mfc/tn031-control-bars.md) 자세한 내용은 합니다.

비트맵 이미지 및 단추에 대 한 내용은 참조는 [CToolBar](../../mfc/reference/ctoolbar-class.md) 개요 및 [CToolBar::LoadBitmap](#loadbitmap)합니다.

##  <a name="setbuttons"></a>  CToolBar::SetButtons

배열의 해당 요소에 지정 된 값을 각 도구 모음 단추의 명령 ID를 설정 하는이 멤버 함수 *lpIDArray*합니다.

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>매개 변수

*lpIDArray*<br/>
명령 Id의 배열에 대 한 포인터입니다. NULL 빈 단추를 할당할 수 있습니다.

*nIDCount*<br/>
가 가리키는 배열의 요소 수가 *lpIDArray*합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

배열의 요소에 값이 있는 ID_SEPARATOR 구분 기호는 도구 모음의 해당 위치에 생성 됩니다. 이 함수는 또한 TBBS_BUTTON TBBS_SEPARATOR, 각 구분 기호 스타일을 각 단추의 스타일을 설정 하 고 각 단추 이미지 인덱스를 지정 하 합니다. 이미지 인덱스 비트맵 내 단추의 이미지의 위치를 지정 합니다.

이 함수는 구분 기호에 대 한 이미지 인덱스를 할당 하지 않는 비트맵에는 구분 기호에 대 한 계정 필요가 없습니다. 도구 모음에 단추 위치 0에 있는 경우 1, 3 및 위치 2, 비트맵에서 위치 0, 1 및 2에 있는 이미지에서 구분 기호에 할당 된 위치 0, 1 및 3에 있는 단추 각각.

하는 경우 *lpIDArray* 가 null 인 경우이 함수에서 지정한 항목의 수에 대 한 공간을 할당 *nIDCount*합니다. 사용 하 여 [SetButtonInfo](#setbuttoninfo) 각 항목의 특성을 설정할 수 있습니다.

##  <a name="setbuttonstyle"></a>  CToolBar::SetButtonStyle

단추 또는 구분 기호 또는 그룹 단추에 스타일을 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
단추 또는 구분 기호 해당 정보를 설정 하는 인덱스입니다.

*nStyle*<br/>
단추 스타일입니다. 다음 단추 스타일 지원 됩니다.

- TBBS_BUTTON 표준 누름 단추 (기본값)

- TBBS_SEPARATOR 구분 기호

- TBBS_CHECKBOX 자동 확인란 단추

- TBBS_GROUP 단추 그룹의 시작을 표시

- TBBS_CHECKGROUP은 확인란 단추 그룹의 시작을 표시

- TBBS_DROPDOWN은 드롭다운 목록에서 단추를 만듭니다.

- 이미지의 크기에 없는 단추의 텍스트를 기반으로 TBBS_AUTOSIZE 단추의 너비를 계산 합니다.

- TBBS_NOPREFIX 단추 텍스트는 접두사가 없습니다는 액셀러레이터 키 연결

### <a name="remarks"></a>설명

단추의 스타일 단추를 표시 하는 방법 및 사용자 입력에 응답 하는 방법을 결정 합니다.

호출 하기 전에 `SetButtonStyle`를 호출 합니다 [GetButtonStyle](#getbuttonstyle) 단추 또는 구분 기호 스타일을 검색 하려면 멤버 함수입니다.

> [!NOTE]
>  단추 상태를 사용 하 여 설정할 수도 있습니다는 *nStyle* 매개 변수 이지만 단추 상태에 의해 제어 됩니다 때문에 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) 처리기 상태가 사용 하 여 설정한 `SetButtonStyle` 손실 됩니다 다음 중 유휴 처리 합니다. 참조 [사용자 인터페이스 개체를 업데이트 하는 방법](../../mfc/how-to-update-user-interface-objects.md) 고 [TN031: 컨트롤 막대](../../mfc/tn031-control-bars.md) 자세한 내용은 합니다.

##  <a name="setbuttontext"></a>  CToolBar::SetButtonText

단추 텍스트를 설정 하려면이 함수를 호출 합니다.

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
설정할 해당 텍스트는 단추의 인덱스입니다.

*lpszText*<br/>
단추에 설정할 텍스트를 가리킵니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CToolBar::GetToolBarCtrl](#gettoolbarctrl)합니다.

##  <a name="setheight"></a>  CToolBar::SetHeight

도구 모음의 높이에 지정 된 픽셀에서 값으로 설정 하는이 멤버 함수 *cyHeight*합니다.

```
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>매개 변수

*cyHeight*<br/>
도구 모음에서의 픽셀 높이입니다.

### <a name="remarks"></a>설명

호출한 후 [SetSizes](#setsizes), 표준 도구 모음의 높이 재정의 하려면이 멤버 함수를 사용 합니다. 높이 너무 작으면 아래쪽 단추가 클리핑됩니다.

이 함수를 호출 하지 않은 경우 프레임 워크를 사용 하 여 단추의 크기 도구 모음 높이 결정 합니다.

##  <a name="setsizes"></a>  CToolBar::SetSizes

도구 모음의 단추에 지정 된 픽셀에서 크기로 설정 하려면이 멤버 함수 호출 *sizeButton*합니다.

```
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>매개 변수

*sizeButton*<br/>
각 단추의 픽셀 크기입니다.

*sizeImage*<br/>
각 이미지의 픽셀 크기입니다.

### <a name="remarks"></a>설명

합니다 *sizeImage* 매개 변수는 도구 모음 비트맵 이미지의 픽셀에서 크기를 포함 해야 합니다. 차원을 *sizeButton* 를 더한 이미지 7 픽셀 너비의 추가 및 6 픽셀 높이에 추가 해야 합니다. 이 함수에는 단추에 맞게 도구 모음의 높이 설정 합니다.

따르지 않는 도구 모음에 대해서만이 멤버 함수를 호출 *소프트웨어 디자인에 대 한 Windows 인터페이스 지침* 단추와 이미지 크기에 대 한 권장 사항입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC Sample DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl 클래스](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)
