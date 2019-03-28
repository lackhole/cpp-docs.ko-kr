---
title: CAnimationController 클래스
ms.date: 03/27/2019
f1_keywords:
- CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::AddAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::AddKeyframeToGroup
- AFXANIMATIONCONTROLLER/CAnimationController::AnimateGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CreateKeyframe
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationManagerEvent
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnablePriorityComparisonHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnableStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::GetKeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionLibrary
- AFXANIMATIONCONTROLLER/CAnimationController::IsAnimationInProgress
- AFXANIMATIONCONTROLLER/CAnimationController::IsValid
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnBeforeAnimationStart
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCancel
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCompress
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityConclude
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityTrim
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAllAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationController::ScheduleGroup
- AFXANIMATIONCONTROLLER/CAnimationController::SetRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::UpdateAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::OnAfterSchedule
- AFXANIMATIONCONTROLLER/CAnimationController::gkeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::m_bIsValid
- AFXANIMATIONCONTROLLER/CAnimationController::m_lstAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::m_pRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionLibrary
helpviewer_keywords:
- CAnimationController [MFC], CAnimationController
- CAnimationController [MFC], AddAnimationObject
- CAnimationController [MFC], AddKeyframeToGroup
- CAnimationController [MFC], AnimateGroup
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], CreateKeyframe
- CAnimationController [MFC], EnableAnimationManagerEvent
- CAnimationController [MFC], EnableAnimationTimerEventHandler
- CAnimationController [MFC], EnablePriorityComparisonHandler
- CAnimationController [MFC], EnableStoryboardEventHandler
- CAnimationController [MFC], FindAnimationGroup
- CAnimationController [MFC], FindAnimationObject
- CAnimationController [MFC], GetKeyframeStoryboardStart
- CAnimationController [MFC], GetUIAnimationManager
- CAnimationController [MFC], GetUIAnimationTimer
- CAnimationController [MFC], GetUITransitionFactory
- CAnimationController [MFC], GetUITransitionLibrary
- CAnimationController [MFC], IsAnimationInProgress
- CAnimationController [MFC], IsValid
- CAnimationController [MFC], OnAnimationIntegerValueChanged
- CAnimationController [MFC], OnAnimationManagerStatusChanged
- CAnimationController [MFC], OnAnimationTimerPostUpdate
- CAnimationController [MFC], OnAnimationTimerPreUpdate
- CAnimationController [MFC], OnAnimationTimerRenderingTooSlow
- CAnimationController [MFC], OnAnimationValueChanged
- CAnimationController [MFC], OnBeforeAnimationStart
- CAnimationController [MFC], OnHasPriorityCancel
- CAnimationController [MFC], OnHasPriorityCompress
- CAnimationController [MFC], OnHasPriorityConclude
- CAnimationController [MFC], OnHasPriorityTrim
- CAnimationController [MFC], OnStoryboardStatusChanged
- CAnimationController [MFC], OnStoryboardUpdated
- CAnimationController [MFC], RemoveAllAnimationGroups
- CAnimationController [MFC], RemoveAnimationGroup
- CAnimationController [MFC], RemoveAnimationObject
- CAnimationController [MFC], RemoveTransitions
- CAnimationController [MFC], ScheduleGroup
- CAnimationController [MFC], SetRelatedWnd
- CAnimationController [MFC], UpdateAnimationManager
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], OnAfterSchedule
- CAnimationController [MFC], gkeyframeStoryboardStart
- CAnimationController [MFC], m_bIsValid
- CAnimationController [MFC], m_lstAnimationGroups
- CAnimationController [MFC], m_pAnimationManager
- CAnimationController [MFC], m_pAnimationTimer
- CAnimationController [MFC], m_pRelatedWnd
- CAnimationController [MFC], m_pTransitionFactory
- CAnimationController [MFC], m_pTransitionLibrary
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
ms.openlocfilehash: a3a533b876b9ca245c0553c4c24a815ef3cabca1
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565963"
---
# <a name="canimationcontroller-class"></a>CAnimationController 클래스

애니메이션을 만들고 관리하기 위한 중앙 인터페이스를 제공하는 애니메이션 컨트롤러를 구현합니다.

## <a name="syntax"></a>구문

