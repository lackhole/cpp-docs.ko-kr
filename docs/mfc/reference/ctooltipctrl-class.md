---
title: CToolTipCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
ms.openlocfilehash: 6055926e05f8a7f9fbecec113e859d08e6b6e636
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323676"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class

애플리케이션 도구의 용도를 설명하는 텍스트 한 줄을 표시하는 작은 팝업 창인 "도구 설명 컨트롤"의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|`CToolTipCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CToolTipCtrl::Activate](#activate)|활성화 및 도구 설명 컨트롤을 비활성화 합니다.|
|[CToolTipCtrl::AddTool](#addtool)|도구 설명 컨트롤을 사용 하 여 도구를 등록합니다.|
|[CToolTipCtrl::AdjustRect](#adjustrect)|도구 설명 컨트롤의 텍스트 간의 변환 사각형 및 해당 창의 사각형을 표시합니다.|
|[CToolTipCtrl::Create](#create)|도구 설명 컨트롤을 만들고 연결 하는 `CToolTipCtrl` 개체입니다.|
|[CToolTipCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 도구 설명 컨트롤을 만들고 연결 하는 `CToolTipCtrl` 개체입니다.|
|[CToolTipCtrl::DelTool](#deltool)|도구 설명 컨트롤에서 도구를 제거합니다.|
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|도구 설명의 크기를 검색합니다.|
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|크기, 위치 및 현재 도구 설명 컨트롤을 표시 하는 도구 설명 창의 텍스트와 같은 정보를 검색 합니다.|
|[CToolTipCtrl::GetDelayTime](#getdelaytime)|초기, 팝업 및 reshow 검색 도구에 대 한 현재 설정 되어 있는 기간 팁 제어 합니다.|
|[CToolTipCtrl::GetMargin](#getmargin)|위쪽, 왼쪽, 아래쪽 및 오른쪽 여백을 도구 팁 창에 대해 설정 된 검색 합니다.|
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|도구 설명 창이 대 한 최대 너비를 검색합니다.|
|[CToolTipCtrl::GetText](#gettext)|도구 설명 컨트롤을 도구에 대 한 유지 관리 하는 텍스트를 검색 합니다.|
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|도구 설명 창의 배경색을 검색합니다.|
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|도구 설명 창이의 텍스트 색을 검색합니다.|
|[CToolTipCtrl::GetTitle](#gettitle)|현재 도구 설명 컨트롤의 제목을 검색합니다.|
|[CToolTipCtrl::GetToolCount](#gettoolcount)|도구 설명 컨트롤에서 유지 관리 도구의 수를 검색 합니다.|
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|도구 설명 컨트롤에서 유지 관리 하는 도구에 대 한 정보를 검색 합니다.|
|[CToolTipCtrl::HitTest](#hittest)|지점에 지정 된 도구의 경계 사각형 내의 인지 여부를 테스트 합니다. 그렇다면 도구에 대 한 정보를 검색 합니다.|
|[CToolTipCtrl::Pop](#pop)|보기에서 표시 된 도구 설명 창을 제거합니다.|
|[CToolTipCtrl::Popup](#popup)|현재 도구 설명 컨트롤이 마지막 마우스 메시지의 좌표에 표시 합니다.|
|[CToolTipCtrl::RelayEvent](#relayevent)|마우스 메시지 처리에 대 한 도구 설명 컨트롤에 전달합니다.|
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|초기에 팝업을 설정 하 고 reshow 도구 설명 컨트롤에 대 한 기간입니다.|
|[CToolTipCtrl::SetMargin](#setmargin)|위쪽, 왼쪽, 아래쪽 및 오른쪽 여백을 도구 팁 창에 대 한 설정합니다.|
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|도구 설명 창이 대 한 최대 너비를 설정합니다.|
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|도구 설명 창의 배경색을 설정 합니다.|
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|도구 설명 창의 텍스트 색을 설정합니다.|
|[CToolTipCtrl::SetTitle](#settitle)|도구 설명에 표준 아이콘 및 제목 문자열을 추가합니다.|
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|도구 설명 하는 도구에 대 한 유지 관리 하는 정보를 설정 합니다.|
|[CToolTipCtrl::SetToolRect](#settoolrect)|도구에 대 한 새로운 경계 사각형을 설정합니다.|
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|도구 설명 창이의 비주얼 스타일을 설정합니다.|
|[CToolTipCtrl::Update](#update)|다시 그려져 야 현재 도구를 강제로 수행 합니다.|
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|도구에 대 한 도구 설명 텍스트를 설정합니다.|

## <a name="remarks"></a>설명

"도구"는 창의 클라이언트 영역 내에서 응용 프로그램 정의 된 사각형 영역을 자식 창 또는 컨트롤 등을 창 중 하나입니다. 도구 설명의 경우 사용자를 도구 위에 커서를 놓습니다 고 그대로 남아 있는 약 절반에 대 한 두 번째 경우에 표시 되는 대부분 숨겨져 있습니다. 도구 설명 커서 옆에 표시 하 고 사용자가 마우스 단추를 클릭 하거나 도구를 해제 하 여 커서를 이동 하면 사라집니다.

`CToolTipCtrl` 도구 설명 텍스트, 도구 설명 창이 자체의 너비 및 도구 설명의 배경색과 텍스트 색을 둘러싼 여백 너비 초기 시간 및 도구 설명의 기간을 제어 하는 기능을 제공 합니다. 단일 도구 설명 컨트롤 둘 이상의 도구에 대 한 정보를 제공할 수 있습니다.

`CToolTipCtrl` 클래스 Windows 일반적인 도구 설명 컨트롤의 기능을 제공 합니다. 이 컨트롤 (및 따라서는 `CToolTipCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.

