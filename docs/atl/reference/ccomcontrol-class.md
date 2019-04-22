---
title: CComControl 클래스
ms.date: 11/04/2016
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
ms.openlocfilehash: ffbec7c1a83c0dd829878f4c73340528d32fb852
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58771554"
---
# <a name="ccomcontrol-class"></a>CComControl 클래스

이 클래스를 만들고 ATL 컨트롤을 관리 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컨트롤을 구현 하는 클래스입니다.

*WinBase*<br/>
기간 이동 함수를 구현 하는 기본 클래스입니다. 기본값으로 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComControl::CComControl](#ccomcontrol)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComControl::ControlQueryInterface](#controlqueryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComControl::CreateControlWindow](#createcontrolwindow)|컨트롤의 창을 만듭니다.|
|[CComControl::FireOnChanged](#fireonchanged)|컨테이너의 싱크를 컨트롤 속성이 변경 되었음을 알립니다.|
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|컨트롤 속성 변경 방법은 진행 방법 개체는 싱크는 요청 및 컨테이너의 싱크를에 알립니다.|
|[CComControl::MessageBox](#messagebox)|만들기, 표시 및 메시지 상자를 작동 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

`CComControl` 유용한 컨트롤 도우미 함수 및 ATL 컨트롤에 대 한 필수 데이터 멤버의 집합이 있습니다. 표준 컨트롤 또는 ATL 컨트롤 마법사를 사용 하 여 DHTML 컨트롤을 만들 때 마법사는 자동으로에서 파생 `CComControl`합니다. `CComControl` 해당 메서드 중 대부분은 파생 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)합니다.

컨트롤을 만드는 방법에 대 한 자세한 내용은 참조는 [ATL 자습서](../../atl/active-template-library-atl-tutorial.md)합니다. ATL 프로젝트 마법사에 대 한 자세한 내용은 문서 참조 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.

데모를 보려면 `CComControl` 메서드 및 데이터 멤버를 참조 합니다 [CIRC](../../overview/visual-cpp-samples.md) 샘플입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="ccomcontrol"></a>  CComControl::CComControl

생성자입니다.

```
CComControl();
```

### <a name="remarks"></a>설명

호출 된 [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) 생성자에 전달 합니다 `m_hWnd` 데이터 멤버를 통해 상속 [CWindowImpl](../../atl/reference/cwindowimpl-class.md).

##  <a name="controlqueryinterface"></a>  CComControl::ControlQueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 요청 된 인터페이스의 GUID입니다.

*ppv*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *iid*, 또는 인터페이스를 찾을 수 없으면 NULL입니다.

### <a name="remarks"></a>설명

COM 맵 테이블의 인터페이스만 처리 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

##  <a name="createcontrolwindow"></a>  CComControl::CreateControlWindow

기본적으로 호출 하 여 컨트롤에 대 한 창을 만듭니다 `CWindowImpl::Create`합니다.

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>매개 변수

*hWndParent*<br/>
[in] 부모 또는 소유자 창에 대 한 핸들입니다. 유효한 창 핸들을 제공 해야 합니다. 컨트롤 창은 부모 창의 영역으로 제한 됩니다.

*rcPos*<br/>
[in] 초기 크기 및 만들려는 창의 위치입니다.

### <a name="remarks"></a>설명

이 메서드를 재정의 하 여 작업을 수행 하려는 경우 아닌 단일 창을 만들고, 예를 들어 두 개의 창을 만들려면 중 하나는 도구 모음이 됩니다 컨트롤에 대 한 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

##  <a name="fireonchanged"></a>  CComControl::FireOnChanged

컨테이너의 싱크를 컨트롤 속성이 변경 되었음을 알립니다.

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>매개 변수

*dispID*<br/>
[in] 변경 된 속성의 식별자입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

컨트롤 클래스에서 파생 되는 경우 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink),이 메서드를 호출 [CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) 연결 된 모든 알림 `IPropertyNotifySink` 하는 인터페이스 지정된 된 컨트롤 속성이 변경 되었습니다. 컨트롤 클래스에서 파생 되지 않은 경우 `IPropertyNotifySink`,이 메서드는 S_OK를 반환 합니다.

이 메서드는 안전 컨트롤 연결점을 지원 하지 않습니다 하는 경우에 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

##  <a name="fireonrequestedit"></a>  CComControl::FireOnRequestEdit

컨트롤 속성 변경 방법은 진행 방법 개체는 싱크는 요청 및 컨테이너의 싱크를에 알립니다.

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>매개 변수

*dispID*<br/>
[in] 변경할 속성의 식별자입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

컨트롤 클래스에서 파생 되는 경우 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink),이 메서드를 호출 [CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit) 연결 된 모든 알림 `IPropertyNotifySink` 하는 인터페이스를 지정 된 컨트롤 속성 변경 되려고 합니다. 컨트롤 클래스에서 파생 되지 않은 경우 `IPropertyNotifySink`,이 메서드는 S_OK를 반환 합니다.

이 메서드는 안전 컨트롤 연결점을 지원 하지 않습니다 하는 경우에 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

##  <a name="messagebox"></a>  CComControl::MessageBox

만들기, 표시 및 메시지 상자를 작동 하려면이 메서드를 호출 합니다.

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
메시지 상자에 표시할 텍스트입니다.

*lpszCaption*<br/>
대화 상자 제목입니다. 경우 NULL (기본값), "Error"는 제목입니다.

*nType*<br/>
내용 및 대화 상자의 동작을 지정합니다. 참조 된 [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) 목록 사용할 수 있는 다양 한 메시지 상자는 Windows SDK 설명서의 항목입니다. 기본 제공 단순 **확인** 단추입니다.

### <a name="return-value"></a>반환 값

아래에 나열 된 메뉴 항목 값 중 하나를 지정 하는 정수 값 반환 [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) Windows SDK 설명서의 합니다.

### <a name="remarks"></a>설명

`MessageBox` 사용자에 게 오류 또는 경고 메시지를 표시 하는 쉬운 방법을 개발 중에 유용 합니다.

## <a name="see-also"></a>참고자료

[CWindowImpl 클래스](../../atl/reference/cwindowimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComControlBase 클래스](../../atl/reference/ccomcontrolbase-class.md)<br/>
[CComCompositeControl 클래스](../../atl/reference/ccomcompositecontrol-class.md)