```
class CAnimationController : public CObject;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAnimationController::CAnimationController](#canimationcontroller)|애니메이션 컨트롤러를 생성합니다.|
|[CAnimationController::~CAnimationController](#_dtorcanimationcontroller)|소멸자입니다. 애니메이션 컨트롤러 개체가 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAnimationController::AddAnimationObject](#addanimationobject)|애니메이션 개체 애니메이션 컨트롤러에 속해 있는 그룹에 추가 합니다.|
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|그룹에 키 프레임을 추가합니다.|
|[CAnimationController::AnimateGroup](#animategroup)|애니메이션을 실행 하는 그룹을 준비 하 고 필요에 따라이 예약 합니다.|
|[CAnimationController::CleanUpGroup](#cleanupgroup)|오버로드됨. 애니메이션을 예약한 경우 그룹을 정리 하기 위해 프레임 워크에서 호출 됩니다.|
|[CAnimationController::CreateKeyframe](#createkeyframe)|오버로드됨. 전환을 사용하는 키 프레임을 만들어 지정된 그룹에 추가합니다.|
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|애니메이션 관리자의 상태가 변경 될 때 호출할 처리기를 해제 하거나 설정 합니다.|
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|타이밍 이벤트에 대 한 처리기 및 업데이트 타이밍에 대 한 처리기를 해제 하거나 설정 합니다.|
|[CAnimationController::EnablePriorityComparisonHandler](#enableprioritycomparisonhandler)|우선 순위 비교 호출할 처리기입니다 있는지 여부를 확인을 예약 된 스토리 보드 수 수 취소, 완료, 트리밍 압축을 해제 하거나 설정 합니다.|
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|스토리 보드 상태 및 업데이트 이벤트에 대 한 처리기를 해제 하거나 설정 합니다.|
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|오버로드됨. 해당 스토리 보드에서 애니메이션 그룹을 찾습니다.|
|[CAnimationController::FindAnimationObject](#findanimationobject)|지정 된 애니메이션 변수를 포함 하는 애니메이션 개체를 찾습니다.|
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|스토리 보드의 시작을 식별 하는 키 프레임을 반환 합니다.|
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|캡슐화 된 IUIAnimationManager 개체에 대 한 액세스를 제공합니다.|
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|캡슐화 된 IUIAnimationTimer 개체에 대 한 액세스를 제공합니다.|
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|IUIAnimationTransitionFactory 인터페이스 또는 전환 라이브러리 생성에 실패 하는 경우에 NULL 포인터입니다.|
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|캡슐화 된 IUIAnimationTransitionLibrary 개체에 대 한 액세스를 제공합니다.|
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|그룹을 하나 이상 애니메이션을 재생 하는지 여부를 알려 줍니다.|
|[CAnimationController::IsValid](#isvalid)|애니메이션 컨트롤러 올바른지 여부를 알려 줍니다.|
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|애니메이션 변수 정수 값이 변경 되었을 때 프레임 워크에서 호출 됩니다.|
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|애니메이션 관리자에서 StatusChanged 이벤트에 대 한 응답에 프레임 워크에서 호출 됩니다.|
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|애니메이션 업데이트가 완료 된 후 프레임 워크에서 호출 됩니다.|
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|애니메이션 업데이트가 시작 되기 전에 프레임 워크에서 호출 됩니다.|
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|애니메이션 렌더링 프레임 속도 최소 원하는 프레임 속도 보다 적을 경우 프레임 워크에서 호출 됩니다.|
|[CAnimationController::OnAnimationValueChanged](#onanimationvaluechanged)|애니메이션 변수 값이 변경 되었을 때 프레임 워크에서 호출 됩니다.|
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|프레임 워크에서 오른쪽 되기 전에 호출 애니메이션이 예약 됩니다.|
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.|
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.|
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.|
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.|
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|스토리 보드 상태 변경 되었을 때 프레임 워크에서 호출 됩니다.|
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|스토리 보드 업데이트 되었을 때 프레임 워크에서 호출 됩니다.|
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|애니메이션 컨트롤러에서 모든 애니메이션 그룹을 제거합니다.|
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|애니메이션 컨트롤러에서 지정한 ID 사용 하 여 애니메이션 그룹을 제거합니다.|
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|애니메이션 컨트롤러에서 애니메이션 개체를 제거 합니다.|
|[CAnimationController::RemoveTransitions](#removetransitions)|전환이 지정된 된 그룹에 속하는 애니메이션 개체에서 제거 합니다.|
|[CAnimationController::ScheduleGroup](#schedulegroup)|애니메이션을 예약합니다.|
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|애니메이션 컨트롤러와 창 사이의 관계를 설정 합니다.|
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|모든 애니메이션 변수의 값을 업데이트 하 여 애니메이션 관리자를 전달 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CAnimationController::CleanUpGroup](#cleanupgroup)|오버로드됨. 그룹을 정리 하는 도우미입니다.|
|[CAnimationController::OnAfterSchedule](#onafterschedule)|지정된 된 그룹에 대 한 애니메이션을 예약 했 때 프레임 워크에서 호출 됩니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|스토리 보드의 시작을 나타내는 키 프레임입니다.|
|[CAnimationController::m_bIsValid](#m_bisvalid)|애니메이션 컨트롤러를 유효한 지 여부를 지정 합니다. 이 멤버는 현재 OS Windows 애니메이션 API를 지원 하지 않는 경우 FALSE로 설정 됩니다.|
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|이 애니메이션 컨트롤러에 속하는 애니메이션 그룹 목록입니다.|
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|애니메이션 관리자 COM 개체에 대 한 포인터를 저장합니다.|
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|애니메이션 타이머 COM 개체에 대 한 포인터를 저장합니다.|
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|애니메이션 관리자의 상태가 변경 되거나 post 업데이트 이벤트가 발생 하는 경우 자동으로 다시 관련된 CWnd 개체에 대 한 포인터입니다. NULL 일 수 있습니다.|
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|전환 팩터리 COM 개체에 대 한 포인터를 저장합니다.|
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|전환 라이브러리 COM 개체에 대 한 포인터를 저장합니다.|

## <a name="remarks"></a>설명

CAnimationController 클래스에는 애니메이션을 관리 하는 키 클래스가입니다. 수 애니메이션 컨트롤러의 하나 이상의 인스턴스 응용 프로그램에서를 만들고 필요에 따라 CAnimationController::SetRelatedWnd를 사용 하 여 CWnd 개체에 애니메이션 컨트롤러의 인스턴스를 연결 합니다. 이 연결 WM_PAINT 메시지 관련된 창에 자동으로 보내도록 애니메이션 관리자 상태 변경 되었거나 애니메이션 타이머 업데이트 된 경우 필요 합니다. 이 관계를 사용 하지 않는 경우에 애니메이션을 수동으로 표시 하는 창을 그려야 합니다. 이 목적을 위해 CAnimationController에서 클래스를 파생 하 고 OnAnimationManagerStatusChanged 및/또는 OnAnimationTimerPostUpdate 재정의 필요한 경우 하나 이상의 창을 무효화 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationController`

## <a name="requirements"></a>요구 사항

**헤더:** afxanimationcontroller.h

##  <a name="_dtorcanimationcontroller"></a>  CAnimationController::~CAnimationController

소멸자입니다. 애니메이션 컨트롤러 개체가 소멸 될 때 호출 됩니다.

```
virtual ~CAnimationController(void);
```

##  <a name="addanimationobject"></a>  CAnimationController::AddAnimationObject

