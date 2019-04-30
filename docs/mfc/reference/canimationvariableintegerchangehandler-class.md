---
title: CAnimationVariableIntegerChangeHandler 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler [MFC], CAnimationVariableIntegerChangeHandler
- CAnimationVariableIntegerChangeHandler [MFC], CreateInstance
- CAnimationVariableIntegerChangeHandler [MFC], OnIntegerValueChanged
- CAnimationVariableIntegerChangeHandler [MFC], SetAnimationController
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
ms.openlocfilehash: e1c3dc080c23ba4ac05539674047a66059ce52d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338183"
---
# <a name="canimationvariableintegerchangehandler-class"></a>CAnimationVariableIntegerChangeHandler 클래스

애니메이션 변수 값이 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|`CAnimationVariableIntegerChangeHandler` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CreateInstance](#createinstance)|인스턴스를 만들고 `CAnimationVariableIntegerChangeHandler` 콜백 합니다.|
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](#onintegervaluechanged)|애니메이션 변수 값이 변경 될 때 호출 합니다. ( `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`을 재정의합니다.)|
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](#setanimationcontroller)|이벤트를 라우팅하도록 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.|

## <a name="remarks"></a>설명

이 이벤트 처리기 생성 되어 CAnimationVariable::EnableIntegerValueChangedEvent 또는 (그러면 CAnimationBaseObject::EnableIntegerValueChangedEvent을 호출할 때 IUIAnimationVariable::SetVariableIntegerChangeHandler 메서드에 전달 이 이벤트는 애니메이션 개체에 캡슐화 하는 모든 애니메이션 변수에 대 한).

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[MFC 클래스](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="canimationvariableintegerchangehandler"></a>  CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler

CAnimationVariableIntegerChangeHandler 개체를 생성합니다.

```
CAnimationVariableIntegerChangeHandler ();
```

##  <a name="createinstance"></a>  CAnimationVariableIntegerChangeHandler::CreateInstance

CAnimationVariableIntegerChangeHandler 콜백 인스턴스를 만듭니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>매개 변수

*pAnimationController*<br/>
이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.

*ppHandler*

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="onintegervaluechanged"></a>  CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged

애니메이션 변수 값이 변경 될 때 호출 합니다.

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>매개 변수

*storyboard*<br/>
변수의 애니메이션을 적용 하는 스토리 보드입니다.

*variable*<br/>
업데이트 된 애니메이션 변수입니다.

*newValue*<br/>
새 반올림된 한 값입니다.

*previousValue*<br/>
이전 반올림된 한 값입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL입니다.

##  <a name="setanimationcontroller"></a>  CAnimationVariableIntegerChangeHandler::SetAnimationController

이벤트를 라우팅하도록 애니메이션 컨트롤러에 대 한 포인터를 저장합니다.

```
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>매개 변수

*pAnimationController*<br/>
이벤트를 수신 하는 애니메이션 컨트롤러에 대 한 포인터입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
