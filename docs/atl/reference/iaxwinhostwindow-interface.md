---
title: IAxWinHostWindow 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
ms.openlocfilehash: 4bdfdf76b48c1e9f2c06213ee25cd15a113525dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276109"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow 인터페이스

이 인터페이스는 컨트롤 및 해당 호스트 개체를 조작 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AttachControl](#attachcontrol)|호스트 개체를 기존 컨트롤을 연결합니다.|
|[CreateControl](#createcontrol)|컨트롤을 만들고 호스트 개체에 연결 합니다.|
|[CreateControlEx](#createcontrolex)|컨트롤을 만들고 호스트 개체에 연결 합니다. 필요에 따라 이벤트 처리기를 설정 합니다.|
|[QueryControl](#querycontrol)|호스팅된 컨트롤에 대 한 인터페이스 포인터를 반환합니다.|
|[SetExternalDispatch](#setexternaldispatch)|외부 설정 `IDispatch` 인터페이스입니다.|
|[SetExternalUIHandler](#setexternaluihandler)|외부 설정 `IDocHostUIHandlerDispatch` 인터페이스입니다.|

## <a name="remarks"></a>설명

이 인터페이스는 개체를 호스트 하는 ATL의 ActiveX 컨트롤에 의해 노출 됩니다. 만들기 및/또는 호스트 된 컨트롤에서 인터페이스를 가져올 수 또는 웹 브라우저를 호스팅하는 경우 외부 dispinterface 또는 사용에 대 한 UI 처리기를 설정 하려면 호스트 개체에 컨트롤을 연결 하는이 인터페이스의 메서드를 호출 합니다.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의 IDL로 제공 됩니다. 또는 C++다음과 같이 합니다.

|정의 유형|파일|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|ATLIFace.h (ATLBase.h에도 포함)|

##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl

기존 (및 이전에 초기화) 컨트롤을 식별 하 여 창을 사용 하 여 호스트 개체에 연결 *hWnd*합니다.

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*pUnkControl*<br/>
[in] 에 대 한 포인터를 `IUnknown` 호스트 개체에 연결 될 컨트롤의 인터페이스입니다.

*hWnd*<br/>
[in] 호스팅에 사용 되는 창 핸들입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="createcontrol"></a>  IAxWinHostWindow::CreateControl

컨트롤을 만들고, 초기화 및 구분 창에 호스팅합니다 *hWnd*합니다.

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*lpTricsData*<br/>
[in] 만들 컨트롤을 식별 하는 문자열입니다. (중괄호를 포함 해야 함) CLSID, ProgID, URL 또는 원시 HTML 수 (접두사로 **MSHTML:**).

*hWnd*<br/>
[in] 호스팅에 사용 되는 창 핸들입니다.

*pStream*<br/>
[in] 컨트롤에 대 한 초기화 데이터를 포함 하는 스트림에 대 한 인터페이스 포인터입니다. NULL 일 수 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

메시지를 컨트롤에 반영 될 수 있습니다 하 고 다른 컨테이너 기능을 사용할 수 있도록이 인터페이스를 노출 하는 호스트 개체에서이 창을 서브클래싱 할 됩니다.

이 메서드를 호출 하는 것 [IAxWinHostWindow::CreateControlEx](#createcontrolex)합니다.

사용이 허가 된 ActiveX 컨트롤을 참조 하세요 [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)합니다.

##  <a name="createcontrolex"></a>  IAxWinHostWindow::CreateControlEx

ActiveX 컨트롤을 만들고, 초기화 및 비슷하게 지정 된 창에서 호스트 [IAxWinHostWindow::CreateControl](#createcontrol)합니다.

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>매개 변수

*lpTricsData*<br/>
[in] 만들 컨트롤을 식별 하는 문자열입니다. (중괄호를 포함 해야 함) CLSID, ProgID, URL 또는 원시 HTML 수 (접두사로 **MSHTML:**).

*hWnd*<br/>
[in] 호스팅에 사용 되는 창 핸들입니다.

*pStream*<br/>
[in] 컨트롤에 대 한 초기화 데이터를 포함 하는 스트림에 대 한 인터페이스 포인터입니다. NULL 일 수 있습니다.

*ppUnk*<br/>
[out] 수신할 포인터의 주소는 `IUnknown` 만든된 컨트롤의 인터페이스입니다. NULL 일 수 있습니다.

*riidAdvise*<br/>
[in] 포함된 된 개체에는 송신 인터페이스의 인터페이스 식별자입니다. Can be IID_NULL.

*punkAdvise*<br/>
[in] 에 대 한 포인터를 `IUnknown` 으로 지정 된 포함된 된 개체의 연결 지점에 연결 되어 싱크 개체의 인터페이스가 `iidSink`합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

와 달리 합니다 `CreateControl` 메서드를 `CreateControlEx` 새로 만든된 컨트롤에 대 한 인터페이스 포인터를 수신 하 고 컨트롤에서 발생 하는 이벤트를 수신 하는 이벤트 싱크 설정 할 수도 있습니다.

사용이 허가 된 ActiveX 컨트롤을 참조 하세요 [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)합니다.

##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl

호스팅된 컨트롤에서 제공 된 인터페이스 포인터를 반환 합니다.

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
[in] 요청 된 컨트롤에 인터페이스의 ID입니다.

*ppvObject*<br/>
[out] 만든된 컨트롤의 지정된 된 인터페이스를 수신할 포인터의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch

통해 포함 된 컨트롤에 사용할 수 있는 외부 dispinterface를 설정 합니다 [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) 메서드.

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
[in] 에 대 한 포인터는 `IDispatch` 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler

외부를 설정 하려면이 함수를 호출 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) 에 대 한 인터페이스를 `CAxWindow` 개체입니다.

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>매개 변수

*pDisp*<br/>
[in] 에 대 한 포인터는 `IDocHostUIHandlerDispatch` 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 함수에 대 한 호스트의 사이트를 쿼리 하는 (예: 웹 브라우저 컨트롤) 컨트롤에서 사용 되는 `IDocHostUIHandlerDispatch` 인터페이스입니다.

## <a name="see-also"></a>참고자료

[IAxWinAmbientDispatch 인터페이스](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