도구 설명을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 하세요. [CFrameWnd에서 파생 되지 않은 Windows에 도구 설명을](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)합니다.

사용 하 여 대 한 자세한 내용은 `CToolTipCtrl`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md) 및 [사용 하 여 CToolTipCtrl](../../mfc/using-ctooltipctrl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="activate"></a>  CToolTipCtrl::Activate

활성화 또는 도구 설명 컨트롤을 비활성화 하려면이 함수를 호출 합니다.

```
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
도구 설명 컨트롤이 활성화 또는 비활성화 될 지 여부를 지정 합니다.

### <a name="remarks"></a>설명

하는 경우 *bActivate* 가 TRUE 인 컨트롤이 활성화 된; FALSE 인 경우 비활성화 됩니다.

도구 설명 정보를 표시 컨트롤을 사용 하 여 등록 된 도구에 커서를 가져갈 때 도구 설명 컨트롤이 활성화 되 면 활성 상태인 경우 도구 설명 정보 나타나지도 도구에 커서가 있을 때.

### <a name="example"></a>예제

  예를 참조 하세요 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.

##  <a name="addtool"></a>  CToolTipCtrl::AddTool

도구 설명 컨트롤을 사용 하 여 도구를 등록합니다.

```
BOOL AddTool(
    CWnd* pWnd,
    UINT nIDText,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);

BOOL AddTool(
    CWnd* pWnd,
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
도구가 포함 된 창에 대 한 포인터입니다.

*nIDText*<br/>
도구에 대 한 텍스트를 포함 하는 문자열 리소스의 ID입니다.

*lpRectTool*<br/>
에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 도구의 좌표가 포함 된 구조체의 경계 사각형입니다. 로 식별 되는 창의 클라이언트 영역의 왼쪽 위 모퉁이 기준으로 좌표가 *pWnd*합니다.

*nIDTool*<br/>
ID는 도구입니다.

*lpszText*<br/>
도구에 대 한 텍스트에 대 한 포인터입니다. TTN_NEEDTEXT 알림 메시지 창의 부모로 이동이 매개 변수 LPSTR_TEXTCALLBACK 값이 포함 된 경우는 *pWnd* 가리킵니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

합니다 *lpRectTool* 하 고 *nIDTool* 매개 변수는 모두 유효 해야 이거나 *lpRectTool* 가 null 인 경우 *nIDTool* 0 이어야 합니다.

도구 설명 컨트롤은 둘 이상의 도구를 사용 하 여 연결할 수 있습니다. 도구에 커서를 가져갈 때 도구 설명에 저장 된 정보가 표시 되도록 도구 설명 컨트롤을 사용 하 여 도구를 등록 하려면이 함수를 호출 합니다.

> [!NOTE]
>  사용 하 여 정적 컨트롤에 도구 설명을 설정할 수 없습니다 `AddTool`합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.

##  <a name="adjustrect"></a>  CToolTipCtrl::AdjustRect

도구 설명 컨트롤의 텍스트 간의 변환 사각형 및 해당 창의 사각형을 표시합니다.

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 도구 팁 창 사각형 또는 텍스트 표시 사각형을 보유 하는 구조입니다.

*bLarger*<br/>
TRUE 이면 *lprc* 텍스트 표시 사각형을 지정 하는 해당 창 사각형을 받습니다. FALSE 이면 *lprc* 창 사각형을 지정 하는 해당 텍스트 표시 사각형을 받습니다.

### <a name="return-value"></a>반환 값

사각형을 성공적으로 조정 되는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 해당 창의 사각형 또는 지정 된 텍스트 표시 사각형을 표시 하는 데 필요한 도구 팁 창 사각형에서 도구 설명 컨트롤의 텍스트 표시 사각형을 계산 합니다.

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_ADJUSTRECT](/windows/desktop/Controls/ttm-adjustrect)Windows SDK에 설명 된 대로 합니다.

##  <a name="create"></a>  CToolTipCtrl::Create

도구 설명 컨트롤을 만들고 연결 하는 `CToolTipCtrl` 개체입니다.

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
일반적으로 도구 설명 컨트롤의 부모 창 지정을 `CDialog`입니다. NULL이 아니어야 합니다.

*dwStyle*<br/>
도구 설명 컨트롤의 스타일을 지정합니다. 참조 된 **주의** 자세한 내용은 섹션입니다.

### <a name="return-value"></a>반환 값

0이 아닌 값을 `CToolTipCtrl` 개체가 성공적으로 만들어진이 고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CToolTipCtrl` 두 단계에서. 먼저 생성 하는 생성자를 호출 합니다 `CToolTipCtrl` 개체를 호출 `Create` 도구 설명 컨트롤을 만들고 연결 하는 `CToolTipCtrl` 개체입니다.

합니다 *dwStyle* 매개 변수 조합 될 수 있습니다 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다. 또한 도구 설명 컨트롤에는 두 가지 클래스 관련 스타일: TTS_ALWAYSTIP 및 TTS_NOPREFIX 합니다.

|스타일|의미|
|-----------|-------------|
|TTS_ALWAYSTIP|도구를 도구 설명 컨트롤의 소유자 창이 활성 또는 비활성 인지에 관계 없이 커서를 가져갈 때 도구 설명 표시 되도록 지정 합니다. 이 스타일 없이 도구 설명 컨트롤이 나타나지만 도구의 소유자 창이 활성 상태일 때 비활성 상태일 때에 없습니다.|
|TTS_NOPREFIX|이 스타일에서 앰퍼샌드 (&) 문자열에서 문자를 제거 합니다. 시스템을 방지 합니다. 도구 설명 컨트롤 TTS_NOPREFIX 스타일에 없는 경우 시스템 앰퍼샌드 문자를 텍스트 도구 설명 컨트롤에서 메뉴 항목을 모두와 동일한 문자열을 사용 하도록 응용 프로그램을 자동으로 제거 합니다.|

도구 설명 컨트롤에 컨트롤을 만들 때의 지정 여부에 관계 없이 WS_POPUP 및 WS_EX_TOOLWINDOW 창 스타일

확장된 창 스타일을 사용 하 여 도구 설명 컨트롤을 만들려면, 호출 [CToolTipCtrl::CreateEx](#createex) 대신 `Create`합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.

##  <a name="createex"></a>  CToolTipCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 된 `CToolTipCtrl` 개체입니다.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
컨트롤의 부모 창에 대 한 포인터입니다.

*dwStyle*<br/>
도구 설명 컨트롤의 스타일을 지정합니다. 참조를 **주의** 부분 [만들기](#create) 자세한 내용은 합니다.

*dwStyleEx*<br/>
만들려는 컨트롤의 확장된 스타일을 지정 합니다. 확장 된 Windows 스타일의 목록은 참조 하세요. 합니다 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK의 합니다.

### <a name="return-value"></a>반환 값

성공 하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 하 여 `CreateEx` of `Create` Windows 확장된 스타일 앞으로 지정 된 Windows 확장된 스타일을 적용할 **WS_EX_** 합니다.

##  <a name="ctooltipctrl"></a>  CToolTipCtrl::CToolTipCtrl

`CToolTipCtrl` 개체를 생성합니다.

```
CToolTipCtrl();
```

### <a name="remarks"></a>설명

호출 해야 `Create` 후 개체를 생성 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

##  <a name="deltool"></a>  CToolTipCtrl::DelTool

지정 된 도구를 제거 *pWnd* 하 고 *nIDTool* 도구 설명 컨트롤에서 지 원하는 도구의 컬렉션에서.

```
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
도구가 포함 된 창에 대 한 포인터입니다.

*nIDTool*<br/>
ID는 도구입니다.

##  <a name="getbubblesize"></a>  CToolTipCtrl::GetBubbleSize

도구 설명의 크기를 검색합니다.

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>매개 변수

*lpToolInfo*<br/>
도구 설명에 대 한 포인터 [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) 구조입니다.

### <a name="return-value"></a>반환 값

도구 설명의 크기입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETBUBBLESIZE](/windows/desktop/Controls/ttm-getbubblesize)Windows SDK에 설명 된 대로 합니다.

