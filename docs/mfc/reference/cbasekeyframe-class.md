---
title: CBaseKeyFrame 클래스
ms.date: 11/04/2016
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
ms.openlocfilehash: d36c924d30bd728fcd54b6cdf6805ade25e20b5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218408"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame 클래스

키프레임의 기본 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|키 프레임 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|스토리 보드에 키 프레임을 추가 합니다.|
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|기본 키 프레임 값을 반환합니다.|
|[CBaseKeyFrame::IsAdded](#isadded)|키 프레임을 스토리 보드에 추가 되었는지 여부를 지정 합니다.|
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|키 프레임을 오프셋 또는 전환 후 스토리 보드에 추가할지 여부를 지정 합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CBaseKeyFrame::m_bAdded](#m_badded)|스토리 보드에이 키 프레임에 추가 되었는지 여부를 지정 합니다.|
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|일부 전환의 끝 또는 다른 기존 키 프레임의 오프셋에서 스토리 보드에이 키 프레임을 추가할지 여부를 지정 합니다.|
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Windows 애니메이션 API 키 프레임을 나타냅니다. 키 프레임 초기화 되지 않은 경우 UI_ANIMATION_KEYFRAME_STORYBOARD_START 미리 정의 된 값으로 설정 됩니다.|

## <a name="remarks"></a>설명

UI_ANIMATION_KEYFRAME 변수를 캡슐화합니다. 키프레임 구현 위한 기본 클래스로 사용 됩니다. 키 프레임을 스토리 보드 내에 순간을 나타내는 및 전환의 시작 및 종료 시간을 지정 하려면 사용할 수 있습니다. 키 프레임-(시간) 내에 지정된 된 오프셋에서 스토리 보드에 추가 하는 키 프레임 또는 지정 된 전환 후 추가 하는 키 프레임의는 다음과 같은 두 종류가 있습니다. 애니메이션 시작 되기 전에 전환의 기간을 알 수 없으므로 때문에 일부 키 프레임의 실제 값만 런타임에 결정 됩니다. 키 프레임의 해당 키 프레임에 종속 되는 전환에 따라 달라질 수 있습니다 이므로 키 프레임 체인을 빌드할 때 무한 재귀를 방지 해야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="addtostoryboard"></a>  CBaseKeyFrame::AddToStoryboard

스토리 보드에 키 프레임을 추가 합니다.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>매개 변수

*pStoryboard*<br/>
스토리 보드에 대 한 포인터입니다.

*bDeepAdd*<br/>
이 매개 변수는 TRUE를 키 프레임 추가 되 고 다른 키 프레임 또는 전환에 따라 달라 집니다이 메서드는이 키 프레임 또는 전환 먼저 스토리 보드에 추가 하려고 합니다.

### <a name="return-value"></a>반환 값

키 프레임은 성공적으로 스토리 보드에 추가 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 스토리 보드에 키 프레임을 추가 합니다.

##  <a name="cbasekeyframe"></a>  CBaseKeyFrame::CBaseKeyFrame

키 프레임 개체를 생성합니다.

```
CBaseKeyFrame();
```

##  <a name="getanimationkeyframe"></a>  CBaseKeyFrame::GetAnimationKeyframe

기본 키 프레임 값을 반환합니다.

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>반환 값

현재 키 프레임입니다. 기본값은 UI_ANIMATION_KEYFRAME_STORYBOARD_START 합니다.

### <a name="remarks"></a>설명

기본 키 프레임 값에 대 한 접근자입니다.

##  <a name="isadded"></a>  CBaseKeyFrame::IsAdded

키 프레임을 스토리 보드에 추가 되었는지 여부를 지정 합니다.

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>반환 값

키 프레임을 스토리 보드;에 추가 되 면 TRUE입니다. 고 FALSE입니다.

### <a name="remarks"></a>설명

기본 클래스에서 IsAdded 항상 TRUE를 반환 합니다 하지만 파생된 클래스에서 재정의 됩니다.

##  <a name="iskeyframeatoffset"></a>  CBaseKeyFrame::IsKeyframeAtOffset

키 프레임을 오프셋 또는 전환 후 스토리 보드에 추가할지 여부를 지정 합니다.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>반환 값

키 프레임 일부 지정 된 오프셋 위치에 스토리 보드에 추가 해야 하는 경우 TRUE입니다. FALSE 이면 키 프레임 일부 전환 후 스토리 보드에 추가 해야 합니다.

### <a name="remarks"></a>설명

키 프레임 오프셋 스토리 보드에 추가할지 여부를 지정 합니다. 파생된 클래스에서 오프셋 또는 전환을 지정 해야 합니다.

##  <a name="m_badded"></a>  CBaseKeyFrame::m_bAdded

스토리 보드에이 키 프레임에 추가 되었는지 여부를 지정 합니다.

```
BOOL m_bAdded;
```

##  <a name="m_biskeyframeatoffset"></a>  CBaseKeyFrame::m_bIsKeyframeAtOffset

일부 전환의 끝 또는 다른 기존 키 프레임의 오프셋에서 스토리 보드에이 키 프레임을 추가할지 여부를 지정 합니다.

```
BOOL m_bIsKeyframeAtOffset;
```

##  <a name="m_keyframe"></a>  CBaseKeyFrame::m_keyframe

Windows 애니메이션 API 키 프레임을 나타냅니다. 키 프레임 초기화 되지 않은 경우 UI_ANIMATION_KEYFRAME_STORYBOARD_START 미리 정의 된 값으로 설정 됩니다.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
