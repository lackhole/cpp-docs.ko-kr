---
title: CMFCRibbonQuickAccessToolBarDefaultState 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
ms.openlocfilehash: 0ea9ec8de0b657fa4e7c601f9c3e676f550defa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380262"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState 클래스

리본 표시줄에 배치 되는 빠른 실행 도구 모음에 대 한 기본 상태를 관리 하는 도우미 클래스 ( [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)).

## <a name="syntax"></a>구문

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|`CMFCRibbonQuickAccessToolbarDefaultState` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|빠른 실행 도구 모음에 대 한 기본 상태는 명령을 추가합니다. 이 도구 모음 자체 변경 되지 않습니다.|
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|다른 속성 하나 빠른 실행 도구 모음을 복사합니다.|
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|빠른 실행 도구 모음에서 모든 명령을 제거합니다. 이 도구 모음 자체 변경 되지 않습니다.|

## <a name="remarks"></a>설명

응용 프로그램에서 빠른 실행 도구 모음을 만든 후 호출 하 여 기본 상태로 설정 하는 것이 좋습니다 [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)합니다. 클릭할 때이 기본 상태가 복원 되는 **재설정** 단추를 **사용자 지정** 응용 프로그램의 페이지 **옵션** 대화 상자.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCRibbonQuickAccessToolbarDefaultState` 클래스 및 빠른 실행 도구 모음에 대 한 기본 상태에 명령을 추가 하는 방법입니다.

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxribbonquickaccesstoolbar.h

##  <a name="addcommand"></a>  CMFCRibbonQuickAccessToolBarDefaultState::AddCommand

빠른 실행 도구 모음에 대 한 기본 상태는 명령을 추가합니다.

```
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>매개 변수

*[in] uiCmd*<br/>
명령 ID를 지정 합니다.

*[in] bIsVisible*<br/>
빠른 실행 도구 모음 기본 상태인 경우 명령의 표시 유형을 설정 합니다.

### <a name="remarks"></a>설명

세 개의 결과 수행 합니다 CMFCRibbonQuickAccessToolBarDefaultState에 명령 추가 합니다. 첫째, 각 추가 명령 빠른 실행 도구 모음의 오른쪽에 드롭다운에 나열 됩니다. 이런 방식으로 사용자는 추가 하거나 빠른 실행 도구 모음에서 해당 명령을 제거 쉽게 수 있습니다. 표시할 나와 있는 명령만 표시 기본 상태에서는 사용자가 클릭할 때 빠른 실행 도구 모음 다시 설정 됩니다 둘째, 합니다 **재설정** 단추를 **사용자 지정** 대화 상자. 세 번째 호출 하지 않은 경우 [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), 빠른 실행 도구 모음 표시 되는 명령을 사용이 목록에서 기본 표시 명령으로 처음으로 사용자 응용 프로그램을 실행 합니다. 원하는 모든 명령에 추가한 후에 호출 [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) 는 리본 표시줄의 빠른 실행 도구 모음에 대 한 기본 상태로이 인스턴스를 설정 합니다.

##  <a name="copyfrom"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom

다른 속성 하나 빠른 실행 도구 모음을 복사합니다.

```
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
[in] 원본에 대 한 참조를 `CMFCRibbonQuickAccessToolBarDefaultState` 복사할 개체입니다.

### <a name="remarks"></a>설명

이 메서드는 소스에서 각 명령 복사 `CMFCRibbonQuickAccessToolBarDefaultState` 개체를 사용 하 여이 개체는 [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) 메서드.

##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState

빠른 실행 도구 모음 기본 상태 개체를 생성합니다.

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>설명

기본적으로 목록 명령의의 새 인스턴스 [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) 포함 비어 있습니다.

##  <a name="removeall"></a>  CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll

빠른 실행 도구 모음에 대 한 기본 명령의 목록을 지웁니다.

```
void RemoveAll();
```

### <a name="remarks"></a>설명

이 함수는 모든 명령을이 인스턴스에서 제거 하는에 대 한 이전 호출 [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) 추가 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)
