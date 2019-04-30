---
title: IOleInPlaceObjectWindowlessImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
ms.openlocfilehash: df14c22f5cf4828b51bf03f6d0f0c4c20cf5a009
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197866"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl 클래스

이 클래스는 구현 `IUnknown` 창 없는 컨트롤 창 메시지를 수신 하 고 끌어서 놓기 작업에 참여할 수 있도록 하는 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IOleInPlaceObjectWindowlessImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|상황에 맞는 도움말을 사용 하도록 설정 합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|제공 된 `IDropTarget` 있는 끌어서 놓기를 지 원하는 전체 활성, 창 없는 개체에 대 한 인터페이스입니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|창 핸들을 가져옵니다.|
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|활성 전체 컨트롤을 비활성화합니다.|
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|내부 활성화 된 창 없는 컨트롤 컨테이너에서 메시지를 디스패치합니다.|
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|이전에 비활성화 된 컨트롤을 다시 활성화합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|전체 컨트롤의 부분을 표시할지 나타냅니다.|
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|비활성화 하 고 내부 활성화를 지 원하는 사용자 인터페이스를 제거 합니다.|

## <a name="remarks"></a>설명

합니다 [위해서는](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceobject) 인터페이스 재 활성화를 관리 하 고 전체 비활성화 컨트롤과 컨트롤의 크기를 표시할지 결정 합니다. 합니다 [IOleInPlaceObjectWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless) 인터페이스에서 창 없는 컨트롤 창 메시지를 수신 하 고 끌어서 놓기 작업에 참여할 수 있습니다. 클래스 `IOleInPlaceObjectWindowlessImpl` 의 기본 구현을 제공 `IOleInPlaceObject` 하 고 `IOleInPlaceObjectWindowless` 구현 하 고 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="contextsensitivehelp"></a>  IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp

E_NOTIMPL 반환.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>설명

참조 [IOleWindow::ContextSensitiveHelp](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) Windows SDK에에서 있습니다.

##  <a name="getdroptarget"></a>  IOleInPlaceObjectWindowlessImpl::GetDropTarget

E_NOTIMPL 반환.

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>설명

참조 [IOleInPlaceObjectWindowless::GetDropTarget](/windows/desktop/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) Windows SDK에에서 있습니다.

##  <a name="getwindow"></a>  IOleInPlaceObjectWindowlessImpl::GetWindow

컨테이너는 컨트롤의 창 핸들을 가져오려면이 함수를 호출 합니다.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>설명

일부 컨테이너는 현재 기간 이동 하는 경우에, 창 없는 된 컨트롤을 사용 하 여 작동 하지 않습니다. ATL의 구현 하는 경우 컨트롤 클래스의 데이터 멤버 `m_bWasOnceWindowless` 가 TRUE 인 함수 E_FAIL을 반환 합니다. 그렇지 않고 *phwnd* NULL이 아니면 `GetWindow` 설정 \* *phwnd* control 클래스의 데이터 멤버에 `m_hWnd` S_OK를 반환 합니다.

참조 [IOleWindow::GetWindow](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-getwindow) Windows SDK에에서 있습니다.

##  <a name="inplacedeactivate"></a>  IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate

전체 활성 컨트롤을 비활성화 하려면 컨테이너에 의해 호출 됩니다.

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>설명

이 메서드는 컨트롤의 상태에 따라 전체 또는 부분 비활성화를 수행합니다. 필요한 경우 컨트롤의 사용자 인터페이스가 비활성화 되 고 컨트롤의 창이 있는 경우 소멸 됩니다. 컨테이너는 컨트롤을 더 이상 활성 상태가 진행에서 하는 알림이 전송 됩니다. `IOleInPlaceUIWindow` 컨테이너 메뉴 협상 공간 테두리를 사용 하는 인터페이스 해제 됩니다.

참조 [IOleInPlaceObject::InPlaceDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) Windows SDK에에서 있습니다.

##  <a name="onwindowmessage"></a>  IOleInPlaceObjectWindowlessImpl::OnWindowMessage

내부 활성화 된 창 없는 컨트롤에는 컨테이너에서 메시지를 디스패치합니다.

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>설명

참조 [IOleInPlaceObjectWindowless::OnWindowMessage](/windows/desktop/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) Windows SDK에에서 있습니다.

##  <a name="reactivateandundo"></a>  IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo

E_NOTIMPL 반환.

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>설명

참조 [IOleInPlaceObject::ReactivateAndUndo](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) Windows SDK에에서 있습니다.

##  <a name="setobjectrects"></a>  IOleInPlaceObjectWindowlessImpl::SetObjectRects

컨트롤의 크기 및/또는 위치 변경 되었음을 알리기 위해 컨테이너에 의해 호출 됩니다.

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>설명

컨트롤의 업데이트 `m_rcPos` 데이터 멤버 및 제어를 표시 합니다. 클립 영역을 교차 하는 컨트롤의 부분만 표시 됩니다. 컨트롤의 표시 된 이전에 잘립니다 하지만 클리핑을 제거 된 경우이 함수에 컨트롤의 전체 뷰를 다시 그리도록 호출할 수 있습니다.

참조 [IOleInPlaceObject::SetObjectRects](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) Windows SDK에에서 있습니다.

##  <a name="uideactivate"></a>  IOleInPlaceObjectWindowlessImpl::UIDeactivate

비활성화 하 고 내부 활성화를 지 원하는 컨트롤의 사용자 인터페이스를 제거 합니다.

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>설명

컨트롤 클래스의 데이터 멤버를 설정 `m_bUIActive` FALSE로 합니다. 이 함수의 ATL 구현에서는 항상 S_OK를 반환합니다.

참조 [IOleInPlaceObject::UIDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
