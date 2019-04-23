---
title: CDHtmlDialog 클래스
ms.date: 03/27/2019
f1_keywords:
- CDHtmlDialog
- AFXDHTML/CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CanAccessExternal
- AFXDHTML/CDHtmlDialog::CreateControlSite
- AFXDHTML/CDHtmlDialog::DDX_DHtml_AxControl
- AFXDHTML/CDHtmlDialog::DDX_DHtml_CheckBox
- AFXDHTML/CDHtmlDialog::DDX_DHtml_ElementText
- AFXDHTML/CDHtmlDialog::DDX_DHtml_Radio
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectIndex
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectString
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectValue
- AFXDHTML/CDHtmlDialog::DestroyModeless
- AFXDHTML/CDHtmlDialog::EnableModeless
- AFXDHTML/CDHtmlDialog::FilterDataObject
- AFXDHTML/CDHtmlDialog::GetControlDispatch
- AFXDHTML/CDHtmlDialog::GetControlProperty
- AFXDHTML/CDHtmlDialog::GetCurrentUrl
- AFXDHTML/CDHtmlDialog::GetDHtmlDocument
- AFXDHTML/CDHtmlDialog::GetDropTarget
- AFXDHTML/CDHtmlDialog::GetElement
- AFXDHTML/CDHtmlDialog::GetElementHtml
- AFXDHTML/CDHtmlDialog::GetElementInterface
- AFXDHTML/CDHtmlDialog::GetElementProperty
- AFXDHTML/CDHtmlDialog::GetElementText
- AFXDHTML/CDHtmlDialog::GetEvent
- AFXDHTML/CDHtmlDialog::GetExternal
- AFXDHTML/CDHtmlDialog::GetHostInfo
- AFXDHTML/CDHtmlDialog::GetOptionKeyPath
- AFXDHTML/CDHtmlDialog::HideUI
- AFXDHTML/CDHtmlDialog::IsExternalDispatchSafe
- AFXDHTML/CDHtmlDialog::LoadFromResource
- AFXDHTML/CDHtmlDialog::Navigate
- AFXDHTML/CDHtmlDialog::OnBeforeNavigate
- AFXDHTML/CDHtmlDialog::OnDocumentComplete
- AFXDHTML/CDHtmlDialog::OnDocWindowActivate
- AFXDHTML/CDHtmlDialog::OnFrameWindowActivate
- AFXDHTML/CDHtmlDialog::OnInitDialog
- AFXDHTML/CDHtmlDialog::OnNavigateComplete
- AFXDHTML/CDHtmlDialog::ResizeBorder
- AFXDHTML/CDHtmlDialog::SetControlProperty
- AFXDHTML/CDHtmlDialog::SetElementHtml
- AFXDHTML/CDHtmlDialog::SetElementProperty
- AFXDHTML/CDHtmlDialog::SetElementText
- AFXDHTML/CDHtmlDialog::SetExternalDispatch
- AFXDHTML/CDHtmlDialog::SetHostFlags
- AFXDHTML/CDHtmlDialog::ShowContextMenu
- AFXDHTML/CDHtmlDialog::ShowUI
- AFXDHTML/CDHtmlDialog::TranslateAccelerator
- AFXDHTML/CDHtmlDialog::TranslateUrl
- AFXDHTML/CDHtmlDialog::UpdateUI
- AFXDHTML/CDHtmlDialog::m_bUseHtmlTitle
- AFXDHTML/CDHtmlDialog::m_nHtmlResID
- AFXDHTML/CDHtmlDialog::m_pBrowserApp
- AFXDHTML/CDHtmlDialog::m_spHtmlDoc
- AFXDHTML/CDHtmlDialog::m_strCurrentUrl
- AFXDHTML/CDHtmlDialog::m_szHtmlResID
helpviewer_keywords:
- CDHtmlDialog [MFC], CDHtmlDialog
- CDHtmlDialog [MFC], CanAccessExternal
- CDHtmlDialog [MFC], CreateControlSite
- CDHtmlDialog [MFC], DDX_DHtml_AxControl
- CDHtmlDialog [MFC], DDX_DHtml_CheckBox
- CDHtmlDialog [MFC], DDX_DHtml_ElementText
- CDHtmlDialog [MFC], DDX_DHtml_Radio
- CDHtmlDialog [MFC], DDX_DHtml_SelectIndex
- CDHtmlDialog [MFC], DDX_DHtml_SelectString
- CDHtmlDialog [MFC], DDX_DHtml_SelectValue
- CDHtmlDialog [MFC], DestroyModeless
- CDHtmlDialog [MFC], EnableModeless
- CDHtmlDialog [MFC], FilterDataObject
- CDHtmlDialog [MFC], GetControlDispatch
- CDHtmlDialog [MFC], GetControlProperty
- CDHtmlDialog [MFC], GetCurrentUrl
- CDHtmlDialog [MFC], GetDHtmlDocument
- CDHtmlDialog [MFC], GetDropTarget
- CDHtmlDialog [MFC], GetElement
- CDHtmlDialog [MFC], GetElementHtml
- CDHtmlDialog [MFC], GetElementInterface
- CDHtmlDialog [MFC], GetElementProperty
- CDHtmlDialog [MFC], GetElementText
- CDHtmlDialog [MFC], GetEvent
- CDHtmlDialog [MFC], GetExternal
- CDHtmlDialog [MFC], GetHostInfo
- CDHtmlDialog [MFC], GetOptionKeyPath
- CDHtmlDialog [MFC], HideUI
- CDHtmlDialog [MFC], IsExternalDispatchSafe
- CDHtmlDialog [MFC], LoadFromResource
- CDHtmlDialog [MFC], Navigate
- CDHtmlDialog [MFC], OnBeforeNavigate
- CDHtmlDialog [MFC], OnDocumentComplete
- CDHtmlDialog [MFC], OnDocWindowActivate
- CDHtmlDialog [MFC], OnFrameWindowActivate
- CDHtmlDialog [MFC], OnInitDialog
- CDHtmlDialog [MFC], OnNavigateComplete
- CDHtmlDialog [MFC], ResizeBorder
- CDHtmlDialog [MFC], SetControlProperty
- CDHtmlDialog [MFC], SetElementHtml
- CDHtmlDialog [MFC], SetElementProperty
- CDHtmlDialog [MFC], SetElementText
- CDHtmlDialog [MFC], SetExternalDispatch
- CDHtmlDialog [MFC], SetHostFlags
- CDHtmlDialog [MFC], ShowContextMenu
- CDHtmlDialog [MFC], ShowUI
- CDHtmlDialog [MFC], TranslateAccelerator
- CDHtmlDialog [MFC], TranslateUrl
- CDHtmlDialog [MFC], UpdateUI
- CDHtmlDialog [MFC], m_bUseHtmlTitle
- CDHtmlDialog [MFC], m_nHtmlResID
- CDHtmlDialog [MFC], m_pBrowserApp
- CDHtmlDialog [MFC], m_spHtmlDoc
- CDHtmlDialog [MFC], m_strCurrentUrl
- CDHtmlDialog [MFC], m_szHtmlResID
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
ms.openlocfilehash: d53d3afb464b9dcfa32ab3cf4ee51446f8313a92
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58771827"
---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog 클래스