애니메이션 개체 애니메이션 컨트롤러에 속해 있는 그룹에 추가 합니다.

```
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```

### <a name="parameters"></a>매개 변수

*pObject*<br/>
애니메이션 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 pObject 추가 된 위치에 대 한 기존 또는 새 애니메이션 그룹에 대 한 포인터 PObject 다른 애니메이션 컨트롤러 속해 있는 그룹에 이미 추가 된 경우 NULL입니다.

### <a name="remarks"></a>설명

애니메이션 개체 애니메이션 컨트롤러를 추가 하려면이 메서드를 호출 합니다. 개체의 그룹 Id에 따라 그룹에 추가할 개체 (CAnimationBaseObject::SetID 참조). 애니메이션 컨트롤러는 지정된 된 GroupID를 사용 하 여 추가 되는 첫 번째 개체 이면 새 그룹을 만듭니다. 애니메이션 개체에 한 애니메이션 컨트롤러에만 추가할 수 있습니다. 다른 컨트롤러에 개체를 추가 해야 할 경우 먼저 RemoveAnimationObject를 호출 합니다. 그룹에 이미 추가 된 개체에 대 한 새 그룹 Id 사용 하 여 SetID를 호출 하는 경우 개체의 이전 그룹에서 제거 되며 지정된 ID 사용 하 여 다른 그룹에 추가

##  <a name="addkeyframetogroup"></a>  CAnimationController::AddKeyframeToGroup

그룹에 키 프레임을 추가합니다.

```
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
그룹 ID를 지정 합니다.

*pKeyframe*<br/>
키 프레임에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

일반적으로 필요가이 메서드를 호출, CAnimationController::CreateKeyframe를 대신 사용 하 여 생성 되 고 그룹에 자동으로 만든된 키 프레임을 추가 합니다.

##  <a name="animategroup"></a>  CAnimationController::AnimateGroup

애니메이션을 실행 하는 그룹을 준비 하 고 필요에 따라이 예약 합니다.

```
BOOL AnimateGroup(
    UINT32 nGroupID,
    BOOL bScheduleNow = TRUE);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
그룹 Id를 지정합니다.

*bScheduleNow*<br/>
애니메이션을 즉시 실행할지 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

애니메이션 성공적으로 예약 및 실행 하는 경우 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드는 스토리 보드를 만들고, 애니메이션 변수 추가, 전환 적용 및 키 프레임을 설정 하는 실제 작업을 수행 합니다. BScheduleNow FALSE로 설정 하는 경우 예약을 지연 하는 것이 가능 합니다. 이 경우 지정된 된 그룹에서는 애니메이션에 대해 설정 된 스토리 보드를 보관 합니다. 이때 스토리 보드 및 애니메이션 변수의 이벤트를 설정할 수 있습니다. 실제로 해야 CAnimationController::ScheduleGroup 애니메이션 호출을 실행 합니다.

##  <a name="canimationcontroller"></a>  CAnimationController::CAnimationController

애니메이션 컨트롤러를 생성합니다.

```
CAnimationController(void);
```

##  <a name="cleanupgroup"></a>  CAnimationController::CleanUpGroup

애니메이션을 예약한 경우 그룹을 정리 하기 위해 프레임 워크에서 호출 됩니다.

```
void CleanUpGroup(UINT32 nGroupID);
void CleanUpGroup(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
그룹 Id를 지정합니다.

*pGroup*<br/>
애니메이션 그룹 정리에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 관련이 없기 때문에 애니메이션을 예약한 후 지정된 된 그룹에서 모든 전환 및 키 프레임이 제거 합니다.

##  <a name="createkeyframe"></a>  CAnimationController::CreateKeyframe

전환을 사용하는 키 프레임을 만들어 지정된 그룹에 추가합니다.

```
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseTransition* pTransition);

CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
키 프레임을 만들 그룹 ID를 지정합니다.

*pTransition*<br/>
전환에 대한 포인터입니다. 이 전환 후 스토리보드에 키 프레임이 삽입됩니다.

*pKeyframe*<br/>
이 키 프레임의 기본 키 프레임에 대한 포인터입니다.

*offset*<br/>
pKeyframe에 지정된 기본 키 프레임에서의 오프셋(초)입니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 새로 생성되는 키 프레임에 대한 포인터입니다.

### <a name="remarks"></a>설명

반환된 포인터를 저장하고 새로 만든 키 프레임을 다른 키 프레임의 기반으로 사용할 수 있습니다(두 번째 오버로드 참조). 키 프레임에서 전환을 시작할 수 있습니다(CBaseTransition::SetKeyframes 참조). 이런 방법으로 만든 키 프레임은 애니메이션 그룹에 의해 자동으로 삭제되기 때문에 삭제할 필요가 없습니다. 다른 키 프레임 및 전환을 기반으로 하여 키 프레임을 만들 때는 순환 참조가 발생하지 않도록 주의하세요.

##  <a name="enableanimationmanagerevent"></a>  CAnimationController::EnableAnimationManagerEvent

애니메이션 관리자의 상태가 변경 될 때 호출할 처리기를 해제 하거나 설정 합니다.

```
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
설정 하거나 해제 처리기를 지정 합니다.

### <a name="return-value"></a>반환 값

처리기를 성공적으로 설정 하거나 해제 하는 경우 TRUE입니다.

### <a name="remarks"></a>설명

(사용) 처리기를 설정 하면 애니메이션 관리자의 상태가 변경 될 때 Windows 애니메이션 OnAnimationManagerStatusChanged를 호출 합니다.

##  <a name="enableanimationtimereventhandler"></a>  CAnimationController::EnableAnimationTimerEventHandler

타이밍 이벤트에 대 한 처리기 및 업데이트 타이밍에 대 한 처리기를 해제 하거나 설정 합니다.

```
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
설정 하거나 해제 처리기를 지정 합니다.

