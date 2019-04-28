---
title: CContainedWindowT 클래스
ms.date: 11/04/2016
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
ms.openlocfilehash: 660c6c047bb700e531fd941ac8ed19d638866070
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246051"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT 클래스

이 클래스는 다른 개체 내에 포함 된 창을 구현 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>
class CContainedWindowT : public TBase
```

#### <a name="parameters"></a>매개 변수

*TBase*<br/>
새 클래스의 기본 클래스입니다. 기본 클래스는 `CWindow`합니다.

*TWinTraits*<br/>
창 스타일을 정의 하는 특성 클래스입니다. 기본값은 `CControlWinTraits`입니다.

> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) 의 특수화 인 `CContainedWindowT`합니다. 사용 하 여 기본 클래스 또는 특성을 변경 하려는 경우 `CContainedWindowT` 직접.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|생성자입니다. 메시지 맵이 포함된 하는 창의 메시지를 처리할 지정 하려면 데이터 멤버를 초기화 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CContainedWindowT::Create](#create)|창을 만듭니다.|
|[CContainedWindowT::DefWindowProc](#defwindowproc)|기본 메시지 처리를 제공합니다.|
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|현재 메시지를 반환합니다.|
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|포함 된 창의 창 클래스를 등록합니다.|
|[CContainedWindowT::SubclassWindow](#subclasswindow)|창을 서브클래싱합니다.|
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|변경 내용이 포함 된 창의 메시지를 처리 하는 메시지 맵을 사용 됩니다.|
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|이전에 서브클래싱된 창을 복원합니다.|
|[CContainedWindowT::WindowProc](#windowproc)|(정적) 포함 된 창으로 전송 된 메시지를 처리 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|메시지 맵이 포함된 하는 창의 메시지를 처리할 식별 합니다.|
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|새 창 클래스를 기반으로 하는 기존 창 클래스의 이름을 지정 합니다.|
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|창 클래스의 원본 창 프로시저를 가리킵니다.|
|[CContainedWindowT::m_pObject](#m_pobject)|포함 하는 개체를 가리킵니다.|

## <a name="remarks"></a>설명

`CContainedWindowT` 다른 개체 내에 포함 된 창을 구현 합니다. `CContainedWindowT`창 프로시저는 메시지를 해당 처리기로 직접 메시지를 포함 하는 개체에 매핑합니다. 생성할 때를 `CContainedWindowT` 개체는 메시지 맵을 사용할지를 지정 합니다.

`CContainedWindowT` 기존 창 클래스 슈퍼 클 래 싱 하 여 새 창을 만들 수 있습니다. 합니다 `Create` 메서드는 먼저 기존 클래스에 기반 이지만 사용 하는 창 클래스 등록 `CContainedWindowT::WindowProc`합니다. `Create` 그런 다음이 새 창 클래스를 기반으로 창을 만듭니다. 각 인스턴스의 `CContainedWindowT` 슈퍼 클래스는 다양 한 창 클래스를 수 있습니다.

`CContainedWindowT`은 또한 창 서브클래싱도 지원합니다. `SubclassWindow` 메서드는 기존 창을 `CContainedWindowT` 개체에 연결하고 창 프로시저를 `CContainedWindowT::WindowProc`로 변경합니다. `CContainedWindowT`의 각 인스턴스는 다른 창을 서브클래싱할 수 있습니다.

> [!NOTE]
>  지정 된 모든 `CContainedWindowT` 개체 중 하나를 호출 `Create` 또는 `SubclassWindow`합니다. 동일한 개체에서 두 메서드를 호출 하지 않아야 합니다.

사용 하는 경우는 **컨트롤 추가 기준** 마법사가 자동으로 추가 하는 ATL 프로젝트 마법사에서 옵션을 `CContainedWindowT` 컨트롤을 구현 하는 클래스 데이터 멤버입니다. 다음 예제에서는 포함된 된 창의 선언 하는 방법을 보여 줍니다.

[!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]

[!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]

[!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]

|추가 정보|참조|
|--------------------------------|---------|
|컨트롤 만들기|[ATL 자습서](../../atl/active-template-library-atl-tutorial.md)|
|ATL에서 창 사용하기|[ATL 창 클래스](../../atl/atl-window-classes.md)|
|ATL 프로젝트 마법사|[ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)|
|Windows|[Windows](/windows/desktop/winmsg/windows) 및 Windows SDK의 후속 항목|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`TBase`

`CContainedWindowT`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="ccontainedwindowt"></a>  CContainedWindowT::CContainedWindowT

생성자는 데이터 멤버를 초기화합니다.

```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
[in] 포함된 된 창의 기반이 될 기존 창 클래스의 이름입니다.

