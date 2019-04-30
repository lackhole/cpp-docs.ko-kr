---
title: CStockPropImpl 클래스
ms.date: 11/06/2018
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
ms.openlocfilehash: 148c9571bb37e2b9063ca9290f51caa1fabb2d21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277489"
---
# <a name="cstockpropimpl-class"></a>CStockPropImpl 클래스

이 클래스는 스톡 속성 값을 지원 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
> 이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <
    class T, 
    class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE CStockPropImpl :
    public IDispatchImpl<InterfaceName, piid, plibid, wMajor, wMinor, tihclass>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컨트롤을 구현 하 고에서 파생 되는 클래스 `CStockPropImpl`합니다.

*InterfaceName*<br/>
스톡 속성을 노출 하는 이중 인터페이스입니다.

*piid*<br/>
에 대 한 포인터의 IID `InterfaceName`합니다.

*plibid*<br/>
에 대 한 포인터의 정의 포함 하는 형식 라이브러리의 LIBID `InterfaceName`합니다.

*wMajor*<br/>
형식 라이브러리의 주 버전입니다. 기본값은 1입니다.

*wMinor*<br/>
형식 라이브러리의 부 버전입니다. 기본값은 0입니다.

*tihclass*<br/>
클래스에 대 한 형식 정보를 관리 하는 데 *T*합니다. 기본값은 `CComTypeInfoHolder`입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|[get_Appearance](#get_appearance)|예를 들어, 플랫 컨트롤에 의해 사용 되는 그리기 스타일 또는 3D를 가져오려면이 메서드를 호출 합니다.|
|[get_AutoSize](#get_autosize)|컨트롤에 다른 크기 일 수 없습니다 경우를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|
|[get_BackColor](#get_backcolor)|컨트롤의 배경색을 가져오려면이 메서드를 호출 합니다.|
|[get_BackStyle](#get_backstyle)|컨트롤의 배경 스타일, 투명 또는 불투명를 가져오려면이 메서드를 호출 합니다.|
|[get_BorderColor](#get_bordercolor)|컨트롤의 테두리 색을 가져오려면이 메서드를 호출 합니다.|
|[get_BorderStyle](#get_borderstyle)|컨트롤의 테두리 스타일을 가져오려면이 메서드를 호출 합니다.|
|[get_BorderVisible](#get_bordervisible)|컨트롤의 테두리를 표시할지 여부 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|
|[get_BorderWidth](#get_borderwidth)|컨트롤의 테두리의 너비 (픽셀)를 가져오려면이 메서드를 호출 합니다.|
|[get_Caption](#get_caption)|개체의 캡션에서 지정 된 텍스트를 가져오려면이 메서드를 호출 합니다.|
|[get_DrawMode](#get_drawmode)|컨트롤의 그리기 모드를 예를 들어, XOR 펜 또는 색 반전를 가져오려면이 메서드를 호출 합니다.|
|[get_DrawStyle](#get_drawstyle)|실선, 파선 또는 점으로 구분 된 예를 들어, 컨트롤의 그리기 스타일을 가져오려면이 메서드를 호출 합니다.|
|[get_DrawWidth](#get_drawwidth)|컨트롤의 그리기 메서드를 사용한는 그리기 너비 (픽셀)를 가져오려면이 메서드를 호출 합니다.|
|[get_Enabled](#get_enabled)|컨트롤이 사용 되는지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|
|[get_FillColor](#get_fillcolor)|컨트롤의 채우기 색을 가져오려면이 메서드를 호출 합니다.|
|[get_FillStyle](#get_fillstyle)|단색, 투명 또는 교차 무늬 예를 들어, 컨트롤의 채우기 스타일을 가져오려면이 메서드를 호출 합니다.|
|[get_Font](#get_font)|컨트롤의 글꼴 속성에 대 한 포인터를 이동 하려면이 메서드를 호출 합니다.|
|[get_ForeColor](#get_forecolor)|컨트롤의 전경색을 가져오려면이 메서드를 호출 합니다.|
|[get_HWND](#get_hwnd)|컨트롤과 연결 된 창 핸들을 가져오려면이 메서드를 호출 합니다.|
|[get_MouseIcon](#get_mouseicon)|(아이콘, 비트맵 또는 메타 파일) 컨트롤 위에 마우스가 있을 때 표시할 그래픽의 그림 속성을 가져오려면이 메서드를 호출 합니다.|
|[get_MousePointer](#get_mousepointer)|예를 들어 마우스가 컨트롤 위에 있을 때 표시 되는 마우스 포인터, 화살표, 간, 또는 모래 시계의 형식을 가져오기 위해이 메서드를 호출 합니다.|
|[get_Picture](#get_picture)|(아이콘, 비트맵 또는 메타 파일) 표시할 그래픽의 그림 속성에 대 한 포인터를 이동 하려면이 메서드를 호출 합니다.|
|[get_ReadyState](#get_readystate)|로드 또는 로드 예를 들어, 컨트롤의 준비 상태를 가져오려면이 메서드를 호출 합니다.|
|[get_TabStop](#get_tabstop)|컨트롤 탭 정지 인지 인지 여부를 나타내는 플래그를 가져오려면이 메서드를 호출 합니다.|
|[get_Text](#get_text)|컨트롤을 사용 하 여 표시 되는 텍스트를 가져오려면이 메서드를 호출 합니다.|
|[getvalid](#get_valid)|컨트롤은 유효한 경우를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.|
|[get_Window](#get_window)|컨트롤과 연결 된 창 핸들을 가져오려면이 메서드를 호출 합니다. 동일 [CStockPropImpl::get_HWND](#get_hwnd)합니다.|
|[put_Appearance](#put_appearance)|예를 들어, 플랫 컨트롤에 의해 사용 되는 그리기 스타일 또는 3D를 설정 하려면이 메서드를 호출 합니다.|
|[put_AutoSize](#put_autosize)|컨트롤에 다른 크기 일 수 없습니다 경우를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.|
|[put_BackColor](#put_backcolor)|컨트롤의 배경색을 설정 하려면이 메서드를 호출 합니다.|
|[put_BackStyle](#put_backstyle)|컨트롤의 배경 스타일을 설정 하려면이 메서드를 호출 합니다.|
|[put_BorderColor](#put_bordercolor)|컨트롤의 테두리 색을 설정 하려면이 메서드를 호출 합니다.|
|[put_BorderStyle](#put_borderstyle)|컨트롤의 테두리 스타일을 설정 하려면이 메서드를 호출 합니다.|
|[put_BorderVisible](#put_bordervisible)|컨트롤의 테두리를 표시할지 여부 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.|
|[put_BorderWidth](#put_borderwidth)|컨트롤의 테두리의 두께 설정 하려면이 메서드를 호출 합니다.|
|[put_Caption](#put_caption)|컨트롤을 사용 하 여 표시할 텍스트를 설정 하려면이 메서드를 호출 합니다.|
|[put_DrawMode](#put_drawmode)|컨트롤의 그리기 모드를 예를 들어, XOR 펜 또는 반전 색을 설정 하려면이 메서드를 호출 합니다.|
|[put_DrawStyle](#put_drawstyle)|실선, 파선 또는 점으로 구분 된 예를 들어, 컨트롤의 그리기 스타일을 설정 하려면이 메서드를 호출 합니다.|
|[put_DrawWidth](#put_drawwidth)|컨트롤의 그리기 메서드에서 사용 하는 너비 (픽셀)를 설정 하려면이 메서드를 호출 합니다.|
|[put_Enabled](#put_enabled)|컨트롤이 사용 되는지 여부를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.|
|[put_FillColor](#put_fillcolor)|컨트롤의 채우기 색을 설정 하려면이 메서드를 호출 합니다.|
|[put_FillStyle](#put_fillstyle)|단색, 투명 또는 교차 무늬 예를 들어, 컨트롤의 채우기 스타일을 설정 하려면이 메서드를 호출 합니다.|
|[put_Font](#put_font)|컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.|
|[put_ForeColor](#put_forecolor)|컨트롤의 전경색을 설정 하려면이 메서드를 호출 합니다.|
|[put_HWND](#put_hwnd)|이 메서드는 E_FAIL을 반환합니다.|
|[put_MouseIcon](#put_mouseicon)|(아이콘, 비트맵 또는 메타 파일) 컨트롤 위에 마우스가 있을 때 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|
|[put_MousePointer](#put_mousepointer)|예를 들어 마우스가 컨트롤 위에 있을 때 표시 되는 마우스 포인터, 화살표, 간, 또는 모래 시계 유형을 설정 하려면이 메서드를 호출 합니다.|
|[put_Picture](#put_picture)|(아이콘, 비트맵 또는 메타 파일) 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|
|[put_ReadyState](#put_readystate)|로드 또는 로드 예를 들어, 컨트롤의 준비 상태를 설정 하려면이 메서드를 호출 합니다.|
|[put_TabStop](#put_tabstop)|컨트롤 탭 정지 인지 인지 여부를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.|
|[put_Text](#put_text)|컨트롤을 사용 하 여 표시 되는 텍스트를 설정 하려면이 메서드를 호출 합니다.|
|[putvalid](#put_valid)|컨트롤은 유효한 경우를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.|
|[put_Window](#put_window)|이 메서드를 호출 [CStockPropImpl::put_HWND](#put_hwnd)는 E_FAIL을 반환 합니다.|
|[putref_Font](#putref_font)|참조 횟수를 사용 하 여 컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.|
|[putref_MouseIcon](#putref_mouseicon)|참조 횟수를 사용 하 여 (아이콘, 비트맵 또는 메타 파일)를 컨트롤 위에 마우스가 있을 때 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|
|[putref_Picture](#putref_picture)|참조 횟수를 사용 하 여 (아이콘, 비트맵 또는 메타 파일)를 표시 해야 할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

`CStockPropImpl` 제공 **배치** 하 고 **가져오기** 각 스톡 속성에 대 한 메서드. 이러한 메서드는 각 속성에 연결 된 데이터 멤버를 가져오거나 설정 하 고 알리고 모든 속성이 변경 되 면 컨테이너와 동기화 하는 데 필요한 코드를 제공 합니다.

Visual C++ 해당 마법사를 통해 스톡 속성에 대 한 지원을 제공 합니다. 컨트롤에 스톡 속성을 추가 하는 방법에 대 한 자세한 내용은 참조는 [ATL 자습서](../../atl/active-template-library-atl-tutorial.md)합니다.

이전 버전과 호환성을 위해 `CStockPropImpl` 노출 `get_Window` 하 고 `put_Window` 메서드를 호출 하기만 하면 됩니다 `get_HWND` 및 `put_HWND`, 각각. 기본 구현을 `put_HWND` HWND는 읽기 전용 속성 해야 하므로 E_FAIL을 반환 합니다.

다음 속성을 갖게를 **putref** 구현 합니다.

- 글꼴

- MouseIcon

- Picture

세 가지 동일한 스톡 속성 형식으로 해당 데이터 멤버는 필요한 `CComPtr` 또는 대입 연산자를 사용 하 여 올바른 인터페이스 참조를 제공 하는 다른 클래스를 계산 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`T`

[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="get_appearance"></a>  CStockPropImpl::get_Appearance

예를 들어, 플랫 컨트롤에 의해 사용 되는 그리기 스타일 또는 3D를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>매개 변수

*pnAppearance*<br/>
컨트롤의 그리기 스타일을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_autosize"></a>  CStockPropImpl::get_AutoSize

컨트롤에 다른 크기 일 수 없습니다 경우를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>매개 변수

*pbAutoSize*<br/>
플래그 상태를 수신 하는 변수입니다. TRUE는 컨트롤에 다른 크기 일 수 없음을 나타냅니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_backcolor"></a>  CStockPropImpl::get_BackColor

컨트롤의 배경색을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>매개 변수

*pclrBackColor*<br/>
컨트롤의 배경색을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_backstyle"></a>  CStockPropImpl::get_BackStyle

컨트롤의 배경 스타일, 투명 또는 불투명를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>매개 변수

*pnBackStyle*<br/>
컨트롤의 배경 스타일을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_bordercolor"></a>  CStockPropImpl::get_BorderColor

컨트롤의 테두리 색을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>매개 변수

*pclrBorderColor*<br/>
컨트롤의 테두리 색을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_borderstyle"></a>  CStockPropImpl::get_BorderStyle

컨트롤의 테두리 스타일을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>매개 변수

*pnBorderStyle*<br/>
컨트롤의 테두리 스타일을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_bordervisible"></a>  CStockPropImpl::get_BorderVisible

컨트롤의 테두리를 표시할지 여부 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>매개 변수

*pbBorderVisible*<br/>
플래그 상태를 수신 하는 변수입니다. TRUE는 컨트롤의 테두리 표시 되어 있는지를 나타냅니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_borderwidth"></a>  CStockPropImpl::get_BorderWidth

컨트롤의 테두리의 두께 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>매개 변수

*pnBorderWidth*<br/>
컨트롤의 테두리 두께 받는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_caption"></a>  CStockPropImpl::get_Caption

개체의 캡션에서 지정 된 텍스트를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>매개 변수

*pbstrCaption*<br/>
컨트롤을 사용 하 여 표시할 텍스트입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_drawmode"></a>  CStockPropImpl::get_DrawMode

컨트롤의 그리기 모드를 예를 들어, XOR 펜 또는 색 반전를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>매개 변수

*pnDrawMode*<br/>
컨트롤의 그리기 모드를 받는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_drawstyle"></a>  CStockPropImpl::get_DrawStyle

실선, 파선 또는 점으로 구분 된 예를 들어, 컨트롤의 그리기 스타일을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>매개 변수

*pnDrawStyle*<br/>
컨트롤의 그리기 스타일을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_drawwidth"></a>  CStockPropImpl::get_DrawWidth

컨트롤의 그리기 메서드를 사용한는 그리기 너비 (픽셀)를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>매개 변수

*pnDrawWidth*<br/>
픽셀 단위의 컨트롤의 너비 값을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_enabled"></a>  CStockPropImpl::get_Enabled

컨트롤이 사용 되는지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>매개 변수

*pbEnabled*<br/>
플래그 상태를 수신 하는 변수입니다. TRUE는 컨트롤 사용 됨을 나타냅니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_fillcolor"></a>  CStockPropImpl::get_FillColor

컨트롤의 채우기 색을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>매개 변수

*pclrFillColor*<br/>
컨트롤의 채우기 색을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_fillstyle"></a>  CStockPropImpl::get_FillStyle

단색, 투명 또는 크로스해칭 예를 들어, 컨트롤의 채우기 스타일을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>매개 변수

*pnFillStyle*<br/>
컨트롤의 채우기 스타일을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_font"></a>  CStockPropImpl::get_Font

컨트롤의 글꼴 속성에 대 한 포인터를 이동 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>매개 변수

*ppFont*<br/>
컨트롤의 글꼴 속성에 대 한 포인터를 받는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_forecolor"></a>  CStockPropImpl::get_ForeColor

컨트롤의 전경색을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>매개 변수

*pclrForeColor*<br/>
변수를 받는 컨트롤 전경색입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_hwnd"></a>  CStockPropImpl::get_HWND

컨트롤과 연결 된 창 핸들을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>매개 변수

*phWnd*<br/>
컨트롤과 연결 된 창 핸들입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_mouseicon"></a>  CStockPropImpl::get_MouseIcon

(아이콘, 비트맵 또는 메타 파일) 컨트롤 위에 마우스가 있을 때 표시할 그래픽의 그림 속성을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>매개 변수

*ppPicture*<br/>
그래픽의 그림 속성에 대 한 포인터를 받는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_mousepointer"></a>  CStockPropImpl::get_MousePointer

예를 들어 마우스가 컨트롤 위에 있을 때 표시 되는 마우스 포인터, 화살표, 간, 또는 모래 시계의 형식을 가져오기 위해이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>매개 변수

*pnMousePointer*<br/>
마우스 포인터의 유형을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_picture"></a>  CStockPropImpl::get_Picture

(아이콘, 비트맵 또는 메타 파일) 표시할 그래픽의 그림 속성에 대 한 포인터를 이동 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>매개 변수

*ppPicture*<br/>
그림의 속성에 대 한 포인터를 받는 변수입니다. 참조 [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) 대 한 자세한 내용은 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_readystate"></a>  CStockPropImpl::get_ReadyState

로드 또는 로드 예를 들어, 컨트롤의 준비 상태를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>매개 변수

*pnReadyState*<br/>
컨트롤의 준비 상태를 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_tabstop"></a>  CStockPropImpl::get_TabStop

컨트롤 탭 정지 인지 인지 여부를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>매개 변수

*pbTabStop*<br/>
플래그 상태를 수신 하는 변수입니다. TRUE는 컨트롤 탭은 임을 나타냅니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_text"></a>  CStockPropImpl::get_Text

컨트롤을 사용 하 여 표시 되는 텍스트를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>매개 변수

*pbstrText*<br/>
컨트롤을 사용 하 여 표시 되는 텍스트입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_valid"></a>  CStockPropImpl::getvalid

컨트롤은 유효한 경우를 나타내는 플래그의 상태를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>매개 변수

*pbValid*<br/>
플래그 상태를 수신 하는 변수입니다. TRUE는 컨트롤이 유효한 지를 나타냅니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="get_window"></a>  CStockPropImpl::get_Window

컨트롤과 연결 된 창 핸들을 가져오려면이 메서드를 호출 합니다. 동일 [CStockPropImpl::get_HWND](#get_hwnd)합니다.

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>매개 변수

*phWnd*<br/>
컨트롤과 연결 된 창 핸들입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_appearance"></a>  CStockPropImpl::put_Appearance

예를 들어, 플랫 컨트롤에 의해 사용 되는 그리기 스타일 또는 3D를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>매개 변수

*nAppearance*<br/>
컨트롤에서 사용할 새 그리기 스타일입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_autosize"></a>  CStockPropImpl::put_AutoSize

컨트롤에 다른 크기 일 수 없습니다 경우를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>매개 변수

*bAutoSize*<br/>
컨트롤에는 다른 크기 수 없는 경우 TRUE입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_backcolor"></a>  CStockPropImpl::put_BackColor

컨트롤의 배경색을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>매개 변수

*clrBackColor*<br/>
새 컨트롤 배경색입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_backstyle"></a>  CStockPropImpl::put_BackStyle

컨트롤의 배경 스타일을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>매개 변수

*nBackStyle*<br/>
새 컨트롤 배경 스타일입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_bordercolor"></a>  CStockPropImpl::put_BorderColor

컨트롤의 테두리 색을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>매개 변수

*clrBorderColor*<br/>
새 테두리 색입니다. 내부적으로 32 비트 정수 OLE_COLOR 데이터 형식이 표시 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_borderstyle"></a>  CStockPropImpl::put_BorderStyle

컨트롤의 테두리 스타일을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>매개 변수

*nBorderStyle*<br/>
새 테두리 스타일입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_bordervisible"></a>  CStockPropImpl::put_BorderVisible

컨트롤의 테두리를 표시할지 여부 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>매개 변수

*bBorderVisible*<br/>
테두리 표시 되도록 이면 TRUE입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_borderwidth"></a>  CStockPropImpl::put_BorderWidth

컨트롤의 테두리의 두께 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>매개 변수

*nBorderWidth*<br/>
컨트롤의 테두리의 새 너비입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_caption"></a>  CStockPropImpl::put_Caption

컨트롤을 사용 하 여 표시할 텍스트를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>매개 변수

*bstrCaption*<br/>
컨트롤을 사용 하 여 표시할 텍스트입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_drawmode"></a>  CStockPropImpl::put_DrawMode

컨트롤의 그리기 모드를 예를 들어, XOR 펜 또는 반전 색을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>매개 변수

*nDrawMode*<br/>
컨트롤에 대 한 새 그리기 모드입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_drawstyle"></a>  CStockPropImpl::put_DrawStyle

실선, 파선 또는 점으로 구분 된 예를 들어, 컨트롤의 그리기 스타일을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>매개 변수

*nDrawStyle*<br/>
컨트롤에 대 한 새 그리기 스타일입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_drawwidth"></a>  CStockPropImpl::put_DrawWidth

컨트롤의 그리기 메서드에서 사용 하는 너비 (픽셀)를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>매개 변수

*nDrawWidth*<br/>
컨트롤에서 사용할 새 너비의 그리기 메서드.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_enabled"></a>  CStockPropImpl::put_Enabled

컨트롤이 사용 되는지 여부를 나타내는 플래그의 값을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>매개 변수

*bEnabled*<br/>
컨트롤을 사용 하는 경우 TRUE입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_fillcolor"></a>  CStockPropImpl::put_FillColor

컨트롤의 채우기 색을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>매개 변수

*clrFillColor*<br/>
컨트롤에 대 한 새 채우기 색입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_fillstyle"></a>  CStockPropImpl::put_FillStyle

단색, 투명 또는 교차 무늬 예를 들어, 컨트롤의 채우기 스타일을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>매개 변수

*nFillStyle*<br/>
컨트롤에 대 한 새 채우기 스타일입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_font"></a>  CStockPropImpl::put_Font

컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
컨트롤의 글꼴 속성에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_forecolor"></a>  CStockPropImpl::put_ForeColor

컨트롤의 전경색을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>매개 변수

*clrForeColor*<br/>
컨트롤의 새 전경색입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_hwnd"></a>  CStockPropImpl::put_HWND

이 메서드는 E_FAIL을 반환합니다.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
예약됨.

### <a name="return-value"></a>반환 값

E_FAIL 반환.

### <a name="remarks"></a>설명

창 핸들에는 읽기 전용 값입니다.

##  <a name="put_mouseicon"></a>  CStockPropImpl::put_MouseIcon

(아이콘, 비트맵 또는 메타 파일) 컨트롤 위에 마우스가 있을 때 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>매개 변수

*pPicture*<br/>
그래픽의 그림 속성에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_mousepointer"></a>  CStockPropImpl::put_MousePointer

예를 들어 마우스가 컨트롤 위에 있을 때 표시 되는 마우스 포인터, 화살표, 간, 또는 모래 시계 유형을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>매개 변수

*nMousePointer*<br/>
마우스 포인터의 형식입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_picture"></a>  CStockPropImpl::put_Picture

(아이콘, 비트맵 또는 메타 파일) 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>매개 변수

*pPicture*<br/>
그림의 속성에 대 한 포인터입니다. 참조 [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) 대 한 자세한 내용은 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_readystate"></a>  CStockPropImpl::put_ReadyState

로드 또는 로드 예를 들어, 컨트롤의 준비 상태를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>매개 변수

*nReadyState*<br/>
컨트롤의 준비 상태입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_tabstop"></a>  CStockPropImpl::put_TabStop

컨트롤 탭 정지 인지 인지 여부를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>매개 변수

*bTabStop*<br/>
컨트롤에 탭 정지 이면 TRUE입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_text"></a>  CStockPropImpl::put_Text

컨트롤을 사용 하 여 표시 되는 텍스트를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>매개 변수

*bstrText*<br/>
컨트롤을 사용 하 여 표시 되는 텍스트입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_valid"></a>  CStockPropImpl::putvalid

컨트롤은 유효한 경우를 나타내는 플래그를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>매개 변수

*bValid*<br/>
컨트롤이 유효한 경우 TRUE입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="put_window"></a>  CStockPropImpl::put_Window

이 메서드를 호출 [CStockPropImpl::put_HWND](#put_hwnd)는 E_FAIL을 반환 합니다.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
창 핸들입니다.

### <a name="return-value"></a>반환 값

E_FAIL 반환.

### <a name="remarks"></a>설명

창 핸들에는 읽기 전용 값입니다.

##  <a name="putref_font"></a>  CStockPropImpl::putref_Font

참조 횟수를 사용 하 여 컨트롤의 글꼴 속성을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
컨트롤의 글꼴 속성에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

동일 [CStockPropImpl::put_Font](#put_font), 있지만 참조 횟수를 사용 하 여 합니다.

##  <a name="putref_mouseicon"></a>  CStockPropImpl::putref_MouseIcon

참조 횟수를 사용 하 여 (아이콘, 비트맵 또는 메타 파일)를 컨트롤 위에 마우스가 있을 때 표시할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>매개 변수

*pPicture*<br/>
그래픽의 그림 속성에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

동일 [CStockPropImpl::put_MouseIcon](#put_mouseicon), 있지만 참조 횟수를 사용 하 여 합니다.

##  <a name="putref_picture"></a>  CStockPropImpl::putref_Picture

참조 횟수를 사용 하 여 (아이콘, 비트맵 또는 메타 파일)를 표시 해야 할 그래픽의 그림 속성을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>매개 변수

*pPicture*<br/>
그림의 속성에 대 한 포인터입니다. 참조 [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) 대 한 자세한 내용은 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

동일 [CStockPropImpl::put_Picture](#put_picture), 있지만 참조 횟수를 사용 하 여 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)