*idleBehavior*<br/>
타이머가 업데이트 처리기에 대 한 유휴 동작을 지정합니다.

### <a name="return-value"></a>반환 값

처리기 된 성공적으로 설정 하거나 해제 하는 경우 TRUE입니다. FALSE 이면이 메서드는 두 번째 시간에 대 한 처리기를 먼저 해제 하지 않고 또는 다른 경우 오류가 발생 합니다.

### <a name="remarks"></a>설명

처리기는이 설정 된 경우 (사용된) Windows 애니메이션 API 호출, OnAnimationTimerPreUpdate OnAnimationTimerPostUpdate, OnRenderingTooSlow 메서드. Windows 애니메이션 API 업데이트 스토리 보드를 허용 하도록 애니메이션 타이머를 사용 하도록 설정 해야 합니다. 그렇지 않으면 모든 애니메이션 변수의 값을 업데이트 하는 관리자 애니메이션 하려면 CAnimationController::UpdateAnimationManager를 호출 해야 합니다.

##  <a name="enableprioritycomparisonhandler"></a>  CAnimationController::EnablePriorityComparisonHandler

우선 순위 비교 호출할 처리기입니다 있는지 여부를 확인을 예약 된 스토리 보드 수 수 취소, 완료, 트리밍 압축을 해제 하거나 설정 합니다.

```
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```

### <a name="parameters"></a>매개 변수

*dwHandlerType*<br/>
어떤 처리기를 설정 또는 해제할지를 지정 하는 (설명 참조), UI_ANIMATION_PHT_ 조합에서 플래그입니다.

### <a name="return-value"></a>반환 값

처리기를 성공적으로 설정 하거나 해제 하는 경우 TRUE입니다.

### <a name="remarks"></a>설명

처리기 경우 집합 (사용) Windows 애니메이션 dwHandlerType에 따라 다음 가상 메서드를 호출 합니다. OnHasPriorityCancel, OnHasPriorityConclude, OnHasPriorityTrim, OnHasPriorityCompress. dwHandler는 플래그의 조합일 수 있습니다. UI_ANIMATION_PHT_NONE-릴리스 모든 처리기 UI_ANIMATION_PHT_CANCEL-취소 설정 비교 처리기 UI_ANIMATION_PHT_CONCLUDE-설정 Conclude 비교 처리기 UI_ANIMATION_PHT_COMPRESS-압축 비교 처리기 UI_ANIMATION_PHT_TRIM 설정-설정 비교 처리기 UI_ANIMATION_PHT_CANCEL_REMOVE 자릅니다-취소 비교 처리기 UI_ANIMATION_PHT_CONCLUDE_REMOVE Conclude 비교 처리기 UI_ANIMATION_PHT_COMPRESS_REMOVE 제거-제거 UI_ANIMATION_PHT 압축 비교 처리기를 제거 합니다. _TRIM_REMOVE-Trim 비교 처리기 제거

##  <a name="enablestoryboardeventhandler"></a>  CAnimationController::EnableStoryboardEventHandler

스토리 보드 상태 및 업데이트 이벤트에 대 한 처리기를 해제 하거나 설정 합니다.

```
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
그룹 ID를 지정 합니다.

*bEnable*<br/>
설정 하거나 해제 처리기를 지정 합니다.

### <a name="return-value"></a>반환 값

처리기를 성공적으로 설정 하거나 해제 하는 경우 TRUE입니다. 지정 된 애니메이션 그룹이 이제 지정된 된 그룹에 대 한 애니메이션을 시작 하지 않았으면 해당 내부 스토리 보드는 NULL 경우 FALSE입니다.

### <a name="remarks"></a>설명

처리기가 설정 된 경우 (사용된) Windows 애니메이션 API OnStoryboardStatusChanges 및 OnStoryboardUpdated 가상 메서드를 호출 합니다. 처리기를 캡슐화 된 IUIAnimationStoryboard 개체를 만들기 때문에 CAnimationController::Animate 호출 된 후에 지정 된 애니메이션 그룹에 대해 설정 되어야 합니다.

##  <a name="findanimationgroup"></a>  CAnimationController::FindAnimationGroup

Id입니다. 해당 그룹에서 애니메이션 그룹을 찾습니다.

```
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
그룹 Id를 지정합니다.

*pStoryboard*<br/>
스토리 보드에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

애니메이션 그룹 또는 지정 된 ID 사용 하 여 그룹이 없는 경우 NULL 포인터입니다.

### <a name="remarks"></a>설명

런타임 시 애니메이션 그룹을 찾으려면이 방법을 사용 합니다. 그룹 생성 되어 특정 그룹 Id 사용 하 여 첫 번째 애니메이션 개체를 애니메이션 컨트롤러에 추가 될 때 애니메이션 그룹의 내부 목록에 추가 합니다.

##  <a name="findanimationobject"></a>  CAnimationController::FindAnimationObject

지정 된 애니메이션 변수를 포함 하는 애니메이션 개체를 찾습니다.

```
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,
    CAnimationBaseObject** ppObject,
    CAnimationGroup** ppGroup);
```

### <a name="parameters"></a>매개 변수

*pVariable*<br/>
애니메이션 변수 포인터입니다.

*ppObject*<br/>
출력입니다. 애니메이션 개체 또는 NULL에 대 한 포인터를 포함합니다.

*ppGroup*<br/>
출력입니다. 애니메이션 개체 또는 NULL을 포함 하는 애니메이션 그룹에 대 한 포인터를 포함 합니다.

### <a name="return-value"></a>반환 값

TRUE 이면 개체를 찾을 수 있습니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

애니메이션 변수를 들어오는에서 애니메이션 개체를 찾기 위해 필요한 이벤트 처리기에서 호출 됩니다.

##  <a name="g_keyframestoryboardstart"></a>  CAnimationController::gkeyframeStoryboardStart

스토리 보드의 시작을 나타내는 키 프레임입니다.

