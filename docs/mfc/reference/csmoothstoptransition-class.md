---
title: CSmoothStopTransition 클래스
ms.date: 11/04/2016
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
ms.openlocfilehash: 89496c1b867d6fbb498f56271de7b45afef7edc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323884"
---
# <a name="csmoothstoptransition-class"></a>CSmoothStopTransition 클래스

부드러운 중지 전환을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSmoothStopTransition::CSmoothStopTransition](#csmoothstoptransition)|부드러운 중지 전환을 생성 하 고 해당 최대 기간 및 최종 값을 초기화 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSmoothStopTransition::Create](#create)|캡슐화 된 전환 COM 개체를 만들려면 전환 라이브러리를 호출 합니다. (재정의 [CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CSmoothStopTransition::m_dblFinalValue](#m_dblfinalvalue)|전환의 끝에 있는 애니메이션 변수의 값입니다.|
|[CSmoothStopTransition::m_maximumDuration](#m_maximumduration)|전환의 최대 기간입니다.|

## <a name="remarks"></a>설명

부드러운 중지 전환을 최종 값을 지정된 방법과 속도 0에 도달 하는 대로 느려집니다. 전환 기간 초기 속도, 초기 및 최종 값 및 지정 된 최대 시간 차이 의해 결정 됩니다. 포물선 원호 한 개로 구성 된 솔루션이 없는 경우이 메서드는 3 차원 전환을 만듭니다. 모든 전환을 자동으로 취소 하므로 것이 좋습니다에 할당 된 새 연산자를 사용 합니다. 캡슐화 된 IUIAnimationTransition COM 개체는 NULL까지 CAnimationController::AnimateGroup에서 생성 됩니다. 이 COM 개체의 생성에 영향을 주지 않습니다 후 멤버 변수를 변경 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="create"></a>  CSmoothStopTransition::Create

캡슐화 된 전환 COM 개체를 만들려면 전환 라이브러리를 호출 합니다.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>매개 변수

*pLibrary*<br/>
표준 전환을 만들기를 담당 하는 전환 라이브러리에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

전환; 성공적으로 만들어졌을 경우 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="csmoothstoptransition"></a>  CSmoothStopTransition::CSmoothStopTransition

부드러운 중지 전환을 생성 하 고 해당 최대 기간 및 최종 값을 초기화 합니다.

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>매개 변수

*maximumDuration*<br/>
전환의 최대 기간입니다.

*dblFinalValue*<br/>
전환의 끝에 있는 애니메이션 변수의 값입니다.

##  <a name="m_dblfinalvalue"></a>  CSmoothStopTransition::m_dblFinalValue

전환의 끝에 있는 애니메이션 변수의 값입니다.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_maximumduration"></a>  CSmoothStopTransition::m_maximumDuration

전환의 최대 기간입니다.

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
