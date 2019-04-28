---
title: CMFCToolBarDateTimeCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
ms.openlocfilehash: dfe1d3dc058371dd13cc335968b9c3a89e057da2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218477"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl 클래스

날짜 및 시간 선택 컨트롤을 포함 하는 도구 모음 단추입니다.

## <a name="syntax"></a>구문

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|`CMFCToolBarDateTimeCtrl` 개체를 생성합니다.|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|사용자가 사용자 지정 하는 동안 단추를 확장할 수 있는지 여부를 지정 합니다. (재정의 [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|현재 단추에 다른 도구 모음 단추의 속성을 복사합니다. (재정의 [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|나중에 사용하기 위해 예약되어 있습니다.|
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|도구 모음 단추에서 메뉴에 텍스트를 복사 합니다.|
|`CMFCToolBarDateTimeCtrl::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|첫 번째 검색 `CMFCToolBarDateTimeCtrl` 지정한 명령 id입니다. 응용 프로그램의 개체|
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|날짜 및 시간 선택 컨트롤에 대 한 포인터를 반환합니다.|
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|도구 모음 단추와 연결 된 창 핸들을 검색 합니다. (재정의 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|날짜 및 시간 선택 컨트롤에서 선택한 시간을 가져오고 지정 된 배치 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 구조입니다.|
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|지정 된 명령 ID가 있는 시간 선택 컨트롤 단추에서 선택한 시간을 반환 합니다.|
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|사용자가 단추를 선택할 때 단추의 테두리가 표시 되는지 여부를 결정 합니다. (재정의 [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|단추를 처리 하는지 여부를 지정 합니다 [WM_COMMAND](/windows/desktop/menurc/wm-command) 메시지입니다. (재정의 [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|단추를 추가할 때 프레임 워크에서 호출을 **사용자 지정** 대화 상자. (재정의 [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|지정 된 디바이스 컨텍스트 및 도킹 상태에 대 한 단추의 크기를 계산 하기 위해 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|새 도구 모음에 단추를 삽입할 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|사용자가 컨트롤을 클릭할 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|부모 도구 모음에서 WM_CTLCOLOR 메시지를 처리 하는 경우 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리기 위해 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|단추를 그리기 위해 프레임 워크에서 호출 합니다 **명령** 창 합니다 **사용자 지정** 대화 상자. (재정의 [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|전역 글꼴 변경 되었을 때 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|부모 도구 모음 이동 하면 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|프레임 워크 호출 단추 되 면 표시 되거나 숨겨지도록입니다. (재정의 [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|부모 도구 모음 크기를 변경 하거나 크기를 변경 하려면 단추를 사용 하면 위치 및이 변경 하는 경우 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|부모 도구 모음 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다. (재정의 [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|보관 파일에서이 개체를 읽거나 보관 파일에 씁니다 (재정의 [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|도구 모음 단추의 스타일을 설정합니다. (재정의 [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|시간 선택 컨트롤에서 날짜 및 시간을 설정합니다.|
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|지정 된 명령 ID를 갖습니다 시간 선택 컨트롤의 모든 인스턴스에서 날짜 및 시간 설정|

## <a name="remarks"></a>설명

날짜 및 시간 선택 컨트롤을 사용 하는 방법의 예로, ToolbarDateTimePicker 샘플 프로젝트를 참조 하세요. 도구 모음 단추 컨트롤을 추가 하는 방법에 대 한 정보를 참조 하세요. [연습: 도구 모음에 컨트롤 넣기](../../mfc/walkthrough-putting-controls-on-toolbars.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbardatetimectrl.h

##  <a name="canbestretched"></a>  CMFCToolBarDateTimeCtrl::CanBeStretched

사용자가 사용자 지정 하는 동안 단추를 확장할 수 있는지 여부를 지정 합니다.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>반환 값

이 메서드는 TRUE를 반환합니다.

### <a name="remarks"></a>설명

기본적으로 프레임 워크 사용자 지정 하는 동안 도구 모음 단추를 확장 하는 사용자를 허용 하지 않습니다. 이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched))에서 사용자 지정 날짜 및 시간 도구 모음 단추를 확장할 수 있도록 허용 합니다.

##  <a name="cmfctoolbardatetimectrl"></a>  CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl

만들고 초기화 된 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md) 개체입니다.

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>매개 변수

*uiID*<br/>
[in] 컨트롤 id입니다.

*iImage*<br/>
[in] 도구 모음 이미지의 인덱스 `CMFCToolBarImages` 개체입니다.

*dwStyle*<br/>
[in] 스타일을 `CMFCToolBarDateTimeCtrlImpl` 단추를 클릭할 때 생성 되는 창입니다.

*iWidth*<br/>
[in] 픽셀 단위의 컨트롤의 너비입니다.

### <a name="remarks"></a>설명

이 개체는 시스템 날짜 및 시간으로 초기화 됩니다. 내부 창 스타일 `CMFCToolBarDateTimeCtrlImpl` 개체를 포함 합니다 *dwStyle* 매개 변수 및 WS_CHILD 및 WS_VISIBLE 스타일입니다. 사용 하 여 이러한 스타일을 변경할 수 없습니다 `CMFCToolBarDateTimeCtrl::SetStyle`합니다. 사용 하 여 `SetStyle` 의 스타일을 변경 하는 `CMFCToolBarDateTimeCtrl` 제어 합니다.

### <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCToolBarDateTimeCtrl` 클래스입니다. 이 코드 조각은의 일부인 합니다 [도구 모음 날짜 시간 선택 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

##  <a name="copyfrom"></a>  CMFCToolBarDateTimeCtrl::CopyFrom

현재 단추에 다른 도구 모음 단추의 속성을 복사합니다.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>매개 변수

*src*<br/>
[in] 복사할 소스 단추에 대 한 참조입니다.

### <a name="remarks"></a>설명

이 도구 모음 단추를 도구 모음 단추 복사 하려면이 메서드를 호출 합니다. *src* 형식 이어야 합니다 `CMFCToolBarDateTimeCtrl`합니다.

##  <a name="exporttomenubutton"></a>  CMFCToolBarDateTimeCtrl::ExportToMenuButton

도구 모음 단추에서 메뉴에 텍스트를 복사 합니다.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>매개 변수

*menuButton*<br/>
[in] 대상 메뉴 단추에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

이 메서드는 TRUE를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) 컨트롤의 명령 ID와 연결 된 문자열 리소스를 로드 합니다. 문자열 리소스에 대 한 자세한 내용은 참조 하세요. [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring)합니다.

##  <a name="getbycmd"></a>  CMFCToolBarDateTimeCtrl::GetByCmd

첫 번째 검색 `CMFCToolBarDateTimeCtrl` 지정한 명령 id입니다. 응용 프로그램의 개체

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 검색할 단추의 명령 ID입니다.

### <a name="return-value"></a>반환 값

첫 번째 `CMFCToolBarDateTimeCtrl` 개체가 없으면 NULL을 지정 된 명령 ID를 가진 응용 프로그램에서 `CMFCToolBarDateTimeCtrl` 개체에 지정 된 명령 id입니다.

### <a name="remarks"></a>설명

이 공유 유틸리티 메서드 같은 방법으로 사용 됩니다 [CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall) 하 고 [CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall) 가져오거나에 있는 모든 인스턴스의 날짜와 시간을 설정 하려면 지정 된 명령 ID가 선택 컨트롤

##  <a name="getdatetimectrl"></a>  CMFCToolBarDateTimeCtrl::GetDateTimeCtrl

날짜 및 시간 선택 컨트롤에 대 한 포인터를 반환합니다.

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>반환 값

날짜 및 시간 선택 컨트롤에 대 한 포인터 또는 컨트롤에 없는 경우 NULL입니다.

### <a name="remarks"></a>설명

`CMFCToolBarDateTimeCtrl` 초기화 클래스는 `m_pWndDateTime` 데이터 멤버를 삽입할 때를 `CMFCToolBarDateTimeCtrl` 도구 모음에는 개체입니다.

##  <a name="gethwnd"></a>  CMFCToolBarDateTimeCtrl::GetHwnd

도구 모음 단추와 연결 된 창 핸들을 검색 합니다.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>반환 값

날짜 및 시간 도구 모음 단추와 연결 된 창 핸들입니다.

### <a name="remarks"></a>설명

이 메서드를 재정의 합니다 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) 메서드.

##  <a name="gettime"></a>  CMFCToolBarDateTimeCtrl::GetTime

지정 된 배치 및 연결 된 날짜 및 시간 선택 컨트롤에서 선택한 시간을 가져옵니다 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 구조

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>매개 변수

*timeDest*<br/>
[out] 첫 번째 오버 로드에는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 시스템 시간 정보를 받게 될 개체입니다. 두 번째 오버 로드에는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 시스템 시간 정보를 받게 될 개체입니다.

*pTimeDest*<br/>
[out] 에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 시스템 시간 정보를 받는 구조체입니다. NULL이 아니어야 합니다.

### <a name="return-value"></a>반환 값

첫 번째 오버 로드에서 시간에 성공적으로 작성 되는 경우 0이 아닌 값을 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 개체 그렇지 않으면 0입니다. 두 번째 및 세 번째 오버 로드의 반환 값은 DWORD에 설정 된 dwFlag 멤버에 해당 합니다 [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) 구조입니다.

### <a name="remarks"></a>설명

메서드 집합을 [NMDATETIMECHANGE](/windows/desktop/api/commctrl/ns-commctrl-tagnmdatetimechange) 멤버 dwFlags 날짜 및 시간 선택 된 날짜 및 시간으로 설정 되었는지 여부를 나타내는 구조체입니다. 로 설정 되어 값 GDT_NONE 같으면 `no date` 상태 DTS_SHOWNONE 스타일을 사용 합니다. 반환 된 값 GDT_VALID 같으면 시스템 시간 대상 위치에 성공적으로 저장 됩니다.

##  <a name="gettimeall"></a>  CMFCToolBarDateTimeCtrl::GetTimeAll

지정한 명령 ID가 있는 시간 선택 컨트롤 단추에서 사용자가 선택한 시간을 반환 합니다.

```
static BOOL GetTimeAll(
    UINT uiCmd,
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeDest);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 도구 모음 단추의 명령 ID를 지정 합니다.

*timeDest*<br/>
[out] 첫 번째 오버 로드에는 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 시스템 시간 정보를 받게 될 개체입니다. 두 번째 오버 로드에는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 시스템 시간 정보를 받게 될 개체입니다.

*pTimeDest*<br/>
[out] 에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 시스템 시간 정보를 받는 구조체입니다. NULL이 아니어야 합니다.

### <a name="return-value"></a>반환 값

프레임 워크 도구 모음 단추의 명령 ID와 일치 하는 경우 찾을 수 없습니다 *uiCmd*, 반환 값은 첫 번째 오버 로드에는 0과 다른 오버 로드에서 GDT_NONE 합니다. 도구 모음 단추가 있으면 반환 값은 호출에서 반환 값과 같으면 [CMFCToolBarDateTimeCtrl::GetTime](#gettime) 는 단추입니다. 반환 값 0 또는 GDT_NONE 단추 발견 되 면 나타냅니다 발생할 수 있습니다에 대 한 호출 `GetTime` 다른 이유로 유효한 날짜를 반환 하지 않았습니다.

### <a name="remarks"></a>설명

이 메서드가 지정 된 명령 ID 및 호출이 있는 도구 모음 단추를 찾습니다 [CMFCToolBarDateTimeCtrl::GetTime](#gettime) 메서드는 단추입니다.

##  <a name="havehotborder"></a>  CMFCToolBarDateTimeCtrl::HaveHotBorder

사용자가 단추를 선택할 때 단추의 테두리가 표시 되는지 여부를 결정 합니다.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>반환 값

단추를 선택 하는 경우의 테두리를 표시 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드는 컨트롤이 표시 되 면 0이 아닌 값을 반환 합니다.

##  <a name="notifycommand"></a>  CMFCToolBarDateTimeCtrl::NotifyCommand

단추를 처리 하는지 여부를 지정 합니다 [WM_COMMAND](/windows/desktop/menurc/wm-command) 메시지입니다.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>매개 변수

*iNotifyCode*<br/>
[in] 명령과 사용 하 여 연결 된 알림 메시지입니다.

### <a name="return-value"></a>반환 값

WM_COMMAND 메시지 또는 FALSE를 나타내는 부모 도구 모음에서 메시지를 처리 해야 하는 단추 처리 하는 경우 TRUE입니다.

### <a name="remarks"></a>설명

프레임 워크를 보내려는 경우이 메서드를 호출을 [WM_COMMAND](/windows/desktop/menurc/wm-command) 부모 창에는 메시지입니다.

이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand))를 처리 하는 [DTN_DATETIMECHANGE](/windows/desktop/Controls/dtn-datetimechange) 알림. 내부 시간 상태를 업데이트 하 고 모든 시간 속성을 업데이트 `CMFCToolBarDateTimeCtrl` 동일한 개체 명령 id입니다.

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarDateTimeCtrl::OnAddToCustomizePage

단추를 추가할 때 프레임 워크에서 호출을 **사용자 지정** 대화 상자.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>설명

이 메서드가 확장 기본 클래스 구현을 [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)에서 첫 번째 날짜에서 속성을 복사 및 시간에서이 개체와 같은 명령 ID를 가진 모든 도구 모음 컨트롤입니다. 이 메서드는 아무 효과도 없습니다 없는 도구 모음에는 날짜 및 시간 컨트롤을이 개체와 같은 명령 ID입니다.

에 대 한 자세한 내용은 합니다 **사용자 지정** 대화 상자, 참조 [CMFCToolBarsCustomizeDialog 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)합니다.

##  <a name="onchangeparentwnd"></a>  CMFCToolBarDateTimeCtrl::OnChangeParentWnd

새 도구 모음에 단추를 삽입할 때 프레임 워크에서 호출 됩니다.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 새 부모 창입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) 내부 다시 만들어 `CMFCToolBarDateTimeCtrlImpl` 개체입니다.

##  <a name="onclick"></a>  CMFCToolBarDateTimeCtrl::OnClick

사용자가 컨트롤을 클릭할 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 사용 되지 않습니다.

*bDelay*<br/>
[in] 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

단추 클릭 메시지를 처리 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 재정의 [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), 경우 0이 아닌 값을 반환 하 여 내부 `CMFCToolBarDateTimeCtrlImpl` 개체를 표시 합니다.

##  <a name="onctlcolor"></a>  CMFCToolBarDateTimeCtrl::OnCtlColor

부모 도구 모음에서 WM_CTLCOLOR 메시지를 처리 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 단추를 표시 하는 장치 컨텍스트.

*nCtlColor*<br/>
[in] 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

단추의 배경을 그릴 프레임 워크를 사용 하는 전역 브러시에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 재정의 [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)에서 텍스트를 설정 및 제공 된 장치 컨텍스트 전역 텍스트의 색 및 배경 색을 각각 백그라운드 합니다.

응용 프로그램에 사용할 수 있는 전역 옵션에 대 한 자세한 내용은 참조 하세요. [AFX_GLOBAL_DATA 구조체](../../mfc/reference/afx-global-data-structure.md)합니다.

##  <a name="onglobalfontschanged"></a>  CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged

전역 글꼴 변경 되었을 때 프레임 워크에서 호출 됩니다.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) 전역 글꼴의 컨트롤의 글꼴을 변경 하 여 합니다.

응용 프로그램에 사용할 수 있는 전역 옵션에 대 한 자세한 내용은 참조 하세요. [AFX_GLOBAL_DATA 구조체](../../mfc/reference/afx-global-data-structure.md)합니다.

##  <a name="onmove"></a>  CMFCToolBarDateTimeCtrl::OnMove

부모 도구 모음 이동 하면 프레임 워크에서 호출 됩니다.

```
virtual void OnMove();
```

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove))의 내부 위치를 업데이트 하 여 `CMFCToolBarDateTimeCtrlImpl` 개체입니다.

##  <a name="onshow"></a>  CMFCToolBarDateTimeCtrl::OnShow

프레임 워크 호출 단추 되 면 표시 되거나 숨겨지도록입니다.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
[in] 단추가 표시 되는지 여부를 지정 합니다. 이 매개 변수가 TRUE 인 경우 단추 표시 됩니다. 그렇지 않으면 단추가 표시 되지 않습니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) 하는 경우에 단추를 표시 하 여 *bShow* 은 TRUE입니다. 그렇지 않은 경우이 메서드 단추를 숨깁니다.

##  <a name="onsize"></a>  CMFCToolBarDateTimeCtrl::OnSize

부모 도구 모음 크기를 변경 하거나 크기를 변경 하려면 단추를 사용 하면 위치 및이 변경 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>매개 변수

*iSize*<br/>
[in] 새 너비 (픽셀)에서 단추를입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 재정의 ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize))의 내부 위치와 크기를 업데이트 하 여 `CMFCToolBarDateTimeCtrlImpl` 개체입니다.

##  <a name="onupdatetooltip"></a>  CMFCToolBarDateTimeCtrl::OnUpdateToolTip

부모 도구 모음 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
[in] 부모 창입니다.

*iButtonIndex*<br/>
[in] 단추의 부모 단추 컬렉션의 0부터 시작 하는 인덱스입니다.

*wndToolTip*<br/>
[in] 도구 설명 텍스트를 표시 하는 컨트롤입니다.

*str*<br/>
[out] `CString` 업데이트 된 도구 설명 텍스트를 받는 개체입니다.

### <a name="return-value"></a>반환 값

메서드는 도구 설명 텍스트를 업데이트 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 메서드는 기본 클래스 구현을 확장 ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) 단추를 사용 하 여 연결 된 도구 설명 텍스트를 표시 하 여 합니다. 단추는 가로로 도킹 되지 않은 경우이 메서드는 아무 작업도 수행 하지 하 고 FALSE를 반환 합니다.

##  <a name="settime"></a>  CMFCToolBarDateTimeCtrl::SetTime

시간 선택 컨트롤에서 날짜 및 시간을 설정합니다.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>매개 변수

*timeNew*<br/>
[in] 첫 번째 버전에서는에 대 한 참조를 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 컨트롤은 설정할 시간을 포함 하는 개체입니다. 두 번째 버전에서는에 대 한 포인터를 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 컨트롤은 설정할 시간을 포함 하는 개체입니다.

*pTimeNew*<br/>
[in] 에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 컨트롤은 설정할 시간을 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

날짜 및 시간 선택 컨트롤을 호출 하 여 시간 설정 [CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime)합니다.

##  <a name="settimeall"></a>  CMFCToolBarDateTimeCtrl::SetTimeAll

지정 된 명령 ID를 갖습니다 시간 선택 컨트롤의 모든 인스턴스에서 날짜 및 시간 설정

```
static BOOL SetTimeAll(
    UINT uiCmd,
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
[in] 도구 모음 단추의 명령 ID를 지정 합니다.

*timeNew*<br/>
[in] 첫 번째 버전에서을 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md) 컨트롤은 설정할 시간을 포함 하는 개체입니다. 두 번째 버전에서는에 대 한 포인터를 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 컨트롤은 설정할 시간을 포함 하는 개체입니다.

*pTimeNew*<br/>
[in] 에 대 한 포인터를 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) 컨트롤은 설정할 시간을 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

지정된 된 명령 ID 사용 하 여 도구 모음 단추를 찾아 호출 하 여 날짜 및 시간 선택 컨트롤에서 시간을 설정 [CMFCToolBarDateTimeCtrl::SetTime](#settime)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)