```
static CBaseKeyFrame gkeyframeStoryboardStart;
```

##  <a name="getkeyframestoryboardstart"></a>  CAnimationController::GetKeyframeStoryboardStart

스토리 보드의 시작을 식별 하는 키 프레임을 반환 합니다.

```
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```

### <a name="return-value"></a>반환 값

스토리 보드의 시작을 식별 하는 기본 키 프레임에 대 한 포인터입니다.

### <a name="remarks"></a>설명

시점은 storyboard를 시작할 때 다른 키 프레임 또는 전환을 기준에이 키 프레임을 가져옵니다.

##  <a name="getuianimationmanager"></a>  CAnimationController::GetUIAnimationManager

캡슐화 된 IUIAnimationManager 개체에 대 한 액세스를 제공합니다.

```
IUIAnimationManager* GetUIAnimationManager();
```

### <a name="return-value"></a>반환 값

IUIAnimationManager 인터페이스 또는 애니메이션 관리자 만들기에 실패 한 경우 NULL 포인터입니다.

### <a name="remarks"></a>설명

현재 OS Windows 애니메이션 API를 지원 하지 않는 경우 NULL이 반환 하 고 그 후 CAnimationController::IsValid 대 한 모든 후속 호출은 FALSE를 반환 합니다. IUIAnimationManager 애니메이션 컨트롤러 래핑되지는 해당 인터페이스 메서드를 호출 하기 위해 액세스 해야 합니다.

##  <a name="getuianimationtimer"></a>  CAnimationController::GetUIAnimationTimer

캡슐화 된 IUIAnimationTimer 개체에 대 한 액세스를 제공합니다.

```
IUIAnimationTimer* GetUIAnimationTimer();
```

### <a name="return-value"></a>반환 값

IUIAnimationTimer 인터페이스 또는 애니메이션 타이머 생성에 실패 하는 경우에 NULL 포인터입니다.

### <a name="remarks"></a>설명

현재 OS Windows 애니메이션 API를 지원 하지 않는 경우 NULL이 반환 하 고 그 후 CAnimationController::IsValid 대 한 모든 후속 호출은 FALSE를 반환 합니다.

##  <a name="getuitransitionfactory"></a>  CAnimationController::GetUITransitionFactory

IUIAnimationTransitionFactory 인터페이스 또는 전환 라이브러리 생성에 실패 하는 경우에 NULL 포인터입니다.

```
IUIAnimationTransitionFactory* GetUITransitionFactory();
```

### <a name="return-value"></a>반환 값

IUIAnimationTransitionFactory 또는 전환 팩터리 생성에 실패 하는 경우에 NULL 포인터입니다.

### <a name="remarks"></a>설명

현재 OS Windows 애니메이션 API를 지원 하지 않는 경우 NULL이 반환 하 고 그 후 CAnimationController::IsValid 대 한 모든 후속 호출은 FALSE를 반환 합니다.

##  <a name="getuitransitionlibrary"></a>  CAnimationController::GetUITransitionLibrary

캡슐화 된 IUIAnimationTransitionLibrary 개체에 대 한 액세스를 제공합니다.

```
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```

### <a name="return-value"></a>반환 값

IUIAnimationTransitionLibrary 인터페이스 또는 전환 라이브러리 생성에 실패 하는 경우에 NULL 포인터입니다.

### <a name="remarks"></a>설명

현재 OS Windows 애니메이션 API를 지원 하지 않는 경우 NULL이 반환 하 고 그 후 CAnimationController::IsValid 대 한 모든 후속 호출은 FALSE를 반환 합니다.

##  <a name="isanimationinprogress"></a>  CAnimationController::IsAnimationInProgress

그룹을 하나 이상 애니메이션을 재생 하는지 여부를 알려 줍니다.

```
virtual BOOL IsAnimationInProgress();
```

### <a name="return-value"></a>반환 값

이 애니메이션 컨트롤러에 대 한 진행 중인 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

애니메이션 관리자의 상태를 확인 하 고 상태가 UI_ANIMATION_MANAGER_BUSY 이면 TRUE를 반환 합니다.

##  <a name="isvalid"></a>  CAnimationController::IsValid

애니메이션 컨트롤러 올바른지 여부를 알려 줍니다.

```
BOOL IsValid() const;
```

### <a name="return-value"></a>반환 값

애니메이션 컨트롤러; 유효한 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

등록 되지 않은 Windows 애니메이션 API는 현재 OS와 애니메이션 관리자 만들기에서 지원 되지 않습니다 하는 경우에 FALSE를 반환 하지 못했습니다. 이 플래그의 설정은 시킬 COM 라이브러리를 초기화 한 후 한 번 이상 GetUIAnimationManager를 호출 해야 합니다.

##  <a name="m_bisvalid"></a>  CAnimationController::m_bIsValid

애니메이션 컨트롤러를 유효한 지 여부를 지정 합니다. 이 멤버는 현재 OS Windows 애니메이션 API를 지원 하지 않는 경우 FALSE로 설정 됩니다.

```
BOOL m_bIsValid;
```

##  <a name="m_lstanimationgroups"></a>  CAnimationController::m_lstAnimationGroups

이 애니메이션 컨트롤러에 속하는 애니메이션 그룹 목록입니다.

```
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;
```

##  <a name="m_panimationmanager"></a>  CAnimationController::m_pAnimationManager

애니메이션 관리자 COM 개체에 대 한 포인터를 저장합니다.

```
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;
```

##  <a name="m_panimationtimer"></a>  CAnimationController::m_pAnimationTimer

애니메이션 타이머 COM 개체에 대 한 포인터를 저장합니다.

```
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;
```

##  <a name="m_prelatedwnd"></a>  CAnimationController::m_pRelatedWnd

