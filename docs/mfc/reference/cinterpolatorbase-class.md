---
title: CInterpolatorBase 클래스
ms.date: 11/04/2016
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
ms.openlocfilehash: 379aa5607e459ad8acfd99c5899315afb84ac4a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392663"
---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase 클래스

애니메이션 API에서 애니메이션 변수의 새 값을 계산해야 할 때 호출하는 콜백을 구현합니다.

## <a name="syntax"></a>구문

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|생성 된 `CInterpolatorBase` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CInterpolatorBase::CreateInstance](#createinstance)|인스턴스를 만들고 `CInterpolatorBase` 이벤트를 처리 하는 사용자 지정 보간에 대 한 포인터를 저장 합니다.|
|[CInterpolatorBase::GetDependencies](#getdependencies)|보간의 종속성을 가져옵니다. ( `CUIAnimationInterpolatorBase::GetDependencies`을 재정의합니다.)|
|[CInterpolatorBase::GetDuration](#getduration)|보간의 기간을 가져옵니다. ( `CUIAnimationInterpolatorBase::GetDuration`을 재정의합니다.)|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|보간 잠재 고객을 최종 값을 가져옵니다. ( `CUIAnimationInterpolatorBase::GetFinalValue`을 재정의합니다.)|
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|지정된 된 오프셋 위치에서 값을 보간합니다 (재정의 `CUIAnimationInterpolatorBase::InterpolateValue`.)|
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|지정된 된 오프셋 위치에서 속도 보간합니다 (재정의 `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|이벤트를 처리 하는 사용자 지정 보간에 대 한 포인터를 저장 합니다.|
|[CInterpolatorBase::SetDuration](#setduration)|보간의 기간 설정 (재정의 `CUIAnimationInterpolatorBase::SetDuration`.)|
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|보간의 초기 값 및 개발 속도 설정합니다. ( `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`을 재정의합니다.)|

## <a name="remarks"></a>설명

이 처리기가 생성 하 고 전달할 `IUIAnimationTransitionFactory::CreateTransition` 경우는 `CCustomTransition` 개체를 애니메이션 초기화 프로세스의 일부로 만들어지고 (에 의해 시작 `CAnimationController::AnimateGroup`). 일반적으로이 클래스를 직접 사용할 필요가 없습니다, 모든 이벤트를 라우트만 `CCustomInterpolator`-파생 클래스에서 해당 포인터의 생성자에 전달 됩니다 `CCustomTransition`합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="cinterpolatorbase"></a>  CInterpolatorBase::CInterpolatorBase

CInterpolatorBase 개체를 생성합니다.

```
CInterpolatorBase();
```

##  <a name="createinstance"></a>  CInterpolatorBase::CreateInstance

CInterpolatorBase의 인스턴스를 만들어 이벤트를 처리 하는 사용자 지정 보간에 대 한 포인터를 저장 합니다.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>매개 변수

*pInterpolator*<br/>
사용자 지정 보간에 대 한 포인터입니다.

*ppHandler*<br/>
출력입니다. 함수가 반환할 때 CInterpolatorBase의 인스턴스에 대 한 포인터를 포함 합니다.

### <a name="return-value"></a>반환 값

##  <a name="getdependencies"></a>  CInterpolatorBase::GetDependencies

보간의 종속성을 가져옵니다.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>매개 변수

*initialValueDependencies*<br/>
출력입니다. 초기 값에 종속 된 보간의 측면 SetInitialValueAndVelocity에 전달 합니다.

*initialVelocityDependencies*<br/>
출력입니다. 보간의 초기 속도에 종속 된 측면 SetInitialValueAndVelocity에 전달 합니다.

*durationDependencies*<br/>
출력입니다. 기간에 종속 된 보간의 측면 SetDuration에 전달 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator을 설정 하지 않으면 또는 사용자 지정 구현을 GetDependencies 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.

##  <a name="getduration"></a>  CInterpolatorBase::GetDuration

보간의 기간을 가져옵니다.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
출력입니다. 기간 (초)에서 전환입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator을 설정 하지 않으면 또는 사용자 지정 구현을 GetDuration 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.

##  <a name="getfinalvalue"></a>  CInterpolatorBase::GetFinalValue

보간 잠재 고객을 최종 값을 가져옵니다.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>매개 변수

*값*<br/>
출력입니다. 전환의 끝에 변수의 최종 값입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator을 설정 하지 않으면 또는 사용자 지정 구현을 GetFinalValue 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.

##  <a name="interpolatevalue"></a>  CInterpolatorBase::InterpolateValue

지정된 된 오프셋 위치에서 값을 보간합니다.

```
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* value);
```

### <a name="parameters"></a>매개 변수

*offset*<br/>
전환의 시작 오프셋입니다. 오프셋 보다 큰 또는 0 및 전환 기간 보다 작은 항상입니다. 전환 기간은 0 하는 경우에이 메서드가 호출 되지 않습니다.

*값*<br/>
출력입니다. 보간된 값입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator을 설정 하지 않으면 또는 사용자 지정 구현을 InterpolateValue 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.

##  <a name="interpolatevelocity"></a>  CInterpolatorBase::InterpolateVelocity

지정 된 오프셋 속도를 보간합니다.

```
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```

### <a name="parameters"></a>매개 변수

*offset*<br/>
전환의 시작 오프셋입니다. 오프셋은 항상 0 보다 크거나 전환 기간 보다 작거나 같으면 합니다. 전환 기간은 0 하는 경우에이 메서드가 호출 되지 않습니다.

*velocity*<br/>
출력입니다. 속도 변수의 오프셋입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator을 설정 하지 않으면 또는 사용자 지정 구현을 InterpolateVelocity 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.

##  <a name="setcustominterpolator"></a>  CInterpolatorBase::SetCustomInterpolator

이벤트를 처리 하는 사용자 지정 보간에 대 한 포인터를 저장 합니다.

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>매개 변수

*pInterpolator*<br/>
사용자 지정 보간에 대 한 포인터입니다.

##  <a name="setduration"></a>  CInterpolatorBase::SetDuration

보간의 기간 설정

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator을 설정 하지 않으면 또는 사용자 지정 구현을 SetDuration 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.

##  <a name="setinitialvalueandvelocity"></a>  CInterpolatorBase::SetInitialValueAndVelocity

보간의 초기 값 및 개발 속도 설정합니다.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue,
  __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>매개 변수

*initialValue*<br/>
전환의 시작 부분에 있는 변수의 값입니다.

*initialVelocity*<br/>
전환의 시작 부분에 있는 변수의 속도입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. CCustomInterpolator을 설정 하지 않으면 또는 사용자 지정 구현을 SetInitialValueAndVelocity 메서드에서 FALSE 반환 하는 경우에 E_FAIL을 반환 합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
