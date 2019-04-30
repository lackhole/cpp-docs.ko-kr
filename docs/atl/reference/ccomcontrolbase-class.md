---
title: CComControlBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
ms.openlocfilehash: 698912100244189bdec99fa3726a063eb2e907a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260112"
---
# <a name="ccomcontrolbase-class"></a>CComControlBase 클래스

이 클래스를 만들고 ATL 컨트롤을 관리 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CComControlBase::AppearanceType](#appearancetype)|재정의 하 `m_nAppearance` 스톡 속성은 형식의 **짧은**합니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComControlBase::CComControlBase](#ccomcontrolbase)|생성자입니다.|
|[CComControlBase::~CComControlBase](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|하는지 확인 합니다 *iVerb* 매개 변수에서 사용 하는 `IOleObjectImpl::DoVerb` 컨트롤의 사용자 인터페이스를 활성화 하거나 (*iVerb* OLEIVERB_UIACTIVATE 같음), 두 번 클릭할 때 수행할 동작을 정의 합니다 컨트롤 (*iVerb* OLEIVERB_PRIMARY 같음), 컨트롤을 표시 (*iVerb* OLEIVERB_SHOW 같음), 컨트롤을 활성화 하거나 (*iVerb* OLEIVERB 같음 _INPLACEACTIVATE)입니다.|
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|하는지 확인 합니다 *iVerb* 매개 변수에서 사용 하는 `IOleObjectImpl::DoVerb` 활성화 하려면 컨트롤의 사용자 인터페이스 시키고 TRUE를 반환 합니다.|
|[CComControlBase::DoVerbProperties](#doverbproperties)|컨트롤의 속성 페이지를 표시합니다.|
|[CComControlBase::FireViewChange](#fireviewchange)|컨트롤의 뷰가 변경 되는 등록 된 advise 싱크 알림 또는 컨트롤을 다시 그리게 컨테이너에 전달 하려면이 메서드를 호출 합니다.|
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|DISPID_AMBIENT_APPEARANCE, 현재 모양 컨트롤에 대 한 설정을 검색 합니다. 단순 및 3D에 대 한 1 0입니다.|
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|DISPID_AMBIENT_AUTOCLIP, 컨테이너 자동 클리핑이 컨트롤 표시 영역을 지원 하는지 여부를 나타내는 플래그를 검색 합니다.|
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|DISPID_AMBIENT_BACKCOLOR, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 배경색을 검색 합니다.|
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|DISPID_AMBIENT_CHARSET를 앰비언트 문자 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 집합을 검색 합니다.|
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|DISPID_AMBIENT_CODEPAGE를 앰비언트 문자 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 집합을 검색 합니다.|
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|DISPID_AMBIENT_DISPLAYASDEFAULT, 컨테이너는이 사이트는 기본 단추 컨트롤을 표시 하 고 따라서 단추 컨트롤을 그려야 자체 두꺼운 프레임을 사용 하 여이 하는 플래그를 검색 합니다.|
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|DISPID_AMBIENT_DISPLAYNAME, 컨테이너 컨트롤에 제공한 이름을 검색 합니다.|
|[CComControlBase::GetAmbientFont](#getambientfont)|검색 된 컨테이너에 대 한 포인터의 앰비언트 `IFont` 인터페이스입니다.|
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|검색 된 컨테이너에 대 한 포인터의 앰비언트 `IFontDisp` 디스패치 인터페이스입니다.|
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|DISPID_AMBIENT_FORECOLOR, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 전경색을 검색 합니다.|
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|DISPID_AMBIENT_LOCALEID, 컨테이너에서 사용 되는 언어의 식별자를 검색 합니다.|
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|DISPID_AMBIENT_MESSAGEREFLECT, 컨테이너 (예: WM_DRAWITEM) 이벤트로 창 메시지를 수신 하려고 하는지 여부를 나타내는 플래그를 검색 합니다.|
|[CComControlBase::GetAmbientPalette](#getambientpalette)|DISPID_AMBIENT_PALETTE, 컨테이너의 HPALETTE에 액세스 하는 데 사용을 검색 합니다.|
|[CComControlBase::GetAmbientProperty](#getambientproperty)|지정 된 컨테이너 속성 검색 *id*합니다.|
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|DISPID_AMBIENT_RIGHTTOLEFT, 콘텐츠를 컨테이너에 의해 표시 되는 방향을 검색 합니다.|
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|DISPID_AMBIENT_SCALEUNITS, 컨테이너의 앰비언트 단위 (예: 인치 또는 센티미터로) 표시 레이블 지정에 대 한를 검색 합니다.|
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|DISPID_AMBIENT_SHOWGRABHANDLES, 컨테이너가 활성 상태인 경우 자체에 대 한 잡기 핸들을 표시 하도록 컨트롤을 허용 하는지 여부를 나타내는 플래그를 검색 합니다.|
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|DISPID_AMBIENT_SHOWHATCHING, 컨테이너 UI 활성 상태일 때 교차 무늬 패턴을 사용 하 여 표시 하도록 컨트롤을 허용 하는지 여부를 나타내는 플래그를 검색 합니다.|
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|DISPID_AMBIENT_SUPPORTSMNEMONICS, 컨테이너 키보드 니모닉 지원 하는지 여부를 나타내는 플래그를 검색 합니다.|
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|DISPID_AMBIENT_TEXTALIGN, 컨테이너에서 지 원하는 기본 텍스트 맞춤을 검색 합니다. 일반 맞춤 (숫자 오른쪽 텍스트 왼쪽)에 대 한 0, 1 왼쪽된 맞춤, 가운데 맞춤에 대 한 2 및 오른쪽 맞춤에 대 한 3.|
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|DISPID_AMBIENT_TOPTOBOTTOM, 콘텐츠를 컨테이너에 의해 표시 되는 방향을 검색 합니다.|
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|DISPID_AMBIENT_UIDEAD, 컨테이너 컨트롤 사용자 인터페이스 작업에 응답할가 있는지 여부를 나타내는 플래그를 검색 합니다.|
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|DISPID_AMBIENT_USERMODE, 컨테이너 (TRUE)를 실행 모드 또는 디자인 모드 (FALSE) 인지 여부를 나타내는 플래그를 검색 합니다.|
|[CComControlBase::GetDirty](#getdirty)|데이터 멤버의 값을 반환 `m_bRequiresSave`합니다.|
|[CComControlBase::GetZoomInfo](#getzoominfo)|검색 x 및 y 값의 분자와 분모 확대/축소 비율의 활성화 된 컨트롤에 대 한 전체 편집 합니다.|
|[CComControlBase::InPlaceActivate](#inplaceactivate)|동사에 관계 없이 상태 비활성 상태에서 전환 컨트롤이 *iVerb* 나타냅니다.|
|[CComControlBase::InternalGetSite](#internalgetsite)|식별된 된 인터페이스에 대 한 포인터에 대 한 컨트롤 사이트를 쿼리 하기 위해이 메서드를 호출 합니다.|
|[CComControlBase::OnDraw](#ondraw)|컨트롤을 그리도록이 메서드를 재정의 합니다.|
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|기본값 `OnDrawAdvanced` 그리기에 대 한 정규화 된 장치 컨텍스트를 준비 합니다. 그런 다음 컨트롤 클래스의 호출 `OnDraw` 메서드.|
|[CComControlBase::OnKillFocus](#onkillfocus)|컨트롤 내부 활성 상태입니다. 유효한 컨트롤 사이트가 다음 알립니다 컨테이너 컨트롤에서 포커스를 잃었을 있는지를 확인 합니다.|
|[CComControlBase::OnMouseActivate](#onmouseactivate)|UI 사용자 모드에는 다음 컨트롤을 활성화를 확인 합니다.|
|[CComControlBase::OnPaint](#onpaint)|그리기에 대 한 컨테이너를 준비, 컨트롤의 클라이언트 영역을 가져옵니다 다음 컨트롤 클래스의 호출 `OnDraw` 메서드.|
|[CComControlBase::OnSetFocus](#onsetfocus)|컨트롤이 내부 활성 상태입니다. 유효한 컨트롤 사이트가 다음 컨테이너 컨트롤에 알립니다는 검사에 포커스가 있습니다.|
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|사용자 고유의 키보드 액셀러레이터 키 처리기를 제공 하려면이 메서드를 재정의 합니다.|
|[CComControlBase::SendOnClose](#sendonclose)|컨트롤이 닫 혔 음 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크를에 알립니다.|
|[CComControlBase::SendOnDataChange](#sendondatachange)|컨트롤 데이터가 변경 되었음을 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크를에 알립니다.|
|[CComControlBase::SendOnRename](#sendonrename)|컨트롤에는 새 모니커 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크를에 알립니다.|
|[CComControlBase::SendOnSave](#sendonsave)|컨트롤에 저장 된 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크를에 알립니다.|
|[CComControlBase::SendOnViewChange](#sendonviewchange)|등록 된 모든 공지 싱크에 컨트롤의 뷰 변경 되었음을 알립니다.|
|[CComControlBase::SetControlFocus](#setcontrolfocus)|설정 하거나 또는 컨트롤에 키보드 포커스를 제거 합니다.|
|[CComControlBase::SetDirty](#setdirty)|데이터 멤버를 설정 `m_bRequiresSave` 에 값 *bDirty*합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComControlBase::m_bAutoSize](#m_bautosize)|컨트롤에는 다른 크기 일 수 없습니다를 나타내는 플래그입니다.|
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|플래그를 나타내는 `IDataObjectImpl::GetData` 하 고 `CComControlBase::GetZoomInfo` 에서 컨트롤 크기를 설정 해야 `m_sizeNatural` 아닌 `m_sizeExtent`합니다.|
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|플래그를 나타내는 `IDataObjectImpl::GetData` 그릴 때 HIMETRIC 단위 및 픽셀이 아닌 사용 해야 합니다.|
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|전체 활성 컨트롤이 나타내는 플래그입니다.|
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|컨테이너 지원을 나타내는 플래그를 `IOleInPlaceSiteEx` 인터페이스 및 OCX96 창 및 깜박임 컨트롤과 같은 기능을 제어 합니다.|
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|OCX96 제어 기능 (예: 깜박임 창 없는 컨트롤)에 대 한 지원에 대 한 컨테이너를 사용 하 여 컨트롤에 협상 하는 여부 및 기간 이동 또는 창 없는 컨트롤 인지를 나타내는 플래그입니다.|
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|컨트롤 컨테이너 컨트롤의 디스플레이 크기 변경 되 면 표시를 재구성 하려는 나타내는 플래그입니다.|
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|컨트롤은 마지막으로 저장 된 이후 변경 되었음을 나타내는 플래그입니다.|
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|컨트롤의 자연 스러운 범위가 (소수 자릿수가 없는 실제 크기)의 크기를 조정 하려고 함을 나타내는 플래그 컨테이너 컨트롤의 디스플레이 크기를 변경 하는 경우.|
|[CComControlBase::m_bUIActive](#m_buiactive)|메뉴 및 도구 모음 같은 컨트롤의 사용자 인터페이스를 나타내는 플래그는 활성 상태입니다.|
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|컨트롤 컨테이너 제공 된 창 영역을 사용 하는 나타내는 플래그입니다.|
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|컨트롤, 창 없는 되었습니다 하지만 수 또는 아닐 창 없는 이제 나타내는 플래그입니다.|
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|컨테이너 창 없는 컨트롤을 지 원하는 경우에 컨트롤, 기간 이동 해야 나타내는 플래그입니다.|
|[CComControlBase::m_bWndLess](#m_bwndless)|창 없는 컨트롤을 나타내는 플래그입니다.|
|[CComControlBase::m_hWndCD](#m_hwndcd)|컨트롤과 연결 된 창 핸들에 대 한 참조를 포함 합니다.|
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|횟수 수가 컨테이너에 이벤트 (이벤트에 대 한 동의)의 중간는 재개 하지 않고 이벤트 (이벤트 수락을 거부) 고정 합니다.|
|[CComControlBase::m_rcPos](#m_rcpos)|컨테이너의 좌표로 표시 되는 컨트롤의 위치 (픽셀)에서입니다.|
|[CComControlBase::m_sizeExtent](#m_sizeextent)|특정 디스플레이 HIMETRIC 단위 (단위당은 0.01 밀리미터)에서 컨트롤의 범위입니다.|
|[CComControlBase::m_sizeNatural](#m_sizenatural)|HIMETRIC 단위 (단위당은 0.01 밀리미터)에서 컨트롤의 실제 크기입니다.|
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|컨테이너에서 권장 하는 연결에 대 한 직접 포인터 (컨테이너의 [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink)).|
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|A `CComDispatchDriver` 를 검색 하 고 컨테이너의 속성을 설정할 수 있는 개체는 `IDispatch` 포인터입니다.|
|[CComControlBase::m_spClientSite](#m_spclientsite)|컨테이너 내에서 컨트롤의 클라이언트 사이트에 대 한 포인터입니다.|
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|표준 의미를 데이터 개체 간의 자문 연결을 보유할 advise 싱크를 제공 합니다.|
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|컨테이너의에 대 한 포인터 [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite)를 [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), 또는 [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) 인터페이스 포인터입니다.|
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|자문 연결을 보유 하는 방법은의 표준 구현을 제공 합니다.|

## <a name="remarks"></a>설명

이 클래스를 만들고 ATL 컨트롤을 관리 하기 위한 메서드를 제공 합니다. [CComControl 클래스](../../atl/reference/ccomcontrol-class.md) 에서 파생 `CComControlBase`합니다. ATL 컨트롤 마법사를 사용 하는 표준 컨트롤 또는 DHTML 컨트롤을 만들 때 마법사는 자동으로에서 파생 `CComControlBase`합니다.

컨트롤을 만드는 방법에 대 한 자세한 내용은 참조는 [ATL 자습서](../../atl/active-template-library-atl-tutorial.md)합니다. ATL 프로젝트 마법사에 대 한 자세한 내용은 문서 참조 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="appearancetype"></a>  CComControlBase::AppearanceType

재정의 하 `m_nAppearance` 스톡 속성은 형식의 **짧은**합니다.

```
typedef short AppearanceType;
```

### <a name="remarks"></a>설명

ATL 컨트롤 마법사 추가 `m_nAppearance` 스톡 짧은 형식의 속성입니다. 재정의 `AppearanceType` 다른 데이터 형식을 사용 하는 경우.

##  <a name="ccomcontrolbase"></a>  CComControlBase::CComControlBase

생성자입니다.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
컨트롤과 연결 된 창에 대 한 핸들입니다.

### <a name="remarks"></a>설명

컨트롤 크기를 HIMETRIC 단위 5080 X 5080 초기화 ("2" X 2)를 초기화 하 고는 `CComControlBase` 데이터 멤버 값을 NULL 또는 FALSE입니다.

##  <a name="dtor"></a>  CComControlBase::~CComControlBase

소멸자입니다.

```
~CComControlBase();
```

### <a name="remarks"></a>설명

컨트롤이 창에 있으면 `~CComControlBase` 를 호출 하 여 소멸 [DestroyWindow](/windows/desktop/api/winuser/nf-winuser-destroywindow)합니다.

##  <a name="controlqueryinterface"></a>  CComControlBase::ControlQueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
요청 된 인터페이스의 GUID입니다.

*ppv*<br/>
로 식별 되는 인터페이스 포인터에 대 한 포인터 *iid*, 또는 인터페이스를 찾을 수 없으면 NULL입니다.

### <a name="remarks"></a>설명

COM 맵 테이블의 인터페이스만 처리 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

##  <a name="doesverbactivate"></a>  CComControlBase::DoesVerbActivate

하는지 확인 합니다 *iVerb* 매개 변수에서 사용 하는 `IOleObjectImpl::DoVerb` 컨트롤의 사용자 인터페이스를 활성화 하거나 (*iVerb* OLEIVERB_UIACTIVATE 같음), 두 번 클릭할 때 수행할 동작을 정의 합니다 컨트롤 (*iVerb* OLEIVERB_PRIMARY 같음), 컨트롤을 표시 (*iVerb* OLEIVERB_SHOW 같음), 컨트롤을 활성화 하거나 (*iVerb* OLEIVERB 같음 _INPLACEACTIVATE)입니다.

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
값의 동작을 수행 하도록 나타내는 `DoVerb`합니다.

### <a name="return-value"></a>반환 값

TRUE를 반환 합니다 *iVerb* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW, 또는 OLEIVERB_INPLACEACTIVATE equals, 그렇지 않으면 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

사용자 고유의 활성화 동사를 정의 하려면이 메서드를 재정의할 수 있습니다.

##  <a name="doesverbuiactivate"></a>  CComControlBase::DoesVerbUIActivate

하는지 확인 합니다 *iVerb* 매개 변수에서 사용 하는 `IOleObjectImpl::DoVerb` 활성화 하려면 컨트롤의 사용자 인터페이스 시키고 TRUE를 반환 합니다.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
값의 동작을 수행 하도록 나타내는 `DoVerb`합니다.

### <a name="return-value"></a>반환 값

TRUE를 반환 합니다 *iVerb* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW, 또는 OLEIVERB_INPLACEACTIVATE와 같습니다. 그렇지 않으면 메서드는 FALSE를 반환합니다.

##  <a name="doverbproperties"></a>  CComControlBase::DoVerbProperties

컨트롤의 속성 페이지를 표시합니다.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
예약됨.

*hwndParent*<br/>
컨트롤이 포함 된 창 핸들입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

##  <a name="fireviewchange"></a>  CComControlBase::FireViewChange

컨트롤의 뷰가 변경 되는 등록 된 advise 싱크 알림 또는 컨트롤을 다시 그리게 컨테이너에 전달 하려면이 메서드를 호출 합니다.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

컨트롤이 활성화 된 경우 (컨트롤 클래스 데이터 멤버 [CComControlBase::m_bInPlaceActive](#m_binplaceactive) true), 전체 컨트롤을 다시 그리도록 하려면 컨테이너에 알립니다. 컨트롤에 현재 없는 경우 컨트롤의 등록 된 알립니다 싱크는 것이 좋습니다 (컨트롤 클래스 데이터 멤버를 통해 [CComControlBase::m_spAdviseSink](#m_spadvisesink)) 컨트롤의 뷰 변경 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

##  <a name="getambientappearance"></a>  CComControlBase::GetAmbientAppearance

DISPID_AMBIENT_APPEARANCE, 현재 모양 컨트롤에 대 한 설정을 검색 합니다. 단순 및 3D에 대 한 1 0입니다.

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>매개 변수

*nAppearance*<br/>
DISPID_AMBIENT_APPEARANCE 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

##  <a name="getambientautoclip"></a>  CComControlBase::GetAmbientAutoClip

DISPID_AMBIENT_AUTOCLIP, 컨테이너 자동 클리핑이 컨트롤 표시 영역을 지원 하는지 여부를 나타내는 플래그를 검색 합니다.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>매개 변수

*bAutoClip*<br/>
DISPID_AMBIENT_AUTOCLIP 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientbackcolor"></a>  CComControlBase::GetAmbientBackColor

DISPID_AMBIENT_BACKCOLOR, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 배경색을 검색 합니다.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>매개 변수

*BackColor*<br/>
DISPID_AMBIENT_BACKCOLOR 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientcharset"></a>  CComControlBase::GetAmbientCharSet

DISPID_AMBIENT_CHARSET를 앰비언트 문자 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 집합을 검색 합니다.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>매개 변수

*bstrCharSet*<br/>
DISPID_AMBIENT_CHARSET 속성입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="getambientcodepage"></a>  CComControlBase::GetAmbientCodePage

DISPID_AMBIENT_CODEPAGE, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 코드 페이지를 검색 합니다.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>매개 변수

*ulCodePage*<br/>
DISPID_AMBIENT_CODEPAGE 속성입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="getambientdisplayasdefault"></a>  CComControlBase::GetAmbientDisplayAsDefault

DISPID_AMBIENT_DISPLAYASDEFAULT, 컨테이너는이 사이트는 기본 단추 컨트롤을 표시 하 고 따라서 단추 컨트롤을 그려야 자체 두꺼운 프레임을 사용 하 여이 하는 플래그를 검색 합니다.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>매개 변수

*bDisplayAsDefault*<br/>
DISPID_AMBIENT_DISPLAYASDEFAULT 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientdisplayname"></a>  CComControlBase::GetAmbientDisplayName

DISPID_AMBIENT_DISPLAYNAME, 컨테이너 컨트롤에 제공한 이름을 검색 합니다.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>매개 변수

*bstrDisplayName*<br/>
DISPID_AMBIENT_DISPLAYNAME 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientfont"></a>  CComControlBase::GetAmbientFont

검색 된 컨테이너에 대 한 포인터의 앰비언트 `IFont` 인터페이스입니다.

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>매개 변수

*ppFont*<br/>
컨테이너에 대 한 포인터의 앰비언트 [IFont](/windows/desktop/api/ocidl/nn-ocidl-ifont) 인터페이스입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

속성이 NULL 인 경우 NULL 포인터가 됩니다. 포인터가 NULL이 아닌 경우 호출자는 포인터를 해제 해야 합니다.

##  <a name="getambientfontdisp"></a>  CComControlBase::GetAmbientFontDisp

검색 된 컨테이너에 대 한 포인터의 앰비언트 `IFontDisp` 디스패치 인터페이스입니다.

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>매개 변수

*ppFont*<br/>
컨테이너에 대 한 포인터의 앰비언트 [IFontDisp](/windows/desktop/api/ocidl/nn-ocidl-ifontdisp) 디스패치 인터페이스입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

속성이 NULL 인 경우 NULL 포인터가 됩니다. 포인터가 NULL이 아닌 경우 호출자는 포인터를 해제 해야 합니다.

##  <a name="getambientforecolor"></a>  CComControlBase::GetAmbientForeColor

DISPID_AMBIENT_FORECOLOR, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 전경색을 검색 합니다.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>매개 변수

*ForeColor*<br/>
DISPID_AMBIENT_FORECOLOR 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientlocaleid"></a>  CComControlBase::GetAmbientLocaleID

DISPID_AMBIENT_LOCALEID, 컨테이너에서 사용 되는 언어의 식별자를 검색 합니다.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>매개 변수

*lcid*<br/>
DISPID_AMBIENT_LOCALEID 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

컨트롤을 다른 언어로 사용자 인터페이스에 맞게이 식별자를 사용할 수 있습니다.

##  <a name="getambientmessagereflect"></a>  CComControlBase::GetAmbientMessageReflect

DISPID_AMBIENT_MESSAGEREFLECT, 컨테이너를 창 메시지를 수신 하려고 하는지 여부를 나타내는 플래그를 검색 합니다 (같은 `WM_DRAWITEM`) 이벤트로 합니다.

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>매개 변수

*bMessageReflect*<br/>
DISPID_AMBIENT_MESSAGEREFLECT 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientpalette"></a>  CComControlBase::GetAmbientPalette

DISPID_AMBIENT_PALETTE, 컨테이너의 HPALETTE에 액세스 하는 데 사용을 검색 합니다.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>매개 변수

*hPalette*<br/>
DISPID_AMBIENT_PALETTE 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientproperty"></a>  CComControlBase::GetAmbientProperty

지정 된 컨테이너 속성 검색 *dispid*합니다.

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
검색할 컨테이너 속성의 식별자입니다.

*var*<br/>
변수 속성을 받을입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

ATL 예를 들어, 특정 속성을 검색 하는 도우미 함수 집합을 제공 했습니다 [CComControlBase::GetAmbientBackColor](#getambientbackcolor)합니다. 사용 하 여 사용할 수 있는 적절 한 방법을 없으면 `GetAmbientProperty`합니다.

##  <a name="getambientrighttoleft"></a>  CComControlBase::GetAmbientRightToLeft

DISPID_AMBIENT_RIGHTTOLEFT, 콘텐츠를 컨테이너에 의해 표시 되는 방향을 검색 합니다.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>매개 변수

*bRightToLeft*<br/>
DISPID_AMBIENT_RIGHTTOLEFT 속성입니다. 콘텐츠는 왼쪽에서 오른쪽으로 표시 되어 있는 경우 오른쪽에서 왼쪽으로 false로 표시 되 면 TRUE로 설정 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="getambientscaleunits"></a>  CComControlBase::GetAmbientScaleUnits

DISPID_AMBIENT_SCALEUNITS, 컨테이너의 앰비언트 단위 (예: 인치 또는 센티미터로) 표시 레이블 지정에 대 한를 검색 합니다.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>매개 변수

*bstrScaleUnits*<br/>
DISPID_AMBIENT_SCALEUNITS 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientshowgrabhandles"></a>  CComControlBase::GetAmbientShowGrabHandles

DISPID_AMBIENT_SHOWGRABHANDLES, 컨테이너가 활성 상태인 경우 자체에 대 한 잡기 핸들을 표시 하도록 컨트롤을 허용 하는지 여부를 나타내는 플래그를 검색 합니다.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>매개 변수

*bShowGrabHandles*<br/>
DISPID_AMBIENT_SHOWGRABHANDLES 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientshowhatching"></a>  CComControlBase::GetAmbientShowHatching

DISPID_AMBIENT_SHOWHATCHING, 컨테이너 컨트롤의 사용자 인터페이스 활성 상태일 때 교차 무늬 패턴을 사용 하 여 표시 하도록 컨트롤을 허용 하는지 여부를 나타내는 플래그를 검색 합니다.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>매개 변수

*bShowHatching*<br/>
DISPID_AMBIENT_SHOWHATCHING 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambientsupportsmnemonics"></a>  CComControlBase::GetAmbientSupportsMnemonics

DISPID_AMBIENT_SUPPORTSMNEMONICS, 컨테이너 키보드 니모닉 지원 하는지 여부를 나타내는 플래그를 검색 합니다.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>매개 변수

*bSupportsMnemonics*<br/>
DISPID_AMBIENT_SUPPORTSMNEMONICS 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambienttextalign"></a>  CComControlBase::GetAmbientTextAlign

DISPID_AMBIENT_TEXTALIGN, 컨테이너에서 지 원하는 기본 텍스트 맞춤을 검색 합니다. 일반 맞춤 (숫자 오른쪽 텍스트 왼쪽)에 대 한 0, 1 왼쪽된 맞춤, 가운데 맞춤에 대 한 2 및 오른쪽 맞춤에 대 한 3.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>매개 변수

*nTextAlign*<br/>
DISPID_AMBIENT_TEXTALIGN 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getambienttoptobottom"></a>  CComControlBase::GetAmbientTopToBottom

DISPID_AMBIENT_TOPTOBOTTOM, 콘텐츠를 컨테이너에 의해 표시 되는 방향을 검색 합니다.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>매개 변수

*bTopToBottom*<br/>
DISPID_AMBIENT_TOPTOBOTTOM 속성입니다. 텍스트 표시 되 면 TRUE로 설정 위쪽에서 아래쪽, 있으면 FALSE 표시 아래쪽 맨 위로 이동 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="getambientuidead"></a>  CComControlBase::GetAmbientUIDead

DISPID_AMBIENT_UIDEAD, 컨테이너 컨트롤 사용자 인터페이스 작업에 응답할가 있는지 여부를 나타내는 플래그를 검색 합니다.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>매개 변수

*bUIDead*<br/>
DISPID_AMBIENT_UIDEAD 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

True 이면 컨트롤이 응답 하지 해야 합니다. 이 플래그는 DISPID_AMBIENT_USERMODE 플래그에 관계 없이 적용 됩니다. 참조 [CComControlBase::GetAmbientUserMode](#getambientusermode)합니다.

##  <a name="getambientusermode"></a>  CComControlBase::GetAmbientUserMode

DISPID_AMBIENT_USERMODE, 컨테이너 (TRUE)를 실행 모드 또는 디자인 모드 (FALSE) 인지 여부를 나타내는 플래그를 검색 합니다.

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>매개 변수

*bUserMode*<br/>
DISPID_AMBIENT_USERMODE 속성입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="getdirty"></a>  CComControlBase::GetDirty

데이터 멤버의 값을 반환 `m_bRequiresSave`합니다.

```
BOOL GetDirty();
```

### <a name="return-value"></a>반환 값

데이터 멤버의 값을 반환 [m_bRequiresSave](#m_brequiressave)합니다.

### <a name="remarks"></a>설명

사용 하 여이 값은 설정 [CComControlBase::SetDirty](#setdirty)합니다.

##  <a name="getzoominfo"></a>  CComControlBase::GetZoomInfo

검색 x 및 y 값의 분자와 분모 확대/축소 비율의 활성화 된 컨트롤에 대 한 전체 편집 합니다.

```
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>매개 변수

*di*<br/>
확대/축소 비율의 분자와 분모를 보유 하는 구조입니다. 자세한 내용은 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)합니다.

### <a name="remarks"></a>설명

확대/축소 비율은 현재 범위에 해당 컨트롤의 기본 크기의 비율입니다.

##  <a name="inplaceactivate"></a>  CComControlBase::InPlaceActivate

동사에 관계 없이 상태 비활성 상태에서 전환 컨트롤이 *iVerb* 나타냅니다.

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>매개 변수

*iVerb*<br/>
값에서 수행할 작업을 나타내는 [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb)합니다.

*prcPosRect*<br/>
전체 컨트롤의 위치에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

활성화 하기 전에이 메서드는 컨트롤 클라이언트 사이트가, 컨트롤의 표시 되는, 확인 및 부모 창에서 컨트롤의 위치를 가져옵니다을 확인 합니다. 컨트롤이 활성화 된 후이 메서드는 컨트롤의 사용자 인터페이스를 활성화 하 고 컨트롤을 표시 되도록 컨테이너에 지시 합니다.

이 메서드는 또한 검색을 `IOleInPlaceSite`, `IOleInPlaceSiteEx`, 또는 `IOleInPlaceSiteWindowless` 인터페이스 포인터를 컨트롤에 대 한 컨트롤 클래스의 데이터 멤버에 저장 합니다 [CComControlBase::m_spInPlaceSite](#m_spinplacesite)합니다. 컨트롤 클래스 데이터 멤버 [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)를 [CComControlBase::m_bWndLess](#m_bwndless)합니다 [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless), 및 [ CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) 적절 하 게 true로 설정 됩니다.

##  <a name="internalgetsite"></a>  CComControlBase::InternalGetSite

식별된 된 인터페이스에 대 한 포인터에 대 한 컨트롤 사이트를 쿼리 하기 위해이 메서드를 호출 합니다.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
반환 되어야 하는 인터페이스 포인터의 IID *ppUnkSite*합니다.

*ppUnkSite*<br/>
요청 된 인터페이스 포인터를 받는 포인터 변수의 주소입니다 *riid*합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

사이트에서 요청 된 인터페이스를 지 원하는 경우 *riid*를 이용 하 여 반환 된 포인터는 *ppUnkSite*합니다. 그렇지 않으면 *ppUnkSite* NULL로 설정 됩니다.

##  <a name="m_bautosize"></a>  CComControlBase::m_bAutoSize

컨트롤에는 다른 크기 일 수 없습니다를 나타내는 플래그입니다.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>설명

이 플래그는으로 선택 되어 `IOleObjectImpl::SetExtent` TRUE 인 경우 사용 하면 함수에서 E_FAIL을 반환 하 고 있습니다.

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

추가 하는 경우는 **자동 크기 조정** 옵션을 [스톡 속성](../../atl/reference/stock-properties-atl-control-wizard.md) ATL 컨트롤 마법사, 마법사의 탭 자동으로 컨트롤 클래스의이 데이터 멤버를 만들고, put 만들고 get 메서드와 속성에 대 한 를 지원 하 고 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) 속성이 변경 되 면 컨테이너를 자동으로 알립니다.

##  <a name="m_bdrawfromnatural"></a>  CComControlBase::m_bDrawFromNatural

플래그를 나타내는 `IDataObjectImpl::GetData` 하 고 `CComControlBase::GetZoomInfo` 에서 컨트롤 크기를 설정 해야 `m_sizeNatural` 아닌 `m_sizeExtent`합니다.

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_bdrawgetdatainhimetric"></a>  CComControlBase::m_bDrawGetDataInHimetric

플래그를 나타내는 `IDataObjectImpl::GetData` 그릴 때 HIMETRIC 단위 및 픽셀이 아닌 사용 해야 합니다.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>설명

각 논리 HIMETRIC 단위는 0.01mm 이며

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_binplaceactive"></a>  CComControlBase::m_bInPlaceActive

전체 활성 컨트롤이 나타내는 플래그입니다.

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>설명

즉, 컨트롤이 표시 되 고 해당 창 있는 경우은 표시 되지만 해당 메뉴 및 도구 모음 활성화 될 수 있습니다. `m_bUIActive` 플래그 메뉴 같은 컨트롤의 사용자 인터페이스에도 작동을 나타냅니다.

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_binplacesiteex"></a>  CComControlBase::m_bInPlaceSiteEx

컨테이너 지원을 나타내는 플래그를 `IOleInPlaceSiteEx` 인터페이스 및 OCX96 창 및 깜박임 컨트롤과 같은 기능을 제어 합니다.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

데이터 멤버 `m_spInPlaceSite` 가리키는 [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite)를 [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), 또는 [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) 값에 따라 인터페이스는 `m_bWndLess` 고 `m_bInPlaceSiteEx` 플래그입니다. (데이터 멤버 `m_bNegotiatedWnd` TRUE 여야에 대 한는 `m_spInPlaceSite` 유효에 대 한 포인터입니다.)

하는 경우 `m_bWndLess` 가 FALSE 및 `m_bInPlaceSiteEx` 가 TRUE 인 `m_spInPlaceSite` 가 `IOleInPlaceSiteEx` 인터페이스 포인터입니다. 참조 [m_spInPlaceSite](#m_spinplacesite) 이러한 세 가지 데이터 멤버 간의 관계를 보여 주는 표입니다.

##  <a name="m_bnegotiatedwnd"></a>  CComControlBase::m_bNegotiatedWnd

OCX96 제어 기능 (예: 깜박임 창 없는 컨트롤)에 대 한 지원에 대 한 컨테이너를 사용 하 여 컨트롤에 협상 하는 여부 및 기간 이동 또는 창 없는 컨트롤 인지를 나타내는 플래그입니다.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

합니다 `m_bNegotiatedWnd` 플래그가 TRUE 여야 합니다.에 대 한는 `m_spInPlaceSite` 유효에 대 한 포인터입니다.

##  <a name="m_brecomposeonresize"></a>  CComControlBase::m_bRecomposeOnResize

컨트롤 컨테이너 컨트롤의 디스플레이 크기 변경 되 면 표시를 재구성 하려는 나타내는 플래그입니다.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

이 플래그는 확인자 [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) TRUE 인 경우 `SetExtent` 변경 내용 보기의 컨테이너에 알립니다. OLEMISC_RECOMPOSEONRESIZE 비트이 플래그를 설정 합니다 [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) 열거형 설정 해야 합니다.

##  <a name="m_brequiressave"></a>  CComControlBase::m_bRequiresSave

컨트롤은 마지막으로 저장 된 이후 변경 되었음을 나타내는 플래그입니다.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>설명

변수의 `m_bRequiresSave` 로 설정할 수 있습니다 [CComControlBase::SetDirty](#setdirty) 사용 하 여 검색 하 고 [CComControlBase::GetDirty](#getdirty)합니다.

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_bresizenatural"></a>  CComControlBase::m_bResizeNatural

컨트롤의 자연 스러운 범위가 (소수 자릿수가 없는 실제 크기)의 크기를 조정 하려고 함을 나타내는 플래그 컨테이너 컨트롤의 디스플레이 크기를 변경 하는 경우.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>설명

이 플래그는 확인자 `IOleObjectImpl::SetExtent` 및 크기에 전달 된 값이 true 이면 `SetExtent` 에 할당 된 `m_sizeNatural`합니다.

크기에 전달 `SetExtent` 항상 할당할 `m_sizeExtent`의 값에 관계 없이, `m_bResizeNatural`합니다.

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_buiactive"></a>  CComControlBase::m_bUIActive

메뉴 및 도구 모음 같은 컨트롤의 사용자 인터페이스를 나타내는 플래그는 활성 상태입니다.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>설명

`m_bInPlaceActive` 플래그 되었음을 컨트롤 활성, 하지만 하지는 활성화 된 해당 사용자 인터페이스입니다.

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_busingwindowrgn"></a>  CComControlBase::m_bUsingWindowRgn

컨트롤 컨테이너 제공 된 창 영역을 사용 하는 나타내는 플래그입니다.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_bwasoncewindowless"></a>  CComControlBase::m_bWasOnceWindowless

컨트롤, 창 없는 되었습니다 하지만 수 또는 아닐 창 없는 이제 나타내는 플래그입니다.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_bwindowonly"></a>  CComControlBase::m_bWindowOnly

컨테이너 창 없는 컨트롤을 지 원하는 경우에 컨트롤, 기간 이동 해야 나타내는 플래그입니다.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_bwndless"></a>  CComControlBase::m_bWndLess

창 없는 컨트롤을 나타내는 플래그입니다.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

데이터 멤버 `m_spInPlaceSite` 가리키는 [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite)를 [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), 또는 [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) 값에 따라 인터페이스는 `m_bWndLess` 하 고 [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) 플래그입니다. (데이터 멤버 [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) TRUE 여야에 대 한 합니다 [CComControlBase::m_spInPlaceSite](#m_spinplacesite) 유효에 대 한 포인터입니다.)

하는 경우 `m_bWndLess` 가 TRUE 인 `m_spInPlaceSite` 되는 `IOleInPlaceSiteWindowless` 인터페이스 포인터입니다. 참조 [CComControlBase::m_spInPlaceSite](#m_spinplacesite) 이러한 데이터 멤버의 전체 관계를 보여 주는 표입니다.

##  <a name="m_hwndcd"></a>  CComControlBase::m_hWndCD

컨트롤과 연결 된 창 핸들에 대 한 참조를 포함 합니다.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_nfreezeevents"></a>  CComControlBase::m_nFreezeEvents

횟수 수가 컨테이너에 이벤트 (이벤트에 대 한 동의)의 중간는 재개 하지 않고 이벤트 (이벤트 수락을 거부) 고정 합니다.

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_rcpos"></a>  CComControlBase::m_rcPos

컨테이너의 좌표로 표시 되는 컨트롤의 위치 (픽셀)에서입니다.

```
RECT m_rcPos;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_sizeextent"></a>  CComControlBase::m_sizeExtent

특정 디스플레이 HIMETRIC 단위 (단위당은 0.01 밀리미터)에서 컨트롤의 범위입니다.

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

이 크기를 표시 하 여 크기가 조정 됩니다. 에 지정 된 컨트롤의 실제 크기는 `m_sizeNatural` 데이터 멤버 고정 됩니다.

전역 함수를 사용 하 여 픽셀 크기를 변환할 수 있습니다 [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)합니다.

##  <a name="m_sizenatural"></a>  CComControlBase::m_sizeNatural

HIMETRIC 단위 (단위당은 0.01 밀리미터)에서 컨트롤의 실제 크기입니다.

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

이 크기는 고정 크기 하는 동안 `m_sizeExtent` 표시에서 크기가 조정 됩니다.

전역 함수를 사용 하 여 픽셀 크기를 변환할 수 있습니다 [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)합니다.

##  <a name="m_spadvisesink"></a>  CComControlBase::m_spAdviseSink

컨테이너에서 권장 하는 연결에 대 한 직접 포인터 (컨테이너의 [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink)).

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_spambientdispatch"></a>  CComControlBase::m_spAmbientDispatch

A `CComDispatchDriver` 를 검색 하 고 개체의 속성을 설정할 수 있는 개체는 `IDispatch` 포인터입니다.

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_spclientsite"></a>  CComControlBase::m_spClientSite

컨테이너 내에서 컨트롤의 클라이언트 사이트에 대 한 포인터입니다.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

##  <a name="m_spdataadviseholder"></a>  CComControlBase::m_spDataAdviseHolder

표준 의미를 데이터 개체 간의 자문 연결을 보유할 advise 싱크를 제공 합니다.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

데이터 개체는 구현 하는 데이터를 전송할 수 있는 컨트롤 [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject), 메서드가 데이터의 형식 및 전송 미디어를 지정 합니다.

인터페이스 `m_spDataAdviseHolder` 구현 합니다 [IDataObject::DAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dadvise) 및 [IDataObject::DUnadvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dunadvise) 메서드를 설정 하 고 컨테이너에 대 한 자문 연결을 삭제 합니다. 컨트롤의 컨테이너를 지원 하 여 advise 싱크를 구현 해야 합니다 [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) 인터페이스입니다.

##  <a name="m_spinplacesite"></a>  CComControlBase::m_spInPlaceSite

컨테이너의에 대 한 포인터 [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite)를 [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), 또는 [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) 인터페이스 포인터입니다.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

합니다 `m_spInPlaceSite` 포인터가 유효한 경우에만 합니다 [m_bNegotiatedWnd](#m_bnegotiatedwnd) 플래그는 TRUE입니다.

다음 표는 하는 방법을 `m_spInPlaceSite` 포인터 형식에 따라 달라 집니다 합니다 [m_bWndLess](#m_bwndless) 하 고 [m_bInPlaceSiteEx](#m_binplacesiteex) 데이터 멤버 플래그:

|m_spInPlaceSite 형식|m_bWndLess 값|m_bInPlaceSiteEx Value|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|TRUE|TRUE 또는 FALSE|
|`IOleInPlaceSiteEx`|FALSE|true|
|`IOleInPlaceSite`|FALSE|FALSE|

##  <a name="m_spoleadviseholder"></a>  CComControlBase::m_spOleAdviseHolder

자문 연결을 보유 하는 방법은의 표준 구현을 제공 합니다.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 컨트롤 클래스는 기본 클래스에 공용 구조체 내에서 선언 되어 있어이 데이터 멤버의 기본 클래스에서 상속 하지 않습니다.

인터페이스 `m_spOleAdviseHolder` 구현 합니다 [IOleObject::Advise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-advise) 및 [IOleObject::Unadvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-unadvise) 메서드를 설정 하 고 컨테이너에 대 한 자문 연결을 삭제 합니다. 컨트롤의 컨테이너를 지원 하 여 advise 싱크를 구현 해야 합니다 [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) 인터페이스입니다.

##  <a name="ondraw"></a>  CComControlBase::OnDraw

컨트롤을 그리도록이 메서드를 재정의 합니다.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>매개 변수

*di*<br/>
에 대 한 참조를 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) 그리기 측면을 컨트롤 범위 같은 그리기 정보가 포함 된 구조체 그리기 최적화 여부 및 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

기본값 `OnDraw` 삭제 또는 장치 컨텍스트를 복원 하지에 설정 된 플래그에 따라 [CComControlBase::OnDrawAdvanced](#ondrawadvanced)합니다.

`OnDraw` 메서드가 ATL 컨트롤 마법사를 사용 하 여 컨트롤을 만들 때 자동으로 컨트롤 클래스에 추가 됩니다. 마법사의 기본 `OnDraw` "ATL 8.0" 레이블이 있는 사각형을 그립니다.

### <a name="example"></a>예제

예를 참조 하세요 [CComControlBase::GetAmbientAppearance](#getambientappearance)합니다.

##  <a name="ondrawadvanced"></a>  CComControlBase::OnDrawAdvanced

기본값 `OnDrawAdvanced` 그리기에 대 한 정규화 된 장치 컨텍스트를 준비 합니다. 그런 다음 컨트롤 클래스의 호출 `OnDraw` 메서드.

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>매개 변수

*di*<br/>
에 대 한 참조를 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) 그리기 측면을 컨트롤 범위 같은 그리기 정보가 포함 된 구조체 그리기 최적화 여부 및 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

정규화 하지 않고 컨테이너가 전달한 장치 컨텍스트를 허용 하려는 경우이 메서드를 재정의 합니다.

참조 [CComControlBase::OnDraw](#ondraw) 대 한 자세한 내용은 합니다.

##  <a name="onkillfocus"></a>  CComControlBase::OnKillFocus

컨트롤 내부 활성 상태입니다. 유효한 컨트롤 사이트가 다음 알립니다 컨테이너 컨트롤에서 포커스를 잃었을 있는지를 확인 합니다.

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
예약됨.

*wParam*<br/>
예약됨.

*lParam*<br/>
예약됨.

*bHandled*<br/>
창 메시지가 성공적으로 처리 되었는지 여부를 나타내는 플래그입니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>반환 값

항상 1을 반환합니다.

##  <a name="onmouseactivate"></a>  CComControlBase::OnMouseActivate

UI 사용자 모드에는 다음 컨트롤을 활성화를 확인 합니다.

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
예약됨.

*wParam*<br/>
예약됨.

*lParam*<br/>
예약됨.

*bHandled*<br/>
창 메시지가 성공적으로 처리 되었는지 여부를 나타내는 플래그입니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>반환 값

항상 1을 반환합니다.

##  <a name="onpaint"></a>  CComControlBase::OnPaint

그리기에 대 한 컨테이너를 준비, 컨트롤의 클라이언트 영역을 가져옵니다 다음 컨트롤 클래스의 호출 `OnDrawAdvanced` 메서드.

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
예약됨.

*wParam*<br/>
기존 HDC 합니다.

*lParam*<br/>
예약됨.

*lResult*<br/>
예약됨.

### <a name="return-value"></a>반환 값

항상 0을 반환 합니다.

### <a name="remarks"></a>설명

하는 경우 *wParam* NULL이 아니면 `OnPaint` 유효한 HDC를 포함 하며 대신를 사용 하 여 가정 [CComControlBase::m_hWndCD](#m_hwndcd)합니다.

##  <a name="onsetfocus"></a>  CComControlBase::OnSetFocus

컨트롤이 내부 활성 상태입니다. 유효한 컨트롤 사이트가 다음 컨테이너 컨트롤에 알립니다는 검사에 포커스가 있습니다.

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>매개 변수

*nMsg*<br/>
예약됨.

*wParam*<br/>
예약됨.

*lParam*<br/>
예약됨.

*bHandled*<br/>
창 메시지가 성공적으로 처리 되었는지 여부를 나타내는 플래그입니다. 기본값은 FALSE입니다.

### <a name="return-value"></a>반환 값

항상 1을 반환합니다.

### <a name="remarks"></a>설명

컨트롤에서 포커스를 받았습니다 컨테이너에 알림을 보냅니다.

##  <a name="pretranslateaccelerator"></a>  CComControlBase::PreTranslateAccelerator

사용자 고유의 키보드 액셀러레이터 키 처리기를 제공 하려면이 메서드를 재정의 합니다.

```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
예약됨.

*hRet*<br/>
예약됨.

### <a name="return-value"></a>반환 값

기본적으로 FALSE를 반환합니다.

##  <a name="sendonclose"></a>  CComControlBase::SendOnClose

컨트롤이 닫 혔 음 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크를에 알립니다.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

컨트롤에 해당 자문 싱크 닫히도록 알림을 보냅니다.

##  <a name="sendondatachange"></a>  CComControlBase::SendOnDataChange

컨트롤 데이터가 변경 되었음을 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크를에 알립니다.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>매개 변수

*advf*<br/>
플래그를 지정 하는 것이 좋습니다 하는 방법에 대 한 호출 [IAdviseSink::OnDataChange](/windows/desktop/api/objidl/nf-objidl-iadvisesink-ondatachange) 이루어집니다. 값은는 [ADVF](/windows/desktop/api/objidl/ne-objidl-tagadvf) 열거형입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="sendonrename"></a>  CComControlBase::SendOnRename

컨트롤에는 새 모니커 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크를에 알립니다.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>매개 변수

*pmk*<br/>
컨트롤의 새 모니커에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

컨트롤에 대 한 모니커 변경 된 알림을 보냅니다.

##  <a name="sendonsave"></a>  CComControlBase::SendOnSave

컨트롤에 저장 된 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크를에 알립니다.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

컨트롤이 해당 데이터를 저장만 알림을 보냅니다.

##  <a name="sendonviewchange"></a>  CComControlBase::SendOnViewChange

등록 된 모든 공지 싱크에 컨트롤의 뷰 변경 되었음을 알립니다.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>매개 변수

*dwAspect*<br/>
모양 또는 컨트롤의 뷰입니다.

*lindex*<br/>
변경 된 보기의 일부입니다. 1만 유효합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

`SendOnViewChange` 호출 [IAdviseSink::OnViewChange](/windows/desktop/api/objidl/nf-objidl-iadvisesink-onviewchange)합니다. 유일한 값 *색인입니다.* 관심 전체 보기를 나타내는-1은 현재 지원 합니다.

##  <a name="setcontrolfocus"></a>  CComControlBase::SetControlFocus

설정 하거나 또는 컨트롤에 키보드 포커스를 제거 합니다.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>매개 변수

*bGrab*<br/>
TRUE 이면 호출 컨트롤에 키보드 포커스를 설정 합니다. FALSE 인 경우는 포커스가 있는 경우 호출 컨트롤에서 키보드 포커스를 제거 합니다.

### <a name="return-value"></a>반환 값

컨트롤이 포커스를 성공적으로 받는 경우 TRUE를 반환합니다 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

Windows API 함수를 창 컨트롤용 [SetFocus](/windows/desktop/api/winuser/nf-winuser-setfocus) 라고 합니다. 창 없는 컨트롤에 대 한 [IOleInPlaceSiteWindowless::SetFocus](/windows/desktop/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) 라고 합니다. 이 호출을 통해 창 없는 컨트롤에서 키보드 포커스 및 창 메시지에 응답할 수 있습니다.

##  <a name="setdirty"></a>  CComControlBase::SetDirty

데이터 멤버를 설정 `m_bRequiresSave` 에 값 *bDirty*합니다.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>매개 변수

*bDirty*<br/>
데이터 멤버의 값 [CComControlBase::m_bRequiresSave](#m_brequiressave)합니다.

### <a name="remarks"></a>설명

`SetDirty(TRUE)` 컨트롤 변경 되었기 때문입니다 마지막으로 저장 된 플래그를 설정 하려면 호출 되어야 합니다. 변수의 `m_bRequiresSave` 사용 하 여 검색 [CComControlBase::GetDirty](#getdirty)합니다.

## <a name="see-also"></a>참고자료

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
