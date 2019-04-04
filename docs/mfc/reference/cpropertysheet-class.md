---
title: CPropertySheet 클래스
ms.date: 11/04/2016
f1_keywords:
- CPropertySheet
- AFXDLGS/CPropertySheet
- AFXDLGS/CPropertySheet::CPropertySheet
- AFXDLGS/CPropertySheet::AddPage
- AFXDLGS/CPropertySheet::Construct
- AFXDLGS/CPropertySheet::Create
- AFXDLGS/CPropertySheet::DoModal
- AFXDLGS/CPropertySheet::EnableStackedTabs
- AFXDLGS/CPropertySheet::EndDialog
- AFXDLGS/CPropertySheet::GetActiveIndex
- AFXDLGS/CPropertySheet::GetActivePage
- AFXDLGS/CPropertySheet::GetPage
- AFXDLGS/CPropertySheet::GetPageCount
- AFXDLGS/CPropertySheet::GetPageIndex
- AFXDLGS/CPropertySheet::GetTabControl
- AFXDLGS/CPropertySheet::MapDialogRect
- AFXDLGS/CPropertySheet::OnInitDialog
- AFXDLGS/CPropertySheet::PressButton
- AFXDLGS/CPropertySheet::RemovePage
- AFXDLGS/CPropertySheet::SetActivePage
- AFXDLGS/CPropertySheet::SetFinishText
- AFXDLGS/CPropertySheet::SetTitle
- AFXDLGS/CPropertySheet::SetWizardButtons
- AFXDLGS/CPropertySheet::SetWizardMode
- AFXDLGS/CPropertySheet::m_psh
helpviewer_keywords:
- CPropertySheet [MFC], CPropertySheet
- CPropertySheet [MFC], AddPage
- CPropertySheet [MFC], Construct
- CPropertySheet [MFC], Create
- CPropertySheet [MFC], DoModal
- CPropertySheet [MFC], EnableStackedTabs
- CPropertySheet [MFC], EndDialog
- CPropertySheet [MFC], GetActiveIndex
- CPropertySheet [MFC], GetActivePage
- CPropertySheet [MFC], GetPage
- CPropertySheet [MFC], GetPageCount
- CPropertySheet [MFC], GetPageIndex
- CPropertySheet [MFC], GetTabControl
- CPropertySheet [MFC], MapDialogRect
- CPropertySheet [MFC], OnInitDialog
- CPropertySheet [MFC], PressButton
- CPropertySheet [MFC], RemovePage
- CPropertySheet [MFC], SetActivePage
- CPropertySheet [MFC], SetFinishText
- CPropertySheet [MFC], SetTitle
- CPropertySheet [MFC], SetWizardButtons
- CPropertySheet [MFC], SetWizardMode
- CPropertySheet [MFC], m_psh
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
ms.openlocfilehash: 0e5194a356684f2ff86d74a0ed1f37f332bcffeb
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781655"
---
# <a name="cpropertysheet-class"></a>CPropertySheet 클래스

속성 시트(탭 대화 상자라고도 함)를 나타냅니다.

## <a name="syntax"></a>구문