애니메이션 관리자의 상태가 변경 되거나 post 업데이트 이벤트가 발생 하는 경우 자동으로 다시 관련된 CWnd 개체에 대 한 포인터입니다. NULL 일 수 있습니다.

```
CWnd* m_pRelatedWnd;
```

##  <a name="m_ptransitionfactory"></a>  CAnimationController::m_pTransitionFactory

전환 팩터리 COM 개체에 대 한 포인터를 저장합니다.

```
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;
```

##  <a name="m_ptransitionlibrary"></a>  CAnimationController::m_pTransitionLibrary

전환 라이브러리 COM 개체에 대 한 포인터를 저장합니다.

```
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;
```

##  <a name="onafterschedule"></a>  CAnimationController::OnAfterSchedule

지정된 된 그룹에 대 한 애니메이션을 예약 했 때 프레임 워크에서 호출 됩니다.

```
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
예약 된 애니메이션 그룹에 대 한 포인터입니다.

### <a name="remarks"></a>설명

지정된 된 그룹에서 키 프레임을 제거 하 고 지정된 된 그룹에 속하는 애니메이션 변수에서 전환 하는 기본 구현. 애니메이션 일정에 따라 추가 작업을 수행 하는 파생된 클래스에서 재정의할 수 있습니다.

##  <a name="onanimationintegervaluechanged"></a>  CAnimationController::OnAnimationIntegerValueChanged

애니메이션 변수 정수 값이 변경 되었을 때 프레임 워크에서 호출 됩니다.

```
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    INT32 newValue,
    INT32 prevValue);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
값을 갖는 애니메이션 개체를 보유 하는 애니메이션 그룹에 대 한 포인터 변경 되었습니다.

*pObject*<br/>
값이 변경 된 애니메이션 변수를 포함 하는 애니메이션 개체에 대 한 포인터입니다.

*variable*<br/>
애니메이션 변수 포인터입니다.

*newValue*<br/>
새 값을 지정합니다.

*prevValue*<br/>
이전 값을 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 EnableIntegerValueChangedEvent 특정 애니메이션 변수 또는 애니메이션 개체에 대 한 호출을 사용 하 여 애니메이션 변수 이벤트를 사용 하는 경우 호출 됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

##  <a name="onanimationmanagerstatuschanged"></a>  CAnimationController::OnAnimationManagerStatusChanged

애니메이션 관리자에서 StatusChanged 이벤트에 대 한 응답에 프레임 워크에서 호출 됩니다.

```
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>매개 변수

*newStatus*<br/>
새 애니메이션 관리자 상태입니다.

*previousStatus*<br/>
이전 애니메이션 관리자 상태입니다.

### <a name="remarks"></a>설명

이 메서드는 EnableAnimationManagerEvent 된 애니메이션 관리자 이벤트를 사용 하는 경우 호출 됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. 기본 구현은 SetRelatedWnd를 사용 하 여 설정 된 경우 관련된 창을 업데이트 합니다.

##  <a name="onanimationtimerpostupdate"></a>  CAnimationController::OnAnimationTimerPostUpdate

애니메이션 업데이트가 완료 된 후 프레임 워크에서 호출 됩니다.

```
virtual void OnAnimationTimerPostUpdate();
```

### <a name="remarks"></a>설명

이 메서드는 EnableAnimationTimerEventHandler를 사용 하 여 타이머 이벤트 처리기를 사용 하는 경우 호출 됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

##  <a name="onanimationtimerpreupdate"></a>  CAnimationController::OnAnimationTimerPreUpdate

애니메이션 업데이트가 시작 되기 전에 프레임 워크에서 호출 됩니다.

```
virtual void OnAnimationTimerPreUpdate();
```

### <a name="remarks"></a>설명

이 메서드는 EnableAnimationTimerEventHandler를 사용 하 여 타이머 이벤트 처리기를 사용 하는 경우 호출 됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

##  <a name="onanimationtimerrenderingtooslow"></a>  CAnimationController::OnAnimationTimerRenderingTooSlow

애니메이션 렌더링 프레임 속도 최소 원하는 프레임 속도 보다 적을 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```

### <a name="parameters"></a>매개 변수

*fps*<br/>
초당 프레임에서 현재 프레임 속도 지정 합니다.

### <a name="remarks"></a>설명

이 메서드는 EnableAnimationTimerEventHandler를 사용 하 여 타이머 이벤트 처리기를 사용 하는 경우 호출 됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. 원하는 최소 프레임 속도 IUIAnimationTimer::SetFrameRateThreshold를 호출 하 여 지정 됩니다.

##  <a name="onanimationvaluechanged"></a>  CAnimationController::OnAnimationValueChanged

애니메이션 변수 값이 변경 되었을 때 프레임 워크에서 호출 됩니다.

```
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    DOUBLE newValue,
    DOUBLE prevValue);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
값을 갖는 애니메이션 개체를 보유 하는 애니메이션 그룹에 대 한 포인터 변경 되었습니다.

*pObject*<br/>
값이 변경 된 애니메이션 변수를 포함 하는 애니메이션 개체에 대 한 포인터입니다.

*variable*<br/>
애니메이션 변수 포인터입니다.

*newValue*<br/>
새 값을 지정합니다.

*prevValue*<br/>
이전 값을 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 EnableValueChangedEvent 특정 애니메이션 변수 또는 애니메이션 개체에 대 한 호출을 사용 하 여 애니메이션 변수 이벤트를 사용 하는 경우 호출 됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

##  <a name="onbeforeanimationstart"></a>  CAnimationController::OnBeforeAnimationStart

프레임 워크에서 오른쪽 되기 전에 호출 애니메이션이 예약 됩니다.

```
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
시작 인 애니메이션은 애니메이션 그룹에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 호출은 관련 cwnd 라우팅됩니다 하 고 지정된 된 그룹에 대 한 애니메이션을 시작 하기 전에 추가 작업을 수행 하는 파생된 클래스에서 재정의할 수 있습니다.