HTML을 사용 하는 대화 상자를 만드는 데 사용 되는 사용자 인터페이스를 구현 하는 대화 상자 리소스 대신 합니다.

## <a name="syntax"></a>구문

```
class CDHtmlDialog : public CDialog, public CDHtmlEventSink
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|CDHtmlDialog 개체를 생성합니다.|
|[CDHtmlDialog::~CDHtmlDialog](#_dtorcdhtmldialog)|CDHtmlDialog 개체를 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|재정의 라고 로드 된 페이지의 개체를 스크립팅 외부 디스패치 컨트롤 사이트에 액세스할 수 있는지를 확인 하려면 액세스 검사를 합니다. 디스패치를 스크립팅 하는 것에 대 한 안전 하지 않은 개체에 대 한 스크립팅 작업에 또는 현재 영역 수 있는지 확인 합니다.|
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|재정의 가능 대화 상자에서 WebBrowser 컨트롤을 호스트할 컨트롤 사이트 인스턴스를 만들려면 사용 합니다.|
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|멤버 변수를 HTML 페이지에서 ActiveX 컨트롤의 속성 값 사이 데이터를 교환합니다.|
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|멤버 변수 및 HTML 페이지에서 확인란을 간에 데이터를 교환 합니다.|
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|멤버 변수에서 HTML 페이지의 HTML 요소 속성 사이 데이터를 교환합니다.|
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|멤버 변수를 HTML 페이지에서 라디오 단추 사이 데이터를 교환합니다.|
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|HTML 페이지의 목록 상자 인덱스를 가져오거나 설정 합니다.|
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|HTML 페이지에서 (현재 인덱스 기반)을 목록 상자 항목의 표시 텍스트를 가져오거나 설정 합니다.|
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|HTML 페이지에서 (현재 인덱스 기반)을 목록 상자 항목의 값을 가져오거나 설정 합니다.|
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|모덜리스 대화 상자를 제거합니다.|
|[CDHtmlDialog::EnableModeless](#enablemodeless)|모덜리스 대화 상자를 사용 하도록 설정 합니다.|
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|대화 상자를 호스트 브라우저에서 생성 하는 클립보드 데이터 개체를 필터링 수 있습니다.|
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|검색 된 `IDispatch` HTML 문서에 포함 된 ActiveX 컨트롤의 인터페이스입니다.|
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|지정된 된 ActiveX 컨트롤의 요청된 된 속성을 검색합니다.|
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|현재 문서와 연결 된 Uniform Resource Locator (URL)를 검색 합니다.|
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|현재 로드 된 HTML 문서에서 IHTMLDocument2 인터페이스를 검색합니다.|
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|대안을 제공 하는 대화 상자의 수 있도록 놓기 대상으로 사용 되는 경우 포함 된 WebBrowser 컨트롤을 호출한 [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget)합니다.|
|[CDHtmlDialog::GetElement](#getelement)|HTML 요소 인터페이스를 가져옵니다.|
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|검색 된 `innerHTML` HTML 요소의 속성입니다.|
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|HTML 요소에서 요청 된 인터페이스 포인터를 검색합니다.|
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|HTML 요소의 속성의 값을 검색합니다.|
|[CDHtmlDialog::GetElementText](#getelementtext)|검색 된 `innerText` HTML 요소의 속성입니다.|
|[CDHtmlDialog::GetEvent](#getevent)|가져옵니다는 `IHTMLEventObj` 현재 이벤트 개체에 대 한 포인터입니다.|
|[CDHtmlDialog::GetExternal](#getexternal)|호스트의 가져옵니다 `IDispatch` 인터페이스입니다.|
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|호스트의 UI 기능을 검색합니다.|
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|사용자 기본 설정 저장 되는 레지스트리 키를 검색 합니다.|
|[CDHtmlDialog::HideUI](#hideui)|호스트의 UI를 숨깁니다.|
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|나타냅니다 여부를 호스트의 `IDispatch` 인터페이스는 스크립팅에 안전 합니다.|
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|WebBrowser 컨트롤에 지정된 된 리소스를 로드합니다.|
|[CDHtmlDialog::Navigate](#navigate)|지정된 된 URL로 이동합니다.|
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|탐색 이벤트가 발생 하기 전에 프레임 워크에서 호출 됩니다.|
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|문서가 READYSTATE_COMPLETE 상태가 도달한 경우 응용 프로그램에 알리기 위해 프레임 워크에서 호출 됩니다.|
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|문서 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.|
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|프레임 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.|
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|WM_INITDIALOG 메시지에 대 한 응답으로 호출 됩니다.|
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|탐색 이벤트 완료 되 면 프레임 워크에서 호출 됩니다.|
|[CDHtmlDialog::ResizeBorder](#resizeborder)|해당 테두리 공간 크기를 조정 해야 함을 개체에 경고 합니다.|
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|ActiveX 컨트롤의 속성을 새 값으로 설정합니다.|
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|집합의 `innerHTML` HTML 요소의 속성입니다.|
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|HTML 요소의 속성을 설정 합니다.|
|[CDHtmlDialog::SetElementText](#setelementtext)|집합의 `innerText` HTML 요소의 속성입니다.|
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|호스트의 설정 `IDispatch` 인터페이스입니다.|
|[CDHtmlDialog::SetHostFlags](#sethostflags)|호스트의 UI 플래그를 설정합니다.|
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|상황에 맞는 메뉴가 표시 되려고 할 때 호출 됩니다.|
|[CDHtmlDialog::ShowUI](#showui)|호스트의 UI를 보여 줍니다.|
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|메뉴 바로 가기 키 메시지를 처리 하기 위해 호출 됩니다.|
|[CDHtmlDialog::TranslateUrl](#translateurl)|로드할 URL을 수정 하기 위해 호출 됩니다.|
|[CDHtmlDialog::UpdateUI](#updateui)|명령 상태가 변경 되었음을 호스트에 알리기 위해 호출 됩니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|HTML 문서의 제목 대화 캡션으로 사용 여부를 나타냅니다.|
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|ID의 HTML 리소스를 표시 합니다.|
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|웹 브라우저 응용 프로그램에 대 한 포인터입니다.|
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|HTML 문서에 대 한 포인터입니다.|
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|현재 URL입니다.|
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|HTML 리소스 ID의 문자열 버전|

## <a name="remarks"></a>설명

`CDHtmlDialog` HTML 리소스 중 하나에서 표시 되는 HTML 또는 URL을 로드할 수 있습니다.

`CDHtmlDialog` 또한 수행할 데이터 HTML 컨트롤을 사용 하 여 exchange를 단추 클릭 등 HTML 컨트롤의 이벤트를 처리 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

`CDHtmlDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdhtml.h