```
class CPropertySheet : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPropertySheet::CPropertySheet](#cpropertysheet)|`CPropertySheet` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPropertySheet::AddPage](#addpage)|속성 시트에 페이지를 추가합니다.|
|[CPropertySheet::Construct](#construct)|`CPropertySheet` 개체를 생성합니다.|
|[CPropertySheet::Create](#create)|모덜리스 속성 시트를 표시합니다.|
|[CPropertySheet::DoModal](#domodal)|모달 속성 시트를 표시합니다.|
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|속성 시트를 누적 또는 스크롤 탭을 사용 하는지 여부를 나타냅니다.|
|[CPropertySheet::EndDialog](#enddialog)|속성 시트를 종료합니다.|
|[CPropertySheet::GetActiveIndex](#getactiveindex)|속성 시트의 현재 페이지의 인덱스를 검색합니다.|
|[CPropertySheet::GetActivePage](#getactivepage)|활성 페이지 개체를 반환합니다.|
|[CPropertySheet::GetPage](#getpage)|지정된 된 페이지에 대 한 포인터를 검색합니다.|
|[CPropertySheet::GetPageCount](#getpagecount)|속성 시트에 페이지 수를 검색합니다.|
|[CPropertySheet::GetPageIndex](#getpageindex)|속성 시트의 지정된 된 페이지의 인덱스를 검색합니다.|
|[CPropertySheet::GetTabControl](#gettabcontrol)|탭 컨트롤에 대 한 포인터를 검색합니다.|
|[CPropertySheet::MapDialogRect](#mapdialogrect)|사각형의 대화 상자 단위 화면 단위로 변환합니다.|
|[CPropertySheet::OnInitDialog](#oninitdialog)|속성 시트 초기화를 확대 하도록 재정의 합니다.|
|[CPropertySheet::PressButton](#pressbutton)|시뮬레이션 속성 시트에서 지정 된 단추를 선택 합니다.|
|[CPropertySheet::RemovePage](#removepage)|속성 시트에서 페이지를 제거 합니다.|
|[CPropertySheet::SetActivePage](#setactivepage)|활성 페이지 개체를 프로그래밍 방식으로 설정합니다.|
|[CPropertySheet::SetFinishText](#setfinishtext)|"마침" 단추에 대 한 텍스트를 설정합니다.|
|[CPropertySheet::SetTitle](#settitle)|속성 시트의 캡션을 설정 합니다.|
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|마법사 단추를 사용 하도록 설정 합니다.|
|[CPropertySheet::SetWizardMode](#setwizardmode)|마법사 모드를 사용 하도록 설정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPropertySheet::m_psh](#m_psh)|Windows [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2) 구조입니다. 기본 속성 시트 매개 변수에 대 한 액세스를 제공합니다.|

## <a name="remarks"></a>설명

구성 속성 시트를 `CPropertySheet` 개체와 하나 이상의 [CPropertyPage](../../mfc/reference/cpropertypage-class.md) 개체입니다. 프레임 워크는 속성 시트의 탭 인덱스와 현재 선택한 페이지를 포함 하는 영역 집합을 사용 하 여 창으로 표시 합니다. 사용자는 해당 탭을 사용 하 여 특정 페이지로 이동 합니다.

`CPropertySheet` 확장 된에 지 [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2) Windows 98 및 Windows NT 2000에 도입 된 구조입니다. 구조 추가 플래그 및 "워터 마크" 배경 비트맵을 사용 하 여 지는 멤버를 포함 합니다.

속성 시트 개체에서 이러한 새 이미지를 자동으로 표시, 색상표 및 비트맵 이미지에 대 한 유효한 값에 대 한 호출에 전달 [CPropertySheet::Construct](#construct) 또는 [CPropertySheet::CPropertySheet](#cpropertysheet).

경우에 `CPropertySheet` 에서 파생 되지 [CDialog](../../mfc/reference/cdialog-class.md)관리는 `CPropertySheet` 관리와 같은 개체가 `CDialog` 개체. 속성 시트 만들기 두 부분으로 구성 생성 해야 하는 예를 들어: 생성자를 호출 하 고 호출 [DoModal](#domodal) 모달 속성 시트 또는 [만들기](#create) 모덜리스 속성 시트에 대 한 합니다. `CPropertySheet` 두 가지 유형의 생성자에 있습니다. [CPropertySheet::Construct](#construct) 하 고 [CPropertySheet::CPropertySheet](#cpropertysheet)합니다.

생성 하는 경우는 `CPropertySheet` 개체를 일부 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 되려면 첫째 예외가 발생할 수 있습니다. 이 시트 만들어지기 전에 속성 시트의 스타일을 변경 하는 동안 시스템에서 발생 합니다. 이 예외를 방지 하려면 만들 때 다음과 같은 스타일을 설정 하는 프로그램 `CPropertySheet`:

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

다음과 같은 스타일 선택 사항이 며 첫 번째 예외를 발생 하지 않습니다.

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

다른 `Window Styles` 을 사용할 수 없습니다 및 사용 하지 마십시오.

간에 데이터를 교환를 `CPropertySheet` 개체와 외부 개체는 사용 하 여 데이터를 교환 비슷합니다는 `CDialog` 개체입니다. 중요 한 차이 속성 시트의 설정을 일반적으로 멤버 변수를 `CPropertyPage` 개체 아닌는 `CPropertySheet` 개체 자체입니다.

속성 시트를 사용자에 게는 뉴스레터를 만들거나 장치를 설정 하는 등 작업의 단계를 안내 하는 속성 페이지의 시퀀스를 사용 하 여 구성 마법사 라는 탭 대화 상자의 형식을 만들 수 있습니다. 마법사 형식의 탭 대화 상자에 속성 페이지 탭 없는 및 한 번에 하나의 속성 페이지가 표시 됩니다. 대신 뿐만 **확인** 및 **지금 적용** 단추, 마법사 종류 탭 대화 상자에는 **다시** 단추를 **다음** 또는  **마침** 단추를 **취소** 단추 및 **도움말** 단추입니다.

마법사 형식의 대화 상자를 만들려면 호출 하지만, 표준 속성 시트 만들기를 수행 하는 동일한 단계를 수행 [SetWizardMode](#setwizardmode) 를 호출 하기 전에 [DoModal](#domodal)합니다. 마법사 단추를 사용 하도록 설정 하려면 호출 [SetWizardButtons](#setwizardbuttons), 플래그를 사용 하 여 해당 함수 및 모양을 사용자 지정할 수 있습니다. 사용 하도록 설정 합니다 **완료** 단추를 호출 [SetFinishText](#setfinishtext) 사용자가 마법사의 마지막 페이지에서 작업을 수행한 후 합니다.

사용 하는 방법에 대 한 자세한 내용은 `CPropertySheet` 문서를 참조 하는 개체를 [속성 시트 및 속성 페이지](../../mfc/property-sheets-and-property-pages-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPropertySheet`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

