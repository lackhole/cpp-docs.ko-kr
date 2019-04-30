---
title: CMFCRibbonMainPanel 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
ms.openlocfilehash: e4bd1ab8cffc87d5079518cf9a1d6e430ca40fd9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403596"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel 클래스

클릭할 때 표시 되는 리본 패널을 구현 합니다 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|기본 생성자입니다.|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonMainPanel::Add](#add)|응용 프로그램 단추 패널의 왼쪽된 창에는 리본 요소를 추가합니다. (재정의 [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|최근 파일 목록 메뉴에 텍스트 문자열을 추가합니다.|
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|리본 응용 프로그램 패널의 아래쪽 창에는 리본 요소를 추가합니다.|
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|응용 프로그램 단추 패널의 오른쪽 창에는 리본 요소를 추가합니다.|
|`CMFCRibbonMainPanel::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|리본의 주 패널의 영역을 나타내는 사각형을 반환 합니다.|
|`CMFCRibbonMainPanel::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|

## <a name="remarks"></a>설명

프레임 워크가 표시는 `CMFCRibbonMainPanel` 응용 프로그램 패널을 열 때. 세 개의 창이 포함 됩니다.

- 왼쪽된 창에 파일을 같은 연관 된 명령을 **엽니다**, **저장**를 **인쇄**, 및 **닫기**합니다. 이 창에 명령을 추가 하려면 호출 [CMFCRibbonMainPanel::Add](#add)합니다.

- 오른쪽 창의 왼쪽된 창에서 클릭 하는 명령을 수정 하는 옵션을 포함 합니다. 예를 들어를 클릭 하면 **다른 이름으로 저장** 왼쪽된 창에서 오른쪽 창에는 사용 가능한 파일 형식을 표시할 수 있습니다. 이 창에 항목 추가 호출 [CMFCRibbonMainPanel::AddToRight](#addtoright)합니다.

- 아래쪽 창에 응용 프로그램의 설정을 변경 하 고 프로그램을 종료할 수 있도록 하는 단추가 있습니다. 이 창에 항목 추가 호출 [CMFCRibbonMainPanel::AddToBottom](#addtobottom)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonMainPanel.h

##  <a name="add"></a>  CMFCRibbonMainPanel::Add

응용 프로그램 단추 패널의 왼쪽된 창에는 리본 요소를 추가합니다.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>매개 변수

*pElem*<br/>
[out에서] 주 패널에 추가 하려면 리본 요소에 대 한 포인터입니다.

### <a name="remarks"></a>설명

패널에 리본 요소를 추가합니다. 이 메서드를 사용 하 여 추가 된 요소는 기본 패널의 왼쪽된 열에 배치 됩니다.

##  <a name="addrecentfileslist"></a>  CMFCRibbonMainPanel::AddRecentFilesList

최근 파일 목록 메뉴에 텍스트 문자열을 추가합니다.

```
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
최근 파일 목록에 추가할 문자열을 지정 합니다.

*nWidth*<br/>
최근 파일 목록 패널의 픽셀에서 너비를 지정 합니다.

### <a name="remarks"></a>설명

##  <a name="addtobottom"></a>  CMFCRibbonMainPanel::AddToBottom

리본 응용 프로그램 패널의 아래쪽 창에는 리본 요소를 추가합니다.

```
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>매개 변수

*pElem*<br/>
[out에서] 주 패널의 맨 아래에 추가 하려면 리본 요소에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="addtoright"></a>  CMFCRibbonMainPanel::AddToRight

응용 프로그램 단추 패널의 오른쪽 창에는 리본 요소를 추가합니다.

```
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>매개 변수

*pElem*<br/>
주 패널의 오른쪽에 추가 될 리본 요소에 대 한 포인터입니다.

*nWidth*<br/>
오른쪽 패널의 픽셀에서 너비를 지정 합니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 오른쪽 패널에 리본 요소를 추가 합니다. 오른쪽 패널에는 일반적으로 최근 파일 목록 표시 하지만 다른 리본 요소 다음에 추가할 수 있습니다.

##  <a name="getcommandsframe"></a>  CMFCRibbonMainPanel::GetCommandsFrame

리본의 주 패널의 영역을 나타내는 사각형을 반환 합니다.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>반환 값

리본의 주 패널의 영역을 나타내는 사각형입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel 클래스](../../mfc/reference/cmfcribbonpanel-class.md)