##  <a name="onhasprioritycancel"></a>  CAnimationController::OnHasPriorityCancel

일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.

```
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>매개 변수

*pGroupScheduled*<br/>
현재 예약된 스토리보드를 소유하고 있는 그룹입니다.

*pGroupNew*<br/>
pGroupScheduled에서 소유한 예약된 스토리보드와 충돌을 예약하고 있는 새 스토리보드를 소유하는 그룹입니다.

*priorityEffect*<br/>
pGroupScheduled에 높은 우선 순위가 있는 경우 pGroupNew에서 발생할 수 있는 효과입니다.

### <a name="return-value"></a>반환 값

pGroupNew에서 소유한 스토리보드가 우선인 경우 TRUE를 반환해야 합니다. pGroupScheduled에서 소유한 스토리보드가 우선인 경우 FALSE를 반환해야 합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnablePriorityComparisonHandler를 사용하여 우선 순위 비교 이벤트를 활성화하고 UI_ANIMATION_PHT_CANCEL을 지정하는 경우 호출됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. 에 대 한 자세한 정보에 대 한 읽기 Windows 애니메이션 API 설명서 [충돌 관리](/windows/desktop/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)합니다.

##  <a name="onhasprioritycompress"></a>  CAnimationController::OnHasPriorityCompress

일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.

```
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>매개 변수

*pGroupScheduled*<br/>
현재 예약된 스토리보드를 소유하고 있는 그룹입니다.

*pGroupNew*<br/>
pGroupScheduled에서 소유한 예약된 스토리보드와 충돌을 예약하고 있는 새 스토리보드를 소유하는 그룹입니다.

*priorityEffect*<br/>
pGroupScheduled에 높은 우선 순위가 있는 경우 pGroupNew에서 발생할 수 있는 효과입니다.

### <a name="return-value"></a>반환 값

pGroupNew에서 소유한 스토리보드가 우선인 경우 TRUE를 반환해야 합니다. pGroupScheduled에서 소유한 스토리보드가 우선인 경우 FALSE를 반환해야 합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnablePriorityComparisonHandler를 사용하여 우선 순위 비교 이벤트를 활성화하고 UI_ANIMATION_PHT_COMPRESS를 지정하는 경우 호출됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. 에 대 한 자세한 정보에 대 한 읽기 Windows 애니메이션 API 설명서 [충돌 관리](/windows/desktop/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)합니다.

##  <a name="onhaspriorityconclude"></a>  CAnimationController::OnHasPriorityConclude

일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.

```
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>매개 변수

*pGroupScheduled*<br/>
현재 예약된 스토리보드를 소유하고 있는 그룹입니다.

*pGroupNew*<br/>
pGroupScheduled에서 소유한 예약된 스토리보드와 충돌을 예약하고 있는 새 스토리보드를 소유하는 그룹입니다.

*priorityEffect*<br/>
pGroupScheduled에 높은 우선 순위가 있는 경우 pGroupNew에서 발생할 수 있는 효과입니다.

### <a name="return-value"></a>반환 값

pGroupNew에서 소유한 스토리보드가 우선인 경우 TRUE를 반환해야 합니다. pGroupScheduled에서 소유한 스토리보드가 우선인 경우 FALSE를 반환해야 합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnablePriorityComparisonHandler를 사용하여 우선 순위 비교 이벤트를 활성화하고 UI_ANIMATION_PHT_TRIM을 지정하는 경우 호출됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. 에 대 한 자세한 정보에 대 한 읽기 Windows 애니메이션 API 설명서 [충돌 관리](/windows/desktop/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)합니다.

##  <a name="onhasprioritytrim"></a>  CAnimationController::OnHasPriorityTrim

일정 충돌을 해결하기 위해 프레임워크에 의해 호출됩니다.

```
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>매개 변수

*pGroupScheduled*<br/>
현재 예약된 스토리보드를 소유하고 있는 그룹입니다.

*pGroupNew*<br/>
pGroupScheduled에서 소유한 예약된 스토리보드와 충돌을 예약하고 있는 새 스토리보드를 소유하는 그룹입니다.

*priorityEffect*<br/>
pGroupScheduled에 높은 우선 순위가 있는 경우 pGroupNew에서 발생할 수 있는 효과입니다.

### <a name="return-value"></a>반환 값

pGroupNew에서 소유한 스토리보드가 우선인 경우 TRUE를 반환해야 합니다. pGroupScheduled에서 소유한 스토리보드가 우선인 경우 FALSE를 반환해야 합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnablePriorityComparisonHandler를 사용하여 우선 순위 비교 이벤트를 활성화하고 UI_ANIMATION_PHT_TRIM을 지정하는 경우 호출됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다. 에 대 한 자세한 정보에 대 한 읽기 Windows 애니메이션 API 설명서 [충돌 관리](/windows/desktop/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)합니다.

##  <a name="onstoryboardstatuschanged"></a>  CAnimationController::OnStoryboardStatusChanged

스토리 보드 상태 변경 되었을 때 프레임 워크에서 호출 됩니다.

```
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,
    UI_ANIMATION_STORYBOARD_STATUS newStatus,
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
상태 스토리 보드를 소유 하는 애니메이션 그룹에 대 한 포인터 변경 되었습니다.

*newStatus*<br/>
새 상태를 지정 합니다.

*previousStatus*<br/>
이전 상태를 지정합니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnableStoryboardEventHandler를 사용 하 여 스토리 보드 이벤트를 사용 하는 경우 호출 됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

##  <a name="onstoryboardupdated"></a>  CAnimationController::OnStoryboardUpdated

스토리 보드 업데이트 되었을 때 프레임 워크에서 호출 됩니다.

```
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>매개 변수

