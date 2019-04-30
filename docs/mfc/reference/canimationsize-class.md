---
title: CAnimationSize 클래스
ms.date: 11/04/2016
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
ms.openlocfilehash: f52016afe39da900dca4847d29beccb97d829b60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325119"
---
# <a name="canimationsize-class"></a>CAnimationSize 클래스

차원에 애니메이션을 적용할 수 있는 크기 개체 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAnimationSize::CAnimationSize](#canimationsize)|오버로드됨. 애니메이션 크기 개체를 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAnimationSize::AddTransition](#addtransition)|너비와 높이 대 한 변환을 추가합니다.|
|[CAnimationSize::GetCX](#getcx)|CAnimationVariable 너비를 나타내는에 대 한 액세스를 제공 합니다.|
|[CAnimationSize::GetCY](#getcy)|CAnimationVariable 높이 나타내는에 대 한 액세스를 제공 합니다.|
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|너비와 높이 대 한 기본 값을 반환합니다.|
|[CAnimationSize::GetValue](#getvalue)|현재 값을 반환합니다.|
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|기본값을 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|캡슐화 된 애니메이션 변수를 목록에 넣습니다. (재정의 [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAnimationSize::operator CSize](#operator_csize)|CAnimationSize CSize를 변환합니다.|
|[CAnimationSize::operator=](#operator_eq)|CAnimationSize szSrc 할당합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAnimationSize::m_cxValue](#m_cxvalue)|캡슐화 된 애니메이션 변수 애니메이션 크기의 너비를 나타내는입니다.|
|[CAnimationSize::m_cyValue](#m_cyvalue)|캡슐화 된 애니메이션 변수 애니메이션 크기의 높이 나타내는입니다.|

## <a name="remarks"></a>설명

CAnimationSize 클래스는 두 CAnimationVariable 개체를 캡슐화 하 고 크기를 응용 프로그램에 나타낼 수 있습니다. 예를 들어,이 클래스의 두 크기에 애니메이션 효과를 사용할 수 있습니다 화면의 차원 개체 (사각형와 같은 컨트롤 등). 응용 프로그램에서이 클래스를 사용 하려면 방금이 클래스의 개체를 인스턴스화하고, CAnimationController::AddAnimationObject를 사용 하 여 애니메이션 컨트롤러를 추가 및 너비 및/또는 높이에 적용할 AddTransition 각 전환에 대 한 호출

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationSize::AddTransition

너비와 높이 대 한 변환을 추가합니다.

```
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>매개 변수

*pCXTransition*<br/>
너비에 대 한 전환에 대 한 포인터입니다.

*pCYTransition*<br/>
높이 대 한 전환에 대 한 포인터입니다.

### <a name="remarks"></a>설명

지정된 된 전환을 너비와 높이 대 한 변수 애니메이션에 적용할 변환의 내부 목록에 추가 하려면이 함수를 호출 합니다. 전환에 추가 하지 즉시 적용 되며 내부 목록에 저장. 전환 (특정 값에 대 한 스토리 보드에 추가) 적용 됩니다 CAnimationController::AnimateGroup를 호출 하는 경우. 전환을 차원 중 하나를 적용할 필요가 없으면 NULL을 전달할 수 있습니다.

##  <a name="canimationsize"></a>  CAnimationSize::CAnimationSize

애니메이션 크기 개체를 생성 합니다.

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>매개 변수

*szDefault*<br/>
기본 크기를 지정합니다.

*nGroupID*<br/>
그룹 ID를 지정 합니다.

*nObjectID*<br/>
개체 ID를 지정합니다.

*dwUserData*<br/>
사용자 정의 데이터를 지정합니다.

### <a name="remarks"></a>설명

너비, 높이 대 한 기본값을 사용 하 여 개체가 생성 될 개체 ID 및 그룹 ID를 0으로 설정 됩니다. 이러한 SetDefaultValue 및 SetID 사용 하 여 런타임 시 나중에 변경할 수 있습니다.

##  <a name="getanimationvariablelist"></a>  CAnimationSize::GetAnimationVariableList

캡슐화 된 애니메이션 변수를 목록에 넣습니다.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>매개 변수

*lst*<br/>
함수는 반환 될 때 너비와 높이 나타내는 두 CAnimationVariable 개체에 대 한 포인터를 포함 합니다.

##  <a name="getcx"></a>  CAnimationSize::GetCX

CAnimationVariable 너비를 나타내는에 대 한 액세스를 제공 합니다.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>반환 값

캡슐화 된 CAnimationVariable 너비를 나타내는 참조입니다.

### <a name="remarks"></a>설명

너비를 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.

##  <a name="getcy"></a>  CAnimationSize::GetCY

CAnimationVariable 높이 나타내는에 대 한 액세스를 제공 합니다.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>반환 값

캡슐화 된 CAnimationVariable 높이 나타내는 참조입니다.

### <a name="remarks"></a>설명

높이 나타내는 기본 CAnimationVariable에 대 한 직접 액세스를 가져오려면이 메서드를 호출할 수 있습니다.

##  <a name="getdefaultvalue"></a>  CAnimationSize::GetDefaultValue

너비와 높이 대 한 기본 값을 반환합니다.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>반환 값

기본 값을 포함 하는 CSize 개체입니다.

### <a name="remarks"></a>설명

생성자 또는 SetDefaultValue 하 여 이전에 설정 된 기본값을 검색 하려면이 함수를 호출 합니다.

##  <a name="getvalue"></a>  CAnimationSize::GetValue

현재 값을 반환합니다.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>매개 변수

*szValue*<br/>
출력입니다. 이 메서드가 반환 될 때 현재 값을 포함 합니다.

### <a name="return-value"></a>반환 값

TRUE 이면 현재 값을 성공적으로 검색 합니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

크기 애니메이션의 현재 값을 검색 하려면이 함수를 호출 합니다. 이 메서드가 실패 하면 너비 및 크기에 대 한 기본 COM 개체 초기화 되지 않은, 경우 szValue SetDefaultValue 또는 생성자에서 이전에 설정 된 기본값을 포함 합니다.

##  <a name="m_cxvalue"></a>  CAnimationSize::m_cxValue

캡슐화 된 애니메이션 변수 애니메이션 크기의 너비를 나타내는입니다.

```
CAnimationVariable m_cxValue;
```

##  <a name="m_cyvalue"></a>  CAnimationSize::m_cyValue

캡슐화 된 애니메이션 변수 애니메이션 크기의 높이 나타내는입니다.

```
CAnimationVariable m_cyValue;
```

##  <a name="operator_csize"></a>  CAnimationSize::operator CSize

CAnimationSize CSize를 변환합니다.

```
operator CSize();
```

### <a name="return-value"></a>반환 값

CSize 크기 애니메이션의 현재 값입니다.

### <a name="remarks"></a>설명

이 함수는 GetValue 내부적으로 호출합니다. Getvalue가 어떤 이유로 실패 하는 경우 반환 되는 크기 너비와 높이 대 한 기본 값이 포함 됩니다.

##  <a name="operator_eq"></a>  CAnimationSize::operator=

CAnimationSize szSrc 할당합니다.

```
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>매개 변수

*szSrc*<br/>
CSize 또는 크기를 나타냅니다.

### <a name="remarks"></a>설명

CAnimationSize szSrc 할당합니다. 이 연산자가 생성 된 너비와 높이 대 한 기본 COM 개체를 다시 SetDefaultValue 호출 되므로 애니메이션이 시작 되기 전에 것이 좋습니다. 이 애니메이션 개체 (ValueChanged 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.

##  <a name="setdefaultvalue"></a>  CAnimationSize::SetDefaultValue

기본값을 설정합니다.

```
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>매개 변수

*szDefault*<br/>
새 기본 크기를 지정합니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 애니메이션 개체에 기본값을 설정 합니다. 이 메서드는 애니메이션 크기의 너비와 높이에 기본값을 할당 합니다. 이 또한 만들지 않은 경우 기본 COM 개체를 다시 합니다. 이 애니메이션 개체 (ValueChanged 또는 IntegerValueChanged) 이벤트를 구독 하는 경우 이러한 이벤트를 다시 사용 하도록 설정 해야 합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
