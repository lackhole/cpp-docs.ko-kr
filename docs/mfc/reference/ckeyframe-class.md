---
title: CKeyFrame 클래스
ms.date: 11/04/2016
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
ms.openlocfilehash: c2c6add30757e1d83b70001679b37a7a22b9d7d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392611"
---
# <a name="ckeyframe-class"></a>CKeyFrame 클래스

애니메이션 키프레임을 나타냅니다.

## <a name="syntax"></a>구문

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CKeyFrame::CKeyFrame](#ckeyframe)|오버로드됨. 다른 키 프레임에 의존 하는 키 프레임을 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|스토리 보드에 키 프레임을 추가합니다. (재정의 [CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|전환 후 스토리 보드에 키 프레임을 추가 합니다.|
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|오프셋에서 스토리 보드에 키 프레임을 추가 합니다.|
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|이 키 프레임에 따라 달라 집니다 키 프레임에 대 한 포인터를 반환 합니다.|
|[CKeyFrame::GetOffset](#getoffset)|다른 키 프레임에서 오프셋을 반환합니다.|
|[CKeyFrame::GetTransition](#gettransition)|이 키 프레임에 따라 달라 집니다 전환에 대 한 포인터를 반환 합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CKeyFrame::m_offset](#m_offset)|M_pExistingKeyFrame에 저장 된 키 프레임에서이 키 프레임의 오프셋을 지정 합니다.|
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|기존 키프레임에 대에 대 한 포인터를 저장합니다. 이 키 프레임은 기존 키 프레임에 대 한 m_offset이 사용 하 여 스토리 보드에 추가 됩니다.|
|[CKeyFrame::m_pTransition](#m_ptransition)|이 키 프레임에서 시작 하는 전환에 대 한 포인터를 저장 합니다.|

## <a name="remarks"></a>설명

이 클래스는 애니메이션 키 프레임을 구현합니다. 키 프레임을 스토리 보드 내에 순간을 나타내는 및 전환의 시작 및 종료 시간을 지정 하려면 사용할 수 있습니다. 키 프레임 다른 키 프레임에 기반 할 수 있습니다 및 오프셋 (초)에서 또는 전환에 따른 있고이 전환 종료 되는 시점을 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard

스토리 보드에 키 프레임을 추가합니다.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>매개 변수

*pStoryboard*<br/>
스토리 보드에 대 한 포인터입니다.

*bDeepAdd*<br/>
키 프레임을 추가 또는 재귀적으로 전환할 것인지 지정 합니다.

### <a name="return-value"></a>반환 값

키 프레임을 성공적으로 추가한 경우 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드는 스토리 보드에 키 프레임을 추가 합니다. 다른 키 프레임 또는 전환에 따라 다르겠지요 bDeepAdd TRUE 인 경우이 메서드를 재귀적으로 추가 하려고 합니다.

##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition

전환 후 스토리 보드에 키 프레임을 추가 합니다.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>매개 변수

*pStoryboard*<br/>
스토리 보드에 대 한 포인터입니다.

*bDeepAdd*<br/>
전환 재귀적을 추가할지 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

키 프레임을 성공적으로 추가한 경우 TRUE입니다.

### <a name="remarks"></a>설명

이 함수는 키프레임을 전환 후 스토리 보드에 추가 하기 위해 프레임 워크에서 호출 됩니다.

##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset

오프셋에서 스토리 보드에 키 프레임을 추가 합니다.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>매개 변수

*pStoryboard*<br/>
스토리 보드에 대 한 포인터입니다.

*bDeepAdd*<br/>
여부를 키 프레임을 추가 하려면이 키 프레임에 따라 달라 집니다 재귀적으로 지정 합니다.

### <a name="return-value"></a>반환 값

키 프레임을 성공적으로 추가한 경우 TRUE입니다.

### <a name="remarks"></a>설명

이 함수는 오프셋 스토리 보드에 키 프레임 추가 프레임 워크에서 호출 됩니다.

##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame

전환에 의존 하는 키 프레임을 생성 합니다.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>매개 변수

*pTransition*<br/>
전환에 대 한 포인터입니다.

*pKeyframe*<br/>
키 프레임에 대 한 포인터입니다.

*offset*<br/>
초 단위, pkeyframe에 지정 된 키 프레임의에서 오프셋입니다.

### <a name="remarks"></a>설명

생성 된 키 프레임은 지정한 전환이 종료 될 때 storyboard 내에 잠시를 나타냅니다.

##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe

이 키 프레임에 따라 달라 집니다 키 프레임에 대 한 포인터를 반환 합니다.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>반환 값

키 프레임, 또는이 키 프레임 다른 키 프레임에 종속 되지 않는 경우 NULL을 유효한 포인터입니다.

### <a name="remarks"></a>설명

이 키 프레임에 따라 달라 집니다 키 프레임에 대 한 접근자입니다.

##  <a name="getoffset"></a>  CKeyFrame::GetOffset

다른 키 프레임에서 오프셋을 반환합니다.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>반환 값

다른 키 프레임에서 수 초 내에 사용 되는 오프셋입니다.

### <a name="remarks"></a>설명

다른 키 프레임에서 수 초 내에 있는 오프셋을 확인 하려면이 메서드를 호출 해야 합니다.

##  <a name="gettransition"></a>  CKeyFrame::GetTransition

이 키 프레임에 따라 달라 집니다 전환에 대 한 포인터를 반환 합니다.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>반환 값

전환, 또는이 키 프레임 전환에 종속 되지 않는 경우 NULL을 유효한 포인터입니다.

### <a name="remarks"></a>설명

이 키 프레임에 따라 달라 집니다 전환에 대 한 접근자입니다.

##  <a name="m_offset"></a>  CKeyFrame::m_offset

M_pExistingKeyFrame에 저장 된 키 프레임에서이 키 프레임의 오프셋을 지정 합니다.

```
UI_ANIMATION_SECONDS m_offset;
```

##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame

기존 키프레임에 대에 대 한 포인터를 저장합니다. 이 키 프레임은 기존 키 프레임에 대 한 m_offset이 사용 하 여 스토리 보드에 추가 됩니다.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

##  <a name="m_ptransition"></a>  CKeyFrame::m_pTransition

이 키 프레임에서 시작 하는 전환에 대 한 포인터를 저장 합니다.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
