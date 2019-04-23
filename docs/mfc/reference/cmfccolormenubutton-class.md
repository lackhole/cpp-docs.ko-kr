---
title: CMFCColorMenuButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: 5fccfbca9fe8c31070f3eb9f208c09cb3722b9b9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780225"
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton 클래스

`CMFCColorMenuButton` 메뉴 명령 또는 도구 모음 단추 색 선택 대화 상자를 시작 하는 클래스를 지원 합니다.

## <a name="syntax"></a>구문

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|`CMFCColorMenuButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|사용 하도록 설정 하 고 일반 색 단추 위에 배치 되는 "자동" 단추를 사용 하지 않도록 설정 합니다. (표준 시스템 자동 단추인 **자동**.)|
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|시스템 색 대신 문서별 색 표시할 수 있습니다.|
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|사용 하도록 설정 하 고 일반 색 단추 아래에 배치 되는 "기타" 단추를 사용 하지 않도록 설정 합니다. (표준 시스템 "기타" 단추인 **다른 색**.)|
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|색 창 분리 하는 기능을 사용 하도록 설정 합니다.|
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|현재 자동 색을 검색합니다.|
|[CMFCColorMenuButton::GetColor](#getcolor)|현재 단추의 색을 검색합니다.|
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|지정한 명령 ID에 해당 하는 색을 검색 합니다.|
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|부모 창을 변경 될 때 프레임 워크에서 호출 합니다.|
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|색 선택 대화 상자를 엽니다.|
|[CMFCColorMenuButton::SetColor](#setcolor)|현재 색 단추의 색을 설정합니다.|
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|지정 된 색 메뉴 단추의 색을 설정합니다.|
|[CMFCColorMenuButton::SetColorName](#setcolorname)|지정된 된 색에 대 한 새 이름을 설정합니다.|
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|설정에 표시 되는 열의 수는 `CMFCColorBar` 개체입니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|현재 단추가 도구 모음 단추를 복사합니다.|
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|색 선택 대화 상자를 만듭니다.|
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|빈 메뉴 지원 되는지 여부를 나타냅니다.|
|[CMFCColorMenuButton::OnDraw](#ondraw)|단추에 이미지를 표시 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|이전 프레임 워크에서 호출을 `CMFCColorMenuButton` 개체는 도구 모음 사용자 지정 대화 상자의 목록에 표시 됩니다.|

## <a name="remarks"></a>설명

원래 메뉴 명령 또는 도구 모음 단추를 사용 하 여 교체할 수는 `CMFCColorMenuButton` 개체를 만듭니다를 `CMFCColorMenuButton` 개체를 모두 적절 한 설정 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 스타일 및 호출을 `ReplaceButton` 메서드의 합니다 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md) 클래스입니다. 도구 모음을 사용자 지정 하는 경우 호출 된 [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) 메서드.

색 선택 대화 상자를 처리 하는 동안 만들어집니다 합니다 [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) 이벤트 처리기입니다. 이벤트 처리기에 WM_COMMAND 메시지를 사용 하 여 부모 프레임을 알립니다. `CMFCColorMenuButton` 개체 원래 메뉴 명령 또는 도구 모음 단추에 할당 되는 컨트롤 ID를 보냅니다.

## <a name="example"></a>예제

다음 예제에는 만들고 색 메뉴 단추에서 다양 한 메서드를 사용 하 여 구성 하는 방법을 보여 줍니다.는 `CMFCColorMenuButton` 클래스입니다. 예에서를 `CPalette` 개체가 먼저 생성 되 고 다음의 개체를 생성 하는 데는 `CMFCColorMenuButton` 클래스입니다. `CMFCColorMenuButton` 그런 다음 해당 자동 및 기타 단추를 사용 하도록 설정 하 고 색 및 열 개수를 설정 하 여 개체를 구성 합니다. 이 코드는 부분을 [워드 패드 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcolormenubutton.h

##  <a name="cmfccolormenubutton"></a>  CMFCColorMenuButton::CMFCColorMenuButton

`CMFCColorMenuButton` 개체를 생성합니다.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
[in] 단추 명령 id입니다.

*lpszText*<br/>
[in] 단추 텍스트입니다.

*pPalette*<br/>
[in] 단추의 색 팔레트에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

첫 번째 생성자는 기본 생성자입니다. 개체의 현재 색 및 자동 색은 검정 RGB (0, 0, 0)으로 초기화 됩니다.

두 번째 생성자는 지정 된 명령 ID에 해당 하는 색으로 단추를 초기화 합니다.

##  <a name="copyfrom"></a>  CMFCColorMenuButton::CopyFrom

하나를 복사 [CMFCToolBarMenuButton 클래스](../../mfc/reference/cmfctoolbarmenubutton-class.md)-다른 파생 개체입니다.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
[in] 복사할 소스 단추입니다.

### <a name="remarks"></a>설명

파생 되는 개체를 복사 하려면이 메서드를 재정의 합니다 `CMFCColorMenuButton` 개체입니다.

##  <a name="createpopupmenu"></a>  CMFCColorMenuButton::CreatePopupMenu

색 선택 대화 상자를 만듭니다.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>반환 값

색 선택 대화 상자를 나타내는 개체입니다.

### <a name="remarks"></a>설명

이 메서드는 사용자가 색 메뉴 단추를 누를 때 프레임 워크에서 호출 됩니다.

##  <a name="enableautomaticbutton"></a>  CMFCColorMenuButton::EnableAutomaticButton

사용 하도록 설정 하 고 일반 색 단추 위에 배치 되는 "자동" 단추를 사용 하지 않도록 설정 합니다. (표준 시스템 자동 단추인 **자동**.)

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
[in] 단추 자동 면 표시 되는 단추 텍스트를 지정 합니다.

*colorAutomatic*<br/>
[in] 새 자동 색을 지정합니다.

*bEnable*<br/>
[in] 단추 자동 인지 여부를 지정 합니다.

### <a name="remarks"></a>설명

자동 단추는 현재 기본 색을 적용합니다.

##  <a name="enabledocumentcolors"></a>  CMFCColorMenuButton::EnableDocumentColors

시스템 색 대신 문서별 색 표시할 수 있습니다.

```
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
[in] 단추 텍스트를 지정합니다.

