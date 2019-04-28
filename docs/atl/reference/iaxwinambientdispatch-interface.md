---
title: IAxWinAmbientDispatch 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
ms.openlocfilehash: 85a8f1d41c6c54f94b500807a1e4ca504206f56a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276161"
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch 인터페이스

이 인터페이스는 호스트 된 컨트롤의 컨테이너 특성을 지정 하는 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|`AllowContextMenu` 속성 상황에 맞는 메뉴를 표시 하는 호스트 된 컨트롤 허용 되는지 여부를 지정 합니다.|
|[get_AllowShowUI](#get_allowshowui)|`AllowShowUI` 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스에 표시할 허용 되는지 여부를 지정 합니다.|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|`AllowWindowlessActivation` 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.|
|[get_BackColor](#get_backcolor)|`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault` 기본 컨트롤 인지 확인 하려면 제어를 허용 하는 앰비언트 속성이입니다.|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|`DocHostDoubleClickFlags` 속성을 두 번 클릭에 대 한 응답에서 수행 해야 하는 작업을 지정 합니다.|
|[get_DocHostFlags](#get_dochostflags)|`DocHostFlags` 속성 호스트 개체의 사용자 인터페이스 기능을 지정 합니다.|
|[get_Font](#get_font)|`Font` 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.|
|[get_ForeColor](#get_forecolor)|`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.|
|[get_LocaleID](#get_localeid)|`LocaleID` 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.|
|[get_MessageReflect](#get_messagereflect)|`MessageReflect` 앰비언트 속성은 컨테이너 호스트 된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.|
|[get_OptionKeyPath](#get_optionkeypath)|`OptionKeyPath` 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.|
|[get_ShowGrabHandles](#get_showgrabhandles)|`ShowGrabHandles` 앰비언트 속성 경우 해당 그려야 자체 잡기 핸들을 사용 하 여 확인 하도록 허용 합니다.|
|[get_ShowHatching](#get_showhatching)|`ShowHatching` 앰비언트 속성 무늬 자체 그리기 해야 하는 경우 확인 하도록 허용 합니다.|
|[get_UserMode](#get_usermode)|`UserMode` 속성에는 컨테이너의 앰비언트 사용자 모드를 지정 합니다.|
|[put_AllowContextMenu](#put_allowcontextmenu)|`AllowContextMenu` 속성 상황에 맞는 메뉴를 표시 하는 호스트 된 컨트롤 허용 되는지 여부를 지정 합니다.|
|[put_AllowShowUI](#put_allowshowui)|`AllowShowUI` 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스에 표시할 허용 되는지 여부를 지정 합니다.|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|`AllowWindowlessActivation` 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.|
|[put_BackColor](#put_backcolor)|`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault` 기본 컨트롤 인지 확인 하려면 제어를 허용 하는 앰비언트 속성이입니다.|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|`DocHostDoubleClickFlags` 속성을 두 번 클릭에 대 한 응답에서 수행 해야 하는 작업을 지정 합니다.|
|[put_DocHostFlags](#put_dochostflags)|`DocHostFlags` 속성 호스트 개체의 사용자 인터페이스 기능을 지정 합니다.|
|[put_Font](#put_font)|`Font` 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.|
|[put_ForeColor](#put_forecolor)|`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.|
|[put_LocaleID](#put_localeid)|`LocaleID` 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.|
|[put_MessageReflect](#put_messagereflect)|`MessageReflect` 앰비언트 속성은 컨테이너 호스트 된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.|
|[put_OptionKeyPath](#put_optionkeypath)|`OptionKeyPath` 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.|
|[put_UserMode](#put_usermode)|`UserMode` 속성에는 컨테이너의 앰비언트 사용자 모드를 지정 합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 개체를 호스트 하는 ATL의 ActiveX 컨트롤에 의해 노출 됩니다. 호스팅된 컨트롤에 사용 가능한 앰비언트 속성을 설정 하려면 또는 컨테이너의 동작의 다른 측면을 지정 하려면이 인터페이스에서 메서드를 호출 합니다. 제공 하는 속성을 보완 하기 위해 `IAxWinAmbientDispatch`를 사용 하 여 [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)합니다.

<xref:System.Windows.Forms.AxHost> 에 대 한 형식 정보를 로드 하려고 `IAxWinAmbientDispatch` 고 `IAxWinAmbientDispatchEx` 코드가 포함 된 typelib에서 합니다.

ATL90.dll를 연결할 경우 **AXHost** DLL의 형식 라이브러리에서 형식 정보를 로드 합니다.

참조 [ActiveX 컨트롤 ATL 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 대 한 자세한 내용은 합니다.

## <a name="requirements"></a>요구 사항

이 인터페이스의 정의 아래 표에 나와 있는 것 처럼 다양 한 폼에서에서 사용할 수 있습니다.

|정의 유형|파일|
|---------------------|----------|
|IDL|atliface.idl|
|형식 라이브러리|ATL.dll|
|C++|atliface.h (ATLBase.h에도 포함)|

##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu

`AllowContextMenu` 속성 상황에 맞는 메뉴를 표시 하는 호스트 된 컨트롤 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>매개 변수

*pbAllowContextMenu*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI

`AllowShowUI` 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스에 표시할 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>매개 변수

*pbAllowShowUI*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_FALSE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation

`AllowWindowlessActivation` 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>매개 변수

*pbAllowWindowless*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor

`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>매개 변수

*pclrBackground*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을 (인지에 따라 호스트 창의 부모 대화 여부)이이 속성의 값을 기본값으로 COLOR_BTNFACE 또는 COLOR_WINDOW를 사용 합니다.

##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault

`DisplayAsDefault` 기본 컨트롤 인지 확인 하려면 제어를 허용 하는 앰비언트 속성이입니다.

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*pbDisplayAsDefault*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_FALSE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` 속성을 두 번 클릭에 대 한 응답에서 수행 해야 하는 작업을 지정 합니다.

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>매개 변수

*pdwDocHostDoubleClickFlags*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 DOCHOSTUIDBLCLK_DEFAULT를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags

`DocHostFlags` 속성 호스트 개체의 사용자 인터페이스 기능을 지정 합니다.

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>매개 변수

*pdwDocHostFlags*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 DOCHOSTUIFLAG_NO3DBORDER를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font

`Font` 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
[out] 주소는 `IFontDisp` 이 속성의 현재 값을 수신 하는 데 사용 되는 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을이 속성의 값을 기본값으로 기본 GUI 글꼴 또는 시스템 글꼴을 사용합니다.

##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor

`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>매개 변수

*pclrForeground*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을이 속성의 값을 기본값으로 시스템 창 텍스트 색을 사용합니다.

##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID

`LocaleID` 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>매개 변수

*plcidLocaleID*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 기본 값으로 사용자의 기본 로캘을 사용 하는 ATL 호스트 개체 구현 합니다.

이 메서드를 사용 하 여 앰비언트 LocalID를 검색할 수 있습니다, 즉, 프로그램의 LocaleID 컨트롤 사용량입니다. LocaleID를 알게 되 면 리소스 파일 또는 위성 DLL에서 등 로캘별 캡션 로드 하는 코드, 오류 메시지 텍스트를 호출할 수 있습니다.

##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect

`MessageReflect` 앰비언트 속성은 컨테이너 호스트 된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>매개 변수

*pbMessageReflect*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath

`OptionKeyPath` 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>매개 변수

*pbstrOptionKeyPath*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles

`ShowGrabHandles` 앰비언트 속성 경우 해당 그려야 자체 잡기 핸들을 사용 하 여 확인 하도록 허용 합니다.

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>매개 변수

*pbShowGrabHandles*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현에서는 항상이 속성의 값으로 VARIANT_FALSE가 반환 됩니다.

##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching

`ShowHatching` 앰비언트 속성 무늬 자체 그리기 해야 하는 경우 확인 하도록 허용 합니다.

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>매개 변수

*pbShowHatching*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현에서는 항상이 속성의 값으로 VARIANT_FALSE가 반환 됩니다.

##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode

`UserMode` 속성에는 컨테이너의 앰비언트 사용자 모드를 지정 합니다.

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>매개 변수

*pbUserMode*<br/>
[out] 이 속성의 현재 값을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu

`AllowContextMenu` 속성 상황에 맞는 메뉴를 표시 하는 호스트 된 컨트롤 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>매개 변수

*bAllowContextMenu*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI

`AllowShowUI` 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스에 표시할 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>매개 변수

*bAllowShowUI*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_FALSE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation

`AllowWindowlessActivation` 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>매개 변수

*bAllowWindowless*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor

`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>매개 변수

*clrBackground*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을 (인지에 따라 호스트 창의 부모 대화 여부)이이 속성의 값을 기본값으로 COLOR_BTNFACE 또는 COLOR_WINDOW를 사용 합니다.

##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault

`DisplayAsDefault` 기본 컨트롤 인지 확인 하려면 제어를 허용 하는 앰비언트 속성이입니다.

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*bDisplayAsDefault*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_FALSE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags

`DocHostDoubleClickFlags` 속성을 두 번 클릭에 대 한 응답에서 수행 해야 하는 작업을 지정 합니다.

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>매개 변수

*dwDocHostDoubleClickFlags*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 DOCHOSTUIDBLCLK_DEFAULT를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags

`DocHostFlags` 속성 호스트 개체의 사용자 인터페이스 기능을 지정 합니다.

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>매개 변수

*dwDocHostFlags*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 DOCHOSTUIFLAG_NO3DBORDER를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font

`Font` 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을이 속성의 값을 기본값으로 기본 GUI 글꼴 또는 시스템 글꼴을 사용합니다.

##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor

`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>매개 변수

*clrForeground*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

ATL 호스트 개체 구현을이 속성의 값을 기본값으로 시스템 창 텍스트 색을 사용합니다.

##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID

`LocaleID` 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>매개 변수

*lcidLocaleID*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 기본 값으로 사용자의 기본 로캘을 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect

`MessageReflect` 앰비언트 속성은 컨테이너 호스트 된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>매개 변수

*bMessageReflect*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath

`OptionKeyPath` 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>매개 변수

*bstrOptionKeyPath*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode

`UserMode` 속성에는 컨테이너의 앰비언트 사용자 모드를 지정 합니다.

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>매개 변수

*bUserMode*<br/>
[in] 이 속성의 새 값입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 속성의 값을 기본값으로 VARIANT_TRUE를 사용 하는 ATL 호스트 개체 구현 합니다.

## <a name="see-also"></a>참고자료

[IAxWinAmbientDispatchEx 인터페이스](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[IAxWinHostWindow 인터페이스](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
