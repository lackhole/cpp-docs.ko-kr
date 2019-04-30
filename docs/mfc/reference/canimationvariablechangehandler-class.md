---
title: CAnimationVariableChangeHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 92189ce5ea76811496d4462aa4254bbd03ebb219
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338144"
---
# <a name="canimationvariablechangehandler-class"></a>CAnimationVariableChangeHandler 클래스

애니메이션 변수 값이 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|`CAnimationVariableChangeHandler` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|인스턴스를 만들고 `CAnimationVariableChangeHandler` 개체입니다.|
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|애니메이션 변수 값이 변경 될 때 호출 합니다. ( `CUIAnimationVariableChangeHandlerBase::OnValueChanged`을 재정의합니다.)|
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|이벤트를 라우팅하도록 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기 생성 되어 전달할 `IUIAnimationVariable::SetVariableChangeHandler` 메서드를 호출할 때 `CAnimationVariable::EnableValueChangedEvent` 또는 `CAnimationBaseObject::EnableValueChangedEvent` (그러면 애니메이션 개체에 캡슐화 하는 모든 애니메이션 변수에 대 한이 이벤트).

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="onvaluechanged"></a>  CAnimationVariableChangeHandler::OnValueChanged

애니메이션 변수 값이 변경 될 때 호출 합니다.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>매개 변수

*storyboard*<br/>
변수의 애니메이션을 적용 하는 스토리 보드입니다.

*variable*<br/>
업데이트 된 애니메이션 변수입니다.

*newValue*<br/>
새 값입니다.

*previousValue*<br/>
이전 값입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="setanimationcontroller"></a>  CAnimationVariableChangeHandler::SetAnimationController

이벤트를 라우팅하도록 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*pAnimationController*<br/>
이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
