---
title: CMDIFrameWnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
ms.openlocfilehash: 9f5289491a7c14749865cfd163417440bc542aba
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776533"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd 클래스

창 관리 멤버와 함께 Windows MDI(다중 문서 인터페이스) 프레임 창 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|`CMDIFrameWnd`를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMDIFrameWnd::CreateClient](#createclient)|이 대 한 Windows MDICLIENT 창 만듭니다 `CMDIFrameWnd`합니다. 에 의해 호출 된 `OnCreate` 멤버 함수 `CWnd`합니다.|
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|새 자식 창을 만듭니다.|
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|창 팝업 메뉴를 반환합니다.|
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|다른 MDI 자식 창을 활성화합니다.|
|[CMDIFrameWnd::MDICascade](#mdicascade)|종속 연결 된 형식으로 모든 자식 창을 정렬합니다.|
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|자식 최대화할지 여부 나타내는 플래그와 함께 현재 활성 상태인 MDI 자식 창을 검색 합니다.|
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|모든 최소화 된 문서의 자식 창을 정렬합니다.|
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|MDI 자식 창을 최대화합니다.|
|[CMDIFrameWnd::MDINext](#mdinext)|현재 활성 자식 창 바로 뒤 자식 창을 활성화 한 현재 활성 자식 창에는 다른 모든 자식 창 뒤에 배치 합니다.|
|[CMDIFrameWnd::MDIPrev](#mdiprev)|이전 자식 창을 활성화 한 현재 활성 자식 창 바로 뒤에 배치 합니다.|
|[CMDIFrameWnd::MDIRestore](#mdirestore)|MDI 자식 창 최대화 또는 최소화 된 크기에서 복원합니다.|
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|MDI 프레임 창의 메뉴, 창 팝업 메뉴 또는 둘 다를 대체합니다.|
|[CMDIFrameWnd::MDITile](#mditile)|모든 자식 창을 바둑판식으로 배열 된 형식으로 정렬합니다.|

## <a name="remarks"></a>설명

응용 프로그램에 대 한 유용한 MDI 프레임 창을 만들려면에서 클래스를 파생 `CMDIFrameWnd`합니다. 응용 프로그램 관련 데이터를 저장 하 고 파생된 클래스에 멤버 변수를 추가 합니다. 파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.

MDI 프레임 창에 호출 하 여 생성할 수 있습니다 합니다 [Create](../../mfc/reference/cframewnd-class.md#create) 또는 [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) 멤버 함수 `CFrameWnd`합니다.

호출 하기 전에 `Create` 하거나 `LoadFrame`, c + +를 사용 하 여 힙에서 프레임 창 개체를 생성 해야 **새** 연산자. 호출 하기 전에 `Create` 사용 하 여 창 클래스를 등록할 수도 있습니다는 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 프레임에 대 한 아이콘 및 클래스 스타일을 설정 하려면 전역 함수입니다.

사용 된 `Create` 프레임의 생성 매개 변수를 즉시 인수를 전달 하는 멤버 함수입니다.

`LoadFrame` 보다 적은 인수가 필요 `Create`, 대신 프레임 캡션, 아이콘, 액셀러레이터 키 테이블 및 메뉴를 포함 하 여 리소스에서 대부분의 해당 기본 값을 검색 합니다. 에 액세스할 수 있도록 `LoadFrame`, 이러한 모든 리소스는 동일한 리소스 ID (예를 들어 IDR_MAINFRAME) 있어야 합니다.

하지만 `MDIFrameWnd` 에서 파생 됩니다 `CFrameWnd`, 프레임 창 클래스에서 파생 된 `CMDIFrameWnd` 로 선언 되지 해야 `DECLARE_DYNCREATE`합니다.

합니다 `CMDIFrameWnd` 클래스는 대부분의 기본 구현을 상속 `CFrameWnd`합니다. 이러한 기능의 자세한 목록은 참조 합니다 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스 설명 합니다. `CMDIFrameWnd` 클래스에 다음 추가 기능:

- MDI 프레임 창은 컨트롤 막대를 사용 하 여 함께 MDICLIENT 창에서 관리 합니다. MDI 클라이언트 창을 MDI 자식 프레임 창의 부모가 직접입니다. 에 지정 된 WS_HSCROLL 및 WS_VSCROLL 창 스타일을 `CMDIFrameWnd` MDI 클라이언트 창을 적용할 사용자 MDI 클라이언트 영역 (에서처럼 Windows 프로그램 관리자, 예를 들어)을 스크롤할 수 있도록 주 프레임 창 대신 합니다.

- MDI 프레임 창은 활성 MDI 자식 창에 없는 경우 메뉴 모음으로 사용 되는 기본 메뉴를 소유 합니다. 활성 MDI 자식 경우 MDI 프레임 창의 메뉴 모음 MDI 자식 창 메뉴에 의해 자동으로 바뀝니다.

- MDI 프레임 창에 있는 경우 현재 MDI 자식 창, 함께에서 작동 합니다. 예를 들어 명령 메시지 전에 MDI 프레임 창은 현재 활성 상태인 MDI 자식으로 위임 됩니다.

- MDI 프레임 창에는 다음 표준 창 메뉴 명령에 대 한 기본 처리기에 있습니다.

    - ID_WINDOW_TILE_VERT

    - ID_WINDOW_TILE_HORZ

    - ID_WINDOW_CASCADE

    - ID_WINDOW_ARRANGE

- MDI 프레임 창에 새 프레임을 현재 문서에서 보기를 만드는 ID_WINDOW_NEW 구현의 있습니다. 응용 프로그램은 MDI 창을 처리에 맞게 이러한 기본 명령 구현을 재정의할 수 있습니다.

C + +를 사용 하지 마세요 **삭제** 프레임 창 제거 하는 연산자입니다. 대신 `CWnd::DestroyWindow`를 사용하세요. 합니다 `CFrameWnd` 구현의 `PostNcDestroy` 창이 소멸 될 때 c + + 개체를 삭제 됩니다. 사용자의 기본 프레임 창에 닫을 때 `OnClose` 처리기를 호출 하는 `DestroyWindow`합니다.

에 대 한 자세한 `CMDIFrameWnd`를 참조 하세요 [프레임 Windows](../../mfc/frame-windows.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cmdiframewnd"></a>  CMDIFrameWnd::CMDIFrameWnd

`CMDIFrameWnd` 개체를 생성합니다.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>설명

호출 된 `Create` 또는 `LoadFrame` 멤버 함수를 표시 하는 MDI 프레임 창을 만듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

##  <a name="createclient"></a>  CMDIFrameWnd::CreateClient

관리 하는 MDI 클라이언트 창을 만듭니다.는 `CMDIChildWnd` 개체입니다.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>매개 변수

*lpCreateStruct*<br/>
에 대 한 긴 포인터를 [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) 구조입니다.

*pWindowMenu*<br/>
팝업 창 메뉴에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

재정의 하는 경우이 멤버 함수를 호출 해야 합니다 `OnCreate` 멤버 함수를 직접.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

##  <a name="createnewchild"></a>  CMDIFrameWnd::CreateNewChild

새 자식 창을 만듭니다.

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>매개 변수

*pClass*<br/>
만들 자식 창의 런타임 클래스입니다.

*nResource*<br/>
자식 창에 연결 된 공유 리소스의 ID입니다.

*hMenu*<br/>
자식 창의 메뉴입니다.

*hAccel*<br/>
자식 창의 가속기입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 자식 MDI 프레임 창에 창을 만들 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

##  <a name="getwindowmenupopup"></a>  CMDIFrameWnd::GetWindowMenuPopup

이름이 "창" (MDI 창 관리에 대 한 메뉴 항목을 사용 하 여 팝업 메뉴) 인 현재 팝업 메뉴에 핸들을 얻기 위해이 멤버 함수를 호출 합니다.

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>매개 변수

*hMenuBar*<br/>
현재 메뉴 모음입니다.

### <a name="return-value"></a>반환 값

있는 경우 창 팝업 메뉴 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

기본 구현은 ID_WINDOW_NEW ID_WINDOW_TILE_HORZ 등 표준 창 메뉴 명령이 포함 된 팝업 메뉴를 찾습니다.

표준 메뉴 명령 Id를 사용 하지 않는 창 메뉴에 있는 경우이 멤버 함수를 재정의 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

##  <a name="mdiactivate"></a>  CMDIFrameWnd::MDIActivate

다른 MDI 자식 창을 활성화합니다.

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>매개 변수

*pWndActivate*<br/>
MDI 자식 창에 활성화를 가리킵니다.

### <a name="remarks"></a>설명

이 멤버 함수는 [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) 자식 창을 활성화와 비활성화 되 고 자식 창에는 메시지입니다.

사용자는 마우스나 키보드를 사용 하 여 MDI 자식 창에 포커스를 변경 하는 경우 전송 되는 동일한 메시지입니다.

> [!NOTE]
>  MDI 자식 창에는 MDI 프레임 창을 독립적으로 활성화 됩니다. 자식 창에 마지막으로 활성화 된 프레임을 활성화 하는 경우 전송 됩니다는 [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) 메시지는 활성 창 프레임 및 캡션 표시줄 하지만 그릴 다른 WM_MDIACTIVATE 메시지를 수신 하지 않습니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)합니다.

##  <a name="mdicascade"></a>  CMDIFrameWnd::MDICascade

계단식 배열 형식에서 모든 MDI 자식 창을 정렬합니다.

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>매개 변수

*nType*<br/>
Cascade 플래그를 지정합니다. 다음 플래그를 지정할 수 있습니다. MDITILE_SKIPDISABLED 비활성화 된 MDI 자식 창을 연계 되 고 않도록 하는 합니다.

### <a name="remarks"></a>설명

첫 번째 버전 `MDICascade`, 매개 변수 없이 사용 안 함 작업을 포함 하 여 모든 MDI 자식 창, 계단식으로 배열 합니다. 에 대 한 MDITILE_SKIPDISABLED를 지정 하는 경우 필요에 따라 두 번째 버전은 사용 하지 않도록 설정 하는 하위 MDI 자식 창이 아니라 않습니다 합니다 *n 형식* 매개 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

##  <a name="mdigetactive"></a>  CMDIFrameWnd::MDIGetActive

현재 활성 MDI 자식 창 자식 창을 최대화 되었는지 여부를 나타내는 플래그와 함께 검색 합니다.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>매개 변수

*pbMaximized*<br/>
BOOL 반환 값에 대 한 포인터입니다. 최대화; 있으면 반환이 TRUE로 설정 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

활성 MDI 자식 창에 대 한 포인터입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)합니다.

##  <a name="mdiiconarrange"></a>  CMDIFrameWnd::MDIIconArrange

모든 최소화 된 문서의 자식 창을 정렬합니다.

```
void MDIIconArrange();
```

### <a name="remarks"></a>설명

자식 창을 최소화 되도록 하지는 영향을 주지 않습니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMDIFrameWnd::MDICascade](#mdicascade)합니다.

##  <a name="mdimaximize"></a>  CMDIFrameWnd::MDIMaximize

지정 된 MDI 자식 창을 최대화합니다.

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
창 최대화를 가리킵니다.

### <a name="remarks"></a>설명

자식 창 최대화 되었을 때 Windows 하 고 클라이언트 창 해당 클라이언트 영역 크기가 조정 됩니다. Windows는 사용자 복원 하거나 자식 창을 닫을 수 있도록 프레임의 메뉴 모음에서 자식 창의 컨트롤 메뉴를 배치 합니다. 또한 자식 창의 제목을 프레임 창 제목에 추가합니다.

현재 활성 상태인 MDI 자식 창을 최대화 하면 MDI 자식 창에 다른 활성화 된 경우 Windows는 현재 활성 자식 복원 하 고 새로 활성화 된 자식 창을 최대화 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)합니다.

##  <a name="mdinext"></a>  CMDIFrameWnd::MDINext

현재 활성 자식 창 바로 뒤 자식 창을 활성화 한 현재 활성 자식 창에는 다른 모든 자식 창 뒤에 배치 합니다.

```
void MDINext();
```

### <a name="remarks"></a>설명

현재 활성 상태인 MDI 자식 창을 최대화 되 면 멤버 함수는 현재 활성 자식 복원 하 고 새로 활성화 된 자식을 최대화 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

##  <a name="mdiprev"></a>  CMDIFrameWnd::MDIPrev

이전 자식 창을 활성화 한 현재 활성 자식 창 바로 뒤에 배치 합니다.

```
void MDIPrev();
```

### <a name="remarks"></a>설명

현재 활성 상태인 MDI 자식 창을 최대화 되 면 멤버 함수는 현재 활성 자식 복원 하 고 새로 활성화 된 자식을 최대화 합니다.

##  <a name="mdirestore"></a>  CMDIFrameWnd::MDIRestore

MDI 자식 창 최대화 또는 최소화 된 크기에서 복원합니다.

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
복원할 창입니다를 가리킵니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore)합니다.

##  <a name="mdisetmenu"></a>  CMDIFrameWnd::MDISetMenu

MDI 프레임 창의 메뉴, 창 팝업 메뉴 또는 둘 다를 대체합니다.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>매개 변수

*pFrameMenu*<br/>
새 프레임 창 메뉴의 메뉴를 지정합니다. NULL 인 경우에 메뉴 변경 되지 않습니다.

*pWindowMenu*<br/>
새 창이 팝업 메뉴의 메뉴를 지정합니다. NULL 인 경우에 메뉴 변경 되지 않습니다.

### <a name="return-value"></a>반환 값

이 메시지에서 대체 프레임 창 메뉴에 대 한 포인터입니다. 해당 포인터는 임시적이며, 나중에 사용하려고 저장하면 안됩니다.

### <a name="remarks"></a>설명

호출한 후 `MDISetMenu`, 응용 프로그램에서 호출 해야 합니다 [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) 멤버 함수 `CWnd` 메뉴 표시줄을 업데이트 하 합니다.

이 호출은 창 팝업 메뉴를 대체 하는 경우 MDI 자식 창 메뉴 항목 이전 창 메뉴에서 제거 되 고 새 창 팝업 메뉴에 추가 합니다.

MDI 자식 창 최대화 하 고 MDI 프레임 창 메뉴를 대체 하는이 호출을 하는 경우 컨트롤 메뉴 및 복원 컨트롤 이전 프레임 창 메뉴에서 제거 되 고 새 메뉴에 추가 합니다.

MDI 자식 창을 관리 하는 프레임 워크를 사용 하는 경우에이 멤버 함수를 호출 하지 마세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

##  <a name="mditile"></a>  CMDIFrameWnd::MDITile

모든 자식 창을 바둑판식으로 배열 된 형식으로 정렬합니다.

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>매개 변수

*nType*<br/>
바둑판식 배열 플래그를 지정합니다. 이 매개 변수는 다음 플래그 중 하나일 수 있습니다.

- MDITILE_HORIZONTAL 타일 MDI 자식 창 위의 다른 하나는 창 표시 되도록 합니다.

- MDITILE_SKIPDISABLED 방지 되 고 바둑판식으로 배열에서 MDI 자식 창을 사용할 수 없습니다.

- MDITILE_VERTICAL 타일 MDI 자식 창 옆에 있는 다른 하나는 창 표시 되도록 합니다.

### <a name="remarks"></a>설명

첫 번째 버전 `MDITile`, 매개 변수 없이 Windows 버전 3.1 이상에서 세로로 창을 바둑판식으로 배열 합니다. 두 번째 버전 창을 바둑판식으로 배열 세로 또는 가로로 값에 따라 합니다 *n 형식* 매개 변수입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CMDIFrameWnd::MDICascade](#mdicascade)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CMDIChildWnd 클래스](../../mfc/reference/cmdichildwnd-class.md)