##  <a name="getcurrenttool"></a>  CToolTipCtrl::GetCurrentTool

크기, 위치 및 현재 도구 설명 컨트롤에서 표시 도구 설명 창의 텍스트와 같은 정보를 검색 합니다.

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*lpToolInfo*|[out] 에 대 한 포인터를 [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) 현재 도구 설명 창에 대 한 정보를 수신 하는 구조입니다.|

### <a name="return-value"></a>반환 값

정보를 성공적으로 검색 되 면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [TTM_GETCURRENTTOOL](/windows/desktop/Controls/ttm-getcurrenttool) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제는 현재 도구 설명 창에 대 한 정보를 검색합니다.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

##  <a name="getdelaytime"></a>  CToolTipCtrl::GetDelayTime

초기에 팝업을 검색 하 고 도구 설명 컨트롤에 대 한 현재 설정 기간 reshow 합니다.

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>매개 변수

*dwDuration*<br/>
기간 값을 검색할 지정 하는 플래그입니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.

- 도구 설명 창 기간 TTDT_AUTOPOP 검색 포인터가 도구의 경계 사각형 내에서 고정 되어 있는 경우 표시 됩니다.

- TTDT_INITIAL 검색 포인터를 도구 설명 창이 전에 도구의 경계 사각형 내에서 고정 되어 있어야 하는 시간의 길이 표시 됩니다.

