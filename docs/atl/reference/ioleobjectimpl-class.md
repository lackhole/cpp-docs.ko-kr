---
title: IOleObjectImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
ms.openlocfilehash: 5a815023d340839068873c32f1477d33053b13b4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775935"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl 클래스

이 클래스는 구현 `IUnknown` 및 컨테이너 컨트롤과 통신 하는 주 인터페이스입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IOleObjectImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IOleObjectImpl::Advise](#advise)|컨트롤을 사용 하 여 권장 된 연결을 설정합니다.|
|[IOleObjectImpl::Close](#close)|로드를 실행에서 컨트롤 상태를 변경 합니다.|
|[IOleObjectImpl::DoVerb](#doverb)|열거 작업 중 하나를 수행할 컨트롤에 알립니다.|
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|유지 관리 하는 모든 실행 취소 상태를 삭제 하려면 컨트롤에 알립니다.|
|[IOleObjectImpl::DoVerbHide](#doverbhide)|보기에서 해당 사용자 인터페이스를 제거 하려면 컨트롤에 알립니다.|
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|컨트롤을 실행 하 고 해당 창을 설치 되지만 컨트롤의 사용자 인터페이스를 설치 하지 않습니다.|
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|컨트롤이 별도 창에서 열고 편집할 수 있습니다.|
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|컨트롤을 두 번 클릭할 때 지정된 된 작업을 수행 합니다. 컨트롤의 컨트롤 전체를 활성화 하려면 일반적으로 작업을 정의 합니다.|
|[IOleObjectImpl::DoVerbShow](#doverbshow)|사용자에 게 새로 삽입된 된 컨트롤을 보여 줍니다.|
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|컨트롤 내부에서 활성화 하 고 메뉴 및 도구 모음 같은 컨트롤의 사용자 인터페이스를 보여 줍니다.|
|[IOleObjectImpl::EnumAdvise](#enumadvise)|컨트롤의 자문 연결을 열거합니다.|
|[IOleObjectImpl::EnumVerbs](#enumverbs)|컨트롤에 대 한 작업을 열거합니다.|
|[IOleObjectImpl::GetClientSite](#getclientsite)|컨트롤의 클라이언트 사이트를 검색합니다.|
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|클립보드에서 데이터를 검색합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleObjectImpl::GetExtent](#getextent)|컨트롤의 표시 영역 범위를 검색합니다.|
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|컨트롤의 상태를 검색합니다.|
|[IOleObjectImpl::GetMoniker](#getmoniker)|컨트롤의 모니커를 검색합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|컨트롤의 클래스 식별자를 검색합니다.|
|[IOleObjectImpl::GetUserType](#getusertype)|컨트롤의 사용자 형식 이름을 검색합니다.|
|[IOleObjectImpl::InitFromData](#initfromdata)|컨트롤에서 선택한 데이터를 초기화합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleObjectImpl::IsUpToDate](#isuptodate)|컨트롤 최신 상태 인지 확인 합니다. ATL 구현은 S_OK를 반환 합니다.|
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|호출한 [DoVerbDiscardUndo](#doverbdiscardundo) 실행 취소 상태는 삭제 후 합니다.|
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|호출한 [DoVerbHide](#doverbhide) 후 컨트롤을 숨깁니다.|
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|호출한 [DoVerbInPlaceActivate](#doverbinplaceactivate) 진행에서 컨트롤이 활성화 된 후입니다.|
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|호출한 [DoVerbOpen](#doverbopen) 컨트롤을 별도 창에서 편집을 위해 열린 후 합니다.|
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|호출한 [DoVerbShow](#doverbshow) 컨트롤 표시 생성 된 후입니다.|
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|호출한 [DoVerbUIActivate](#doverbuiactivate) 후 컨트롤의 사용자 인터페이스를 활성화 합니다.|
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|호출한 [DoVerbDiscardUndo](#doverbdiscardundo) 실행 취소 하기 전에 상태는 삭제 됩니다.|
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|호출한 [DoVerbHide](#doverbhide) 전에 컨트롤을 숨깁니다.|
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|호출한 [DoVerbInPlaceActivate](#doverbinplaceactivate) 컨트롤에서 현재 위치 활성화 되기 전에 합니다.|
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|호출한 [DoVerbOpen](#doverbopen) 전에 컨트롤을 별도 창에서 편집을 위해 열렸습니다.|
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|호출한 [DoVerbShow](#doverbshow) 표시 되기 전에 컨트롤에 되었습니다.|
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|호출한 [DoVerbUIActivate](#doverbuiactivate) 컨트롤의 사용자 인터페이스에 활성화 합니다.|
|[IOleObjectImpl::SetClientSite](#setclientsite)|컨테이너에 해당 클라이언트 사이트에 대 한 컨트롤에 알립니다.|
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|모든 경우에 컨트롤의 응용 프로그램에 색 구성표를 권장 합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleObjectImpl::SetExtent](#setextent)|컨트롤의 표시 영역 범위를 설정합니다.|
|[IOleObjectImpl::SetHostNames](#sethostnames)|컨트롤 컨테이너 응용 프로그램 및 컨테이너 문서의 이름을 알려 줍니다.|
|[IOleObjectImpl::SetMoniker](#setmoniker)|해당 모니커 이란 컨트롤에 알립니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleObjectImpl::Unadvise](#unadvise)|컨트롤을 사용 하 여 권장 된 연결을 삭제합니다.|
|[IOleObjectImpl::Update](#update)|컨트롤을 업데이트합니다. ATL 구현은 S_OK를 반환 합니다.|

## <a name="remarks"></a>설명

합니다 [IOleObject](/windows/desktop/api/oleidl/nn-oleidl-ioleobject) 인터페이스 컨테이너 컨트롤과 통신 하는 주 인터페이스입니다. 클래스 `IOleObjectImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IOleObject`

`IOleObjectImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="advise"></a>  IOleObjectImpl::Advise

컨트롤을 사용 하 여 권장 된 연결을 설정합니다.

```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```

### <a name="remarks"></a>설명

참조 [IOleObject::Advise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-advise) Windows SDK에에서 있습니다.

##  <a name="close"></a>  IOleObjectImpl::Close

로드를 실행에서 컨트롤 상태를 변경 합니다.

```
STDMETHOD(Close)(DWORD dwSaveOption);
```

### <a name="remarks"></a>설명

컨트롤을 비활성화 하 고 있는 경우 컨트롤 창을 제거 합니다. 클래스 데이터 멤버를 컨트롤 하는 경우 [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) 가 TRUE 고 *dwSaveOption* 매개 변수는 OLECLOSE_SAVEIFDIRTY 또는 OLECLOSE_PROMPTSAVE, 컨트롤 속성은 닫기 전에 저장 합니다.

컨트롤 클래스 데이터 멤버에 저장 된 포인터 [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) 하 고 [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) 출시 되 면 데이터 멤버 및 [CComControlBase:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), 및 [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) FALSE로 설정 됩니다.

참조 [IOleObject::Close](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-close) Windows SDK에에서 있습니다.

##  <a name="doverb"></a>  IOleObjectImpl::DoVerb

열거 작업 중 하나를 수행할 컨트롤에 알립니다.

```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```

### <a name="remarks"></a>설명

값에 따라 `iVerb`, ATL 중 `DoVerb` 도우미 함수는 다음과 같이 호출 됩니다.

|*iVerb* Value|DoVerb 도우미 함수 호출|
|-------------------|-----------------------------------|
|OLEIVERB_DISCARDUNDOSTATE|[DoVerbDiscardUndo](#doverbdiscardundo)|
|OLEIVERB_HIDE|[DoVerbHide](#doverbhide)|
|OLEIVERB_INPLACEACTIVATE|[DoVerbInPlaceActivate](#doverbinplaceactivate)|
|OLEIVERB_OPEN|[DoVerbOpen](#doverbopen)|
|OLEIVERB_PRIMARY|[DoVerbPrimary](#doverbprimary)|
|OLEIVERB_PROPERTIES|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|
|OLEIVERB_SHOW|[DoVerbShow](#doverbshow)|
|OLEIVERB_UIACTIVATE|[DoVerbUIActivate](#doverbuiactivate)|

참조 [IOleObject::DoVerb](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb) Windows SDK에에서 있습니다.

##  <a name="doverbdiscardundo"></a>  IOleObjectImpl::DoVerbDiscardUndo

유지 관리 하는 모든 실행 취소 상태를 삭제 하려면 컨트롤에 알립니다.

```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
[in] 사각형 컨테이너에 대 한 포인터를 그릴 제어를 하려고 합니다.

*hwndParent*<br/>
[in] 컨트롤이 포함 된 창 핸들입니다.

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="doverbhide"></a>  IOleObjectImpl::DoVerbHide

비활성화 및 컨트롤의 사용자 인터페이스를 제거 하 고 컨트롤을 숨깁니다.

```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
[in] 사각형 컨테이너에 대 한 포인터를 그릴 제어를 하려고 합니다.

*hwndParent*<br/>
[in] 컨트롤이 포함 된 창 핸들입니다. ATL 구현에서 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="doverbinplaceactivate"></a>  IOleObjectImpl::DoVerbInPlaceActivate

컨트롤을 실행 하 고 해당 창을 설치 되지만 컨트롤의 사용자 인터페이스를 설치 하지 않습니다.

```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
[in] 사각형 컨테이너에 대 한 포인터를 그릴 제어를 하려고 합니다.

*hwndParent*<br/>
[in] 컨트롤이 포함 된 창 핸들입니다. ATL 구현에서 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

호출 하 여 제어를에서 활성화 [CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate)합니다. 하지 않는 한 컨트롤 클래스의 데이터 멤버 `m_bWindowOnly` 가 TRUE 인 `DoVerbInPlaceActivate` 창 없는 컨트롤로 컨트롤을 활성화 하려면 먼저 시도 (컨테이너를 지원 하는 경우에 사용 가능 [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless)). 함수 확장된 기능을 사용 하 여 컨트롤을 활성화 하려고 시도 실패 하는 경우 (컨테이너를 지원 하는 경우에 사용 가능 [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex)). 함수 확장 기능이 없는 컨트롤을 활성화 하려고 시도 실패 하는 경우 (컨테이너를 지원 하는 경우에 사용 가능 [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite)). 정품 인증에 성공 하면 함수에 알립니다. 컨테이너 컨트롤을 활성화 합니다.

##  <a name="doverbopen"></a>  IOleObjectImpl::DoVerbOpen

컨트롤이 별도 창에서 열고 편집할 수 있습니다.

```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
[in] 사각형 컨테이너에 대 한 포인터를 그릴 제어를 하려고 합니다.

*hwndParent*<br/>
[in] 컨트롤이 포함 된 창 핸들입니다.

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

##  <a name="doverbprimary"></a>  IOleObjectImpl::DoVerbPrimary

컨트롤을 두 번 클릭할 때 수행할 동작을 정의 합니다.

```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
[in] 사각형 컨테이너에 대 한 포인터를 그릴 제어를 하려고 합니다.

*hwndParent*<br/>
[in] 컨트롤이 포함 된 창 핸들입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

기본적으로 속성 페이지를 표시 하도록 설정 합니다. 이 두 번 클릭;에서 다른 동작을 호출 하려면 컨트롤 클래스에서 재정의할 수 있습니다. 예를 들어 비디오를 재생 하거나 내부 활성화를 이동 합니다.

##  <a name="doverbshow"></a>  IOleObjectImpl::DoVerbShow

컨트롤이 표시 되도록 컨테이너에 지시 합니다.

```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
[in] 사각형 컨테이너에 대 한 포인터를 그릴 제어를 하려고 합니다.

*hwndParent*<br/>
[in] 컨트롤이 포함 된 창 핸들입니다. ATL 구현에서 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="doverbuiactivate"></a>  IOleObjectImpl::DoVerbUIActivate

컨트롤의 사용자 인터페이스를 활성화 하 고 합성 메뉴에서 메뉴 대체 되는 컨테이너에에 알립니다.

```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```

### <a name="parameters"></a>매개 변수

*prcPosRec*<br/>
[in] 사각형 컨테이너에 대 한 포인터를 그릴 제어를 하려고 합니다.

*hwndParent*<br/>
[in] 컨트롤이 포함 된 창 핸들입니다. ATL 구현에서 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

##  <a name="enumadvise"></a>  IOleObjectImpl::EnumAdvise

이 컨트롤에 대 한 자문 등록 된 연결의 열거형을 제공합니다.

```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```

### <a name="remarks"></a>설명

참조 [IOleObject::EnumAdvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumadvise) Windows SDK에에서 있습니다.

##  <a name="enumverbs"></a>  IOleObjectImpl::EnumVerbs

호출 하 여이 컨트롤에 대 한 등록된 작업 (동사)의 열거형을 제공 `OleRegEnumVerbs`합니다.

```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```

### <a name="remarks"></a>설명

프로젝트의.rgs 파일에 동사를 추가할 수 있습니다. 예를 들어 CIRCCTL를 참조 하세요. RG에는 [CIRC](../../overview/visual-cpp-samples.md) 샘플입니다.

참조 [ioleobject:: Enumverbs](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumverbs) Windows SDK에에서 있습니다.

##  <a name="getclientsite"></a>  IOleObjectImpl::GetClientSite

컨트롤 클래스 데이터 멤버의 포인터를 놓습니다 [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) 로 *ppClientSite* 포인터의 참조 횟수를 증가 시킵니다.

```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```

### <a name="remarks"></a>설명

참조 [IOleObject::GetClientSite](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getclientsite) Windows SDK에에서 있습니다.

##  <a name="getclipboarddata"></a>  IOleObjectImpl::GetClipboardData

클립보드에서 데이터를 검색합니다.

```
STDMETHOD(GetClipboardData)(
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IOleObject::GetClipboardData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getclipboarddata) Windows SDK에에서 있습니다.

##  <a name="getextent"></a>  IOleObjectImpl::GetExtent

실행 중인 컨트롤의 디스플레이 크기를 HIMETRIC 단위 (단위당 0.01mm))를 검색합니다.

```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>설명

크기 컨트롤 클래스 데이터 멤버에 저장 됩니다 [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)합니다.

참조 [IOleObject::GetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getextent) Windows SDK에에서 있습니다.

##  <a name="getmiscstatus"></a>  IOleObjectImpl::GetMiscStatus

포인터를 호출 하 여 컨트롤에 대 한 등록된 상태 정보를 반환 `OleRegGetMiscStatus`합니다.

```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```

### <a name="remarks"></a>설명

상태 정보를 제어 및 프레젠테이션 데이터가 지 원하는 동작을 포함 합니다. 프로젝트의.rgs 파일에 상태 정보를 추가할 수 있습니다.

참조 [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) Windows SDK에에서 있습니다.

##  <a name="getmoniker"></a>  IOleObjectImpl::GetMoniker

컨트롤의 모니커를 검색합니다.

```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IOleObject::GetMoniker](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmoniker) Windows SDK에에서 있습니다.

##  <a name="getuserclassid"></a>  IOleObjectImpl::GetUserClassID

컨트롤의 클래스 식별자를 반환합니다.

```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```

### <a name="remarks"></a>설명

참조 [IOleObject::GetUserClassID](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getuserclassid) Windows SDK에에서 있습니다.

##  <a name="getusertype"></a>  IOleObjectImpl::GetUserType

호출 하 여 컨트롤의 사용자 형식 이름을 반환 `OleRegGetUserType`합니다.

```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```

### <a name="remarks"></a>설명

사용자 형식 이름의 메뉴 및 대화 상자와 같은 사용자 인터페이스 요소에 표시 하기 위해 사용 됩니다. 프로젝트의.rgs 파일에 사용자 형식 이름을 변경할 수 있습니다.

참조 [IOleObject::GetUserType](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getusertype) Windows SDK에에서 있습니다.

##  <a name="initfromdata"></a>  IOleObjectImpl::InitFromData

컨트롤에서 선택한 데이터를 초기화합니다.

```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IOleObject::InitFromData](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-initfromdata) Windows SDK에에서 있습니다.

##  <a name="isuptodate"></a>  IOleObjectImpl::IsUpToDate

컨트롤 최신 상태 인지 확인 합니다.

```
STDMETHOD(IsUpToDate)(void);
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

참조 [IOleObject::IsUpToDate](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-isuptodate) Windows SDK에에서 있습니다.

##  <a name="onpostverbdiscardundo"></a>  IOleObjectImpl::OnPostVerbDiscardUndo

호출한 [DoVerbDiscardUndo](#doverbdiscardundo) 실행 취소 상태는 삭제 후 합니다.

```
HRESULT OnPostVerbDiscardUndo();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

실행 취소 상태는 삭제 후에 실행 하려는 코드를 사용 하 여이 메서드를 재정의 합니다.

##  <a name="onpostverbhide"></a>  IOleObjectImpl::OnPostVerbHide

호출한 [DoVerbHide](#doverbhide) 후 컨트롤을 숨깁니다.

```
HRESULT OnPostVerbHide();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤을 숨긴 후에 실행 하려는 코드를 사용 하 여이 메서드를 재정의 합니다.

##  <a name="onpostverbinplaceactivate"></a>  IOleObjectImpl::OnPostVerbInPlaceActivate

호출한 [DoVerbInPlaceActivate](#doverbinplaceactivate) 진행에서 컨트롤이 활성화 된 후입니다.

```
HRESULT OnPostVerbInPlaceActivate();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤이 현재 위치에서 활성화 된 후에 실행 하려는 코드를 사용 하 여이 메서드를 재정의 합니다.

##  <a name="onpostverbopen"></a>  IOleObjectImpl::OnPostVerbOpen

호출한 [DoVerbOpen](#doverbopen) 컨트롤을 별도 창에서 편집을 위해 열린 후 합니다.

```
HRESULT OnPostVerbOpen();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤을 별도 창에서 편집을 위해 열린 후 실행할 코드를 사용 하 여이 메서드를 재정의 합니다.

##  <a name="onpostverbshow"></a>  IOleObjectImpl::OnPostVerbShow

호출한 [DoVerbShow](#doverbshow) 컨트롤 표시 생성 된 후입니다.

```
HRESULT OnPostVerbShow();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤 표시 생성 된 후 실행 하는 것이 원하는 코드를 사용 하 여이 메서드를 재정의 합니다.

##  <a name="onpostverbuiactivate"></a>  IOleObjectImpl::OnPostVerbUIActivate

호출한 [DoVerbUIActivate](#doverbuiactivate) 후 컨트롤의 사용자 인터페이스를 활성화 합니다.

```
HRESULT OnPostVerbUIActivate();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤의 사용자 인터페이스에 활성화 된 후 실행할 코드를 사용 하 여이 메서드를 재정의 합니다.

##  <a name="onpreverbdiscardundo"></a>  IOleObjectImpl::OnPreVerbDiscardUndo

호출한 [DoVerbDiscardUndo](#doverbdiscardundo) 실행 취소 하기 전에 상태는 삭제 됩니다.

```
HRESULT OnPreVerbDiscardUndo();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

실행 취소 상태를 삭제 하기을 방지 하려면 오류 HRESULT를 반환 하려면이 메서드를 재정의 합니다.

##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide

호출한 [DoVerbHide](#doverbhide) 전에 컨트롤을 숨깁니다.

```
HRESULT OnPreVerbHide();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤에서 숨겨진를 방지 하려면 오류 HRESULT를 반환 하려면이 메서드를 재정의 합니다.

##  <a name="onpreverbinplaceactivate"></a>  IOleObjectImpl::OnPreVerbInPlaceActivate

호출한 [DoVerbInPlaceActivate](#doverbinplaceactivate) 컨트롤에서 현재 위치 활성화 되기 전에 합니다.

```
HRESULT OnPreVerbInPlaceActivate();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤 내부에서 활성화 되 고을 방지 하려면 오류 HRESULT를 반환 하려면이 메서드를 재정의 합니다.

##  <a name="onpreverbopen"></a>  IOleObjectImpl::OnPreVerbOpen

호출한 [DoVerbOpen](#doverbopen) 전에 컨트롤을 별도 창에서 편집을 위해 열렸습니다.

```
HRESULT OnPreVerbOpen();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤을 별도 창에서 편집에 대 한 열을 방지 하려면 오류 HRESULT를 반환 하려면이 메서드를 재정의 합니다.

##  <a name="onpreverbshow"></a>  IOleObjectImpl::OnPreVerbShow

호출한 [DoVerbShow](#doverbshow) 표시 되기 전에 컨트롤에 되었습니다.

```
HRESULT OnPreVerbShow();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤에서 표시 되지 않으려면 오류 HRESULT를 반환 하려면이 메서드를 재정의 합니다.

##  <a name="onpreverbuiactivate"></a>  IOleObjectImpl::OnPreVerbUIActivate

호출한 [DoVerbUIActivate](#doverbuiactivate) 컨트롤의 사용자 인터페이스에 활성화 합니다.

```
HRESULT OnPreVerbUIActivate();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

컨트롤의 사용자 인터페이스를 활성화할를 방지 하려면 오류 HRESULT를 반환 하려면이 메서드를 재정의 합니다.

##  <a name="setclientsite"></a>  IOleObjectImpl::SetClientSite

컨테이너에 해당 클라이언트 사이트에 대 한 컨트롤에 알립니다.

```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```

### <a name="remarks"></a>설명

메서드는 S_OK를 반환합니다.

참조 [IOleObject::SetClientSite](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setclientsite) Windows SDK에에서 있습니다.

##  <a name="setcolorscheme"></a>  IOleObjectImpl::SetColorScheme

모든 경우에 컨트롤의 응용 프로그램에 색 구성표를 권장 합니다.

```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IOleObject::SetColorScheme](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setcolorscheme) Windows SDK에에서 있습니다.

##  <a name="setextent"></a>  IOleObjectImpl::SetExtent

컨트롤의 표시 영역 범위를 설정합니다.

```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```

### <a name="remarks"></a>설명

이 고, 그렇지 `SetExtent` 가리키는 값을 저장 `psizel` 컨트롤 클래스 데이터 멤버에서 [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)합니다. 이 값은 HIMETRIC 단위 (단위당 0.01mm))입니다.

클래스 데이터 멤버를 컨트롤 하는 경우 [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) 가 TRUE 인 `SetExtent` 가리키는 값 저장 `psizel` 컨트롤 클래스 데이터 멤버의 [CComControlBase::m_sizeNatural ](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).

클래스 데이터 멤버를 컨트롤 하는 경우 [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) 가 TRUE 인 `SetExtent` 호출 `SendOnDataChange` 고 `SendOnViewChange` 컨트롤 크기가 advise 소유자를 사용 하 여 등록 된 모든 공지 싱크에 알리기 위해 변경 합니다.

참조 [IOleObject::SetExtent](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setextent) Windows SDK에에서 있습니다.

##  <a name="sethostnames"></a>  IOleObjectImpl::SetHostNames

컨트롤 컨테이너 응용 프로그램 및 컨테이너 문서의 이름을 알려 줍니다.

```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

참조 [IOleObject::SetHostNames](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-sethostnames) Windows SDK에에서 있습니다.

##  <a name="setmoniker"></a>  IOleObjectImpl::SetMoniker

해당 모니커 이란 컨트롤에 알립니다.

```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IOleObject::SetMoniker](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-setmoniker) Windows SDK에에서 있습니다.

##  <a name="unadvise"></a>  IOleObjectImpl::Unadvise

컨트롤 클래스의 저장 된 자문 연결 삭제 `m_spOleAdviseHolder` 데이터 멤버입니다.

```
STDMETHOD(Unadvise)(DWORD dwConnection);
```

### <a name="remarks"></a>설명

참조 [IOleObject::Unadvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-unadvise) Windows SDK에에서 있습니다.

##  <a name="update"></a>  IOleObjectImpl::Update

컨트롤을 업데이트합니다.

```
STDMETHOD(Update)(void);
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

참조 [IOleObject::Update](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-update) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX 컨트롤 인터페이스](/windows/desktop/com/activex-controls-interfaces)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