##  <a name="ddx_dhtml_helper_macros"></a>  DDX_DHtml Helper Macros

DDX_DHtml 도우미 매크로는 HTML 페이지에 있는 컨트롤의 자주 사용 되는 속성에 쉽게 액세스할 수 있도록 합니다.

### <a name="data-exchange-macros"></a>데이터 교환 매크로

|||
|-|-|
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|설정 하거나 선택한 컨트롤에서 값 속성을 검색 합니다.|
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|설정 하거나 현재 요소의 시작 및 끝 태그 사이의 텍스트를 검색 합니다.|
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|설정 하거나 현재 요소의 시작 및 끝 태그 사이의 HTML을 검색 합니다.|
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|설정 하거나 대상 URL 또는 앵커 지점을 검색 합니다.|
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|설정 하거나 대상 창이 나 프레임을 검색 합니다.|
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|설정 하거나 이미지 또는 문서에서 비디오 클립의 이름을 검색 합니다.|
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|설정 하거나 연결된 된 프레임의 URL을 검색 합니다.|
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|설정 하거나 연결된 된 프레임의 URL을 검색 합니다.|

##  <a name="canaccessexternal"></a>  CDHtmlDialog::CanAccessExternal

재정의 라고 로드 된 페이지의 개체를 스크립팅 외부 디스패치 컨트롤 사이트에 액세스할 수 있는지를 확인 하려면 액세스 검사를 합니다. 디스패치를 스크립팅 하는 것에 대 한 안전 하지 않은 개체에 대 한 스크립팅 작업에 또는 현재 영역 수 있는지 확인 합니다.

```
virtual BOOL CanAccessExternal();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="cdhtmldialog"></a>  CDHtmlDialog::CDHtmlDialog

리소스를 기반으로 동적 HTML 대화 상자를 생성합니다.

```
CDHtmlDialog();

CDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID,
    CWnd *pParentWnd = NULL);

CDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd *pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름을 나타내는 null로 끝나는 문자열입니다.

*szHtmlResID*<br/>
HTML 리소스의 이름을 나타내는 null로 끝나는 문자열입니다.

*pParentWnd*<br/>
부모 또는 소유자 창 개체에 대 한 포인터 (형식의 [CWnd](../../mfc/reference/cwnd-class.md)) 대화 상자 개체 속한 합니다. NULL 인 경우 대화 상자 개체의 부모 창 주 응용 프로그램 창으로 설정 됩니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

*nHtmlResID*<br/>
HTML 리소스의 ID 번호를 포함합니다.

### <a name="remarks"></a>설명

생성자의 두 번째 형태는 템플릿 이름을 통해 대화 상자 리소스에 대 한 액세스를 제공합니다. 생성자의 세 번째 폼 리소스 템플릿의 ID 통해 대화 상자 리소스에 대 한 액세스를 제공합니다. ID로 시작 하는 일반적으로 **IDD_** 접두사입니다.

##  <a name="_dtorcdhtmldialog"></a>  CDHtmlDialog::~CDHtmlDialog

CDHtmlDialog 개체를 제거합니다.

```
virtual ~CDHtmlDialog();
```

### <a name="remarks"></a>설명

