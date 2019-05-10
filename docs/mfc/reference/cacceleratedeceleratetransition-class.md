---
title: Cacceleratedeceleratetransition 클래스 클래스
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: dbebe794ba76ae4abd3d1e3ea6bc8ee31bc3007f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151203"
---
# <a name="cacceleratedeceleratetransition-class"></a>Cacceleratedeceleratetransition 클래스 클래스

가속-감속 전환을 구현합니다.

## <a name="syntax"></a>구문

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|전환 개체를 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAccelerateDecelerateTransition::Create](#create)|캡슐화 된 전환 COM 개체를 만들려면 전환 라이브러리를 호출 합니다. (재정의 [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|지속 시간을 가속화 하는 데 걸린 시간의 비율입니다.|
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|기간으로 감속 하는 데 걸린 시간의 비율입니다.|
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|전환 기간입니다.|
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|전환의 끝에 있는 애니메이션 변수의 값입니다.|

## <a name="remarks"></a>설명

중 가속-감속 전환을, 애니메이션 변수의 속도 다음 지정된 된 값에서 끝나는 전환 기간 동안 느려집니다. 변수의 가속화 하 고 다른 가속 및 감속을 지정 하 여 독립적으로 감속 하는 방법을 신속 하 게 제어할 수 있습니다. 초기 속도 0 이면 가속 비율은 가속화; 변수는 소비 하는 기간의 비율 마찬가지로 감속 비율을 사용 하 여입니다. 초기 속도 0이 아닌 경우 0 및 전환의 끝에 도달 하는 속도 간격의 소수 부분 것입니다. 가속 비율 및 감속 비율 1.0 최대 합계를 계산 해야 합니다. 모든 전환을 자동으로 취소 하므로 것이 좋습니다에 할당 된 새 연산자를 사용 합니다. 캡슐화 된 IUIAnimationTransition COM 개체는 NULL까지 CAnimationController::AnimateGroup에서 생성 됩니다. 이 COM 개체의 생성에 영향을 주지 않습니다 후 멤버 변수를 변경 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="cacceleratedeceleratetransition"></a>  CAccelerateDecelerateTransition::CAccelerateDecelerateTransition

전환 개체를 생성 합니다.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

*finalValue*<br/>
전환의 끝에 있는 애니메이션 변수의 값입니다.

*accelerationRatio*<br/>
지속 시간을 가속화 하는 데 걸린 시간의 비율입니다.

*decelerationRatio*<br/>
기간으로 감속 하는 데 걸린 시간의 비율입니다.

##  <a name="create"></a>  CAccelerateDecelerateTransition::Create

캡슐화 된 전환 COM 개체를 만들려면 전환 라이브러리를 호출 합니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>매개 변수

*pLibrary*<br/>
에 대 한 포인터를 [IUIAnimationTransitionLibrary 인터페이스](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), 표준 전환의 라이브러리를 정의 하는 합니다.

### <a name="return-value"></a>반환 값

전환; 성공적으로 만들어졌을 경우 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="m_accelerationratio"></a>  CAccelerateDecelerateTransition::m_accelerationRatio

지속 시간을 가속화 하는 데 걸린 시간의 비율입니다.

```
DOUBLE m_accelerationRatio;
```

##  <a name="m_decelerationratio"></a>  CAccelerateDecelerateTransition::m_decelerationRatio

기간으로 감속 하는 데 걸린 시간의 비율입니다.

```
DOUBLE m_decelerationRatio;
```

##  <a name="m_duration"></a>  CAccelerateDecelerateTransition::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CAccelerateDecelerateTransition::m_finalValue

전환의 끝에 있는 애니메이션 변수의 값입니다.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
