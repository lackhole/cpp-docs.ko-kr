---
title: CAnimationManagerEventHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::OnManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationManagerEventHandler [MFC], CAnimationManagerEventHandler
- CAnimationManagerEventHandler [MFC], CreateInstance
- CAnimationManagerEventHandler [MFC], OnManagerStatusChanged
- CAnimationManagerEventHandler [MFC], SetAnimationController
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
ms.openlocfilehash: bd13ba4d0dd60f65372b2c1f51d70d338566301e
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916255"
---
# <a name="canimationmanagereventhandler-class"></a>CAnimationManagerEventHandler 클래스

애니메이션 관리자의 상태가 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](#canimationmanagereventhandler)|`CAnimationManagerEventHandler` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CAnimationManagerEventHandler::CreateInstance](#createinstance)|개체의 `CAnimationManagerEventHandler` 인스턴스를 만듭니다.|
|[CAnimationManagerEventHandler::OnManagerStatusChanged](#onmanagerstatuschanged)|애니메이션 관리자의 상태가 변경 되 면 호출 됩니다. ( `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`을 재정의합니다.)|
|[CAnimationManagerEventHandler::SetAnimationController](#setanimationcontroller)|애니메이션 컨트롤러에 대 한 포인터를 저장 하 여 이벤트를 라우팅합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기는 CAnimationController:: EnableAnimationManagerEvent를 호출할 때 생성 되 고 Iui-: SetManagerEventHandler 메서드로 전달 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="canimationmanagereventhandler"></a>  CAnimationManagerEventHandler::CAnimationManagerEventHandler

Visual Studio 2010 SP1이 필요합니다.

CAnimationManagerEventHandler 개체를 생성 합니다.

```
CAnimationManagerEventHandler();
```

##  <a name="createinstance"></a>  CAnimationManagerEventHandler::CreateInstance

Visual Studio 2010 SP1이 필요합니다.

CAnimationManagerEventHandler 개체의 인스턴스를 만듭니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>매개 변수

*pAnimationController*<br/>
이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.

*ppManagerEventHandler*<br/>
출력. 메서드가 성공 하면 애니메이션 관리자에 대 한 상태 업데이트를 처리 하는 COM 개체에 대 한 포인터가 포함 됩니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환 합니다.

##  <a name="onmanagerstatuschanged"></a>  CAnimationManagerEventHandler::OnManagerStatusChanged

Visual Studio 2010 SP1이 필요합니다.

애니메이션 관리자의 상태가 변경 되 면 호출 됩니다.

```
IFACEMETHOD(OnManagerStatusChanged)(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>매개 변수

*newStatus*<br/>
새 상태입니다.

*previousStatus*<br/>
이전 상태.

### <a name="return-value"></a>반환 값

현재 구현에서는 항상 S_OK를 반환 합니다.

##  <a name="setanimationcontroller"></a>  CAnimationManagerEventHandler::SetAnimationController

Visual Studio 2010 SP1이 필요합니다.

애니메이션 컨트롤러에 대 한 포인터를 저장 하 여 이벤트를 라우팅합니다.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*pAnimationController*<br/>
이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
