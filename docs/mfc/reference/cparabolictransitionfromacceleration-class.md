---
title: CParabolicTransitionFromAcceleration 클래스
ms.date: 11/04/2016
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
ms.openlocfilehash: 3d4a073a0fd74f7564d9183779acfd66b41a9540
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372974"
---
# <a name="cparabolictransitionfromacceleration-class"></a>CParabolicTransitionFromAcceleration 클래스

포물선 가속 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CParabolicTransitionFromAcceleration : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|포물선 가속 전환을 생성 하 고 지정 된 매개 변수를 사용 하 여 초기화 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::Create](#create)|캡슐화 된 전환 COM 개체를 만들려면 전환 라이브러리를 호출 합니다. (재정의 [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|전환 하는 동안 애니메이션 변수의 가속화 합니다.|
|[CParabolicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|전환의 끝에 있는 애니메이션 변수의 값입니다.|
|[CParabolicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|전환의 끝에 있는 애니메이션 변수의 속도입니다.|

## <a name="remarks"></a>설명

포물선 가속 전환 하는 동안 애니메이션 변수의 값 초기 값에서 지정 된 속도로 종료 최종 값으로 변경 합니다. 변수의 가속 비율을 지정 하 여 최종 값에 도달 하는 방법을 신속 하 게 제어할 수 있습니다. 모든 전환을 자동으로 취소 하므로 것이 좋습니다에 할당 된 새 연산자를 사용 합니다. 캡슐화 된 IUIAnimationTransition COM 개체는 NULL까지 CAnimationController::AnimateGroup에서 생성 됩니다. 이 COM 개체의 생성에 영향을 주지 않습니다 후 멤버 변수를 변경 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="cparabolictransitionfromacceleration"></a>  CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration

포물선 가속 전환을 생성 하 고 지정 된 매개 변수를 사용 하 여 초기화 합니다.

```
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,
    DOUBLE dblFinalVelocity,
    DOUBLE dblAcceleration);
```

### <a name="parameters"></a>매개 변수

*dblFinalValue*<br/>
전환의 끝에 있는 애니메이션 변수의 값입니다.

*dblFinalVelocity*<br/>
전환의 끝에 있는 애니메이션 변수의 속도입니다.

*dblAcceleration*<br/>
전환 하는 동안 애니메이션 변수의 가속화 합니다.

##  <a name="create"></a>  CParabolicTransitionFromAcceleration::Create

캡슐화 된 전환 COM 개체를 만들려면 전환 라이브러리를 호출 합니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* /* not used */);
```

### <a name="parameters"></a>매개 변수

*pLibrary*<br/>
표준 전환을 만들기를 담당 하는 전환 라이브러리에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

전환; 성공적으로 만들어졌을 경우 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="m_dblacceleration"></a>  CParabolicTransitionFromAcceleration::m_dblAcceleration

전환 하는 동안 애니메이션 변수의 가속화 합니다.

```
DOUBLE m_dblAcceleration;
```

##  <a name="m_dblfinalvalue"></a>  CParabolicTransitionFromAcceleration::m_dblFinalValue

전환의 끝에 있는 애니메이션 변수의 값입니다.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblfinalvelocity"></a>  CParabolicTransitionFromAcceleration::m_dblFinalVelocity

전환의 끝에 있는 애니메이션 변수의 속도입니다.

```
DOUBLE m_dblFinalVelocity;
```

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
