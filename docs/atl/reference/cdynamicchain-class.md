---
title: CDynamicChain 클래스
ms.date: 11/04/2016
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
ms.openlocfilehash: 4b68198c17d7bd030b88bc78ad4de1367c914703
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259003"
---
# <a name="cdynamicchain-class"></a>CDynamicChain 클래스

이 클래스는 메시지 맵의 동적 연결을 지 원하는 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CDynamicChain
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDynamicChain::CDynamicChain](#cdynamicchain)|생성자입니다.|
|[CDynamicChain::~CDynamicChain](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDynamicChain::CallChain](#callchain)|다른 개체의 메시지 맵에 Windows 메시지를 보냅니다.|
|[CDynamicChain::RemoveChainEntry](#removechainentry)|메시지 맵 항목을 컬렉션에서 제거합니다.|
|[CDynamicChain::SetChainEntry](#setchainentry)|메시지 맵 항목을 컬렉션에 추가 하거나 기존 항목을 수정 합니다.|

## <a name="remarks"></a>설명

`CDynamicChain` 메시지 맵, Windows 메시지를 다른 개체의 메시지 맵에 런타임에 전달 설정의 컬렉션을 관리 합니다.

메시지 맵의 동적 연결에 대 한 지원을 추가 하려면 다음을 수행 합니다.

- 클래스를 파생 `CDynamicChain`합니다. 메시지 맵에서 지정 된 [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) 매크로를 다른 개체의 기본 메시지 맵에 체인.

- 연결 하려는 모든 클래스를 파생 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다. `CMessageMap` 개체가 다른 개체에는 메시지 맵을 노출할 수 있습니다.

- 호출 `CDynamicChain::SetChainEntry` 개체 및 메시지 맵에 체인으로 연결 해야 하는 데 있습니다.

예를 들어, 클래스는 다음과 같이 정의 됩니다.

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

클라이언트 호출 `CMyWindow::SetChainEntry`:

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

여기서 `chainedObj` 에서 파생 된 클래스의 인스턴스는 연결 된 개체 이며 `CMessageMap`합니다. 이제 경우 `myCtl` 하 여 처리 되지 않은 메시지를 받을 `OnPaint` 또는 `OnSetFocus`, 창 프로시저에서 메시지를 보냅니다 `chainedObj`의 기본 메시지 맵.

메시지 맵 연결에 대 한 자세한 내용은 참조 하세요. [메시지 맵](../../atl/message-maps-atl.md) 문서의 "ATL 창 클래스입니다."

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="callchain"></a>  CDynamicChain::CallChain

다른 개체의 메시지 맵 Windows 메시지를 보냅니다.

```
BOOL CallChain(
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```

### <a name="parameters"></a>매개 변수

*dwChainID*<br/>
[in] 연결 된 개체 및 자신의 메시지 맵을 사용 하 여 연결 된 고유 식별자입니다.

*hWnd*<br/>
[in] 메시지를 받는 창에 대 한 핸들입니다.

*uMsg*<br/>
[in] 창으로 전송 하는 메시지입니다.

*wParam*<br/>
[in] 추가 메시지 관련 정보입니다.

*lParam*<br/>
[in] 추가 메시지 관련 정보입니다.

*lResult*<br/>
[out] 메시지 처리의 결과입니다.

### <a name="return-value"></a>반환 값

메시지는 완벽 하 게 처리 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

호출 하기 위해 창 프로시저에 대 한 `CallChain`를 지정 해야 합니다 [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) 메시지 맵에서 매크로입니다. 예를 들어 참조 된 [CDynamicChain](../../atl/reference/cdynamicchain-class.md) 개요.

`CallChain` 이전 호출을 [SetChainEntry](#setchainentry) 연결 하는 *dwChainID* 개체 및 자신의 메시지 맵을 사용 하 여 값입니다.

##  <a name="cdynamicchain"></a>  CDynamicChain::CDynamicChain

생성자입니다.

```
CDynamicChain();
```

##  <a name="dtor"></a>  CDynamicChain::~CDynamicChain

소멸자입니다.

```
~CDynamicChain();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="removechainentry"></a>  CDynamicChain::RemoveChainEntry

컬렉션에서 지정 된 메시지 맵을 제거합니다.

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>매개 변수

*dwChainID*<br/>
[in] 연결 된 개체 및 자신의 메시지 맵을 사용 하 여 연결 된 고유 식별자입니다. 호출 하 여이 값을 원래 정의한 [SetChainEntry](#setchainentry)합니다.

### <a name="return-value"></a>반환 값

메시지 맵에서 컬렉션에서 성공적으로 제거 되 면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="setchainentry"></a>  CDynamicChain::SetChainEntry

컬렉션에 지정 된 메시지 맵에 추가합니다.

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>매개 변수

*dwChainID*<br/>
[in] 연결 된 개체 및 자신의 메시지 맵을 사용 하 여 연결 된 고유 식별자입니다.

*pObject*<br/>
[in] 메시지 맵에서 선언 하는 연결 된 개체에 대 한 포인터입니다. 이 개체에서 파생 되어야 합니다 [CMessageMap](../../atl/reference/cmessagemap-class.md)합니다.

*dwMsgMapID*<br/>
[in] 메시지 맵에서 연결 된 개체에서의 식별자입니다. 기본값은 0으로, 사용 하 여 선언 된 기본 메시지 맵에서 식별 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)합니다. 대체 메시지 맵을 지정을 사용 하 여 선언 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), 전달 `msgMapID`합니다.

### <a name="return-value"></a>반환 값

메시지 맵에서 컬렉션에 추가 되 면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

경우는 *dwChainID* 값이 이미 컬렉션에 있는지, 해당 연결 된 개체 및 메시지 맵 바뀝니다 *pObject* 하 고 *dwMsgMapID*각각. 그렇지 않으면 새 항목이 추가 됩니다.

## <a name="see-also"></a>참고자료

[CWindowImpl 클래스](../../atl/reference/cwindowimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