합니다 [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) 모덜리스 대화 상자에서 만든 제거할 멤버 함수를 사용 해야 [CDialog::Create](../../mfc/reference/cdialog-class.md#create)합니다.

##  <a name="createcontrolsite"></a>  CDHtmlDialog::CreateControlSite

재정의 가능 대화 상자에서 WebBrowser 컨트롤을 호스트할 컨트롤 사이트 인스턴스를 만들려면 사용 합니다.

```
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,
    COleControlSite** ppSite,
    UINT /* nID */,
    REFCLSID /* clsid */);
```

### <a name="parameters"></a>매개 변수

*pContainer*<br/>
에 대 한 포인터를 [COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md) 개체

*ppSite*<br/>
에 대 한 포인터에 대 한 포인터를 [COleControlSite](../../mfc/reference/colecontrolsite-class.md)합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용자 지정 컨트롤 사이트 클래스의 인스턴스를 반환 하려면이 멤버 함수를 재정의할 수 있습니다.

##  <a name="ddx_dhtml_axcontrol"></a>  CDHtmlDialog::DDX_DHtml_AxControl

멤버 변수를 HTML 페이지에서 ActiveX 컨트롤의 속성 값 사이 데이터를 교환합니다.

```
void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    VARIANT& var);

void DDX_DHtml_AxControl(
    CDataExchange* pDX,
    LPCTSTR szId,
    LPCTSTR szPropName,
    VARIANT& var);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*szId*<br/>
ActiveX 컨트롤의 HTML 소스에서 object 태그의 ID 매개 변수의 값입니다.

*dispId*<br/>
데이터를 교환 하려는 속성의 디스패치 ID입니다.

*szPropName*<br/>
속성의 이름입니다.

*var*<br/>
데이터 멤버 형식 변형 [COleVariant](../../mfc/reference/colevariant-class.md), 또는 [CComVariant](../../atl/reference/ccomvariant-class.md), ActiveX 컨트롤 속성을 사용 하 여 교환 하는 값을 보유 하는 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#1](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]

##  <a name="ddx_dhtml_checkbox"></a>  CDHtmlDialog::DDX_DHtml_CheckBox

멤버 변수 및 HTML 페이지에서 확인란을 간에 데이터를 교환 합니다.

```
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,
    LPCTSTR szId,
    int& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*값*<br/>
교환할 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#2](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]

##  <a name="ddx_dhtml_elementtext"></a>  CDHtmlDialog::DDX_DHtml_ElementText

멤버 변수에서 HTML 페이지의 HTML 요소 속성 사이 데이터를 교환합니다.

```
void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    CString& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    short& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    int& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    long& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    DWORD& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    float& value);

void DDX_DHtml_ElementText(
    CDataExchange* pDX,
    LPCTSTR szId,
    DISPID dispId,
    double& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*dispId*<br/>
데이터를 교환 하려는 HTML 요소의 디스패치 ID입니다.

*값*<br/>
교환할 값입니다.

##  <a name="ddx_dhtml_radio"></a>  CDHtmlDialog::DDX_DHtml_Radio

멤버 변수를 HTML 페이지에서 라디오 단추 사이 데이터를 교환합니다.

```
void DDX_DHtml_Radio(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*값*<br/>
교환할 값입니다.

##  <a name="ddx_dhtml_selectindex"></a>  CDHtmlDialog::DDX_DHtml_SelectIndex

HTML 페이지의 목록 상자 인덱스를 가져오거나 설정 합니다.

```
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,
    LPCTSTR szId,
    long& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*szId*<br/>
HTML 컨트롤의 지정 된 값 `id` 매개 변수입니다.

*값*<br/>
교환할 값입니다.

##  <a name="ddx_dhtml_selectstring"></a>  CDHtmlDialog::DDX_DHtml_SelectString

HTML 페이지에서 (현재 인덱스 기반)을 목록 상자 항목의 표시 텍스트를 가져오거나 설정 합니다.

```
void DDX_DHtml_SelectString(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*값*<br/>
교환할 값입니다.

##  <a name="ddx_dhtml_selectvalue"></a>  CDHtmlDialog::DDX_DHtml_SelectValue

HTML 페이지에서 (현재 인덱스 기반)을 목록 상자 항목의 값을 가져오거나 설정 합니다.

```
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,
    LPCTSTR szId,
    CString& value);
```

### <a name="parameters"></a>매개 변수

*pDX*<br/>
에 대 한 포인터를 [CDataExchange](../../mfc/reference/cdataexchange-class.md) 개체입니다.

*szId*<br/>
HTML 컨트롤의 ID 매개 변수에 대해 지정 된 값입니다.

*값*<br/>
교환할 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#3](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]

##  <a name="destroymodeless"></a>  CDHtmlDialog::DestroyModeless

모덜리스 대화 상자에서 분리 된 `CDHtmlDialog` 개체 및 개체를 소멸 시킵니다.

```
void DestroyModeless();
```

##  <a name="enablemodeless"></a>  CDHtmlDialog::EnableModeless

모덜리스 대화 상자를 사용 하도록 설정 합니다.

```
STDMETHOD(EnableModeless)(BOOL fEnable);
```

### <a name="parameters"></a>매개 변수

*fEnable*<br/>
참조 *fEnable* 에 [IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\)) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="filterdataobject"></a>  CDHtmlDialog::FilterDataObject

대화 상자를 호스트 브라우저에서 생성 하는 클립보드 데이터 개체를 필터링 수 있습니다.

```
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,
    IDataObject** ppDORet);
```

### <a name="parameters"></a>매개 변수

*pDO*<br/>
참조 *pDO* 에 [IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\)) Windows SDK에 있습니다.

*ppDORet*<br/>
참조 *ppDORet* 에서 `IDocHostUIHandler::FilterDataObject` Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

S_FALSE 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="getcontroldispatch"></a>  CDHtmlDialog::GetControlDispatch

검색 된 `IDispatch` 에서 반환 되는 HTML 문서에 포함 된 ActiveX 컨트롤의 인터페이스 [GetDHtmlDocument](#getdhtmldocument)합니다.

```
HRESULT GetControlDispatch(
    LPCTSTR szId,
    IDispatch** ppdisp);
```

### <a name="parameters"></a>매개 변수

*szId*<br/>
ActiveX 컨트롤의 HTML ID입니다.

*ppdisp*<br/>
`IDispatch` 인터페이스 컨트롤의 경우 웹 페이지에서 찾을 수 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="getcontrolproperty"></a>  CDHtmlDialog::GetControlProperty

지정된 된 ActiveX 컨트롤의 요청된 된 속성을 검색합니다.

```
VARIANT GetControlProperty(
    LPCTSTR szId,
    LPCTSTR szPropName);

VARIANT GetControlProperty(
    LPCTSTR szId,
    DISPID dispId);

VARIANT GetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId);
```

### <a name="parameters"></a>매개 변수

*szId*<br/>
ActiveX 컨트롤의 HTML ID입니다.

*szPropName*<br/>
현재 사용자의 기본 로캘로 속성의 이름입니다.

*pdispControl*<br/>
`IDispatch` ActiveX 컨트롤의 포인터입니다.

*dispId*<br/>
속성의 디스패치 ID입니다.

### <a name="return-value"></a>반환 값

컨트롤 또는 속성을 찾을 수 없는 경우 요청된 된 속성 또는 비어 있는 변수를 포함 하는 variant입니다.

### <a name="remarks"></a>설명

오버 로드는 맨 위에 있는 효율성이에서 가장 효율적인 아래쪽에 나열 됩니다.

##  <a name="getcurrenturl"></a>  CDHtmlDialog::GetCurrentUrl

현재 문서와 연결 된 Uniform Resource Locator (URL)를 검색 합니다.

```
void GetCurrentUrl(CString& szUrl);
```

### <a name="parameters"></a>매개 변수

*szUrl*<br/>
A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 검색 하는 URL을 포함 하는 개체입니다.

##  <a name="getdhtmldocument"></a>  CDHtmlDialog::GetDHtmlDocument

검색 된 [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) 현재 로드 된 HTML 문서에 대 한 인터페이스입니다.

```
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```

### <a name="parameters"></a>매개 변수

*\*\*pphtmlDoc* HTML 문서에 대 한 포인터에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다. 성공 하면 S_OK를 반환 합니다.

##  <a name="getdroptarget"></a>  CDHtmlDialog::GetDropTarget

대안을 제공 하는 대화 상자의 수 있도록 놓기 대상으로 사용 되는 경우 포함 된 WebBrowser 컨트롤을 호출한 [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget)합니다.

```
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,
    IDropTarget** ppDropTarget);
```

### <a name="parameters"></a>매개 변수

*pDropTarget*<br/>
참조 *pDropTarget* 에 [IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\)) Windows SDK에 있습니다.

*ppDropTarget*<br/>
참조 *ppDropTarget* 에서 `IDocHostUIHandler::GetDropTarget` Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="getelement"></a>  CDHtmlDialog::GetElement

지정 된 HTML 요소에 대해 인터페이스를 반환 *szElementId*합니다.

```
HRESULT GetElement(
    LPCTSTR szElementId,
    IDispatch** ppdisp,
    BOOL* pbCollection = NULL);

HRESULT GetElement(
    LPCTSTR szElementId,
    IHTMLElement** pphtmlElement);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*ppdisp*<br/>
`IDispatch` 요청 된 요소 또는 요소의 컬렉션에 대 한 포인터입니다.

*pbCollection*<br/>
가 나타내는 개체가 있는지 여부를 나타내는 부울 값 *ppdisp* 단일 요소 또는 요소의 컬렉션입니다.

*pphtmlElement*<br/>
`IHTMLElement` 요청된 된 요소에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

조건에는 있을 수 있습니다 지정된 된 ID 사용 하 여 둘 이상의 요소를 처리 하는 경우 첫 번째 오버 로드를 사용 합니다. 컬렉션 또는 단일 항목에 반환된 된 인터페이스 포인터 인지 확인 하려면 마지막 매개 변수를 사용할 수 있습니다. 인터페이스 포인터를 컬렉션에 있으면 쿼리할 수 있습니다 합니다 `IHTMLElementCollection` 사용 하 여 해당 `item` 순서에 따라 요소를 참조 하는 속성입니다.

두 번째 오버 로드 페이지에서 동일한 ID 가진 요소가 둘 이상 있으면 실패 합니다.

##  <a name="getelementhtml"></a>  CDHtmlDialog::GetElementHtml

검색 된 `innerHTML` 속성으로 식별 되는 HTML 요소의 *szElementId*합니다.

```
BSTR GetElementHtml(LPCTSTR szElementId);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

### <a name="return-value"></a>반환 값

합니다 `innerHTML` 속성으로 식별 되는 HTML 요소의 *szElementId* 또는 요소를 찾을 수 없는 경우 NULL입니다.

##  <a name="getelementinterface"></a>  CDHtmlDialog::GetElementInterface

으로 식별 되는 HTML 요소에서 요청 된 인터페이스 포인터를 검색 *szElementId*합니다.

```
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,
    Q** ppvObj);

HRESULT GetElementInterface(
    LPCTSTR szElementId,
    REFIID refiid,
    void** ppvObj);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*ppvObj*<br/>
주소는 요소가 없으면 요청 된 인터페이스 포인터를 사용 하 여 채울 수 있는 포인터와 쿼리 성공 합니다.

*refiid*<br/>
요청된 된 인터페이스의 ID (IID) 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#4](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]

##  <a name="getelementproperty"></a>  CDHtmlDialog::GetElementProperty

로 식별 된 속성의 값을 가져옵니다 *dispId* 으로 식별 되는 HTML 요소에서 *szElementId*합니다.

```
VARIANT GetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*dispId*<br/>
속성의 디스패치 ID입니다.

### <a name="return-value"></a>반환 값

값 속성 또는 속성 또는 요소를 찾을 수 없는 경우 비어 있는 변수입니다.

##  <a name="getelementtext"></a>  CDHtmlDialog::GetElementText

검색 된 `innerText` 속성으로 식별 되는 HTML 요소의 *szElementId*합니다.

```
BSTR GetElementText(LPCTSTR szElementId);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

### <a name="return-value"></a>반환 값

합니다 `innerText` 속성으로 식별 되는 HTML 요소의 *szElementId* 또는 속성이 나 요소를 찾을 수 없는 경우 NULL입니다.

##  <a name="getevent"></a>  CDHtmlDialog::GetEvent

반환 된 `IHTMLEventObj` 현재 이벤트 개체에 대 한 포인터입니다.

```
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```

### <a name="parameters"></a>매개 변수

*ppEventObj*<br/>
채워집니다는 포인터의 주소는 `IHTMLEventObj` 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

DHTML 이벤트 처리기 내에서이 함수에서 호출할 수만 있습니다.

##  <a name="getexternal"></a>  CDHtmlDialog::GetExternal

호스트의 가져옵니다 `IDispatch` 인터페이스입니다.

```
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```

### <a name="parameters"></a>매개 변수

*ppDispatch*<br/>
참조 *ppDispatch* 에 [IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\)) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL이 성공 또는 실패 시 S_OK를 반환합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="gethostinfo"></a>  CDHtmlDialog::GetHostInfo

호스트의 UI 기능을 검색합니다.

```
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```

### <a name="parameters"></a>매개 변수

*pInfo*<br/>
참조 *pInfo* 에 [IDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\)) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="getoptionkeypath"></a>  CDHtmlDialog::GetOptionKeyPath

사용자 기본 설정 저장 되는 레지스트리 키를 검색 합니다.

```
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,
    DWORD dw);