*pObject*<br/>
[in] 메시지 맵에서 선언 하는 포함 하는 개체에 대 한 포인터입니다. 이 개체의이 클래스에서 파생 되어야 합니다 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.

*dwMsgMapID*<br/>
[in] 포함 된 창의 메시지를 처리 하는 메시지 맵을 식별 합니다. 기본값 0으로 지정으로 선언 된 기본 메시지 맵에서 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)합니다. 대체 메시지 맵을 사용 하 여를 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), 전달 `msgMapID`합니다.

### <a name="remarks"></a>설명

통해 새 창을 만들지 않으려면 [만들기](#create)에 대 한 기존 창 클래스의 이름을 전달 해야 합니다 *lpszClassName* 매개 변수. 예를 들어 참조 된 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) 개요.

세 가지 생성자를 가지 있습니다.

- 세 개의 인수를 사용 하 여 생성자는 일반적으로 호출 됩니다.

- 두 개의 인수를 사용 하 여 생성자에서 클래스 이름을 사용 하 여 `TBase::GetWndClassName`입니다.

- 인수가 없는 생성자는 인수를 나중에 지정 하려는 경우에 사용 됩니다. 나중에 호출할 때 창 클래스 이름, 메시지 맵 개체 및 메시지 맵 ID를 제공 해야 `Create`합니다.

하는 경우 기존 창 서브를 통해 [SubclassWindow](#subclasswindow)의 *lpszClassName* 값은 사용 하지 않으면 따라서이 매개 변수에 대해 NULL을 전달할 수 있습니다.

##  <a name="create"></a>  CContainedWindowT::Create

호출 [RegisterWndSuperclass](#registerwndsuperclass) 기존 클래스에 기반 이지만 사용 하는 창 클래스 등록 [CContainedWindowT::WindowProc](#windowproc)합니다.

```
HWND Create(
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszClassName*<br/>
[in] 포함된 된 창의 기반이 될 기존 창 클래스의 이름입니다.

*pObject*<br/>
[in] 메시지 맵에서 선언 하는 포함 하는 개체에 대 한 포인터입니다. 이 개체의이 클래스에서 파생 되어야 합니다 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.

*dwMsgMapID*<br/>
[in] 포함 된 창의 메시지를 처리 하는 메시지 맵을 식별 합니다. 기본값 0으로 지정으로 선언 된 기본 메시지 맵에서 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)합니다. 대체 메시지 맵을 사용 하 여를 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), 전달 `msgMapID`합니다.

*hWndParent*<br/>
[in] 부모 또는 소유자 창에 대 한 핸들입니다.

*rect*<br/>
[in] A [RECT](/previous-versions/dd162897\(v=vs.85\)) 창의 위치를 지정 하는 구조입니다. `RECT` 포인터 또는 참조로 전달할 수 있습니다.

*szWindowName*<br/>
[in] 창의 이름을 지정합니다. 기본값은 NULL입니다.

*dwStyle*<br/>
[in] 창 스타일입니다. 기본값은 WS_CHILD &#124; WS_VISIBLE 합니다. 가능한 값 목록을 참조 하세요 [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) Windows SDK에 있습니다.

*dwExStyle*<br/>
[in] 확장된 창 스타일입니다. 기본값은 0, 확장 된 스타일이 없습니다. 가능한 값 목록을 참조 하세요 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK에 있습니다.

*MenuOrID*<br/>
[in] 자식 창의 창 식별자입니다. 최상위 창에 대 한 메뉴 창에 대 한 처리 합니다. 기본값은 **0U**합니다.

*lpCreateParam*<br/>
[in] 창 만들기 데이터에 대 한 포인터입니다. 에 마지막 매개 변수에 대 한 설명을 참조 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa)합니다.

### <a name="return-value"></a>반환 값

성공 하면 새로 만든된 창에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

기존 창 클래스 이름에 저장 됩니다 [m_lpszClassName](#m_lpszclassname)합니다. `Create` 그런 다음이 새 클래스를 기반으로 창을 만듭니다. 새로 만든된 창에 자동으로 연결 되는 `CContainedWindowT` 개체입니다.

> [!NOTE]
>  호출 하지 마세요 `Create` 이미 호출한 경우 [SubclassWindow](#subclasswindow)합니다.

> [!NOTE]
>  0 값으로 사용 되는 경우는 *MenuOrID* 매개 변수를 0U로 지정 되어야 합니다 (기본값) 컴파일러 오류를 방지 하려면.

##  <a name="defwindowproc"></a>  CContainedWindowT::DefWindowProc

호출한 [WindowProc](#windowproc) 메시지 맵에서에서 처리 되지 않은 메시지를 처리 하도록 합니다.

```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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

##  <a name="getcurrentmessage"></a>  CContainedWindowT::GetCurrentMessage

현재 메시지를 반환 합니다 (`m_pCurrentMsg`).

```
const _ATL_MSG* GetCurrentMessage();
```

### <a name="return-value"></a>반환 값

현재 메시지에 패키지를 `MSG` 구조입니다.

##  <a name="m_dwmsgmapid"></a>  CContainedWindowT::m_dwMsgMapID

포함 된 창에 대 한 현재 사용 중인 메시지 맵의 식별자를 포함 합니다.

```
DWORD m_dwMsgMapID;
```

### <a name="remarks"></a>설명

이 메시지 맵은 포함 하는 개체에 선언 되어야 합니다.

기본 메시지 맵을 사용 하 여 선언 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), 항상 0으로 식별 됩니다. 대체 메시지 지도 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map),으로 식별 되 `msgMapID`합니다.

`m_dwMsgMapID` 생성자가 먼저 초기화 되 고 호출 하 여 변경할 수 있습니다 [SwitchMessageMap](#switchmessagemap)합니다. 예를 들어 참조 된 [CContainedWindowT 개요](../../atl/reference/ccontainedwindowt-class.md)합니다.

##  <a name="m_lpszclassname"></a>  CContainedWindowT::m_lpszClassName

기존 창 클래스의 이름을 지정 합니다.

```
LPTSTR m_lpszClassName;
```

### <a name="remarks"></a>설명

창을 만들 때 [Create](#create) 이 기존 클래스를 기반 이지만 사용 하는 새 창 클래스 등록 [CContainedWindowT::WindowProc](#windowproc)합니다.

`m_lpszClassName` 생성자에서 초기화 됩니다. 예를 들어 참조 된 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) 개요.

##  <a name="m_pfnsuperwindowproc"></a>  CContainedWindowT::m_pfnSuperWindowProc

포함 된 창을 서브클래싱은 경우 `m_pfnSuperWindowProc` 창 클래스의 원본 창 프로시저를 가리킵니다.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>설명

포함된 된 창의 슈퍼 클래스로 지정 된 경우 기존 클래스를 수정 하는 창 클래스에 기반 의미 `m_pfnSuperWindowProc` 기존 창 클래스의 창 프로시저를 가리킵니다.

합니다 [DefWindowProc](#defwindowproc) 메서드를 저장 창 프로시저로 메시지 정보를 보냅니다 `m_pfnSuperWindowProc`합니다.

##  <a name="m_pobject"></a>  CContainedWindowT::m_pObject

포함 하는 개체를 가리키는 `CContainedWindowT` 개체입니다.

```
CMessageMap* m_pObject;
```

### <a name="remarks"></a>설명

이 컨테이너에 해당 클래스에서 파생 되어야 합니다 [CMessageMap](../../atl/reference/cmessagemap-class.md), 포함 된 창에서 사용 되는 메시지 맵을 선언 합니다.

`m_pObject` 생성자에서 초기화 됩니다. 예를 들어 참조 된 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) 개요.

##  <a name="registerwndsuperclass"></a>  CContainedWindowT::RegisterWndSuperclass

호출한 [만들기](#create) 포함 된 창의 창 클래스를 등록 합니다.

```
ATOM RegisterWndSuperClass();
```

### <a name="return-value"></a>반환 값

성공 하면 atom 고유 하 게 식별 하는 등록 되는 창 클래스 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 창 클래스는 기존 클래스에 기반 하지만 사용 하 여 [CContainedWindowT::WindowProc](#windowproc)합니다. 기존 창 클래스 이름 및 창 프로시저에 저장 됩니다 [m_lpszClassName](#m_lpszclassname) 하 고 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc), 각각.

##  <a name="subclasswindow"></a>  CContainedWindowT::SubclassWindow

창으로 식별 되는 서브 클래스 *hWnd* 에 연결 하 고는 `CContainedWindowT` 개체입니다.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>매개 변수

*hWnd*<br/>
[in] 서브클래싱 되 고 창에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

TRUE 이면 성공적으로 서브클래싱된; 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

서브클래싱된 창을 사용 하 여 이제 [CContainedWindowT::WindowProc](#windowproc)합니다. 원본 창 프로시저에 저장 됩니다 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.

> [!NOTE]
>  호출 하지 마세요 `SubclassWindow` 이미 호출한 경우 [만들기](#create)합니다.

##  <a name="switchmessagemap"></a>  CContainedWindowT::SwitchMessageMap

메시지 맵이 포함 된 창의 메시지를 처리 하는 데 사용 되는 변경 내용입니다.

```
void SwitchMessageMap(DWORD dwMsgMapID);
```

### <a name="parameters"></a>매개 변수

*dwMsgMapID*<br/>
[in] 메시지 맵 식별자입니다. 기본 메시지 맵을 사용 하 여를 사용 하 여 선언 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), 0을 전달 합니다. 대체 메시지 맵을 사용 하 여를 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), 전달 `msgMapID`합니다.

### <a name="remarks"></a>설명

메시지 맵은 포함 하는 개체에 정의 되어야 합니다.

처음에 생성자에서 메시지 맵 식별자를 지정 합니다.

##  <a name="unsubclasswindow"></a>  CContainedWindowT::UnsubclassWindow

서브클래싱된 창을 분리 합니다 `CContainedWindowT` 개체를 저장, 원본 창 프로시저를 복원 [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)합니다.

```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```

### <a name="parameters"></a>매개 변수

*bForce*<br/>
[in] 복원할 원본 창 프로시저 강제 하려면 true로 설정 하더라도이 위한 창 프로시저 `CContainedWindowT` 개체가 현재 활성 상태가 아닙니다. 하는 경우 *bForce* 가 FALSE로 설정 되며 창 프로시저를이 `CContainedWindowT` 개체 현재 활성 상태인 원본 창 프로시저 복원 되지 것입니다.

### <a name="return-value"></a>반환 값

이전에 서브클래싱된 창에 대 한 핸들입니다. 하는 경우 *bForce* 가 FALSE로 설정 되며 창 프로시저를이 `CContainedWindowT` 개체 현재 활성화 되지 않으면 NULL을 반환 합니다.

### <a name="remarks"></a>설명

창 소멸 되기 전에 원본 창 프로시저를 복원 하려는 경우에이 메서드를 사용 합니다. 그렇지 않으면 [WindowProc](#windowproc) 는 자동으로 수행이 창이 소멸 되는 경우.

##  <a name="windowproc"></a>  CContainedWindowT::WindowProc

이 정적 메서드는 창 프로시저를 구현합니다.

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

`WindowProc` 로 식별 되는 메시지 맵에 메시지를 보냅니다 [m_dwMsgMapID](#m_dwmsgmapid)합니다. 필요한 경우 `WindowProc` 호출 [DefWindowProc](#defwindowproc) 추가 메시지 처리에 대 한 합니다.

## <a name="see-also"></a>참고자료

[CWindow 클래스](../../atl/reference/cwindow-class.md)<br/>
[CWindowImpl 클래스](../../atl/reference/cwindowimpl-class.md)<br/>
[CMessageMap 클래스](../../atl/reference/cmessagemap-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