*pGroup*<br/>
스토리 보드를 소유 하는 그룹에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드는 CAnimationController::EnableStoryboardEventHandler를 사용 하 여 스토리 보드 이벤트를 사용 하는 경우 호출 됩니다. 응용 프로그램별 작업을 수행하기 위해 파생된 클래스에서 재정의될 수 있습니다.

##  <a name="removeallanimationgroups"></a>  CAnimationController::RemoveAllAnimationGroups

애니메이션 컨트롤러에서 모든 애니메이션 그룹을 제거합니다.

```
void RemoveAllAnimationGroups();
```

### <a name="remarks"></a>설명

모든 그룹이 삭제 해당 포인터를 응용 프로그램 수준에 저장 하는 경우 무효화 되어야 합니다. CAnimationGroup::m_bAutodestroyAnimationObjects 삭제할 그룹에 대해 TRUE 인 경우 해당 그룹에 속하는 모든 애니메이션 개체 삭제 됩니다. 그렇지 않으면 부모 애니메이션 컨트롤러에 해당 참조가 NULL로 설정 됩니다 하 고 다른 컨트롤러에 추가할 수 있습니다.

##  <a name="removeanimationgroup"></a>  CAnimationController::RemoveAnimationGroup

애니메이션 컨트롤러에서 지정한 ID 사용 하 여 애니메이션 그룹을 제거합니다.

```
void RemoveAnimationGroup(UINT32 nGroupID);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
애니메이션 그룹 ID를 지정 합니다.

### <a name="remarks"></a>설명

이 메서드는 내부 그룹 목록에서 애니메이션 그룹을 제거 하 고 삭제, 따라서 해당 애니메이션 그룹에 대 한 포인터를 저장 한 경우 무효화 시켜야 합니다. CAnimationGroup::m_bAutodestroyAnimationObjects TRUE 인 경우 해당 그룹에 속하는 모든 애니메이션 개체 삭제 됩니다. 그렇지 않으면 부모 애니메이션 컨트롤러에 해당 참조가 NULL로 설정 됩니다 하 고 다른 컨트롤러에 추가할 수 있습니다.

##  <a name="removeanimationobject"></a>  CAnimationController::RemoveAnimationObject

애니메이션 컨트롤러에서 애니메이션 개체를 제거 합니다.

```
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,
    BOOL bNoDelete = FALSE);
```

### <a name="parameters"></a>매개 변수

*pObject*<br/>
애니메이션 개체에 대 한 포인터입니다.

*bNoDelete*<br/>
이 매개 변수가 TRUE 이면 개체 제거 시 삭제 되지 않습니다.

### <a name="remarks"></a>설명

애니메이션 컨트롤러 및 애니메이션 그룹에서 애니메이션 개체를 제거합니다. 특정 개체를 더 이상 애니메이션 되지 경우 또는 다른 애니메이션 컨트롤러 개체를 이동 해야 할 경우이 함수를 호출 합니다. 다음 최근 기간의 사례 bNoDelete TRUE 여야 합니다.

##  <a name="removetransitions"></a>  CAnimationController::RemoveTransitions

전환이 지정된 된 그룹에 속하는 애니메이션 개체에서 제거 합니다.

```
void RemoveTransitions(UINT32 nGroupID);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
그룹 ID를 지정 합니다.

### <a name="remarks"></a>설명

그룹의 애니메이션 개체를 반복 하 고 각 애니메이션 개체에 대 한 ClearTransitions(FALSE)를 호출 합니다. 이 메서드는 애니메이션을 예약한 후 프레임 워크에서 호출 됩니다.

##  <a name="schedulegroup"></a>  CAnimationController::ScheduleGroup

애니메이션을 예약합니다.

```
BOOL ScheduleGroup(
    UINT32 nGroupID,
    UI_ANIMATION_SECONDS time = 0.0);
```

### <a name="parameters"></a>매개 변수

*nGroupID*<br/>
애니메이션을 예약 하려면 그룹 ID를 지정 합니다.

*time*<br/>
시간을 지정 합니다.

### <a name="return-value"></a>반환 값

애니메이션을 성공적으로 예약 된 경우 TRUE입니다. 스토리 보드를 만들어지지 않은, 또는 다른 오류가 발생 하는 경우에 FALSE입니다.

### <a name="remarks"></a>설명

AnimateGroup 이전 ScheduleGroup FALSE로 설정 하는 매개 변수 bScheduleNow를 사용 하 여 호출 해야 합니다. 원하는 애니메이션에 IUIAnimationTimer::GetTime에서 가져온 지정할 수 있습니다. 시간 매개 변수가 0.0 인 경우 애니메이션은 현재 시간에 대 한 예약 됩니다.

##  <a name="setrelatedwnd"></a>  CAnimationController::SetRelatedWnd

애니메이션 컨트롤러와 창 사이의 관계를 설정 합니다.

```
void SetRelatedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
창 개체 집합에 대 한 포인터입니다.

### <a name="remarks"></a>설명

관련된 CWnd 개체 설정 되 면 애니메이션 컨트롤러를 자동으로 업데이트할 수 그 (WM_PAINT 메시지를 보낼) 때 애니메이션 관리자의 상태가 변경 되었음을 또는 타이머 post 업데이트 이벤트가 발생 합니다.

##  <a name="updateanimationmanager"></a>  CAnimationController::UpdateAnimationManager

모든 애니메이션 변수의 값을 업데이트 하 여 애니메이션 관리자를 전달 합니다.

```
virtual void UpdateAnimationManager();
```

### <a name="remarks"></a>설명

이 메서드는 현재 애니메이션 관리자를 이동 하는 호출, 필요에 따라 스토리 보드의 상태를 변경 하 고 적절 한 애니메이션 변수를 업데이트 하는 중 값 보간됩니다. 내부적으로 IUIAnimationTimer::GetTime(timeNow) 및 IUIAnimationManager::Update(timeNow)이이 메서드를 호출 합니다. 이 동작을 사용자 지정 파생된 클래스에서이 메서드를 재정의 합니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