```

### <a name="parameters"></a>매개 변수

*pchKey*<br/>
참조 *pchKey* 에 [IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\)) Windows SDK에 있습니다.

*dw*<br/>
참조 *dw* 에서 `IDocHostUIHandler::GetOptionKeyPath` Windows SDK에에서 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="hideui"></a>  CDHtmlDialog::HideUI

호스트의 UI를 숨깁니다.

```
STDMETHOD(HideUI)(void);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="isexternaldispatchsafe"></a>  CDHtmlDialog::IsExternalDispatchSafe

나타냅니다 여부를 호스트의 `IDispatch` 인터페이스는 스크립팅에 안전 합니다.

```
virtual BOOL IsExternalDispatchSafe();
```

### <a name="return-value"></a>반환 값

FALSE 반환.

##  <a name="loadfromresource"></a>  CDHtmlDialog::LoadFromResource

DHTML 대화 상자에서 WebBrowser 컨트롤에 지정된 된 리소스를 로드합니다.

```
BOOL LoadFromResource(LPCTSTR lpszResource);
BOOL LoadFromResource(UINT nRes);
```

### <a name="parameters"></a>매개 변수

*lpszResource*<br/>
로드할 리소스의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*nRes*<br/>
로드할 리소스의 ID입니다.

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

##  <a name="m_busehtmltitle"></a>  CDHtmlDialog::m_bUseHtmlTitle

