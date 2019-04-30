---
title: CWndClassInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
ms.openlocfilehash: 4aeac558c28d0ac89707423433e51f348bc35d29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276720"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo 클래스

이 클래스는 창 클래스에 대 한 정보를 등록 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CWndClassInfo
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|[등록](#register)|창 클래스를 등록합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_atom](#m_atom)|등록 된 창 클래스를 고유 하 게 식별합니다.|
|[m_bSystemCursor](#m_bsystemcursor)|커서 리소스 시스템 커서 또는 모듈 리소스에 포함 된 커서를 참조 하는지 여부를 지정 합니다.|
|[m_lpszCursorID](#m_lpszcursorid)|커서 리소스의 이름을 지정합니다.|
|[m_lpszOrigName](#m_lpszorigname)|기존 창 클래스의 이름을 포함합니다.|
|[m_szAutoName](#m_szautoname)|창 클래스의 ATL 생성 된 이름을 보유합니다.|
|[m_wc](#m_wc)|창 클래스 정보를 유지 관리는 `WNDCLASSEX` 구조입니다.|
|[pWndProc](#pwndproc)|기존 창 클래스의 창 프로시저를 가리킵니다.|

## <a name="remarks"></a>설명

`CWndClassInfo` 창 클래스의 정보를 관리합니다. 일반적으로 사용할 `CWndClassInfo` 매크로, DECLARE_WND_CLASS, DECLARE_WND_CLASS_EX, 또는 DECLARE_WND_SUPERCLASS, 다음 표에 설명 된 대로 세 가지 중 하나를 통해:

|매크로|설명|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` 새 창 클래스에 대 한 정보를 등록합니다.|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` 클래스 매개 변수를 포함 하 여 새 창 클래스에 대 한 정보를 등록 합니다.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` 기존 클래스에 기반 이지만 다른 창 프로시저를 사용 하는 창 클래스에 대 한 정보를 등록 합니다. 이 기술은 슈퍼 클 래 싱을 라고 합니다.|

기본적으로 [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 포함 된 `DECLARE_WND_CLASS` 새 창 클래스를 기반으로 창을 만들려면 매크로입니다. DECLARE_WND_CLASS는 컨트롤에 대 한 기본 스타일 및 배경색을 제공합니다. 스타일 지정 및 배경색 직접 하려는 경우 파생 클래스에서 `CWindowImpl` 클래스 정의에 DECLARE_WND_CLASS_EX 매크로 포함 합니다.

기존 창 클래스를 기반으로 창을 만들려는 경우 파생 클래스에서 `CWindowImpl` 클래스 정의에 DECLARE_WND_SUPERCLASS 매크로 포함 합니다. 예를 들어:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

창 클래스에 대 한 자세한 내용은 참조 하세요. [창 클래스](/windows/desktop/winmsg/window-classes) Windows SDK에 있습니다.

ATL에서 창 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 창 클래스](../../atl/atl-window-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="m_atom"></a>  CWndClassInfo::m_atom

등록 된 window 클래스에 대 한 고유 식별자를 포함 합니다.

```
ATOM m_atom;
```

##  <a name="m_bsystemcursor"></a>  CWndClassInfo::m_bSystemCursor

True 이면 시스템 커서 리소스 창 클래스 등록 될 때 로드 됩니다.

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>설명

그렇지 않으면 모듈에 포함 된 커서 리소스 로드 됩니다.

`CWndClassInfo` 사용 하 여 `m_bSystemCursor` 경우에만 합니다 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (기본값 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) 또는 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 매크로 지정 합니다. 이 경우 `m_bSystemCursor` TRUE로 초기화 됩니다. 자세한 내용은 참조는 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 개요.

##  <a name="m_lpszcursorid"></a>  CWndClassInfo::m_lpszCursorID

하위 단어 및 상위 단어에 0이 커서 리소스의 이름 또는 리소스 식별자를 지정합니다.

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>설명

창 클래스 등록 되 면,로 식별 되는 커서에 대 한 핸들 `m_lpszCursorID` 를 검색 하 고 저장 [m_wc](#m_wc)합니다.

`CWndClassInfo` 사용 하 여 `m_lpszCursorID` 경우에만 합니다 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (기본값 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) 또는 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 매크로 지정 합니다. 이 경우 `m_lpszCursorID` IDC_ARROW로 초기화 됩니다. 자세한 내용은 참조는 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 개요.

##  <a name="m_lpszorigname"></a>  CWndClassInfo::m_lpszOrigName

기존 창 클래스의 이름을 포함합니다.

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>설명

`CWndClassInfo` 사용 하 여 `m_lpszOrigName` 만 포함 하는 경우는 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 클래스 정의에 매크로입니다. 이 예에서 `CWndClassInfo` 으로 명명 된 클래스를 기반으로 창 클래스 등록 `m_lpszOrigName`합니다. 자세한 내용은 참조는 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 개요.

##  <a name="m_szautoname"></a>  CWndClassInfo::m_szAutoName

창 클래스의 이름을 보유 합니다.

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>설명

`CWndClassInfo` 사용 하 여 `m_szAutoName` 에 대 한 NULL이 전달 되는 경우에 합니다 `WndClassName` 매개 변수를 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)의 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 또는 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) . ATL 창 클래스를 등록 하는 경우 이름을 생성 합니다.

##  <a name="m_wc"></a>  CWndClassInfo::m_wc

창 클래스 정보를 유지 관리를 [WNDCLASSEX](/windows/desktop/api/winuser/ns-winuser-tagwndclassexa) 구조입니다.

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>설명

지정한 경우에 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (의 기본값 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) 또는 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 매크로 `m_wc` 에 대 한 정보는 새 창 클래스입니다.

지정한 경우에 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로 `m_wc` 슈퍼 클래스에 대 한 정보가-기존 클래스에 기반 이지만 다른 창 프로시저를 사용 하는 창 클래스입니다. [m_lpszOrigName](#m_lpszorigname) 하 고 [pWndProc](#pwndproc) 기존 창 클래스 이름 및 창 프로시저를 각각 저장 합니다.

##  <a name="pwndproc"></a>  CWndClassInfo::pWndProc

기존 창 클래스의 창 프로시저를 가리킵니다.

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>설명

`CWndClassInfo` 사용 하 여 `pWndProc` 만 포함 하는 경우는 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 클래스 정의에 매크로입니다. 이 경우 `CWndClassInfo` 기존 클래스에 기반 이지만 다른 창 프로시저를 사용 하는 창 클래스를 등록 합니다. 기존 창 클래스의 창 프로시저에 저장 된 `pWndProc`합니다. 자세한 내용은 참조는 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 개요.

##  <a name="register"></a>  CWndClassInfo::Register

호출한 [CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create) 아직 등록 되지 않은 경우 창 클래스를 등록 합니다.

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>매개 변수

*pProc*<br/>
[out] 기존 창 클래스의 원본 창 프로시저를 지정합니다.

### <a name="return-value"></a>반환 값

성공 하면 atom 고유 하 게 식별 하는 창 클래스 등록 합니다. 그렇지 않을 경우 0입니다.

### <a name="remarks"></a>설명

지정한 경우에 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) (의 기본값 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)) 또는 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 매크로 `Register` 새 창 클래스 등록 합니다. 이 경우에 *pProc* 매개 변수가 사용 되지 않습니다.

지정한 경우에 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 매크로 `Register` 슈퍼 클래스 등록-기존 클래스에 기반 이지만 다른 창 프로시저를 사용 하는 창 클래스입니다. 기존 창 클래스의 창 프로시저에서 반환 됩니다 *pProc*합니다.

## <a name="see-also"></a>참고자료

[CComControl 클래스](../../atl/reference/ccomcontrol-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
