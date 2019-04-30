---
title: CAnimationTimerEventHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
ms.openlocfilehash: e5e6b0a22d438f9c26318129e2d04df96d386cda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391337"
---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler 클래스

타이밍 이벤트가 발생할 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|인스턴스를 만들고 `CAnimationTimerEventHandler` 콜백 합니다.|
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|애니메이션 업데이트가 완료 된 후 발생 하는 이벤트를 처리 합니다. ( `CUIAnimationTimerEventHandlerBase::OnPostUpdate`을 재정의합니다.)|
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|애니메이션 업데이트가 시작 되기 전에 발생 하는 이벤트를 처리 합니다. ( `CUIAnimationTimerEventHandlerBase::OnPreUpdate`을 재정의합니다.)|
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|애니메이션 렌더링 프레임 속도가 최소 원하는 프레임 속도 아래로 떨어질 때 발생 하는 이벤트를 처리 합니다. ( `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`을 재정의합니다.)|
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|이벤트를 라우팅하도록 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기 생성 되어 IUIAnimationTimer::SetTimerEventHandler CAnimationController::EnableAnimationTimerEventHandler를 호출할 때 전달 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="createinstance"></a>  CAnimationTimerEventHandler::CreateInstance

CAnimationTimerEventHandler 콜백 인스턴스를 만듭니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>매개 변수

*pAnimationController*<br/>
이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.

*ppTimerEventHandler*

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="onpostupdate"></a>  CAnimationTimerEventHandler::OnPostUpdate

애니메이션 업데이트가 완료 된 후 발생 하는 이벤트를 처리 합니다.

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.

##  <a name="onpreupdate"></a>  CAnimationTimerEventHandler::OnPreUpdate

애니메이션 업데이트가 시작 되기 전에 발생 하는 이벤트를 처리 합니다.

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.

##  <a name="onrenderingtooslow"></a>  CAnimationTimerEventHandler::OnRenderingTooSlow

애니메이션 렌더링 프레임 속도가 최소 원하는 프레임 속도 아래로 떨어질 때 발생 하는 이벤트를 처리 합니다.

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>매개 변수

*fps*

### <a name="return-value"></a>반환 값

메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.

##  <a name="setanimationcontroller"></a>  CAnimationTimerEventHandler::SetAnimationController

이벤트를 라우팅하도록 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*pAnimationController*<br/>
이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