HTML 문서의 제목 대화 캡션으로 사용 여부를 나타냅니다.

```
BOOL m_bUseHtmlTitle;
```

### <a name="remarks"></a>설명

하는 경우 **m**_ **bUseHtmlTitle** 가 TRUE 인 대화 상자 캡션을 HTML 문서의 제목을 집합입니다. 그렇지 않으면 대화 상자 리소스의 캡션을 사용 합니다.

##  <a name="m_nhtmlresid"></a>  CDHtmlDialog::m_nHtmlResID

ID의 HTML 리소스를 표시 합니다.

```
UINT m_nHtmlResID;
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#5](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]

##  <a name="m_pbrowserapp"></a>  CDHtmlDialog::m_pBrowserApp

웹 브라우저 응용 프로그램에 대 한 포인터입니다.

```
CComPtr <IWebBrowser2> m_pBrowserApp;
```

##  <a name="m_sphtmldoc"></a>  CDHtmlDialog::m_spHtmlDoc

HTML 문서에 대 한 포인터입니다.

```
CComPtr<IHTMLDocument2> m_spHtmlDoc;
```

##  <a name="m_strcurrenturl"></a>  CDHtmlDialog::m_strCurrentUrl

현재 URL입니다.

```
CString m_strCurrentUrl;
```

##  <a name="m_szhtmlresid"></a>  CDHtmlDialog::m_szHtmlResID

HTML 리소스 ID의 문자열 버전

```
LPTSTR m_szHtmlResID;
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCHtmlHttp#6](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]

##  <a name="navigate"></a>  CDHtmlDialog::Navigate

지정 된 URL로 식별 되는 리소스를 이동할 *lpszURL*합니다.

```
void Navigate(
    LPCTSTR lpszURL,
    DWORD dwFlags = 0,
    LPCTSTR lpszTargetFrameName = NULL,
    LPCTSTR lpszHeaders = NULL,
    LPVOID lpvPostData = NULL,
    DWORD dwPostDataLen = 0);
```

### <a name="parameters"></a>매개 변수

*lpszURL*<br/>
대상 URL이 포함 된 문자열에 대 한 포인터입니다.

*dwFlags*<br/>
리소스 기록 목록에 추가할지 여부를, 캐시에 읽기 또는 쓰기 캐시에서 것인지 및 리소스를 새 창에 표시할지 여부를 지정 하는 변수는 플래그입니다. 변수에서 정의 된 값의 조합 수를 [BrowserNavConstants](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768360\(v=vs.85\)) 열거형입니다.

