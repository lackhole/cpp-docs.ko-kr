---
title: 복합 컨트롤 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
ms.openlocfilehash: fb41134de21cc030ae4e96360cad67222026ce4d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278412"
---
# <a name="composite-control-global-functions"></a>복합 컨트롤 전역 함수

이러한 함수는 만들고 호스트 하 고 ActiveX 컨트롤 라이선스 획득 한 대화 상자 만들기에 대 한 지원을 제공 합니다.

> [!IMPORTANT]
>  다음 표에 나열 된 함수를 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|사용자가 제공한 대화 상자 템플릿에서 모달 대화 상자를 만듭니다. 대화 상자가 열리면 ActiveX 컨트롤을 포함할 수 있습니다.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|사용자가 제공한 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다. 대화 상자가 열리면 ActiveX 컨트롤을 포함할 수 있습니다.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX 컨트롤을 만들고, 초기화, 지정 된 창에서 호스트 및 컨트롤에서 인터페이스 포인터를 (또는 포인터)를 검색 합니다.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|사용이 허가 된 ActiveX 컨트롤을 만듭니다, 그리고 초기화, 지정 된 창에서 호스트 및 컨트롤에서 인터페이스 포인터를 (또는 포인터)를 검색 합니다.|
|[AtlAxAttachControl](#atlaxattachcontrol)|지정한 창에 이전에 만든 컨트롤을 연결합니다.|
|[AtlAxGetHost](#atlaxgethost)|지정한 창 (있는 경우)에 대 한 컨테이너에 직접 인터페이스 포인터를 가져오는 데 해당 핸들을 지정 합니다.|
|[AtlAxGetControl](#atlaxgetcontrol)|지정한 창 (있는 경우) 내에 포함 된 컨트롤에 직접 인터페이스 포인터를 가져오는 데 해당 핸들을 지정 합니다.|
|[AtlSetChildSite](#atlsetchildsite)|초기화는 `IUnknown` 자식 사이트의.|
|[AtlAxWinInit](#atlaxwininit)|AxWin 개체에 대 한 호스팅 코드를 초기화합니다.|
|[AtlAxWinTerm](#atlaxwinterm)|AxWin 개체에 대 한 호스팅 코드를 초기화 하지 않습니다.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|개체의 기본 소스 인터페이스에 대 한 정보를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** atlhost.h

##  <a name="atlaxdialogbox"></a>  AtlAxDialogBox

사용자가 제공한 대화 상자 템플릿에서 모달 대화 상자를 만듭니다.

```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
[in] 해당 실행 파일 대화 상자 템플릿이 포함 된 모듈의 인스턴스를 식별 합니다.

*lpTemplateName*<br/>
[in] 대화 상자 템플릿을 식별합니다. 이 매개 변수는 대화 상자 템플릿의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터 이거나 대화 상자 템플릿의 리소스 식별자를 지정 하는 정수 값입니다. 매개 변수는 리소스 식별자를 지정 하는 경우 경우 상위 워드가 0 이어야 합니다 하 고 해당 하위 단어는 식별자가 있어야 합니다. 사용할 수는 [MAKEINTRESOURCE](/windows/desktop/api/winuser/nf-winuser-makeintresourcea) 매크로이 값을 생성 합니다.

*hWndParent*<br/>
[in] 대화 상자를 소유 하는 창을 식별 합니다.

*lpDialogProc*<br/>
[in] 대화 상자 프로시저를 가리킵니다. 대화 상자 프로시저에 대 한 자세한 내용은 참조 하세요. [DialogProc](/windows/desktop/api/winuser/nc-winuser-dlgproc)합니다.

*dwInitParam*<br/>
[in] 대화 상자에 전달할 값을 지정 합니다 *lParam* WM_INITDIALOG 메시지의 매개 변수입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

사용 하 `AtlAxDialogBox` ActiveX 컨트롤이 포함 된 대화 상자 템플릿을 사용으로 올바른 APPID, CLSID, URL 문자열을 지정 합니다 *텍스트* 필드를 **컨트롤** 섹션 대화 상자 리소스의 함께 " AtlAxWin80 "로 합니다 *클래스 이름* 동일한 섹션에서 필드입니다. 다음 어떤 올바른 방법을 보여 줍니다 **제어** 섹션은 다음과 같을 수 있습니다.

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

리소스 스크립트 편집에 대 한 자세한 내용은 참조 하세요. [방법: 리소스 스크립트 파일을 텍스트 형식으로 열기](../../windows/how-to-open-a-resource-script-file-in-text-format.md)합니다. 컨트롤 리소스 정의 문에 대 한 자세한 내용은 참조 하세요. [공통 제어 매개 변수](/windows/desktop/menurc/common-control-parameters) Windows SDK에서: SDK Tools입니다.

일반 대화 상자에 대 한 자세한 내용은 참조 [DialogBox](/windows/desktop/api/winuser/nf-winuser-dialogboxa) 하 고 [CreateDialogParam](/windows/desktop/api/winuser/nf-winuser-createdialogparama) Windows SDK에 있습니다.

##  <a name="atlaxcreatedialog"></a>  AtlAxCreateDialog

사용자가 제공한 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다.

```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
[in] 해당 실행 파일 대화 상자 템플릿이 포함 된 모듈의 인스턴스를 식별 합니다.

*lpTemplateName*<br/>
[in] 대화 상자 템플릿을 식별합니다. 이 매개 변수는 대화 상자 템플릿의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터 이거나 대화 상자 템플릿의 리소스 식별자를 지정 하는 정수 값입니다. 매개 변수는 리소스 식별자를 지정 하는 경우 경우 상위 워드가 0 이어야 합니다 하 고 해당 하위 단어는 식별자가 있어야 합니다. 사용할 수는 [MAKEINTRESOURCE](/windows/desktop/api/winuser/nf-winuser-makeintresourcea) 매크로이 값을 생성 합니다.

*hWndParent*<br/>
[in] 대화 상자를 소유 하는 창을 식별 합니다.

*lpDialogProc*<br/>
[in] 대화 상자 프로시저를 가리킵니다. 대화 상자 프로시저에 대 한 자세한 내용은 참조 하세요. [DialogProc](/windows/desktop/api/winuser/nc-winuser-dlgproc)합니다.

*dwInitParam*<br/>
[in] 대화 상자에 전달할 값을 지정 합니다 *lParam* WM_INITDIALOG 메시지의 매개 변수입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

대화 상자가 열리면 ActiveX 컨트롤을 포함할 수 있습니다.

참조 [CreateDialog](/windows/desktop/api/winuser/nf-winuser-createdialoga) 하 고 [CreateDialogParam](/windows/desktop/api/winuser/nf-winuser-createdialogparama) Windows SDK에에서 있습니다.

##  <a name="atlaxcreatecontrol"></a>  AtlAxCreateControl

ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤에 전달할 문자열 포인터입니다. 다음 방법 중 하나로 포맷 되어야 합니다.

- ProgID "MSCAL 예:. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID

- 와 같은 URL "<http://www.microsoft.com>"

- 와 같은 활성 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"

- 와 같은 html 조각 "MSHTML:\<HTML >\<본문 > 텍스트 줄을 이것이\</B >\</HTML >"

   > [!NOTE]
   > "MSHTML:" 하는 MSHTML stream으로 지정 된 HTML 조각의 앞에 야 합니다.

*hWnd*<br/>
[in] 컨트롤을 연결할 수 있는 창으로 처리 합니다.

*pStream*<br/>
[in] 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. NULL 일 수 있습니다.

*ppUnkContainer*<br/>
[out] 수신할 포인터의 주소는 `IUnknown` 컨테이너입니다. NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

이 전역 함수를 호출할 때와 동일한 결과 사용 [AtlAxCreateControlEx](#atlaxcreatecontrolex)(*lpszName*를 *hWnd*하십시오 *pStream*, NULL, NULL NULL, NULL)입니다.

사용이 허가 된 ActiveX 컨트롤을 참조 하세요 [AtlAxCreateControlLic](#atlaxcreatecontrollic)합니다.

##  <a name="atlaxcreatecontrolex"></a>  AtlAxCreateControlEx

ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다. 새 컨트롤에 대한 인터페이스 포인터와 이벤트 싱크를 만들 수도 있습니다.

```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤에 전달할 문자열 포인터입니다. 다음 방법 중 하나로 포맷 되어야 합니다.

- ProgID "MSCAL 예:. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID

- 와 같은 URL "<http://www.microsoft.com>"

- 와 같은 활성 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"

- 와 같은 html 조각 "MSHTML:\<HTML >\<본문 > 텍스트 줄을 이것이\</B >\</HTML >"

   > [!NOTE]
   > "MSHTML:" 하는 MSHTML stream으로 지정 된 HTML 조각의 앞에 야 합니다.

*hWnd*<br/>
[in] 컨트롤을 연결할 수 있는 창으로 처리 합니다.

*pStream*<br/>
[in] 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. NULL 일 수 있습니다.

*ppUnkContainer*<br/>
[out] 수신할 포인터의 주소는 `IUnknown` 컨테이너입니다. NULL 일 수 있습니다.

*ppUnkControl*<br/>
[out] 수신할 포인터의 주소는 `IUnknown` 만든된 컨트롤입니다. NULL 일 수 있습니다.

*iidSink*<br/>
포함된 된 개체에는 송신 인터페이스의 인터페이스 식별자입니다.

*punkSink*<br/>
에 대 한 포인터를 `IUnknown` 으로 지정 된 연결 지점에 연결할 싱크 개체의 인터페이스가 *iidSink* 포함된 된 개체 성공적으로 만들어진 후 포함된 된 개체에서.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`AtlAxCreateControlEx` 비슷합니다 [AtlAxCreateControl](#atlaxcreatecontrol) 하지만 새로 만든된 컨트롤에 대 한 인터페이스 포인터를 수신 하 고 컨트롤에서 발생 하는 이벤트를 수신할 이벤트 싱크를 설정 수 있습니다.

사용이 허가 된 ActiveX 컨트롤을 참조 하세요 [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)합니다.

##  <a name="atlaxcreatecontrollic"></a>  AtlAxCreateControlLic

사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤에 전달할 문자열 포인터입니다. 다음 방법 중 하나로 포맷 되어야 합니다.

- ProgID "MSCAL 예:. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID

- 와 같은 URL "<http://www.microsoft.com>"

- 와 같은 활성 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"

- 와 같은 html 조각 "MSHTML:\<HTML >\<본문 > 텍스트 줄을 이것이\</B >\</HTML >"

   > [!NOTE]
   > "MSHTML:" 하는 MSHTML stream으로 지정 된 HTML 조각의 앞에 야 합니다.

*hWnd*<br/>
컨트롤을 연결할 수 있는 창으로 처리 합니다.

*pStream*<br/>
컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. NULL 일 수 있습니다.

*ppUnkContainer*<br/>
수신할 포인터의 주소는 `IUnknown` 컨테이너입니다. NULL 일 수 있습니다.

*bstrLic*<br/>
컨트롤에 대 한 라이선스를 포함 하는 BSTR입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="example"></a>예제

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 방법의 예는 `AtlAxCreateControlLic`합니다.

##  <a name="atlaxcreatecontrollicex"></a>  AtlAxCreateControlLicEx

사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다. 새 컨트롤에 대한 인터페이스 포인터와 이벤트 싱크를 만들 수도 있습니다.

```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
컨트롤에 전달할 문자열 포인터입니다. 다음 방법 중 하나로 포맷 되어야 합니다.

- ProgID "MSCAL 예:. Calendar.7 "

- "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID

- 와 같은 URL "<http://www.microsoft.com>"

- 와 같은 활성 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"

- 와 같은 html 조각 "MSHTML:\<HTML >\<본문 > 텍스트 줄을 이것이\</B >\</HTML >"

   > [!NOTE]
   > "MSHTML:" 하는 MSHTML stream으로 지정 된 HTML 조각의 앞에 야 합니다.

*hWnd*<br/>
컨트롤을 연결할 수 있는 창으로 처리 합니다.

*pStream*<br/>
컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. NULL 일 수 있습니다.

*ppUnkContainer*<br/>
수신할 포인터의 주소는 `IUnknown` 컨테이너입니다. NULL 일 수 있습니다.

*ppUnkControl*<br/>
[out] 수신할 포인터의 주소는 `IUnknown` 만든된 컨트롤입니다. NULL 일 수 있습니다.

*iidSink*<br/>
포함된 된 개체에는 송신 인터페이스의 인터페이스 식별자입니다.

*punkSink*<br/>
에 대 한 포인터를 `IUnknown` 으로 지정 된 연결 지점에 연결할 싱크 개체의 인터페이스가 *iidSink* 포함된 된 개체 성공적으로 만들어진 후 포함된 된 개체에서.

*bstrLic*<br/>
컨트롤에 대 한 라이선스를 포함 하는 BSTR입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`AtlAxCreateControlLicEx` 비슷합니다 [AtlAxCreateControlLic](#atlaxcreatecontrollic) 하지만 새로 만든된 컨트롤에 대 한 인터페이스 포인터를 수신 하 고 컨트롤에서 발생 하는 이벤트를 수신할 이벤트 싱크를 설정 수 있습니다.

### <a name="example"></a>예제

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 방법의 예는 `AtlAxCreateControlLicEx`합니다.

##  <a name="atlaxattachcontrol"></a>  AtlAxAttachControl

지정한 창에 이전에 만든 컨트롤을 연결합니다.

```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```

### <a name="parameters"></a>매개 변수

*pControl*<br/>
[in] 에 대 한 포인터를 `IUnknown` 컨트롤입니다.

*hWnd*<br/>
[in] 컨트롤을 호스트 하는 창으로 처리 합니다.

*ppUnkContainer*<br/>
[out] 에 대 한 포인터에 대 한 포인터를 `IUnknown` 컨테이너 개체입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

사용 하 여 [AtlAxCreateControlEx](#atlaxcreatecontrolex) 하 고 [AtlAxCreateControl](#atlaxcreatecontrol) 동시에 만들고 컨트롤을 연결 합니다.

> [!NOTE]
>  연결 되 고 있는 컨트롤 개체를 호출 하기 전에 올바르게 초기화 `AtlAxAttachControl`합니다.

##  <a name="atlaxgethost"></a>  AtlAxGetHost

핸들이 제공되는 지정된 창(있는 경우)의 컨테이너에 직접 인터페이스 포인터를 가져옵니다.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
[in] 컨트롤을 호스트 하는 창 핸들입니다.

*pp*<br/>
[out] `IUnknown` 컨트롤의 컨테이너입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl

핸들이 제공되는 지정된 창 내에 포함된 컨트롤에 직접 인터페이스 포인터를 가져옵니다.

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
[in] 컨트롤을 호스트 하는 창 핸들입니다.

*pp*<br/>
[out] `IUnknown` 호스팅되고 제어 합니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="atlsetchildsite"></a>  AtlSetChildSite

자식 개체의 사이트를 설정 하려면이 함수를 호출 합니다 `IUnknown` 부모 개체입니다.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>매개 변수

*punkChild*<br/>
[in] 에 대 한 포인터를 `IUnknown` 자식 인터페이스입니다.

*punkParent*<br/>
[in] 에 대 한 포인터를 `IUnknown` 부모의 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="atlaxwininit"></a>  AtlAxWinInit

이 함수에는 ATL의 컨트롤 호스팅 코드를 등록 하 여 초기화 된 **"AtlAxWin80"** 하 고 **"AtlAxWinLic80"** 창 클래스는 몇 가지 사용자 지정 창 메시지와 함께 합니다.

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>반환 값

컨트롤 호스팅 코드의 초기화에 성공 하면 0이 아닌 값 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

ATL 컨트롤 호스팅 API를 사용 하기 전에이 함수를 호출 해야 합니다. 이 함수를 호출 합니다 **"AtlAxWin"** 창 클래스에 대 한 호출에서 사용할 수 있습니다 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) 또는 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa)Windows SDK에 설명 된 대로 합니다.

##  <a name="atlaxwinterm"></a>  AtlAxWinTerm

이 함수 ATL의 컨트롤 호스팅 코드의 등록을 취소 하 여 초기화를 취소 합니다 **"AtlAxWin80"** 하 고 **"AtlAxWinLic80"** 창 클래스입니다.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

이 함수 호출 [UnregisterClass](/windows/desktop/api/winuser/nf-winuser-unregisterclassa) Windows SDK에 설명 된 대로 합니다.

이 함수를 호출 하면 모든 기존 호스트 창을 제거 된 후 정리 하기 위해 호출 [AtlAxWinInit](#atlaxwininit) 및 호스트 창을 만들 필요가 없습니다. 이 함수를 호출 하지 않으면, 창 클래스를 등록 취소할 수 자동으로 프로세스가 종료 될 때.

##  <a name="atlgetobjectsourceinterface"></a>  AtlGetObjectSourceInterface

개체의 기본 소스 인터페이스에 대한 정보를 검색하려면 이 함수를 호출합니다.

```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```

### <a name="parameters"></a>매개 변수

*punkObj*<br/>
[in] 정보는 반환 될 개체에 대 한 포인터입니다.

*plibid*<br/>
[out] 소스 인터페이스의 정의 포함 하는 형식 라이브러리의 LIBID 포인터입니다.

*piid*<br/>
[out] 개체의 기본 소스 인터페이스의 인터페이스 ID에 대 한 포인터입니다.

*pdwMajor*<br/>
[out] 소스 인터페이스의 정의 포함 하는 형식 라이브러리의 주 버전 번호에 대 한 포인터입니다.

*pdwMinor*<br/>
[out] 소스 인터페이스의 정의 포함 하는 형식 라이브러리의 부 버전 번호에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`AtlGetObjectSourceInterface` LIBID 함께 및 주요 기본 소스 인터페이스의 인터페이스 ID와 해당 인터페이스를 설명 하는 형식 라이브러리의 부 버전 번호를 제공할 수 있습니다.

> [!NOTE]
>  가 나타내는 개체가 성공적으로 요청된 된 정보를 검색 하려면이 함수에 대 한 *punkObj* 구현 해야 `IDispatch` (통해 형식 정보를 반환 하 고 `IDispatch::GetTypeInfo`)와 어느 도구현해야합니다`IProvideClassInfo2` 또는 `IPersist`합니다. 소스 인터페이스의 형식 정보를 동일한 형식 라이브러리에 대 한 형식 정보를 묶어야 `IDispatch`합니다.

### <a name="example"></a>예제

아래 예제에서는 이벤트 싱크 클래스를 정의 하는 방법을 보여 줍니다 `CEasySink`를 전달할 수 있는 템플릿 인수 개수를 줄여 주는 `IDispEventImpl` 완전 essentials. `EasyAdvise` 및 `EasyUnadvise` 사용 하 여 `AtlGetObjectSourceInterface` 초기화 하는 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) 호출 하기 전에 멤버 [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) 또는 [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)합니다.

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>참고자료

[함수](../../atl/reference/atl-functions.md)<br/>
[복합 컨트롤 매크로](../../atl/reference/composite-control-macros.md)
