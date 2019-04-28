---
title: CComCompositeControl 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
ms.openlocfilehash: f1a9a2d0628b3683f047ce9858d809040438db03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260242"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl 클래스

이 클래스는 복합 컨트롤을 구현 하는 데 필요한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T>
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)처럼 다른 인터페이스 에서도 잘 복합 컨트롤에 대 한 지원 하려고 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|생성자입니다.|
|[CComCompositeControl::~CComCompositeControl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|Advise 하거나 unadvise 복합 컨트롤에 의해 호스팅되는 모든 컨트롤에이 메서드를 호출 합니다.|
|[CComCompositeControl::CalcExtent](#calcextent)|복합 컨트롤을 호스트 하는 데 사용 하는 대화 상자 리소스의 HIMETRIC 단위에서 크기를 계산 하려면이 메서드를 호출 합니다.|
|[CComCompositeControl::Create](#create)|이 메서드는 복합 컨트롤에 대 한 컨트롤 창을 만들 수 있습니다.|
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|컨트롤 창을 만들 바꾼 모든 호스트 된 컨트롤에이 메서드를 호출 합니다.|
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|컨테이너의 배경색을 사용 하 여 복합 컨트롤의 배경색을 설정 하려면이 메서드를 호출 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|배경 브러시입니다.|
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|현재 포커스가 있는 창 핸들입니다.|

## <a name="remarks"></a>설명

클래스에서 파생 된 클래스 `CComCompositeControl` ActiveX 복합 컨트롤의 기능을 상속 합니다. ActiveX 컨트롤에서 파생 된 `CComCompositeControl` 표준 대화 상자를 통해 호스팅됩니다. 이러한 종류의 컨트롤을 다른 컨트롤 (네이티브 Windows 컨트롤 및 ActiveX 컨트롤)를 호스트할 수 있기 때문에 복합 컨트롤 이라고 합니다.

`CComCompositeControl` 자식 클래스에 열거형된 데이터 멤버를 검색 하 여 복합 컨트롤을 만드는 데 사용할 대화 상자 리소스를 식별 합니다. IDD이 자식 클래스의 멤버는 컨트롤의 창으로 사용 될 대화 상자 리소스의 리소스 ID로 설정 됩니다. 다음은 클래스에서 파생 된 데이터 멤버의 예로 `CComCompositeControl` 컨트롤의 창에 사용 되는 대화 상자 리소스를 식별 하려면 포함 되어야 합니다.

[!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]

> [!NOTE]
>  창 없는 컨트롤을 포함할 수는 있지만 복합 컨트롤은 항상 창 있는 컨트롤입니다.

구현 된 컨트롤을 `CComCompositeControl`-파생된 클래스에 기본 동작을 기본 제공 탭 합니다. 포커스를 받으면 컨트롤을 포함 하는 응용 프로그램에서 탭 되 여, 연속 해 서 TAB 키를 누르면 하면 포커스를 순환 하도록 모든 복합 컨트롤의 포함 된 컨트롤을 복합 컨트롤에서의 다음 항목에는 컨테이너의 탭 순서입니다. 대화 상자 리소스에 의해 결정 됩니다 하 고 순서를 결정 하는 호스트 된 컨트롤의 탭 순서는 탭에서 발생 합니다.

> [!NOTE]
>  액셀러레이터 키가 제대로 작동 되려면를 `CComCompositeControl`에 컨트롤을 만들 때 액셀러레이터 키 테이블을 로드, 다시 액셀러레이터 키의 수와 핸들을 전달 하는 데 필요한 것 [IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo), 및 마지막으로 컨트롤에서 해제 될 때 테이블을 삭제 합니다.

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

[CComControl](../../atl/reference/ccomcontrol-class.md)

`CComCompositeControl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="advisesinkmap"></a>  CComCompositeControl::AdviseSinkMap

Advise 하거나 unadvise 복합 컨트롤에 의해 호스팅되는 모든 컨트롤에이 메서드를 호출 합니다.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>매개 변수

*bAdvise*<br/>
True 이면 모든 컨트롤은 알림을 받을 수 있습니다. 그렇지 않으면 false입니다.

### <a name="return-value"></a>반환 값

|||
|-|-|
|S_OK  |모든 컨트롤에서 이벤트 싱크 맵 또는 연결 된 해당 이벤트 소스에서 성공적으로 해제 합니다.|
|E_FAIL  |모든 이벤트 싱크 맵과 연결 되거나 해당 이벤트 소스에서 성공적으로 연결이 끊긴 수를 제어 합니다.|
|E_POINTER  |이 오류는 일반적으로 컨트롤의 이벤트 싱크 맵 항목을 사용 하 여 문제나에 사용 되는 템플릿 인수를 사용 하 여 문제가 나타냅니다는 `IDispEventImpl` 또는 `IDispEventSimpleImpl` 기본 클래스입니다.|
|CONNECT_E_ADVISELIMIT  |연결 지점에 이미 연결 한계에 도달 했습니다 및 더 이상 받아들일 수 없습니다.|
|CONNECT_E_CANNOTCONNECT  |싱크는 연결점이 필요한 인터페이스를 지원 하지 않습니다.|
|CONNECT_E_NOCONNECTION  |쿠키 값에 올바른 연결을 나타내지 않습니다. 이 오류는 일반적으로 컨트롤의 이벤트 싱크 맵 항목을 사용 하 여 문제나에 사용 되는 템플릿 인수를 사용 하 여 문제가 나타냅니다는 `IDispEventImpl` 또는 `IDispEventSimpleImpl` 기본 클래스입니다.|

### <a name="remarks"></a>설명

이 메서드의 기본 구현을 싱크 맵과 이벤트 항목을 통해 검색합니다. 그런 다음 제안 하거나 unadvises 이벤트 싱크 맵 싱크 항목에 설명 된 COM 개체에 연결 지점. 이 멤버 메서드는 또한 파생된 클래스의 인스턴스 하나에서 상속 되는 사실에 따라 `IDispEventImpl` unadvised 또는 권장 되는 싱크 맵에서 모든 컨트롤에 대 한 합니다.

##  <a name="calcextent"></a>  CComCompositeControl::CalcExtent

복합 컨트롤을 호스트 하는 데 사용 하는 대화 상자 리소스의 HIMETRIC 단위에서 크기를 계산 하려면이 메서드를 호출 합니다.

```
BOOL CalcExtent(SIZE& size);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
에 대 한 참조를 `SIZE` 구조를이 방법으로 채울 수 있습니다.

### <a name="return-value"></a>반환 값

컨트롤을 대화 상자에서 호스팅되는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

크기에 반환 되는 *크기* 매개 변수입니다.

##  <a name="create"></a>  CComCompositeControl::Create

이 메서드는 복합 컨트롤에 대 한 컨트롤 창을 만들 수 있습니다.

```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWndParent*<br/>
컨트롤의 부모 창 핸들입니다.

*rcPos*<br/>
예약됨.

*dwInitParam*<br/>
컨트롤을 만드는 동안 컨트롤에 전달할 데이터입니다. 데이터를 전달 *dwInitParam* LPARAM 매개 변수로 표시 됩니다는 [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) 메시지를 생성 하는 경우 복합 컨트롤에 전송 됩니다.

### <a name="return-value"></a>반환 값

새로 만든된 복합 컨트롤 대화 상자에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 일반적으로 컨트롤의 내부 활성화 동안 호출 됩니다.

##  <a name="ccomcompositecontrol"></a>  CComCompositeControl::CComCompositeControl

생성자입니다.

```
CComCompositeControl();
```

### <a name="remarks"></a>설명

초기화 된 [CComCompositeControl::m_hbrBackground](#m_hbrbackground) 및 [CComCompositeControl::m_hWndFocus](#m_hwndfocus) NULL로 데이터 멤버입니다.

##  <a name="dtor"></a>  CComCompositeControl::~CComCompositeControl

소멸자입니다.

```
~CComCompositeControl();
```

### <a name="remarks"></a>설명

존재 하는 경우 백그라운드 개체를 삭제 합니다.

##  <a name="createcontrolwindow"></a>  CComCompositeControl::CreateControlWindow

컨트롤 창을 만들 바꾼 모든 호스트 된 컨트롤에이 메서드를 호출 합니다.

```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```

### <a name="parameters"></a>매개 변수

*hWndParent*<br/>
컨트롤의 부모 창 핸들입니다.

*rcPos*<br/>
에 상대적인 좌표를 클라이언트에서 복합 컨트롤의 위치 사각형이 *hWndParent*합니다.

### <a name="return-value"></a>반환 값

새로 만든된 복합 컨트롤 대화 상자에 대 한 핸들을 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [CComCompositeControl::Create](#create) 하 고 [CComCompositeControl::AdviseSinkMap](#advisesinkmap)합니다.

##  <a name="m_hbrbackground"></a>  CComCompositeControl::m_hbrBackground

배경 브러시입니다.

```
HBRUSH m_hbrBackground;
```

##  <a name="m_hwndfocus"></a>  CComCompositeControl::m_hWndFocus

현재 포커스가 있는 창 핸들입니다.

```
HWND m_hWndFocus;
```

##  <a name="setbackgroundcolorfromambient"></a>  CComCompositeControl::SetBackgroundColorFromAmbient

컨테이너의 배경색을 사용 하 여 복합 컨트롤의 배경색을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT SetBackgroundColorFromAmbient();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

## <a name="see-also"></a>참고자료

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[복합 컨트롤 기본 사항](../../atl/atl-composite-control-fundamentals.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