- TTDT_RESHOW 검색 다음 도구 설명 창이 포인터가 표시 하는 데 걸리는 시간의 길이 하나의 도구에서 다른 위치로 이동 합니다.

### <a name="return-value"></a>반환 값

지정 된 지연 시간 (밀리초)

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETDELAYTIME](/windows/desktop/Controls/ttm-getdelaytime)Windows SDK에 설명 된 대로 합니다.

##  <a name="getmargin"></a>  CToolTipCtrl::GetMargin

위쪽, 왼쪽, 아래쪽 및 오른쪽 여백 도구 팁 창에 대 한 설정을 검색 합니다.

```
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
주소는 `RECT` 여백 정보를 받는 구조체입니다. 멤버는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조는 경계 사각형을 정의 하지 않습니다. 이 메시지를 목적으로 구조체 멤버는 다음과 같이 해석 됩니다.

|멤버|표현|
|------------|--------------------|
|`top`|위쪽 테두리와 픽셀에서의 도구 설명 텍스트의 위쪽 사이의 거리입니다.|
|`left`|왼쪽된 테두리와 픽셀에서 팁 텍스트의 왼쪽된 끝 사이의 거리입니다.|
|`bottom`|아래쪽 테두리와 픽셀에서 팁 텍스트의 아래쪽 사이의 거리입니다.|
|`right`|오른쪽 테두리와 픽셀에서 팁 텍스트의 오른쪽 끝 사이의 거리입니다.|

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETMARGIN](/windows/desktop/Controls/ttm-getmargin)Windows SDK에 설명 된 대로 합니다.

##  <a name="getmaxtipwidth"></a>  CToolTipCtrl::GetMaxTipWidth

도구 설명 창이 대 한 최대 너비를 검색합니다.

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>반환 값

도구 설명 창이 대 한 최대 너비입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETMAXTIPWIDTH](/windows/desktop/Controls/ttm-getmaxtipwidth)Windows SDK에 설명 된 대로 합니다.

##  <a name="gettext"></a>  CToolTipCtrl::GetText

도구 설명 컨트롤을 도구에 대 한 유지 관리 하는 텍스트를 검색 합니다.

```
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>매개 변수