*lpszTargetFrameName*<br/>
리소스를 표시 하는 프레임의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*lpszHeaders*<br/>
서버에 보낼 HTTP 헤더를 지정 하는 값에 대 한 포인터입니다. 이러한 헤더는 기본 Internet Explorer 헤더에 추가 됩니다. 헤더, 서버 또는 상태 코드에 전달 되는 데이터 형식의 서버의 필요한 작업 등의 정보가 지정할 수 있습니다. 이 매개 변수는 URL을 HTTP URL이 아닙니다.

*lpvPostData*<br/>
HTTP POST 트랜잭션과 보낼 데이터에 대 한 포인터입니다. 예를 들어 HTML 형식에서 수집 된 데이터를 보낼 POST 트랜잭션이 사용 됩니다. 이 매개 변수는 모든 게시 데이터를 지정 하지 않는 경우 `Navigate` 는 HTTP GET 트랜잭션을 실행 합니다. 이 매개 변수는 URL을 HTTP URL이 아닙니다.

*dwPostDataLen*<br/>
HTTP POST 트랜잭션과 보낼 데이터입니다. 예를 들어 HTML 형식에서 수집 된 데이터를 보낼 POST 트랜잭션이 사용 됩니다. 이 매개 변수는 모든 게시 데이터를 지정 하지 않는 경우 `Navigate` 는 HTTP GET 트랜잭션을 실행 합니다. 이 매개 변수는 URL을 HTTP URL이 아닙니다.

##  <a name="onbeforenavigate"></a>  CDHtmlDialog::OnBeforeNavigate

이동 하기 전에 발생 시키는 이벤트를 발생 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
`IDispatch` 개체에 대한 포인터입니다.

*szUrl*<br/>
이동 URL이 포함 된 문자열에 대 한 포인터입니다.

##  <a name="ondocumentcomplete"></a>  CDHtmlDialog::OnDocumentComplete

문서가 READYSTATE_COMPLETE 상태가 달성 하는 경우 응용 프로그램에 알리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
`IDispatch` 개체에 대한 포인터입니다.

*szUrl*<br/>
탐색 된 URL이 포함 된 문자열에 대 한 포인터입니다.

##  <a name="ondocwindowactivate"></a>  CDHtmlDialog::OnDocWindowActivate

문서 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.

```
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>매개 변수

*fActivate*<br/>
참조 *fActivate* 에 [IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\)) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="onframewindowactivate"></a>  CDHtmlDialog::OnFrameWindowActivate

프레임 창이 활성화 또는 비활성화 하는 경우 프레임 워크에서 호출 됩니다.

```
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```

### <a name="parameters"></a>매개 변수

*fActivate*<br/>
참조 *fActivate* 에 [IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\)) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="oninitdialog"></a>  CDHtmlDialog::OnInitDialog

WM_INITDIALOG 메시지에 대 한 응답으로 호출 됩니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>반환 값

기본 구현에서는 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 전송 하는 동안 대화 상자에는 `Create`, `CreateIndirect`, 또는 `DoModal` 대화 상자가 표시 됩니다 직전에 발생 하는 호출 합니다.

대화 상자 초기화 될 때 특수 한 처리를 수행 해야 하는 경우이 멤버 함수를 재정의 합니다. 재정의 된 버전에서는 기본 클래스를 호출 먼저 `OnInitDialog` 하지만 해당 반환 값을 무시 합니다. 일반적으로 재정의 된 멤버 함수에서 TRUE를 반환 합니다.

Windows 호출을 `OnInitDialog` 에 메시지 맵을 통해 따라서 않아도 메시지 맵 항목을이 멤버 함수에 대 한 것이 아니라 모든 Microsoft Foundation Class 라이브러리 대화 상자에 공통적인 표준 전역 대화 상자 프로시저를 통해 작동 합니다.

##  <a name="onnavigatecomplete"></a>  CDHtmlDialog::OnNavigateComplete

지정된 된 URL에 대 한 탐색이 완료 된 후 프레임 워크에서 호출 됩니다.

```
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,
    LPCTSTR szUrl);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
`IDispatch` 개체에 대한 포인터입니다.

*szUrl*<br/>
탐색 된 URL이 포함 된 문자열에 대 한 포인터입니다.

##  <a name="resizeborder"></a>  CDHtmlDialog::ResizeBorder

해당 테두리 공간 크기를 조정 해야 함을 개체에 경고 합니다.

```
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fRameWindow);
```

### <a name="parameters"></a>매개 변수

*prcBorder*<br/>
참조 *prcBorder* 에 [IDocHostUIHandler::ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\)) Windows SDK에 있습니다.

*pUIWindow*<br/>
참조 *pUIWindow* 에서 `IDocHostUIHandler::ResizeBorder` Windows SDK에 있습니다.

*fFrameWindow*<br/>
참조 *fFrameWindow* 에서 `IDocHostUIHandler::ResizeBorder` Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

##  <a name="setcontrolproperty"></a>  CDHtmlDialog::SetControlProperty

ActiveX 컨트롤의 속성을 새 값으로 설정합니다.

