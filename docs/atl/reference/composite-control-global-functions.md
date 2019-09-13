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
ms.openlocfilehash: 525fc01247053a1e2bc993398978cb332262a1a5
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927777"
---
# <a name="composite-control-global-functions"></a>복합 컨트롤 전역 함수

이러한 함수는 대화 상자 만들기, ActiveX 컨트롤 생성, 호스팅 및 라이선스에 대 한 지원을 제공 합니다.

> [!IMPORTANT]
>  다음 표에 나열 된 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlAxDialogBox](#atlaxdialogbox)|사용자가 제공한 대화 상자 템플릿에서 모달 대화 상자를 만듭니다. 결과 대화 상자에는 ActiveX 컨트롤이 포함 될 수 있습니다.|
|[AtlAxCreateDialog](#atlaxcreatedialog)|사용자가 제공한 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다. 결과 대화 상자에는 ActiveX 컨트롤이 포함 될 수 있습니다.|
|[AtlAxCreateControl](#atlaxcreatecontrol)|ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX 컨트롤을 만들고 초기화 하 여 지정 된 창에 호스팅하고 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.|
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|사용이 허가 된 ActiveX 컨트롤을 만들고 초기화 하 여 지정 된 창에 호스팅하고 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.|
|[AtlAxAttachControl](#atlaxattachcontrol)|지정한 창에 이전에 만든 컨트롤을 연결합니다.|
|[AtlAxGetHost](#atlaxgethost)|핸들이 지정 된 경우 지정 된 창 (있는 경우)의 컨테이너에 대 한 직접 인터페이스 포인터를 가져오는 데 사용 됩니다.|
|[AtlAxGetControl](#atlaxgetcontrol)|핸들이 지정 된 경우 지정 된 창에 포함 된 컨트롤에 대 한 직접 인터페이스 포인터를 가져오는 데 사용 됩니다 (있는 경우).|
|[AtlSetChildSite](#atlsetchildsite)|자식 사이트 `IUnknown` 의를 초기화 합니다.|
|[AtlAxWinInit](#atlaxwininit)|AxWin 개체의 호스팅 코드를 초기화 합니다.|
|[AtlAxWinTerm](#atlaxwinterm)|AxWin 개체에 대 한 호스팅 코드를 초기화 하지 않습니다 합니다.|
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|개체의 기본 소스 인터페이스에 대 한 정보를 반환 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** 고 호스트 .h

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
진행 실행 파일에 대화 상자 템플릿이 포함 되어 있는 모듈의 인스턴스를 식별 합니다.

*lpTemplateName*<br/>
진행 대화 상자 템플릿을 식별 합니다. 이 매개 변수는 대화 상자 템플릿의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터 이거나 대화 상자 템플릿의 리소스 식별자를 지정 하는 정수 값입니다. 매개 변수가 리소스 식별자를 지정 하는 경우 상위 단어는 0 이어야 하며 하위 단어는 식별자를 포함 해야 합니다. [Makeintresource](/windows/win32/api/winuser/nf-winuser-makeintresourcew) 매크로를 사용 하 여이 값을 만들 수 있습니다.

*hWndParent*<br/>
진행 대화 상자를 소유 하는 창을 식별 합니다.

*lpDialogProc*<br/>
진행 대화 상자 프로시저를 가리킵니다. 대화 상자 절차에 대 한 자세한 내용은 [Dialogproc](/windows/win32/api/winuser/nc-winuser-dlgproc)를 참조 하세요.

*dwInitParam*<br/>
진행 WM_INITDIALOG 메시지의 *lParam* 매개 변수에서 대화 상자에 전달할 값을 지정 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

ActiveX 컨트롤 `AtlAxDialogBox` 을 포함 하는 대화 상자 템플릿과 함께 사용 하려면 올바른 CLSID, APPID 또는 URL 문자열을 대화 상자 리소스의 **control** 섹션 *텍스트* 필드로 지정 하 고 *클래스 이름* 필드에 "AtlAxWin80"를 지정 합니다. 같은 섹션에 있습니다. 다음은 유효한 **컨트롤** 섹션이 표시 되는 모습을 보여 줍니다.

```
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100
```

리소스 스크립트를 [편집 하는 방법에 대 한 자세한 내용은 방법: 리소스 스크립트 파일을 텍스트 형식](../../windows/how-to-open-a-resource-script-file-in-text-format.md)으로 엽니다. 컨트롤 리소스 정의 문에 대 한 자세한 내용은 Windows SDK 아래의 [공용 컨트롤 매개 변수](/windows/win32/menurc/common-control-parameters) 를 참조 하세요. SDK Tools.

일반 대화 상자에 대 한 자세한 내용은 Windows SDK의 [DialogBox](/windows/win32/api/winuser/nf-winuser-dialogboxw) 및 [createdialogparam](/windows/win32/api/winuser/nf-winuser-createdialogparamw) 을 참조 하십시오.

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
진행 실행 파일에 대화 상자 템플릿이 포함 되어 있는 모듈의 인스턴스를 식별 합니다.

*lpTemplateName*<br/>
진행 대화 상자 템플릿을 식별 합니다. 이 매개 변수는 대화 상자 템플릿의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터 이거나 대화 상자 템플릿의 리소스 식별자를 지정 하는 정수 값입니다. 매개 변수가 리소스 식별자를 지정 하는 경우 상위 단어는 0 이어야 하며 하위 단어는 식별자를 포함 해야 합니다. [Makeintresource](/windows/win32/api/winuser/nf-winuser-makeintresourcew) 매크로를 사용 하 여이 값을 만들 수 있습니다.

*hWndParent*<br/>
진행 대화 상자를 소유 하는 창을 식별 합니다.

*lpDialogProc*<br/>
진행 대화 상자 프로시저를 가리킵니다. 대화 상자 절차에 대 한 자세한 내용은 [Dialogproc](/windows/win32/api/winuser/nc-winuser-dlgproc)를 참조 하세요.

*dwInitParam*<br/>
진행 WM_INITDIALOG 메시지의 *lParam* 매개 변수에서 대화 상자에 전달할 값을 지정 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

결과 대화 상자에는 ActiveX 컨트롤이 포함 될 수 있습니다.

Windows SDK에서 [Createdialog](/windows/win32/api/winuser/nf-winuser-createdialogw) 및 [createdialogparam](/windows/win32/api/winuser/nf-winuser-createdialogparamw) 을 참조 하십시오.

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
컨트롤에 전달 되는 문자열에 대 한 포인터입니다. 다음 방법 중 하나로 형식을 지정 해야 합니다.

- 와 같은 ProgID`"MSCAL.Calendar.7"`

- 와 같은 CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL (예:)`"<https://www.microsoft.com>"`

- 과 같은 활성 문서에 대 한 참조입니다.`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`는 MSHTML 스트림으로 지정 되도록 HTML 조각 앞에와 야 합니다.

*hWnd*<br/>
진행 컨트롤이 연결 되는 창에 대 한 핸들입니다.

*pStream*<br/>
진행 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. NULL 일 수 있습니다.

*ppUnkContainer*<br/>
제한이 컨테이너의를 `IUnknown` 받는 포인터의 주소입니다. NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

이 전역 함수는 [AtlAxCreateControlEx](#atlaxcreatecontrolex)(*lpszName*, *hWnd*, *pstream*, null, null, null, null)를 호출 하는 것과 동일한 결과를 제공 합니다.

사용이 허가 된 ActiveX 컨트롤을 만들려면 [AtlAxCreateControlLic](#atlaxcreatecontrollic)를 참조 하세요.

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
컨트롤에 전달 되는 문자열에 대 한 포인터입니다. 다음 방법 중 하나로 형식을 지정 해야 합니다.

- 와 같은 ProgID`"MSCAL.Calendar.7"`

- 와 같은 CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL (예:)`"<https://www.microsoft.com>"`

- 과 같은 활성 문서에 대 한 참조입니다.`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`는 MSHTML 스트림으로 지정 되도록 HTML 조각 앞에와 야 합니다.

*hWnd*<br/>
진행 컨트롤이 연결 되는 창에 대 한 핸들입니다.

*pStream*<br/>
진행 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. NULL 일 수 있습니다.

*ppUnkContainer*<br/>
제한이 컨테이너의를 `IUnknown` 받는 포인터의 주소입니다. NULL 일 수 있습니다.

*ppUnkControl*<br/>
제한이 만든 컨트롤의를 `IUnknown` 받는 포인터의 주소입니다. NULL 일 수 있습니다.

*iidSink*<br/>
포함 된 개체의 송신 인터페이스에 대 한 인터페이스 식별자입니다.

*punkSink*<br/>
포함 된 개체가 성공적 `IUnknown` 으로 생성 된 후 포함 된 개체에서 *iidsink* 로 지정 된 연결 지점에 연결할 싱크 개체의 인터페이스에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`AtlAxCreateControlEx`은 [Atlaxcreatecontrol](#atlaxcreatecontrol) 과 비슷하지만 새로 만든 컨트롤에 대 한 인터페이스 포인터를 받고 컨트롤에서 발생 한 이벤트를 수신 하도록 이벤트 싱크를 설정할 수도 있습니다.

사용이 허가 된 ActiveX 컨트롤을 만들려면 [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)를 참조 하세요.

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
컨트롤에 전달 되는 문자열에 대 한 포인터입니다. 다음 방법 중 하나로 형식을 지정 해야 합니다.

- 와 같은 ProgID`"MSCAL.Calendar.7"`

- 와 같은 CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL (예:)`"<https://www.microsoft.com>"`

- 과 같은 활성 문서에 대 한 참조입니다.`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`는 MSHTML 스트림으로 지정 되도록 HTML 조각 앞에와 야 합니다.

*hWnd*<br/>
컨트롤이 연결 되는 창에 대 한 핸들입니다.

*pStream*<br/>
컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. NULL 일 수 있습니다.

*ppUnkContainer*<br/>
컨테이너의를 `IUnknown` 받는 포인터의 주소입니다. NULL 일 수 있습니다.

*bstrLic*<br/>
컨트롤의 라이선스를 포함 하는 BSTR입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

### <a name="example"></a>예제

를 사용 `AtlAxCreateControlLic`하는 방법에 대 한 샘플은 [ATL Axhost를 사용 하 여 ActiveX 컨트롤 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 을 참조 하세요.

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
컨트롤에 전달 되는 문자열에 대 한 포인터입니다. 다음 방법 중 하나로 형식을 지정 해야 합니다.

- 와 같은 ProgID`"MSCAL.Calendar.7"`

- 와 같은 CLSID`"{8E27C92B-1264-101C-8A2F-040224009C02}"`

- URL (예:)`"<https://www.microsoft.com>"`

- 과 같은 활성 문서에 대 한 참조입니다.`"file://\\\Documents\MyDoc.doc"`

- 와 같은 HTML의 조각`"MSHTML:\<HTML>\<BODY>This is a line of text\</BODY>\</HTML>"`

   > [!NOTE]
   > `"MSHTML:"`는 MSHTML 스트림으로 지정 되도록 HTML 조각 앞에와 야 합니다.

*hWnd*<br/>
컨트롤이 연결 되는 창에 대 한 핸들입니다.

*pStream*<br/>
컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. NULL 일 수 있습니다.

*ppUnkContainer*<br/>
컨테이너의를 `IUnknown` 받는 포인터의 주소입니다. NULL 일 수 있습니다.

*ppUnkControl*<br/>
제한이 만든 컨트롤의를 `IUnknown` 받는 포인터의 주소입니다. NULL 일 수 있습니다.

*iidSink*<br/>
포함 된 개체의 송신 인터페이스에 대 한 인터페이스 식별자입니다.

*punkSink*<br/>
포함 된 개체가 성공적 `IUnknown` 으로 생성 된 후 포함 된 개체에서 *iidsink* 로 지정 된 연결 지점에 연결할 싱크 개체의 인터페이스에 대 한 포인터입니다.

*bstrLic*<br/>
컨트롤의 라이선스를 포함 하는 BSTR입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

`AtlAxCreateControlLicEx`는 [AtlAxCreateControlLic](#atlaxcreatecontrollic) 와 비슷하지만 새로 만든 컨트롤에 대 한 인터페이스 포인터를 받고 컨트롤에서 발생 한 이벤트를 수신 하도록 이벤트 싱크를 설정할 수 있습니다.

### <a name="example"></a>예제

를 사용 `AtlAxCreateControlLicEx`하는 방법에 대 한 샘플은 [ATL Axhost를 사용 하 여 ActiveX 컨트롤 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 을 참조 하세요.

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
진행 컨트롤 `IUnknown` 의에 대 한 포인터입니다.

*hWnd*<br/>
진행 컨트롤을 호스팅하는 창에 대 한 핸들입니다.

*ppUnkContainer*<br/>
제한이 컨테이너 개체 `IUnknown` 의에 대 한 포인터에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

[AtlAxCreateControlEx](#atlaxcreatecontrolex) 및 [Atlaxcreatecontrol](#atlaxcreatecontrol) 을 사용 하 여 컨트롤을 동시에 만들고 연결 합니다.

> [!NOTE]
>  연결 중인 컨트롤 개체는를 호출 `AtlAxAttachControl`하기 전에 올바르게 초기화 되어야 합니다.

##  <a name="atlaxgethost"></a>  AtlAxGetHost

핸들이 제공되는 지정된 창(있는 경우)의 컨테이너에 직접 인터페이스 포인터를 가져옵니다.

```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
진행 컨트롤을 호스팅하는 창에 대 한 핸들입니다.

*pp*<br/>
제한이 컨트롤의 컨테이너에 대한입니다.`IUnknown`

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl

핸들이 제공되는 지정된 창 내에 포함된 컨트롤에 직접 인터페이스 포인터를 가져옵니다.

```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
진행 컨트롤을 호스팅하는 창에 대 한 핸들입니다.

*pp*<br/>
제한이 호스트 되는 컨트롤 의입니다.`IUnknown`

### <a name="return-value"></a>반환 값

표준 HRESULT 값 중 하나입니다.

##  <a name="atlsetchildsite"></a>  AtlSetChildSite

자식 개체의 사이트를 부모 개체 `IUnknown` 의로 설정 하려면이 함수를 호출 합니다.

```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```

### <a name="parameters"></a>매개 변수

*punkChild*<br/>
진행 자식의 `IUnknown` 인터페이스에 대 한 포인터입니다.

*punkParent*<br/>
진행 부모의 `IUnknown` 인터페이스에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="atlaxwininit"></a>  AtlAxWinInit

이 함수는 **"AtlAxWin80"** 및 **"AtlAxWinLic80"** 창 클래스와 몇 가지 사용자 지정 창 메시지를 등록 하 여 ATL의 컨트롤 호스팅 코드를 초기화 합니다.

```
ATLAPI_(BOOL) AtlAxWinInit();
```

### <a name="return-value"></a>반환 값

컨트롤 호스팅 코드의 초기화가 성공 하면 0이 아닌 값입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

ATL 컨트롤 호스팅 API를 사용 하기 전에이 함수를 호출 해야 합니다. 이 함수에 대 한 호출을 수행 하면 Windows SDK에 설명 된 대로 **"Atlaxwin"** 창 클래스를 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 또는 [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)호출에서 사용할 수 있습니다.

##  <a name="atlaxwinterm"></a>  AtlAxWinTerm

이 함수는 **"AtlAxWin80"** 및 **"AtlAxWinLic80"** 창 클래스의 등록을 취소 하 여 ATL의 컨트롤 호스팅 코드를 초기화 하지 않습니다 합니다.

```
inline BOOL AtlAxWinTerm();
```

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

이 함수는 Windows SDK에 설명 된 대로 단순히 [UnregisterClass](/windows/win32/api/winuser/nf-winuser-unregisterclassw) 를 호출 합니다.

[AtlAxWinInit](#atlaxwininit) 를 호출 하 고 더 이상 호스트 창을 만들 필요가 없는 경우이 함수를 호출 하 여 모든 기존 호스트 창이 제거 된 후 정리 합니다. 이 함수를 호출 하지 않으면 프로세스가 종료 될 때 window 클래스가 자동으로 등록 취소 됩니다.

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
진행 정보가 반환 되는 개체에 대 한 포인터입니다.

*plibid*<br/>
제한이 원본 인터페이스의 정의가 포함 된 형식 라이브러리의 LIBID에 대 한 포인터입니다.

*piid*<br/>
제한이 개체의 기본 소스 인터페이스의 인터페이스 ID에 대 한 포인터입니다.

*pdwMajor*<br/>
제한이 원본 인터페이스의 정의를 포함 하는 형식 라이브러리의 주 버전 번호에 대 한 포인터입니다.

*pdwMinor*<br/>
제한이 원본 인터페이스의 정의를 포함 하는 형식 라이브러리의 부 버전 번호에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

`AtlGetObjectSourceInterface`는 해당 인터페이스를 설명 하는 형식 라이브러리의 LIBID 및 주 버전 번호와 함께 기본 소스 인터페이스의 인터페이스 ID를 제공할 수 있습니다.

> [!NOTE]
>  이 함수에서 요청 된 정보를 성공적으로 검색 하려면 *punkObj* 로 표시 되는 개체 `IDispatch` 는를 구현 하 고을 `IDispatch::GetTypeInfo`통해 형식 정보를 반환 해야 합니다 `IProvideClassInfo2` . 또한 또는 를구현해야합니다.`IPersist`. 원본 인터페이스에 대 한 형식 정보는의 `IDispatch`형식 정보와 동일한 형식 라이브러리에 있어야 합니다.

### <a name="example"></a>예제

아래 예제에서는 이벤트 싱크 클래스 `CEasySink`를 정의 하는 방법을 보여 줍니다 .이를 통해에 `IDispEventImpl` 전달할 수 있는 템플릿 인수의 수가 완전 하지 않을 수 있습니다. `EasyAdvise`및 `EasyUnadvise` 는 `AtlGetObjectSourceInterface` [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) 또는 [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)를 호출 하기 전에 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) 멤버를 초기화 하는 데 사용 합니다.

[!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]

## <a name="see-also"></a>참고자료

[함수](../../atl/reference/atl-functions.md)<br/>
[복합 컨트롤 매크로](../../atl/reference/composite-control-macros.md)
