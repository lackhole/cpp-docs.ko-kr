---
title: CCubicTransition 클래스
ms.date: 11/04/2016
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
ms.openlocfilehash: f4d5898172c0544064fad82856e404f4fb12b561
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164009"
---
# <a name="ccubictransition-class"></a>CCubicTransition 클래스

3차원 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CCubicTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CCubicTransition::CCubicTransition](#ccubictransition)|전환 개체를 생성 하 고 해당 매개 변수를 초기화 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CCubicTransition::Create](#create)|캡슐화 된 전환 COM 개체를 만들려면 전환 라이브러리를 호출 합니다. (재정의 [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CCubicTransition::m_dblFinalValue](#m_dblfinalvalue)|전환의 끝에 있는 애니메이션 변수의 값입니다.|
|[CCubicTransition::m_dblFinalVelocity](#m_dblfinalvelocity)|전환의 끝에 있는 변수의 속도입니다.|
|[CCubicTransition::m_duration](#m_duration)|전환 기간입니다.|

## <a name="remarks"></a>설명

입방 형 3 전환 중 애니메이션 변수의 변경 초기 값에서 지정 된 마지막 값 지정 된 속도로 종료 전환 기간 동안 됩니다. 모든 전환을 자동으로 취소 하므로 것이 좋습니다에 할당 된 새 연산자를 사용 합니다. 캡슐화 된 IUIAnimationTransition COM 개체는 NULL까지 CAnimationController::AnimateGroup에서 생성 됩니다. 이 COM 개체의 생성에 영향을 주지 않습니다 후 멤버 변수를 변경 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCubicTransition`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="ccubictransition"></a>  CCubicTransition::CCubicTransition

전환 개체를 생성 하 고 해당 매개 변수를 초기화 합니다.

```
CCubicTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE finalVelocity);
```

### <a name="parameters"></a>매개 변수

*duration*<br/>
전환 기간입니다.

*finalValue*<br/>
전환의 끝에 있는 애니메이션 변수의 값입니다.

*finalVelocity*<br/>
전환의 끝에 있는 변수의 속도입니다.

##  <a name="create"></a>  CCubicTransition::Create

캡슐화 된 전환 COM 개체를 만들려면 전환 라이브러리를 호출 합니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>매개 변수

*pLibrary*<br/>
에 대 한 포인터를 [IUIAnimationTransitionLibrary 인터페이스](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), 표준 전환의 라이브러리를 정의 하는 합니다.

### <a name="return-value"></a>반환 값

전환; 성공적으로 만들어졌을 경우 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="m_dblfinalvalue"></a>  CCubicTransition::m_dblFinalValue

전환의 끝에 있는 애니메이션 변수의 값입니다.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblfinalvelocity"></a>  CCubicTransition::m_dblFinalVelocity

전환의 끝에 있는 변수의 속도입니다.

```
DOUBLE m_dblFinalVelocity;
```

##  <a name="m_duration"></a>  CCubicTransition::m_duration

전환 기간입니다.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