*str*<br/>
에 대 한 참조를 `CString` 도구의 텍스트를 받는 개체입니다.

*pWnd*<br/>
도구가 포함 된 창에 대 한 포인터입니다.

*nIDTool*<br/>
ID는 도구입니다.

### <a name="remarks"></a>설명

합니다 *pWnd* 하 고 *nIDTool* 매개 변수는 도구를 확인 합니다. 해당 도구에 대 한 이전 호출을 통해 도구 설명 컨트롤을 사용 하 여 이전에 등록 되어 있으면 `CToolTipCtrl::AddTool`를 참조 하는 개체를 *str* 매개 변수는 도구의 텍스트를 할당 합니다.

##  <a name="gettipbkcolor"></a>  CToolTipCtrl::GetTipBkColor

도구 설명 창의 배경색을 검색합니다.

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>반환 값

A [COLORREF](/windows/desktop/gdi/colorref) 배경색을 나타내는 값입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETTIPBKCOLOR](/windows/desktop/Controls/ttm-gettipbkcolor)Windows SDK에 설명 된 대로 합니다.

##  <a name="gettiptextcolor"></a>  CToolTipCtrl::GetTipTextColor

도구 설명 창이의 텍스트 색을 검색합니다.

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>반환 값

A [COLORREF](/windows/desktop/gdi/colorref) 텍스트 색을 나타내는 값입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_GETTIPTEXTCOLOR](/windows/desktop/Controls/ttm-gettiptextcolor)Windows SDK에 설명 된 대로 합니다.

##  <a name="gettitle"></a>  CToolTipCtrl::GetTitle

현재 도구 설명 컨트롤의 제목을 검색합니다.