*bEnable*<br/>
[in] 문서에 고유한 색 또는 시스템 색을 표시 하려면 FALSE를 표시 하려면 TRUE입니다.

### <a name="remarks"></a>설명

색 메뉴 단추를 클릭할 때 현재 문서의 색 또는 시스템 색상표를 표시 하려면이 메서드를 사용 합니다.

##  <a name="enableotherbutton"></a>  CMFCColorMenuButton::EnableOtherButton

사용 하도록 설정 하 고 일반 색 단추 아래에 배치 되는 "기타" 단추를 사용 하지 않도록 설정 합니다. (표준 시스템 "기타" 단추인 **다른 색**.)

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
[in] 단추 텍스트를 지정합니다.

*bAltColorDlg*<br/>
[in] 표시 하려면 TRUE로 지정 된 `CMFCColorDialog` 대화 상자나 표준 시스템 색 대화 상자를 표시 하려면 FALSE입니다.

*bEnable*<br/>
[in] "기타" 단추를 표시 하려면 TRUE를 지정 합니다. 그렇지 않으면 FALSE입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

##  <a name="enabletearoff"></a>  CMFCColorMenuButton::EnableTearOff

색 창 분리 하는 기능을 사용 하도록 설정 합니다.

```
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
[in] 분리 막대가 창에 대 한 ID를 지정합니다.

*nVertDockColumns*<br/>
[in] 분리 상태에서 세로로 도킹된 색 창에서 열 수를 지정 합니다.

*nHorzDockRows*<br/>
[in] 분리 상태에서 가로로 도킹된 색 창에 대 한 행 수를 지정 합니다.

### <a name="remarks"></a>설명

때 표시 되는 색 창에 대 한 "분리" 기능을 사용 하도록이 메서드를 호출 합니다 `CMFCColorMenuButton` 단추가 눌러져 있습니다.

##  <a name="getautomaticcolor"></a>  CMFCColorMenuButton::GetAutomaticColor

현재 자동 색을 검색합니다.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>반환 값

현재 자동 색을 나타내는 RGB 색 값입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 하 여 설정 된 자동 색을 가져옵니다 [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)합니다.

##  <a name="getcolor"></a>  CMFCColorMenuButton::GetColor

현재 단추의 색을 검색합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>반환 값

단추의 색입니다.

### <a name="remarks"></a>설명

##  <a name="getcolorbycmdid"></a>  CMFCColorMenuButton::GetColorByCmdID

지정한 명령 ID에 해당 하는 색을 검색 합니다.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
[in] 명령 id입니다.

### <a name="return-value"></a>반환 값

지정한 명령 ID에 해당 하는 색

### <a name="remarks"></a>설명

응용 프로그램에서 여러 색 단추를 사용 해야 하는 경우이 메서드를 사용 합니다. 사용자가 색 단추를 클릭 하면 단추 명령 ID 부모 WM_COMMAND 메시지를 보냅니다. `GetColorByCmdID` 메서드를 해당 색을 검색할 때 명령 ID를 사용 합니다.

##  <a name="isemptymenuallowed"></a>  CMFCColorMenuButton::IsEmptyMenuAllowed

빈 메뉴 지원 되는지 여부를 나타냅니다.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>반환 값

비어 있는 경우 0이 아닌 메뉴 허용 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

빈 메뉴는 기본적으로 지원 됩니다. 파생된 클래스에서이 동작을 변경 하려면이 메서드를 재정의 합니다.

##  <a name="onchangeparentwnd"></a>  CMFCColorMenuButton::OnChangeParentWnd

부모 창을 변경 될 때 프레임 워크에서 호출 합니다.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 새 부모 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="ondraw"></a>  CMFCColorMenuButton::OnDraw

단추에 이미지를 표시 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 그릴 영역을 제한 하는 사각형입니다.

*pImages*<br/>
[in] 도구 모음 이미지의 목록 가리킵니다.

*bHorz*<br/>
[in] 가로 도킹 된 상태 이면 도구 모음을 지정 하려면 TRUE 그렇지 않으면 FALSE입니다. 기본값은 TRUE입니다.

*bCustomizeMode*<br/>
[in] 사용자 지정 모드에서 응용 프로그램 임을 지정. 그렇지 않으면 FALSE입니다. 기본값은 FALSE입니다.

*bHighlight*<br/>
[in] TRUE 이면는 단추를 강조 표시 됩니다. 그렇지 않으면 FALSE입니다. 기본값은 FALSE입니다.

*bDrawBorder*<br/>
[in] 단추의 테두리; 표시 되도록 지정 하려면 TRUE 그렇지 않으면 FALSE입니다. 기본값은 TRUE입니다.

*bGrayDisabledButtons*<br/>
[in] 초과 사용 안 함된 단추는 회색으로 표시 (흐리게 표시)을 지정 하려면 TRUE 그렇지 않으면 FALSE입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

##  <a name="ondrawoncustomizelist"></a>  CMFCColorMenuButton::OnDrawOnCustomizeList

이전 프레임 워크에서 호출을 `CMFCColorMenuButton` 개체는 도구 모음 사용자 지정 대화 상자의 목록에 표시 됩니다.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 단추를 그릴 수를 제한 하는 사각형입니다.

*bSelected*<br/>
[in] TRUE 단추를 선택한 상태 인지 지정 합니다. 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

단추의 너비입니다.

### <a name="remarks"></a>설명

프레임 워크에서이 메서드는 때를 `CMFCColorMenuButton` 도구 모음 사용자 지정 프로세스 중 개체 목록 상자에 표시 됩니다.

##  <a name="opencolordialog"></a>  CMFCColorMenuButton::OpenColorDialog

색 선택 대화 상자를 엽니다.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>매개 변수

*colorDefault*<br/>
[in] 색 대화 상자에서 선택한 기본 색입니다.

*colorRes*<br/>
[out] 색 대화 상자에서 사용자가 선택한 색을 반환 합니다.

### <a name="return-value"></a>반환 값

사용자가 새 색;를 선택 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

메뉴 단추를 클릭 하면 색 대화 상자를 열려면이 메서드를 호출 합니다. 반환 값은 0이 아닌, 사용자가 선택한 색에 저장 됩니다는 *colorRes* 매개 변수입니다. 사용 된 [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) 표준 색 대화 상자를 전환 하는 방법 및 [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md) 대화 상자.

##  <a name="setcolor"></a>  CMFCColorMenuButton::SetColor

현재 색 단추의 색을 설정합니다.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>매개 변수

*clr*<br/>
[in] RGB 색 값입니다.

*bNotify*<br/>
[in] 적용 되 면 TRUE를 *clr* 연결된 메뉴 단추 또는 도구 모음 단추에 대 한 매개 변수 색, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

현재 색 단추의 색을 변경 하려면이 메서드를 호출 합니다. 경우는 *bNotify* 매개 변수는 0이 아닌, 연결 된 팝업 메뉴 또는 도구 모음에는 해당 단추의 색이 지정 되는 색을 변경 합니다 *clr* 매개 변수입니다.

##  <a name="setcolorbycmdid"></a>  CMFCColorMenuButton::SetColorByCmdID

지정 된 색 메뉴 단추의 색을 설정합니다.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>매개 변수

*uiCmdID*<br/>
[in] 색 메뉴 단추를의 리소스 ID입니다.

*color*<br/>
[in] RGB 색 값입니다.

##  <a name="setcolorname"></a>  CMFCColorMenuButton::SetColorName

지정된 된 색에 대 한 새 이름을 설정합니다.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>매개 변수

*color*<br/>
[in] 이름이 변경 된 색의 RGB 값입니다.

*strName*<br/>
[in] 새 색의 이름입니다.

### <a name="remarks"></a>설명

##  <a name="setcolumnsnumber"></a>  CMFCColorMenuButton::SetColumnsNumber

색 선택 컨트롤에서 표시할 열 수를 설정 ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) 개체).

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>매개 변수

*nColumns*<br/>
[in] 표시할 열의 수입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarsCustomizeDialog 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[CMFCColorButton 클래스](../../mfc/reference/cmfccolorbutton-class.md)