##  <a name="addpage"></a>  CPropertySheet::AddPage

속성 시트의 오른쪽에 있는 탭을 사용 하 여 제공 된 페이지를 추가합니다.

```
void AddPage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*pPage*<br/>
속성 시트에 추가할 페이지를 가리킵니다. NULL일 수 없습니다.

### <a name="remarks"></a>설명

표시 하려면 왼쪽에서 오른쪽 순서로 속성 시트에 페이지를 추가 합니다.

`AddPage` 추가 합니다 [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) 개체는 `CPropertySheet` 개체 페이지 목록을 있지만 실제로 페이지의 창을 만들지 않습니다. 프레임 워크는 사용자가 해당 페이지를 선택할 때까지 페이지에 대 한 창 만들기를 연기 합니다.

사용 하 여 속성 페이지를 추가 하면 `AddPage`서 `CPropertySheet` 의 부모인는 `CPropertyPage`합니다. 속성 페이지에서 속성 시트의 액세스 권한을 얻으려면 호출 [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent)합니다.

호출 속성 시트 창의 생성 될 때까지 기다릴 필요는 없습니다 `AddPage`합니다. 일반적으로 호출 `AddPage` 호출 하기 전에 [DoModal](#domodal) 하거나 [Create](#create)합니다.

호출 하는 경우 `AddPage` 탭 행의 속성 페이지를 표시 한 후 새로 추가한 페이지 반영 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#129](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]

##  <a name="construct"></a>  CPropertySheet::Construct

`CPropertySheet` 개체를 생성합니다.

```
void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

