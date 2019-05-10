---
title: CCustomInterpolator 클래스
ms.date: 11/04/2016
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
ms.openlocfilehash: 8d3f2ed95cfb9e7e885713252171c98834ae5c0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164139"
---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator 클래스

기본 보간자를 구현합니다.

## <a name="syntax"></a>구문

```
class CCustomInterpolator;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|오버로드됨. 보간 사용자 지정 개체를 생성 하 고 기간 및 지정한 값으로 속도 초기화 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CCustomInterpolator::GetDependencies](#getdependencies)|보간의 종속성을 가져옵니다.|
|[CCustomInterpolator::GetDuration](#getduration)|보간의 기간을 가져옵니다.|
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|보간 잠재 고객을 최종 값을 가져옵니다.|
|[CCustomInterpolator::Init](#init)|기간 및 최종 값을 초기화합니다.|
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|지정 된 오프셋 값을 보간합니다.|
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|지정 된 오프셋 속도를 보간합니다.|
|[CCustomInterpolator::SetDuration](#setduration)|보간의 기간을 설정합니다.|
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|보간의 초기 값 및 개발 속도 설정합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|보간된 값입니다.|
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|보간된 속도입니다.|
|[CCustomInterpolator::m_duration](#m_duration)|전환 기간입니다.|
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|전환의 끝에 변수의 최종 값입니다.|
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|전환의 시작 부분에 있는 변수의 값입니다.|
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|전환의 시작 부분에 있는 변수의 속도입니다.|

## <a name="remarks"></a>설명

CCustomInterpolator에서 클래스를 파생 하 고 보간 사용자 지정 알고리즘을 구현 하기 위해 필요한 모든 메서드를 재정의 합니다. 이 클래스에 대 한 포인터 CCustomTransition를 매개 변수로 전달 되어야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CCustomInterpolator`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="ccustominterpolator"></a>  CCustomInterpolator::CCustomInterpolator

보간 사용자 지정 개체를 생성 하 고 기본값은 0에 있는 모든 값을 설정 합니다.

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

*finalValue*

### <a name="remarks"></a>설명

기간 및 코드에서 나중에 최종 값을 초기화 하려면 CCustomInterpolator::Init를 사용 합니다.

##  <a name="getdependencies"></a>  CCustomInterpolator::GetDependencies

보간의 종속성을 가져옵니다.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>매개 변수

*initialValueDependencies*<br/>
출력입니다. 초기 값에 종속 된 보간의 측면 SetInitialValueAndVelocity에 전달 합니다.

*initialVelocityDependencies*<br/>
출력입니다. 보간의 초기 속도에 종속 된 측면 SetInitialValueAndVelocity에 전달 합니다.

*durationDependencies*<br/>
출력입니다. 기간에 종속 된 보간의 측면 SetDuration에 전달 합니다.

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다. FALSE 반환 재정의 된 구현에서 이벤트를 실패 하도록 하려는 경우.

##  <a name="getduration"></a>  CCustomInterpolator::GetDuration

보간의 기간을 가져옵니다.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
출력입니다. 기간 (초)에서 전환입니다.

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다. FALSE 반환 재정의 된 구현에서 이벤트를 실패 하도록 하려는 경우.

##  <a name="getfinalvalue"></a>  CCustomInterpolator::GetFinalValue

보간 잠재 고객을 최종 값을 가져옵니다.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>매개 변수

*값*<br/>
출력입니다. 전환의 끝에 변수의 최종 값입니다.

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다. FALSE 반환 재정의 된 구현에서 이벤트를 실패 하도록 하려는 경우.

##  <a name="init"></a>  CCustomInterpolator::Init

기간 및 최종 값을 초기화합니다.

```
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

*finalValue*<br/>
전환의 끝에 변수의 최종 값입니다.

##  <a name="interpolatevalue"></a>  CCustomInterpolator::InterpolateValue

지정 된 오프셋 값을 보간합니다.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>매개 변수

*값*<br/>
출력입니다. 보간된 값입니다.

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다. FALSE 반환 재정의 된 구현에서 이벤트를 실패 하도록 하려는 경우.

##  <a name="interpolatevelocity"></a>  CCustomInterpolator::InterpolateVelocity

지정 된 오프셋 속도를 보간합니다.

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>매개 변수

*velocity*<br/>
출력입니다. 속도 변수의 오프셋입니다.

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다. FALSE 반환 재정의 된 구현에서 이벤트를 실패 하도록 하려는 경우.

##  <a name="m_currentvalue"></a>  CCustomInterpolator::m_currentValue

보간된 값입니다.

```
DOUBLE m_currentValue;
```

##  <a name="m_currentvelocity"></a>  CCustomInterpolator::m_currentVelocity

보간된 속도입니다.

```
DOUBLE m_currentVelocity;
```

##  <a name="m_duration"></a>  CCustomInterpolator::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CCustomInterpolator::m_finalValue

전환의 끝에 변수의 최종 값입니다.

```
DOUBLE m_finalValue;
```

##  <a name="m_initialvalue"></a>  CCustomInterpolator::m_initialValue

전환의 시작 부분에 있는 변수의 값입니다.

```
DOUBLE m_initialValue;
```

##  <a name="m_initialvelocity"></a>  CCustomInterpolator::m_initialVelocity

전환의 시작 부분에 있는 변수의 속도입니다.

```
DOUBLE m_initialVelocity;
```

##  <a name="setduration"></a>  CCustomInterpolator::SetDuration

보간의 기간을 설정합니다.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다. FALSE 반환 재정의 된 구현에서 이벤트를 실패 하도록 하려는 경우.

##  <a name="setinitialvalueandvelocity"></a>  CCustomInterpolator::SetInitialValueAndVelocity

보간의 초기 값 및 개발 속도 설정합니다.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>매개 변수

*initialValue*<br/>
전환의 시작 부분에 있는 변수의 값입니다.

*initialVelocity*<br/>
전환의 시작 부분에 있는 변수의 속도입니다.

### <a name="return-value"></a>반환 값

기본 구현에서는 항상 TRUE를 반환합니다. FALSE 반환 재정의 된 구현에서 이벤트를 실패 하도록 하려는 경우.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