```
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*pttgt*|[out] 에 대 한 포인터를 [TTGETTITLE](/windows/desktop/api/commctrl/ns-commctrl-_ttgettitle) 도구 설명 컨트롤에 대 한 정보를 포함 하는 구조입니다. 이 메서드가 반환 하는 경우는 *pszTitle* 의 멤버는 [TTGETTITLE](/windows/desktop/api/commctrl/ns-commctrl-_ttgettitle) 제목의 텍스트를 가리키는 구조체입니다.|

### <a name="remarks"></a>설명

이 메서드는 전송 된 [TTM_GETTITLE](/windows/desktop/Controls/ttm-gettitle) Windows SDK에 설명 된 메시지입니다.

##  <a name="gettoolcount"></a>  CToolTipCtrl::GetToolCount

도구 설명 컨트롤을 사용 하 여 등록 된 도구 수를 검색 합니다.

```
int GetToolCount() const;
```

### <a name="return-value"></a>반환 값

도구 수가 도구 설명 컨트롤을 사용 하 여 등록 합니다.

##  <a name="gettoolinfo"></a>  CToolTipCtrl::GetToolInfo

도구 설명 컨트롤에서 유지 관리 하는 도구에 대 한 정보를 검색 합니다.

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>매개 변수

*ToolInfo*<br/>
에 대 한 참조를 `TOOLINFO` 도구의 텍스트를 받는 개체입니다.

*pWnd*<br/>
도구가 포함 된 창에 대 한 포인터입니다.

*nIDTool*<br/>
ID는 도구입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

합니다 `hwnd` 및 `uId` 의 멤버는 [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) 에서 참조 하는 구조 *CToolInfo* 도구를 식별 합니다. 해당 도구에 대 한 이전 호출을 통해 도구 설명 컨트롤을 사용 하 여 등록 되어 있으면 `AddTool`, `TOOLINFO` 구조 도구에 대 한 정보를 사용 하 여 채워집니다.

##  <a name="hittest"></a>  CToolTipCtrl::HitTest

지정 된 도구의 경계 사각형 내의 인지 여부를 확인 하 고 그렇다면 도구에 대 한 정보를 검색 하기 위한 지점을 테스트 합니다.

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
도구가 포함 된 창에 대 한 포인터입니다.

*pt*<br/>
에 대 한 포인터를 `CPoint` 테스트할 점의 좌표를 포함 하는 개체입니다.

*lpToolInfo*<br/>
에 대 한 포인터 [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) 도구에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

적중 테스트 정보를 통해 지정한 점을 도구의 경계 사각형 내에 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 0이 아닌 값을 반환 하는 경우 구조체를 가리키는 *lpToolInfo* 점이 해당 사각형 내에서 도구에 대 한 정보를 사용 하 여 채워집니다.

`TTHITTESTINFO` 구조는 다음과 같이 정의 됩니다.

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   도구의 핸들을 지정합니다.

- `pt`

   지점이 도구의의 경계 사각형 경우 한 점의 좌표를 지정 합니다.

- `ti`

   도구에 대 한 정보를 제공 합니다. 에 대 한 자세한 내용은 합니다 `TOOLINFO` 구조체를 참조 하십시오 [CToolTipCtrl::GetToolInfo](#gettoolinfo)합니다.

##  <a name="pop"></a>  CToolTipCtrl::Pop

보기에서 표시 된 도구 설명 창을 제거합니다.

```
void Pop();
```

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_POP](/windows/desktop/Controls/ttm-pop)Windows SDK에 설명 된 대로 합니다.

##  <a name="popup"></a>  CToolTipCtrl::Popup

현재 도구 설명 컨트롤이 마지막 마우스 메시지의 좌표에 표시 합니다.

```
void Popup();
```

### <a name="remarks"></a>설명

이 메서드는 전송 된 [TTM_POPUP](/windows/desktop/Controls/ttm-popup) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에는 도구 설명 창이 표시 됩니다.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

##  <a name="relayevent"></a>  CToolTipCtrl::RelayEvent

마우스 메시지 처리에 대 한 도구 설명 컨트롤에 전달합니다.

```
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*lpMsg*<br/>
에 대 한 포인터를 [MSG](/windows/desktop/api/winuser/ns-winuser-msg) 릴레이에 메시지를 포함 하는 구조입니다.

### <a name="remarks"></a>설명

도구 설명 컨트롤에서 전송한 다음 메시지만 처리 `RelayEvent`:

|WM_LBUTTONDOWN|WM_MOUSEMOVE|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>예제

  예를 참조 하세요 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.

##  <a name="setdelaytime"></a>  CToolTipCtrl::SetDelayTime

도구 설명 컨트롤에 대 한 지연 시간을 설정합니다.

```
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>매개 변수

*nDelay*<br/>
새 지연 시간을 밀리초 단위로 지정합니다.

*dwDuration*<br/>
기간 값을 검색할 지정 하는 플래그입니다. 참조 [CToolTipCtrl::GetDelayTime](#getdelaytime) 유효한 값에 대 한 합니다.

*iTime*<br/>
지정 된 지연 시간 (밀리초)입니다.

### <a name="remarks"></a>설명

지연 시간은 도구 설명 창이 나타나기 전에 도구 커서 있어야 하는 시간의 길이입니다. 기본 지연 시간은 500 밀리초입니다.

##  <a name="setmargin"></a>  CToolTipCtrl::SetMargin

위쪽, 왼쪽, 아래쪽 및 오른쪽 여백을 도구 팁 창에 대 한 설정합니다.

```
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
주소는 `RECT` 설정할 여백 정보를 포함 하는 구조입니다. 멤버는 `RECT` 구조는 경계 사각형을 정의 하지 않습니다. 참조 [CToolTipCtrl::GetMargin](#getmargin) 여백 정보에 대 한 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETMARGIN](/windows/desktop/Controls/ttm-setmargin)Windows SDK에 설명 된 대로 합니다.

##  <a name="setmaxtipwidth"></a>  CToolTipCtrl::SetMaxTipWidth

도구 설명 창이 대 한 최대 너비를 설정합니다.

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>매개 변수

*iWidth*<br/>
설정할 최대 도구 팁 창 너비입니다.

### <a name="return-value"></a>반환 값

이전 최대 설명 너비입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETMAXTIPWIDTH](/windows/desktop/Controls/ttm-setmaxtipwidth)Windows SDK에 설명 된 대로 합니다.