void Construct(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

void Construct(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>매개 변수

*nIDCaption*<br/>
속성 시트에 사용할 캡션의 ID입니다.

*pParentWnd*<br/>
속성 시트의 부모 창에 대 한 포인터입니다. NULL 인 경우 부모 창에 응용 프로그램의 주 창이 됩니다.

*iSelectPage*<br/>
처음에 위에 표시 되도록 페이지의 인덱스입니다. 기본값은 시트에 추가할 첫 번째 페이지입니다.

*pszCaption*<br/>
속성 시트에 사용 되는 캡션을 포함 하는 문자열에 대 한 포인터입니다. NULL일 수 없습니다.

*hbmWatermark*<br/>
속성 페이지의 워터 마크 비트맵에 대 한 핸들입니다.

*hpalWatermark*<br/>
워터 마크 비트맵 및/또는 헤더 비트맵의 색상표를 처리 합니다.

*hbmHeader*<br/>
속성 페이지의 헤더 비트맵에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이미 호출 되지 않은 클래스 생성자 중 하나는 경우이 멤버 함수를 호출 합니다. 예를 들어, 호출 `Construct` 선언 하거나 배열을 할당할 때 `CPropertySheet` 개체입니다. 호출 해야 배열 경우 `Construct` 배열의 각 멤버에 대 한 합니다.

속성 시트를 표시 하려면 호출 [DoModal](#domodal) 하거나 [만들기](#create)합니다. 첫 번째 매개 변수에 포함 된 문자열 속성 시트에 대 한 캡션 표시줄에 표시 됩니다.

세 번째 또는 네 번째 프로토타입을 사용 하는 경우 워터 마크 및/또는 헤더 이미지를 자동으로 표시할 수 있습니다 `Construct`위에 나열 된, 및에 대 한 유효한 값을 전달 합니다 *hbmWatermark*합니다 *hpalWatermark* 및/또는 *hbmHeader* 매개 변수입니다.

### <a name="example"></a>예제

다음 예제에서 호출 하면 어떤 상황 `Construct`합니다.

[!code-cpp[NVC_MFCDocView#130](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]

##  <a name="cpropertysheet"></a>  CPropertySheet::CPropertySheet

`CPropertySheet` 개체를 생성합니다.

```
CPropertySheet();

explicit CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

explicit CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd = NULL,
    UINT iSelectPage = 0);

CPropertySheet(
    UINT nIDCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);

CPropertySheet(
    LPCTSTR pszCaption,
    CWnd* pParentWnd,
    UINT iSelectPage,
    HBITMAP hbmWatermark,
    HPALETTE hpalWatermark = NULL,
    HBITMAP hbmHeader = NULL);
```

### <a name="parameters"></a>매개 변수

*nIDCaption*<br/>
속성 시트에 사용할 캡션의 ID입니다.

*pParentWnd*<br/>
속성 시트의 부모 창을 가리킵니다. NULL 인 경우 부모 창에 응용 프로그램의 주 창이 됩니다.

*iSelectPage*<br/>
처음에 위에 표시 되도록 페이지의 인덱스입니다. 기본값은 시트에 추가할 첫 번째 페이지입니다.

*pszCaption*<br/>
속성 시트에 사용 되는 캡션을 포함 하는 문자열을 가리킵니다. NULL일 수 없습니다.

*hbmWatermark*<br/>
속성 시트의 배경 비트맵 핸들입니다.

*hpalWatermark*<br/>
워터 마크 비트맵 및/또는 헤더 비트맵의 색상표 핸들입니다.

*hbmHeader*<br/>
속성 페이지의 헤더 비트맵 핸들입니다.

### <a name="remarks"></a>설명

속성 시트를 표시 하려면 호출 [DoModal](#domodal) 하거나 [만들기](#create)합니다. 첫 번째 매개 변수에 포함 된 문자열 속성 시트에 대 한 캡션 표시줄에 표시 됩니다.

사용 하 여 여러 매개 변수 (예: 배열을 사용 하는 경우)에 있으면 [생성할](#construct) 대신 `CPropertySheet`합니다.

세 번째 또는 네 번째 프로토타입을 사용 하는 경우 워터 마크 및/또는 헤더 이미지를 자동으로 표시할 수 있습니다 `CPropertySheet`위의에 대 한 유효한 값을 전달 합니다 *hbmWatermark*를 *hpalWatermark*, 및 / 또는 *hbmHeader* 매개 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#131](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]

##  <a name="create"></a>  CPropertySheet::Create

모덜리스 속성 시트를 표시합니다.

```
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)-1,
    DWORD dwExStyle = 0);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
부모 창을 가리킵니다. NULL 인 경우 부모는 바탕 화면입니다.

*dwStyle*<br/>
속성 시트에 대 한 창 스타일입니다. 사용 가능한 스타일의 전체 목록은 참조 하세요 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.

*dwExStyle*<br/>
속성 시트에 대 한 확장된 창 스타일입니다. 사용 가능한 스타일의 전체 목록은 참조 하세요. [확장 창 스타일](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

### <a name="return-value"></a>반환 값

0이 아닌 속성 시트를 만들었습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

에 대 한 호출 `Create` 생성자 내에 있을 수 있습니다 또는 생성자가 호출 된 후 호출할 수 있습니다.

기본 스타일으로-1로 전달 하 여 표현 *dwStyle*, 실제로 WS_SYSMENU 됩니다&#124;WS_POPUP&#124;WS_CAPTION&#124;DS_MODALFRAME&#124;DS_CONTEXTHELP&#124;WS_VISIBLE 합니다. 기본 확장 창 스타일 0을 전달 하 여 표현 *dwExStyle*, 실제로 WS_EX_DLGMODALFRAME 됩니다.

`Create` 멤버 함수는 속성 시트를 만든 후 즉시 반환 합니다. 속성 시트를 삭제 하려면 호출 [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)합니다.

모덜리스 속성 시트에 대 한 호출을 사용 하 여 표시 `Create` 모달 속성 시트와 마찬가지로 OK, Cancel, 지금 적용 및 도움말 단추가 없는 합니다. 사용자가 원하는 단추를 만들어야 합니다.

모달 속성 시트를 표시 하려면 호출 [DoModal](#domodal) 대신 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#132](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]

[!code-cpp[NVC_MFCDocView#133](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]

##  <a name="domodal"></a>  CPropertySheet::DoModal

모달 속성 시트를 표시합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

IDOK 또는 함수에 성공 하면 IDCANCEL 그렇지 않으면 0 또는-1입니다. 속성 시트 마법사로 설정 된 경우 (참조 [SetWizardMode](#setwizardmode)), `DoModal` ID_WIZFINISH 또는 IDCANCEL을 반환 합니다.

### <a name="remarks"></a>설명

반환 값은 속성 시트를 종료 하는 컨트롤의 ID에 해당 합니다. 이 함수에서 반환 된 후 속성 시트 및 모든 페이지에 해당 하는 windows 소멸 된지 것입니다. 개체 자체는 계속 존재 합니다. 일반적으로 데이터를 검색 합니다는 [CPropertyPage](../../mfc/reference/cpropertypage-class.md) 한 후 개체 `DoModal` IDOK를 반환 합니다.

모덜리스 속성 시트를 표시 하려면 호출 [만들기](#create) 대신 합니다.

속성 페이지는 해당 대화 상자 리소스에서 만들어지면 첫째 예외를 발생할 수 있습니다. 이 페이지를 만들기 전에 필요한 스타일으로 대화 상자 리소스의 스타일을 변경 하는 속성 페이지에서 발생 합니다. 리소스는 일반적으로 읽기 전용 이기 때문에이 예외가 발생 합니다. 시스템 예외를 처리 하 고 수정된 된 리소스의 복사본을 만듭니다. 따라서 첫 번째 예외를 무시할 수 있습니다.

> [!NOTE]
>  이 예외는 비동기 예외 처리 모델을 사용 하 여 컴파일하는 경우 운영 체제에서 처리 되어야 합니다. 예외 처리 모델에 대 한 자세한 내용은 참조 하세요. [/EH (예외 처리 모델)](../../build/reference/eh-exception-handling-model.md)합니다. 이 경우에 대 한 호출을 래핑하지 마십시오 `CPropertySheet::DoModal` c + + try / catch 블록을 사용 하 여 catch 처리 하는 모든 예외를 예를 들어 `catch (...)`합니다. 이 블록에는 운영 체제 및 원인 예측할 수 없는 동작을 위한 예외를 처리 하려고 합니다. 그러나 운영 체제에 액세스 위반 예외 전달 되는 특정 예외 형식 또는 구조적된 예외 처리를 사용 하 여 처리 하는 c + + 예외를 안전 하 게 사용할 수 있습니다.

이 첫 번째 예외를 생성을 방지 하려면 수동으로 보장할 수 속성 시트에 올바른 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다. 속성 시트에 대 한 다음과 같은 스타일을 설정 해야 합니다.

- DS_3DLOOK

- DS_CONTROL

- WS_CHILD

- WS_TABSTOP

첫째 예외를 발생 하지 않고 다음과 같은 선택적 스타일을 사용할 수 있습니다.

- DS_SHELLFONT

- DS_LOCALEDIT

- WS_CLIPCHILDREN

속성 시트에 호환 되지 않기 때문에 다른 모든 Windows 스타일을 사용 하지 않도록 설정 합니다. 이 권장 사항은 확장된 스타일에 적용 되지 않습니다. 이러한 표준 스타일을 적절 하 게 설정 속성 시트를 수정할 필요가 없습니다를 첫째 예외를 생성 하는 피해 야 할 보장 됩니다.

### <a name="example"></a>예제

예를 참조 하세요 [CPropertySheet::AddPage](#addpage)합니다.

##  <a name="enablestackedtabs"></a>  CPropertySheet::EnableStackedTabs

속성 시트의 탭 행 스택 여부를 나타냅니다.

```
void EnableStackedTabs(BOOL bStacked);
```

### <a name="parameters"></a>매개 변수

*bStacked*<br/>
속성 시트에서 누적된 탭 사용 되는지 여부를 나타냅니다. 태그의 누적된 행을 사용 하지 않도록 설정 하 여 *bStacked* FALSE로 합니다.

### <a name="remarks"></a>설명

기본적으로 속성 시트에 속성 시트의 너비에 단일 행에 들어가는 것 보다 더 많은 탭 탭이 여러 행에 스택 됩니다. 호출 스택 탭 대신 스크롤 탭을 사용 하려면 `EnableStackedTabs` 사용 하 여 *bStacked* 호출 하기 전에 FALSE로 설정 [DoModal](#domodal) 하거나 [만들기](#create)합니다.

호출 해야 `EnableStackedTabs` 모달 또는 모덜리스 속성 시트를 만들 때. 이 스타일의 통합을 `CPropertySheet`-파생 클래스인 WM_CREATE 메시지 처리기를 작성 합니다. 재정의 된 버전의 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)를 호출 `EnableStackedTabs( FALSE )` 기본 클래스 구현을 호출 하기 전에 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#134](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]

##  <a name="enddialog"></a>  CPropertySheet::EndDialog

속성 시트를 종료합니다.

```
void EndDialog(int nEndID);
```

### <a name="parameters"></a>매개 변수

*nEndID*<br/>
속성 시트의 반환 값으로 사용할 식별자입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 확인, [취소] 또는 [닫기] 단추를 누를 때 프레임 워크에서 호출 됩니다. 이 멤버 함수는 이벤트가 발생 하는 경우 속성 시트를 닫아야 합니다. 호출입니다.

이 멤버 함수는 모달 대화 상자를 사용 하 여만 사용 됩니다.

### <a name="example"></a>예제

예를 참조 하세요 [CPropertySheet::PressButton](#pressbutton)합니다.

##  <a name="getactiveindex"></a>  CPropertySheet::GetActiveIndex

속성 시트 창의 현재 페이지의 인덱스 번호를 가져오고 다음에 대 한 매개 변수로 반환 된 인덱스 번호를 사용 하 여 `GetPage`입니다.

```
int GetActiveIndex() const;
```

### <a name="return-value"></a>반환 값

현재 페이지의 인덱스 번호입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CPropertySheet::GetActivePage](#getactivepage)합니다.

##  <a name="getactivepage"></a>  CPropertySheet::GetActivePage

속성 시트 창의 활성 페이지를 검색합니다.

```
CPropertyPage* GetActivePage() const;
```

### <a name="return-value"></a>반환 값

현재 페이지에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 사용 하 여 현재 페이지의 일부 작업을 수행 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#135](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]

##  <a name="getpage"></a>  CPropertySheet::GetPage

이 속성 시트에 지정된 된 페이지에 대 한 포인터를 반환합니다.

```
CPropertyPage* GetPage(int nPage) const;
```

### <a name="parameters"></a>매개 변수

*nPage*<br/>
원하는 페이지를 인덱스 0부터 시작 합니다. 0과 1 포함 속성 시트의 페이지 수보다 작아야 사이 여야 합니다.

### <a name="return-value"></a>반환 값

에 해당 하는 페이지에 대 한 포인터를 *n 페이지* 매개 변수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish)합니다.

##  <a name="getpagecount"></a>  CPropertySheet::GetPageCount

속성 시트에서 현재 페이지 수를 결정합니다.

```
int GetPageCount() const;
```

### <a name="return-value"></a>반환 값

속성 시트의 페이지 수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish)합니다.

##  <a name="getpageindex"></a>  CPropertySheet::GetPageIndex

속성 시트에 지정된 된 페이지의 인덱스 번호를 검색합니다.

```
int GetPageIndex(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*pPage*<br/>
찾을 인덱스를 사용 하 여 페이지를 가리킵니다. NULL일 수 없습니다.

### <a name="return-value"></a>반환 값

페이지의 인덱스 번호입니다.

### <a name="remarks"></a>설명

사용 예를 들어 `GetPageIndex` 인덱스를 가져오려면 페이지를 사용 하려면 [SetActivePage](#setactivepage) 하거나 [GetPage](#getpage)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CPropertySheet::GetActivePage](#getactivepage)합니다.

##  <a name="gettabcontrol"></a>  CPropertySheet::GetTabControl

탭 컨트롤에 특정 작업을 수행 하는 tab 컨트롤에 대 한 포인터를 검색 합니다 (즉,의 Api를 사용 하기 위해 [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).

```
CTabCtrl* GetTabControl() const;
```

### <a name="return-value"></a>반환 값

탭 컨트롤에 대 한 포인터입니다.

### <a name="remarks"></a>설명

예를 들어, 초기화 하는 동안 각 탭에 비트맵을 추가 하려는 경우이 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#136](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]

##  <a name="m_psh"></a>  CPropertySheet::m_psh

해당 멤버의 특성을 저장 하는 구조체 [PROPSHEETHEADER](/windows/desktop/api/prsht/ns-prsht-_propsheetheadera_v2)합니다.

### <a name="remarks"></a>설명

이 구조를 사용 하 여 사용 하 여 표시 되기 전에 하지만 생성 된 후 속성 시트의 모양을 초기화 합니다 [DoModal](#domodal) 멤버 함수입니다. 예를 들어 설정 합니다 *dwSize* 소속 `m_psh` 할 속성 시트를 원하는 크기.

해당 멤버의 목록을 포함 하 여이 구조에 대 한 자세한 내용은 Windows SDK의 PROPSHEETHEADER를 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#143](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]

##  <a name="mapdialogrect"></a>  CPropertySheet::MapDialogRect

사각형의 대화 상자 단위 화면 단위로 변환합니다.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
가리키는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 변환할 조정 대화 상자를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

대화 상자 단위 평균 너비와 높이 대화 상자의 텍스트에 사용 된 글꼴의 문자에서 파생 된 현재 대화 상자 기본 단위를 기준으로 명시 됩니다. 하나의 가로 단위는 1-4 대화 상자 기본 너비 단위 이며 세로 단위 대화 상자 기본 높이 단위의 1 / 8입니다.

합니다 [GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) Windows 함수는 시스템 글꼴에 대 한 크기 정보를 반환 하지만 DS_SETFONT 스타일 리소스 정의 파일에서 사용 하는 경우에 각 속성 시트에 대 한 다른 글꼴을 지정할 수 있습니다. 합니다 [MapDialogRect](/windows/desktop/api/winuser/nf-winuser-mapdialogrect) Windows 함수를 Windows SDK에 설명 된이 대화 상자에 대 한 적절 한 글꼴을 사용 합니다.

합니다 `MapDialogRect` 대화 상자 단위를 대체 하는 멤버 함수 *lpRect* 사용 하 여 사각형 상자 내에서 컨트롤을 배치 또는 만들기 대화 상자를 사용할 수 있도록 단위 (픽셀)를 화면.

##  <a name="oninitdialog"></a>  CPropertySheet::OnInitDialog

속성 시트 초기화 보강를 재정의 합니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>반환 값

응용 프로그램 속성 시트에 컨트롤 중 하나에 입력된 포커스를 설정 않았는지 여부를 지정 합니다. 경우 `OnInitDialog` 반환 되는 0이 아닌 경우 Windows는 속성 시트의 첫 번째 컨트롤에 입력된 포커스를을 설정 합니다. 응용 프로그램에 입력된 포커스가 속성 시트에 컨트롤 중 하나를 명시적으로 설정한 경우에 0을 반환할 수 있습니다.

### <a name="remarks"></a>설명

이 멤버 함수는 WM_INITDIALOG 메시지에 대 한 응답으로 호출 됩니다. 이 전송 하는 동안 속성 시트에는 [만들기](#create) 또는 [DoModal](#domodal) 속성 시트가 표시 되기 직전에 발생 하는 호출 합니다.

속성 시트를 초기화할 때 특수 한 처리를 수행 해야 하는 경우이 멤버 함수를 재정의 합니다. 재정의 된 버전에서는 기본 클래스를 호출 먼저 `OnInitDialog` 하지만 해당 반환 값을 무시 합니다. 일반적으로 재정의 된 멤버 함수에서 TRUE를 반환 합니다.

이 멤버 함수에 대 한 메시지 맵 항목을 필요가 없습니다.

##  <a name="pressbutton"></a>  CPropertySheet::PressButton

시뮬레이션 속성 시트에서 지정 된 단추를 선택 합니다.

```
void PressButton(int nButton);
```

### <a name="parameters"></a>매개 변수

*nButton*<br/>
n 단추: 단추를 누른 것을 식별 합니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.

- PSBTN_BACK 뒤로 단추를 선택합니다.

- PSBTN_NEXT 다음 단추를 선택합니다.

- PSBTN_FINISH "마침" 단추를 선택합니다.

- PSBTN_OK 확인 단추를 선택 합니다.

- PSBTN_APPLYNOW 지금 적용 단추를 선택합니다.

- PSBTN_CANCEL 취소 단추를 선택합니다.

- PSBTN_HELP은 도움말 단추를 선택합니다.

### <a name="remarks"></a>설명

참조 [PSM_PRESSBUTTON](/windows/desktop/Controls/psm-pressbutton) Windows SDK Pressbutton 메시지에 대 한 자세한 내용은 합니다.

에 대 한 호출 `PressButton` 보내지 않습니다 합니다 [PSN_APPLY](/windows/desktop/Controls/psn-apply) framework 속성 페이지에서 알림. 이 알림을 보내기 위해 호출할 [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#137](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]

##  <a name="removepage"></a>  CPropertySheet::RemovePage

속성 시트에서 페이지를 제거 하 고 연결 된 창을 제거 합니다.

```
void RemovePage(CPropertyPage* pPage);
void RemovePage(int nPage);
```

### <a name="parameters"></a>매개 변수

*pPage*<br/>
속성 시트에서 제거할 페이지를 가리킵니다. NULL일 수 없습니다.

*nPage*<br/>
제거할 페이지의 인덱스입니다. 0과 1 포함 속성 시트의 페이지 수보다 작아야 사이 여야 합니다.

### <a name="remarks"></a>설명

합니다 [CPropertyPage](../../mfc/reference/cpropertypage-class.md) 개체 자체의 소유자 될 때까지 제거 되지 않습니다는 `CPropertySheet` 창이 닫힙니다.

##  <a name="setactivepage"></a>  CPropertySheet::SetActivePage

활성 페이지를 변경합니다.

```
BOOL SetActivePage(int nPage);
BOOL SetActivePage(CPropertyPage* pPage);
```

### <a name="parameters"></a>매개 변수

*nPage*<br/>
설정 페이지의 인덱스입니다. 0과 1 포함 속성 시트의 페이지 수보다 작아야 사이 여야 합니다.

*pPage*<br/>
속성 시트에서 설정 페이지를 가리킵니다. 두 일 수 없습니다.

### <a name="return-value"></a>반환 값

속성 시트를 성공적으로 활성화 된 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

예를 들어, 사용 하 여 `SetActivePage` 한 페이지에 사용자의 작업에는 활성 페이지가 되 다른 페이지 발생 해야 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CPropertySheet::GetActivePage](#getactivepage)합니다.

##  <a name="setfinishtext"></a>  CPropertySheet::SetFinishText

마침 명령 단추에 텍스트를 설정합니다.

```
void SetFinishText(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
마침 명령 단추에 표시할 텍스트를 가리킵니다.

### <a name="remarks"></a>설명

호출 `SetFinishText` 마침 명령 단추에 텍스트를 표시 및 사용자가 마법사의 마지막 페이지에서 작업을 완료 한 후 다음 및 뒤로 단추를 숨깁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="settitle"></a>  CPropertySheet::SetTitle

속성 시트의 캡션 (프레임 창의 제목 표시줄에 표시 되는 텍스트)를 지정 합니다.

```
void SetTitle(
    LPCTSTR lpszText,
    UINT nStyle = 0);
```

### <a name="parameters"></a>매개 변수

*nStyle*<br/>
속성 시트의 스타일을 지정합니다. 스타일은 PSH_PROPTITLE 또는 0으로 지정 되어야 합니다. 스타일을 PSH_PROPTITLE로 설정 하면 "속성" 이라는 단어 캡션으로 지정 된 텍스트 뒤에 표시 됩니다. 예를 들어 호출 `SetTitle`"간단한 속성입니다."의 속성 시트 캡션에 하면 ("Simple", PSH_PROPTITLE)

*lpszText*<br/>
속성 시트의 제목 표시줄의 캡션으로 사용할 텍스트를 가리킵니다.

### <a name="remarks"></a>설명

기본적으로 속성 시트는 속성 시트 생성자에서 캡션 매개 변수를 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#139](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]

##  <a name="setwizardbuttons"></a>  CPropertySheet::SetWizardButtons

사용 하거나 마법사 속성 시트에서 뒤로, Next 또는 마침 단추를 사용 하지 않도록 설정 합니다.

```
void SetWizardButtons(DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
집합 함수 및 마법사 단추의 모양을 사용자 지정 하는 플래그입니다. 이 매개 변수 값의 조합일 수 있습니다.

- PSWIZB_BACK 뒤로 단추

- PSWIZB_NEXT 다음 단추

- PSWIZB_FINISH 마침 단추

- PSWIZB_DISABLEDFINISH 비활성 마침 단추

### <a name="remarks"></a>설명

호출 `SetWizardButtons` 대화 상자를 열어 후에 호출할 수 없습니다 `SetWizardButtons` 를 호출 하기 전에 [DoModal](#domodal)합니다. 일반적으로 호출 해야 `SetWizardButtons` 에서 [CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)합니다.

"마침" 단추 텍스트를 변경 하거나, 다음 숨길 하려는 경우 뒤로 단추를 한 번 호출 마법사 완료 [SetFinishText](#setfinishtext)합니다. 완료 한 다음에는 동일한 단추 공유 되는 note 합니다. 완료 된 후 또는 다음 단추 한 번에 하나만 표시할 수 있습니다.

### <a name="example"></a>예제

A `CPropertySheet` 세 개의 마법사 속성 페이지: `CStylePage`를 `CColorPage`, 및 `CShapePage`합니다.  아래 코드 조각에 설정 및 해제 하는 방법을 보여 줍니다 합니다 **다시** 하 고 **다음** 마법사 속성 페이지의 단추입니다.

[!code-cpp[NVC_MFCDocView#140](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]

[!code-cpp[NVC_MFCDocView#141](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]

[!code-cpp[NVC_MFCDocView#138](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]

##  <a name="setwizardmode"></a>  CPropertySheet::SetWizardMode

속성 페이지는 마법사를 설정합니다.

```
void SetWizardMode();
```

### <a name="remarks"></a>설명

마법사 속성 페이지의 주요 특징은 사용자 다음 사용 하 여 이동 또는 완료, 백업, 탭 대신 단추를 취소입니다.

호출 `SetWizardMode` 호출 하기 전에 [DoModal](#domodal)합니다. 호출한 후 `SetWizardMode`, `DoModal` ID_WIZFINISH ("마침" 단추를 사용 하 여 사용자가 닫을) 하는 경우 또는 IDCANCEL 반환 됩니다.

`SetWizardMode` PSH_WIZARD 플래그를 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#142](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 PROPDLG](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
