---
title: CAnimationRect 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
ms.openlocfilehash: 84c4cf92894a9ece2021417445c9d7ab94ee6bdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378182"
---
# <a name="canimationrect-class"></a>CAnimationRect 클래스

면에 애니메이션을 적용할 수 있는 사각형 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAnimationRect::CAnimationRect](#canimationrect)|오버로드됨. 애니메이션 rect 개체를 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAnimationRect::AddTransition](#addtransition)|왼쪽, 위쪽, 오른쪽 및 아래쪽 좌표에 대 한 변환을 추가합니다.|
|[CAnimationRect::GetBottom](#getbottom)|CAnimationVariable 아래쪽 좌표를 나타내는에 대 한 액세스를 제공 합니다.|
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|사각형의 경계에 대 한 기본 값을 반환합니다.|
|[CAnimationRect::GetLeft](#getleft)|CAnimationVariable 왼쪽된 좌표를 나타내는에 대 한 액세스를 제공 합니다.|
|[CAnimationRect::GetRight](#getright)|CAnimationVariable 오른쪽 좌표를 나타내는에 대 한 액세스를 제공 합니다.|
|[CAnimationRect::GetTop](#gettop)|CAnimationVariable 위쪽 좌표를 나타내는에 대 한 액세스를 제공 합니다.|
|[CAnimationRect::GetValue](#getvalue)|현재 값을 반환합니다.|
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|기본값을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|캡슐화 된 애니메이션 변수를 목록에 넣습니다. (재정의 [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[RECT CAnimationRect::operator](#operator_rect)|사각형을 CAnimationRect 변환|
|[CAnimationRect::operator=](#operator_eq)|CAnimationRect에 영역을 할당합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|사각형에 고정 크기 여부를 지정 합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|캡슐화 된 애니메이션 나타내는 변수는 아래 애니메이션 사각형의 경계입니다.|
|[CAnimationRect::m_leftValue](#m_leftvalue)|왼쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.|
|[CAnimationRect::m_rightValue](#m_rightvalue)|오른쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.|
|[CAnimationRect::m_szInitial](#m_szinitial)|애니메이션 사각형의 초기 크기를 지정 합니다.|
|[CAnimationRect::m_topValue](#m_topvalue)|위쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.|

## <a name="remarks"></a>설명

CAnimationRect 클래스는 4 개의 CAnimationVariable 개체를 캡슐화 하 고 사각형 응용 프로그램에 나타낼 수 있습니다. 응용 프로그램에서이 클래스를 사용 하려면 방금이 클래스의 개체를 인스턴스화할 CAnimationController::AddAnimationObject를 사용 하 여 애니메이션 컨트롤러를 추가 및 왼쪽, 오른쪽 위쪽 및 아래쪽 좌표에 적용할 각 전환에 대 한 AddTransition 호출 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationRect::AddTransition

왼쪽, 위쪽, 오른쪽 및 아래쪽 좌표에 대 한 변환을 추가합니다.

```
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>매개 변수

*pLeftTransition*<br/>
왼쪽에 대 한 전환을 지정합니다.

*pTopTransition*<br/>
위쪽에 대 한 전환을 지정합니다.

*pRightTransition*<br/>
오른쪽에 대 한 전환을 지정합니다.

*pBottomTransition*<br/>
아래쪽 면에 대 한 전환을 지정합니다.

### <a name="remarks"></a>설명

각 사각형 측면에 대 한 변수 애니메이션에 적용할 변환의 내부 목록에 지정된 된 전환을 추가 하려면이 함수를 호출 합니다. 전환에 추가 하지 즉시 적용 되며 내부 목록에 저장. 전환 (특정 값에 대 한 스토리 보드에 추가) 적용 됩니다 CAnimationController::AnimateGroup를 호출 하는 경우. 전환을 사각형 측면 중 하나를 적용할 필요가 없으면 NULL을 전달할 수 있습니다.

##  <a name="canimationrect"></a>  CAnimationRect::CAnimationRect

CAnimationRect 개체를 생성합니다.

```
CAnimationRect();

CAnimationRect(
    const CRect& rect,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    const CPoint& pt,
    const CSize& sz,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    int nLeft,
    int nTop,
    int nRight,
    int nBottom,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
기본 사각형을 지정합니다.

*nGroupID*<br/>
그룹 ID를 지정 합니다.

*nObjectID*<br/>
개체 ID를 지정합니다.

*dwUserData*<br/>
사용자 정의 데이터를 지정합니다.

*pt*<br/>
왼쪽 위 모퉁이의 좌표입니다.

*sz*<br/>
사각형의 크기입니다.

*nLeft*<br/>
왼쪽된 경계에 대 한 좌표를 지정합니다.

*nTop*<br/>
위쪽 경계에 대 한 좌표를 지정 합니다.

*nRight*<br/>
오른쪽 경계에 대 한 좌표를 지정합니다.

*nBottom*<br/>
아래쪽 경계에 대 한 좌표를 지정 합니다.

### <a name="remarks"></a>설명

개체에 대 한 기본값 왼쪽, 위쪽, 오른쪽 및 아래쪽, 개체 ID 및 0으로 설정할 수 있는 그룹 ID를 사용 하 여 생성 됩니다. 이러한 SetDefaultValue 및 SetID 사용 하 여 런타임 시 나중에 변경할 수 있습니다.

##  <a name="getanimationvariablelist"></a>  CAnimationRect::GetAnimationVariableList

캡슐화 된 애니메이션 변수를 목록에 넣습니다.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>매개 변수

*lst*<br/>
함수는 반환 될 때 사각형의 좌표를 나타내는 네 CAnimationVariable 개체에 대 한 포인터를 포함 합니다.

##  <a name="getbottom"></a>  CAnimationRect::GetBottom

CAnimationVariable 아래쪽 좌표를 나타내는에 대 한 액세스를 제공 합니다.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>반환 값

캡슐화 된 CAnimationVariable 아래쪽 좌표를 나타내는 참조입니다.

### <a name="remarks"></a>설명

아래쪽 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.

##  <a name="getdefaultvalue"></a>  CAnimationRect::GetDefaultValue

사각형의 경계에 대 한 기본 값을 반환합니다.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>반환 값

왼쪽, 오른쪽, 위쪽 및 아래쪽에 대 한 기본값을 포함 하는 CRect 값입니다.

### <a name="remarks"></a>설명

생성자 또는 SetDefaultValue 하 여 이전에 설정 된 기본값을 검색 하려면이 함수를 호출 합니다.

##  <a name="getleft"></a>  CAnimationRect::GetLeft

CAnimationVariable 왼쪽된 좌표를 나타내는에 대 한 액세스를 제공 합니다.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>반환 값

캡슐화 된 CAnimationVariable 왼쪽된 좌표를 나타내는 참조입니다.

### <a name="remarks"></a>설명

왼쪽된 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.

##  <a name="getright"></a>  CAnimationRect::GetRight

CAnimationVariable 오른쪽 좌표를 나타내는에 대 한 액세스를 제공 합니다.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>반환 값

캡슐화 된 CAnimationVariable 오른쪽 좌표를 나타내는 참조입니다.

### <a name="remarks"></a>설명

오른쪽 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.

##  <a name="gettop"></a>  CAnimationRect::GetTop

CAnimationVariable 위쪽 좌표를 나타내는에 대 한 액세스를 제공 합니다.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>반환 값

캡슐화 된 CAnimationVariable 위쪽 좌표를 나타내는 참조입니다.

### <a name="remarks"></a>설명

위쪽 좌표를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.

##  <a name="getvalue"></a>  CAnimationRect::GetValue

현재 값을 반환합니다.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
출력입니다. 이 메서드가 반환 될 때 현재 값을 포함 합니다.

### <a name="return-value"></a>반환 값

TRUE 이면 현재 값을 성공적으로 검색 합니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

애니메이션 사각형의 현재 값을 검색 하려면이 함수를 호출 합니다. 이 메서드가 실패 하면 또는 기본 COM 개체 왼쪽 위쪽, 오른쪽 및 아래쪽 초기화 되지 않은 경우 rect SetDefaultValue 또는 생성자에서 이전에 설정 된 기본값을 포함 합니다.

##  <a name="m_bfixedsize"></a>  CAnimationRect::m_bFixedSize

사각형에 고정 크기 여부를 지정 합니다.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>설명

이 멤버가 true 이면 사각형의 크기는 고정 오른쪽 및 아래쪽 값에는 왼쪽 위 모퉁이 고정된 크기에 따라 이동 될 때마다 다시 계산 됩니다 하는 것입니다. 이 값을 쉽게 화면 주위로 사각형을 이동 하려면 TRUE로 설정 합니다. 이 경우 오른쪽 아래 좌표에 적용 되는 전환 무시 됩니다. 크기는 개체를 생성 하거나 SetDefaultValue를 호출 하는 경우 내부적으로 저장 됩니다. 이 멤버는 기본적으로 FALSE로 설정 됩니다.

##  <a name="m_bottomvalue"></a>  CAnimationRect::m_bottomValue

캡슐화 된 애니메이션 나타내는 변수는 아래 애니메이션 사각형의 경계입니다.

```
CAnimationVariable m_bottomValue;
```

##  <a name="m_leftvalue"></a>  CAnimationRect::m_leftValue

왼쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.

```
CAnimationVariable m_leftValue;
```

##  <a name="m_rightvalue"></a>  CAnimationRect::m_rightValue

오른쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.

```
CAnimationVariable m_rightValue;
```

##  <a name="m_szinitial"></a>  CAnimationRect::m_szInitial

애니메이션 사각형의 초기 크기를 지정 합니다.

```
CSize m_szInitial;
```

##  <a name="m_topvalue"></a>  CAnimationRect::m_topValue

위쪽을 나타내는 캡슐화 된 애니메이션 변수의 애니메이션 사각형의 경계입니다.

```
CAnimationVariable m_topValue;
```

##  <a name="operator_rect"></a>  CAnimationRect::operator RECT

사각형을 CAnimationRect 변환

```
operator RECT();
```

### <a name="return-value"></a>반환 값

사각형으로 애니메이션 사각형의 현재 값

### <a name="remarks"></a>설명

이 함수는 GetValue 내부적으로 호출합니다. Getvalue가 어떤 이유로 실패 하는 경우 반환 되는 RECT 모든 사각형 좌표에 대 한 기본 값이 포함 됩니다.

##  <a name="operator_eq"></a>  CAnimationRect::operator=

CAnimationRect에 영역을 할당합니다.

```
void operator=(const RECT& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
애니메이션 사각형의 새 값입니다.

### <a name="remarks"></a>설명

이 연산자가 생성 된 색의 구성 요소에 대 한 기본 COM 개체를 다시 SetDefaultValue 호출 되므로 애니메이션이 시작 되기 전에 것이 좋습니다. 이 애니메이션 개체 (ValueChanged 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.

##  <a name="setdefaultvalue"></a>  CAnimationRect::SetDefaultValue

기본값을 설정합니다.

```
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
왼쪽, 위쪽, 오른쪽 및 아래쪽에 대 한 새 기본값을 지정합니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 애니메이션 개체에 기본값을 설정 합니다. 이 메서드는 사각형의 경계에 기본값을 할당 합니다. 이 또한 만들지 않은 경우 기본 COM 개체를 다시 합니다. 이 애니메이션 개체 (ValueChanged 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