##  <a name="settipbkcolor"></a>  CToolTipCtrl::SetTipBkColor

도구 설명 창의 배경색을 설정 합니다.

```
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*clr*<br/>
새 배경색입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETTIPBKCOLOR](/windows/desktop/Controls/ttm-settipbkcolor)Windows SDK에 설명 된 대로 합니다.

##  <a name="settiptextcolor"></a>  CToolTipCtrl::SetTipTextColor

도구 설명 창의 텍스트 색을 설정합니다.

```
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*clr*<br/>
새 텍스트 색입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETTIPTEXTCOLOR](/windows/desktop/Controls/ttm-settiptextcolor)Windows SDK에 설명 된 대로 합니다.

##  <a name="settitle"></a>  CToolTipCtrl::SetTitle

도구 설명에 표준 아이콘 및 제목 문자열을 추가합니다.

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>매개 변수

*uIcon*<br/>
참조 *아이콘* 에 [TTM_SETTITLE](/windows/desktop/Controls/ttm-settitle) Windows SDK에 있습니다.

*lpstrTitle*<br/>
제목 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TTM_SETTITLE](/windows/desktop/Controls/ttm-settitle)Windows SDK에 설명 된 대로 합니다.

##  <a name="settoolinfo"></a>  CToolTipCtrl::SetToolInfo

도구 설명 하는 도구에 대 한 유지 관리 하는 정보를 설정 합니다.

```
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>매개 변수

*lpToolInfo*<br/>
에 대 한 포인터를 [TOOLINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtoolinfoa) 설정 정보를 지정 하는 구조입니다.

##  <a name="settoolrect"></a>  CToolTipCtrl::SetToolRect

도구에 대 한 새로운 경계 사각형을 설정합니다.

```
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
도구가 포함 된 창에 대 한 포인터입니다.

*nIDTool*<br/>
ID는 도구입니다.

*lpRect*<br/>
에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조 새 경계 사각형을 지정 합니다.

##  <a name="setwindowtheme"></a>  CToolTipCtrl::SetWindowTheme

도구 설명 창이의 비주얼 스타일을 설정합니다.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>매개 변수

*pszSubAppName*<br/>
비주얼 스타일 집합을 포함 하는 유니코드 문자열 포인터입니다.

### <a name="return-value"></a>반환 값

반환 값은 사용 되지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는의 기능을 에뮬레이션 합니다 [TTM_SETWINDOWTHEME](/windows/desktop/Controls/ttm-setwindowtheme) Windows SDK에 설명 된 대로 메시지입니다.

##  <a name="update"></a>  CToolTipCtrl::Update

다시 그려져 야 현재 도구를 강제로 수행 합니다.

```
void Update();
```

##  <a name="updatetiptext"></a>  CToolTipCtrl::UpdateTipText

이 컨트롤의이 도구에 대 한 도구 설명 텍스트를 업데이트합니다.

```
void UpdateTipText(
    LPCTSTR lpszText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);

void UpdateTipText(
    UINT nIDText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
도구에 대 한 텍스트에 대 한 포인터입니다.

*pWnd*<br/>
도구가 포함 된 창에 대 한 포인터입니다.

*nIDTool*<br/>
ID는 도구입니다.

*nIDText*<br/>
도구에 대 한 텍스트를 포함 하는 문자열 리소스의 ID입니다.

## <a name="see-also"></a>참고자료

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CToolBar 클래스](../../mfc/reference/ctoolbar-class.md)
