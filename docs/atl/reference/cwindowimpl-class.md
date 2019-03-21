---
title: CWindowImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::CWindowImpl::DefWindowProc
- ATLWIN/ATL::CWindowImpl::GetCurrentMessage
- ATLWIN/ATL::CWindowImpl::GetWindowProc
- ATLWIN/ATL::CWindowImpl::OnFinalMessage
- ATLWIN/ATL::CWindowImpl::SubclassWindow
- ATLWIN/ATL::CWindowImpl::UnsubclassWindow
- ATLWIN/ATL::CWindowImpl::GetWndClassInfo
- ATLWIN/ATL::CWindowImpl::WindowProc
- ATLWIN/ATL::CWindowImpl::m_pfnSuperWindowProc
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
ms.openlocfilehash: f835f2869af20a1cb22595837c317eb165ef5fe9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820353"
---
# <a name="cwindowimpl-class"></a>CWindowImpl 클래스

창을 만들거나 서브클래싱하기 위한 메서드를 제공합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>

  `CWindowImpl`에서 파생된 새 클래스입니다.

*TBase*<br/>
클래스의 기본 클래스입니다. 기본 클래스는 기본적으로 [CWindow](../../atl/reference/cwindow-class.md)합니다.

*TWinTraits*<br/>
A [traits 클래스](../../atl/understanding-window-traits.md) 창 스타일을 정의 하는 합니다. 기본값은 `CControlWinTraits`입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWindowImpl::Create](#create)|창을 만듭니다.|

### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT 메서드

|||
|-|-|
|[DefWindowProc](#defwindowproc)|기본 메시지 처리를 제공합니다.|
|[GetCurrentMessage](#getcurrentmessage)|현재 메시지를 반환합니다.|
|[GetWindowProc](#getwindowproc)|현재 창 프로시저를 반환합니다.|
|[OnFinalMessage](#onfinalmessage)|마지막 메시지를 받은 후에 호출 됩니다 (일반적으로 WM_NCDESTROY).|
|[SubclassWindow](#subclasswindow)|창을 서브클래싱합니다.|
|[UnsubclassWindow](#unsubclasswindow)|이전에 서브클래싱된 창을 복원합니다.|

### <a name="static-methods"></a>정적 메서드

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|정적 인스턴스를 반환 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), 창 클래스 정보를 관리 하는 합니다.|
|[WindowProc](#windowproc)|창으로 보내는 메시지를 처리합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|창 클래스의 원본 창 프로시저를 가리킵니다.|

## <a name="remarks"></a>설명

사용할 수 있습니다 `CWindowImpl` 창 또는 서브 클래스는 기존 창을 만들 수 있습니다. `CWindowImpl` 창 프로시저를 해당 처리기로 메시지를 보내는 메시지 맵을 사용 합니다.

`CWindowImpl::Create` 관리 되는 창 클래스 정보를 기반으로 창을 만듭니다 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)합니다. `CWindowImpl` 포함 된 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) 의미 하는 매크로 `CWndClassInfo` 새 창 클래스 등록 합니다. 슈퍼 기존 창 클래스를 파생 클래스에서 `CWindowImpl` 포함 된 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로입니다. 이 경우 `CWndClassInfo`는 기존 클래스를 기반으로 하는 창 클래스 등록하지만 `CWindowImpl::WindowProc`를 사용합니다. 예를 들어:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
>  
  `CWndClassInfo`는 한 윈도우 클래스의 정보만 관리하기 때문에, `CWindowImpl`의 인스턴스를 통해 생성된 각 창은 동일한 창 클래스를 기반으로 합니다.

`CWindowImpl`은 또한 창 서브클래싱도 지원합니다. 
  `SubclassWindow` 메서드는 기존 창을 `CWindowImpl` 개체에 연결하고 창 프로시저를 `CWindowImpl::WindowProc`로 변경합니다. 
  `CWindowImpl`의 각 인스턴스는 다른 창을 서브클래싱할 수 있습니다.

> [!NOTE]
>  지정 된 모든 `CWindowImpl` 개체 중 하나를 호출 `Create` 또는 `SubclassWindow`합니다. 동일한 개체에서 두 메서드를 모두 호출하지는 마십시오.

외에 `CWindowImpl`, ATL 제공 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 다른 개체에 포함 된 창을 만들 수 있습니다.

기본 클래스 소멸자 (~ `CWindowImplRoot`) 개체를 제거 하기 전에 창이 사라집니다 인지 확인 합니다.

`CWindowImpl` 파생 `CWindowImplBaseT`에서 파생 되는 `CWindowImplRoot`에서 파생 되는 `TBase` 하 고 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.

|추가 정보|참조|
|--------------------------------|---------|
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|
|ATL에서 창 사용하기|[ATL 창 클래스](../../atl/atl-window-classes.md)|
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CWindowImplBaseT`

`CWindowImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="create"></a>  CWindowImpl::Create

새 창 클래스를 기반으로 창을 만듭니다.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>매개 변수

*hWndParent*<br/>
[in] 부모 또는 소유자 창에 대 한 핸들입니다.

*rect*<br/>
[in] A [RECT](/previous-versions/dd162897\(v=vs.85\)) 창의 위치를 지정 하는 구조입니다. `RECT` 포인터 또는 참조로 전달할 수 있습니다.

*szWindowName*<br/>
[in] 창의 이름을 지정합니다. 기본값은 NULL입니다.

*dwStyle*<br/>
[in] 창 스타일입니다. 이 값은 창에 대 한 특성 클래스에서 제공 하는 스타일을 사용 하 여 결합 됩니다. 기본 값을 특성 클래스를 완전히 제어할 스타일을 제공합니다. 가능한 값 목록을 참조 하세요 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Windows SDK에 있습니다.

*dwExStyle*<br/>
[in] 확장된 창 스타일입니다. 이 값은 창에 대 한 특성 클래스에서 제공 하는 스타일을 사용 하 여 결합 됩니다. 기본 값을 특성 클래스를 완전히 제어할 스타일을 제공합니다. 가능한 값 목록을 참조 하세요 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK에 있습니다.

*MenuOrID*<br/>
[in] 자식 창의 창 식별자입니다. 최상위 창에 대 한 메뉴 창에 대 한 처리 합니다. 기본값은 **0U**합니다.

*lpCreateParam*<br/>
[in] 창 만들기 데이터에 대 한 포인터입니다. 에 마지막 매개 변수에 대 한 설명을 참조 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa)합니다.

### <a name="return-value"></a>반환 값

성공 하면 새로 만든된 창에 대 한 핸들입니다. 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

`Create` 아직 등록 하지 않은 경우 먼저 창 클래스를 등록 합니다. 새로 만든된 창에 자동으로 연결 되는 `CWindowImpl` 개체입니다.

> [!NOTE]
>  호출 하지 마세요 `Create` 이미 호출한 경우 [SubclassWindow](#subclasswindow)합니다.

기존 창 클래스를 기반으로 하는 창 클래스를 사용 하려면에서 클래스를 파생 `CWindowImpl` 포함 된 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로입니다. 기존 창 클래스의 창 프로시저에 저장 됩니다 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다. 자세한 내용은 참조는 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 개요.

> [!NOTE]
>  0 값으로 사용 되는 경우는 *MenuOrID* 매개 변수를 0U로 지정 되어야 합니다 (기본값) 컴파일러 오류를 방지 하려면.

##  <a name="defwindowproc"></a>  CWindowImpl::DefWindowProc

호출한 [WindowProc](#windowproc) 메시지 맵에서에서 처리 되지 않은 메시지를 처리 하도록 합니다.

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>매개 변수

*uMsg*<br/>
[in] 창으로 전송 하는 메시지입니다.

*wParam*<br/>
[in] 추가 메시지 관련 정보입니다.

*lParam*<br/>
[in] 추가 메시지 관련 정보입니다.

### <a name="return-value"></a>반환 값

메시지 처리의 결과입니다.

### <a name="remarks"></a>설명

기본적으로 `DefWindowProc` 호출을 [CallWindowProc](/windows/desktop/api/winuser/nf-winuser-callwindowproca) Win32 함수에 지정 된 창 프로시저 메시지 정보를 보낼 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.

자동으로 매개 변수가 없는 함수는 현재 메시지에서 필요한 매개 변수를 검색합니다.

##  <a name="getcurrentmessage"></a>  CWindowImpl::GetCurrentMessage

패키지에서 현재 메시지를 반환 합니다 `MSG` 구조입니다.

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>반환 값

현재 메시지입니다.

##  <a name="getwindowproc"></a>  CWindowImpl::GetWindowProc

반환 `WindowProc`, 현재 창 프로시저입니다.

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>반환 값

현재 창 프로시저입니다.

### <a name="remarks"></a>설명

고유한 창 프로시저를 대체 하려면이 메서드를 재정의 합니다.

##  <a name="getwndclassinfo"></a>  CWindowImpl::GetWndClassInfo

호출한 [만들기](#create) 창 클래스 정보에 액세스할 수 있습니다.

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>반환 값

정적 인스턴스 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)합니다.

### <a name="remarks"></a>설명

기본적으로 `CWindowImpl` 를 통해이 메서드를 가져옵니다 합니다 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) 새 창 클래스를 지정 하는 매크로입니다.

기존 창 클래스 슈퍼 클래스에서 클래스 파생 `CWindowImpl` 등과 합니다 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로 재정의를 `GetWndClassInfo`합니다. 자세한 내용은 참조는 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 개요.

DECLARE_WND_CLASS 및 DECLARE_WND_SUPERCLASS 매크로 사용 하는 것 외에도 재정의할 수 있습니다 `GetWndClassInfo` 고유한 구현 합니다.

##  <a name="m_pfnsuperwindowproc"></a>  CWindowImpl::m_pfnSuperWindowProc

창에 따라 창 절차 중 하나를 가리킵니다.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>설명

|창 유형|창 프로시저|
|--------------------|----------------------|
|통해 지정 된 새 창 클래스를 기반으로 창을 합니다 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) 매크로입니다.|합니다 [DefWindowProc](/windows/desktop/api/winuser/nf-winuser-defwindowproca) Win32 함수입니다.|
|통해 지정 된 기존 클래스를 수정 하는 창 클래스를 기반으로 창을 합니다 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로입니다.|기존 창 클래스의 창 프로시저입니다.|
|서브클래싱된 창입니다.|서브클래싱된 창의 원래 창 프로시저입니다.|

[CWindowImpl::DefWindowProc](#defwindowproc) 메시지 정보를 저장 창 프로시저로 보냅니다 `m_pfnSuperWindowProc`합니다.

##  <a name="onfinalmessage"></a>  CWindowImpl::OnFinalMessage

(일반적으로 WM_NCDESTROY) 마지막 메시지를 받은 후 호출 됩니다.

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
[in] 소멸 될 창의 핸들입니다.

### <a name="remarks"></a>설명

기본 구현을 `OnFinalMessage` 하지 않지만 창을 제거 하기 전에 정리를 처리 하려면이 함수를 재정의할 수 있습니다. 창 소멸 시 개체를 자동으로 삭제 하려는 경우 호출할 수 있습니다 **; 삭제** 이 함수에서.

##  <a name="subclasswindow"></a>  CWindowImpl::SubclassWindow

창으로 식별 되는 서브 클래스 *hWnd* 에 연결 하 고는 `CWindowImpl` 개체입니다.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
[in] 서브클래싱 되 고 창에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

TRUE 이면 성공적으로 서브클래싱된; 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

서브클래싱된 창을 사용 하 여 이제 [CWindowImpl::WindowProc](#windowproc)합니다. 원본 창 프로시저에 저장 됩니다 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.

> [!NOTE]
>  호출 하지 마세요 `SubclassWindow` 이미 호출한 경우 [만들기](#create)합니다.

##  <a name="unsubclasswindow"></a>  CWindowImpl::UnsubclassWindow

서브클래싱된 창을 분리 합니다 `CWindowImpl` 개체를 저장, 원본 창 프로시저를 복원 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>반환 값

이전에 서브클래싱된 창에 대 한 핸들입니다.

##  <a name="windowproc"></a>  CWindowImpl::WindowProc

이 정적 함수는 창 프로시저를 구현합니다.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
[in] 창에 대 한 핸들입니다.

*uMsg*<br/>
[in] 창으로 전송 하는 메시지입니다.

*wParam*<br/>
[in] 추가 메시지 관련 정보입니다.

*lParam*<br/>
[in] 추가 메시지 관련 정보입니다.

### <a name="return-value"></a>반환 값

메시지 처리의 결과입니다.

### <a name="remarks"></a>설명

`WindowProc` 기본 메시지 맵을 사용 하 여 (사용 하 여 선언 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map))를 해당 처리기로 메시지를 보내도록 합니다. 필요한 경우 `WindowProc` 호출 [DefWindowProc](#defwindowproc) 추가 메시지 처리에 대 한 합니다. 최종 메시지 처리 되지 않은 경우 `WindowProc` 다음을 수행 합니다.

- 창을 서브클래싱 되었으면 unsubclassing 수행 합니다.

- `m_hWnd`을 지웁니다.

- 호출 [OnFinalMessage](#onfinalmessage) 창을 소멸 되기 전에 합니다.

재정의할 수 있습니다 `WindowProc` 메시지를 처리 하기 위한 다른 메커니즘을 제공 합니다.

## <a name="see-also"></a>참고자료

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