```
void SetControlProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    IDispatch* pdispControl,
    DISPID dispId,
    VARIANT* pVar);

void SetControlProperty(
    LPCTSTR szElementId,
    LPCTSTR szPropName,
    VARIANT* pVar);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
ActiveX 컨트롤의 HTML ID입니다.

*dispId*<br/>
설정할 속성의 디스패치 ID입니다.

*pVar*<br/>
새 속성 값을 포함 하는 VARIANT에 대 한 포인터입니다.

*pdispControl*<br/>
ActiveX 컨트롤에 대 한 포인터 `IDispatch` 인터페이스입니다.

*szPropName*<br/>
설정할 속성의 이름을 포함 하는 문자열입니다.

##  <a name="setelementhtml"></a>  CDHtmlDialog::SetElementHtml

집합의 `innerHTML` HTML 요소의 속성입니다.

```
void SetElementHtml(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementHtml(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*bstrText*<br/>
`innerHTML` 속성의 새 값입니다.

*punkElem*<br/>
`IUnknown` HTML 요소의 포인터입니다.

##  <a name="setelementproperty"></a>  CDHtmlDialog::SetElementProperty

HTML 요소의 속성을 설정 합니다.

```
void SetElementProperty(
    LPCTSTR szElementId,
    DISPID dispId,
    VARIANT* pVar);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*dispId*<br/>
설정할 속성의 디스패치 ID입니다.

*pVar*<br/>
속성의 새 값입니다.

##  <a name="setelementtext"></a>  CDHtmlDialog::SetElementText

집합의 `innerText` HTML 요소의 속성입니다.

```
void SetElementText(
    LPCTSTR szElementId,
    BSTR bstrText);

void SetElementText(
    IUnknown* punkElem,
    BSTR bstrText);
```

### <a name="parameters"></a>매개 변수

*szElementId*<br/>
HTML 요소의 ID입니다.

*bstrText*<br/>
`innerText` 속성의 새 값입니다.

*punkElem*<br/>
`IUnknown` HTML 요소의 포인터입니다.

##  <a name="setexternaldispatch"></a>  CDHtmlDialog::SetExternalDispatch

호스트의 설정 `IDispatch` 인터페이스입니다.

```
void SetExternalDispatch(IDispatch* pdispExternal);
```

### <a name="parameters"></a>매개 변수

*pdispExternal*<br/>
새 `IDispatch` 인터페이스입니다.

##  <a name="sethostflags"></a>  CDHtmlDialog::SetHostFlags

호스트 UI 플래그를 설정합니다.

```
void SetHostFlags(DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
가능한 값을 참조 하세요 [DOCHOSTUIFLAG](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753277\(v=vs.85\)) Windows SDK에 있습니다.

##  <a name="showcontextmenu"></a>  CDHtmlDialog::ShowContextMenu

상황에 맞는 메뉴가 표시 되려고 할 때 호출 됩니다.

```
STDMETHOD(ShowContextMenu)(
    DWORD dwID,
    POINT* ppt,
    IUnknown* pcmdtReserved,
    IDispatch* pdispReserved);
```

### <a name="parameters"></a>매개 변수

*dwID*<br/>
참조 *dwID* 에 [IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\)) Windows SDK에 있습니다.

*ppt*<br/>
참조 *ppt* 에서 `IDocHostUIHandler::ShowContextMenu` Windows SDK에에서 있습니다.

*pcmdtReserved*<br/>
참조 *pcmdtReserved* 에서 `IDocHostUIHandler::ShowContextMenu` Windows SDK에 있습니다.

*pdispReserved*<br/>
참조 *pdispReserved* 에서 `IDocHostUIHandler::ShowContextMenu` Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

S_FALSE 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="showui"></a>  CDHtmlDialog::ShowUI

호스트의 UI를 보여 줍니다.

```
STDMETHOD(ShowUI)(
    DWORD dwID,
    IOleInPlaceActiveObject* pActiveObject,
    IOleCommandTarget* pCommandTarget,
    IOleInPlaceFrame* pFrame,
    IOleInPlaceUIWindow* pDoc);
```

### <a name="parameters"></a>매개 변수

*dwID*<br/>
참조 *dwID* 에 [IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\)) Windows SDK에 있습니다.

*pActiveObject*<br/>
참조 *d pActiveObject* 에서 `IDocHostUIHandler::ShowUI` Windows SDK에 있습니다.

*pCommandTarget*<br/>
참조 *pCommandTarget* 에서 `IDocHostUIHandler::ShowUI` Windows SDK에 있습니다.

*pFrame*<br/>
참조 *pFrame* 에서 `IDocHostUIHandler::ShowUI` Windows SDK에 있습니다.

*pDoc*<br/>
참조 *입력* 에서 `IDocHostUIHandler::ShowUI` Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

S_FALSE 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="translateaccelerator"></a>  CDHtmlDialog::TranslateAccelerator

메뉴 바로 가기 키 메시지를 처리 하기 위해 호출 됩니다.

```
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,
    const GUID* pguidCmdGroup,
    DWORD nCmdID);
```

### <a name="parameters"></a>매개 변수

*lpMsg*<br/>
참조 *lpMsg* 에 [IDocHostUIHandler::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\)) Windows SDK에 있습니다.

*pguidCmdGroup*<br/>
참조 *pguidCmdGroup* 에서 `IDocHostUIHandler::TranslateAccelerator` Windows SDK에 있습니다.

*nCmdID*<br/>
참조 *nCmdID* 에서 `IDocHostUIHandler::TranslateAccelerator` Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

S_FALSE 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="translateurl"></a>  CDHtmlDialog::TranslateUrl

로드할 URL을 수정 하기 위해 호출 됩니다.

```
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,
    OLECHAR* pchURLIn,
    OLECHAR** ppchURLOut);
```

### <a name="parameters"></a>매개 변수

*dwTranslate*<br/>
참조 *dwTranslate* 에 [IDocHostUIHandler::TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\)) Windows SDK에 있습니다.

*pchURLIn*<br/>
참조 *pchURLIn* 에서 `IDocHostUIHandler::TranslateUrl` Windows SDK에 있습니다.

*ppchURLOut*<br/>
참조 *ppchURLOut* 에서 `IDocHostUIHandler::TranslateUrl` Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

S_FALSE 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

##  <a name="updateui"></a>  CDHtmlDialog::UpdateUI

명령 상태가 변경 되었음을 호스트에 알리기 위해 호출 됩니다.

```
STDMETHOD(UpdateUI)(void);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

이 멤버 함수는 CDHtmlDialog의 구현의 [IDocHostUIHandler::UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))Windows SDK에 설명 된 대로 합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 DHtmlExplore](../../overview/visual-cpp-samples.md)<br/>
[DDX_DHtml 도우미 매크로](#ddx_dhtml_helper_macros)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
