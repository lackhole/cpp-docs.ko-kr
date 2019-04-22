---
title: CPaneDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
ms.openlocfilehash: c78b8f2cd19e87fa559c3f9bbd24d07543d887c5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769747"
---
# <a name="cpanedialog-class"></a>CPaneDialog 클래스

`CPaneDialog` 클래스는 도킹 가능한 모덜리스 대화 상자를 지원 합니다.

## <a name="syntax"></a>구문

```
class CPaneDialog : public CDockablePane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CPaneDialog::CPaneDialog`|기본 생성자입니다.|
|`CPaneDialog::~CPaneDialog`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPaneDialog::Create](#create)|도킹 가능한 대화 상자를 만들고 연결 하는 `CPaneDialog` 개체입니다.|
|`CPaneDialog::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CPaneDialog::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|처리를 [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) 메시지입니다. (재정의 `CBasePane::HandleInitDialog`.)|
|`CPaneDialog::OnEraseBkgnd`|처리를 [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) 메시지입니다. (재정의 [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|
|`CPaneDialog::OnLButtonDblClk`|처리를 [WM_LBUTTONDBLCLK](/windows/desktop/inputdev/wm-lbuttondblclk) 메시지입니다. (재정의 [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|처리를 [WM_LBUTTONDOWN](/windows/desktop/inputdev/wm-lbuttondown) 메시지입니다. (재정의 [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|
|`CPaneDialog::OnUpdateCmdUI`|대화 상자 창에 업데이트 하기 위해 프레임 워크에서 호출 됩니다. (재정의 [cdockablepane:: Onupdatecmdui](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|처리를 [WM_WINDOWPOSCHANGING](/windows/desktop/winmsg/wm-windowposchanging) 메시지입니다. (재정의 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE 컨트롤 컨테이너의 대화 상자에 대 한 템플릿을 지정 합니다.|

## <a name="remarks"></a>설명

생성 된 `CPaneDialog` 두 단계로 개체입니다. 먼저 코드에서 개체를 생성 합니다. 둘째, 호출 [CPaneDialog::Create](#create)합니다. 올바른 리소스 템플릿 이름 또는 템플릿 ID를 지정 하 고 부모 창에 대 한 포인터를 전달 해야 합니다. 그렇지 않은 경우 만들기 프로세스가 실패합니다. 대화 상자 WS_CHILD과 WS_VISIBLE 스타일을 지정 해야 합니다. WS_CLIPCHILDREN 및 WS_CLIPSIBLINGS 스타일을 지정 하는 것이 좋습니다. 자세한 내용은 [창 스타일](styles-used-by-mfc.md#window-styles)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CPaneDialog](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpanedialog.h

##  <a name="create"></a>  CPaneDialog::Create

도킹 대화 상자를 만들고 연결 하는 `CPaneDialog` 개체입니다.

```
BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID,
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*lpszWindowName*<br/>
[in] 대화 상자를 도킹의 이름입니다.

*pParentWnd*<br/>
[in] 부모 창을 가리킵니다.

*bHasGripper*<br/>
[in] TRUE (그리퍼); 캡션을 사용 하 여 도킹 대화 상자를 만들려면 그렇지 않으면 FALSE입니다.

*lpszTemplateName*<br/>
[in] 리소스 대화 상자 템플릿의 이름입니다.

*nStyle*<br/>
[in] Windows 스타일입니다.

*nID*<br/>
[in] 컨트롤 id입니다.

*nIDTemplate*<br/>
[in] 대화 상자 템플릿의 리소스 ID입니다.

*dwTabbedStyle*<br/>
[in] 스타일 사용자가 컨트롤로 끌어 다른 컨트롤 창이 컨트롤 창의 캡션을 때 발생 하는 탭된 창입니다. 기본값은 AFX_CBRS_REGULAR_TABS 합니다. 자세한 내용은의 설명 섹션을 참조 하십시오.는 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex) 메서드.

*dwControlBarStyle*<br/>
[in] 추가 스타일 특성입니다. 기본값은 AFX_DEFAULT_DOCKING_PANE_STYLE 합니다. 자세한 내용은의 설명 섹션을 참조 하십시오.는 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex) 메서드.

### <a name="return-value"></a>반환 값

이 메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `Create` 의 메서드는 `CPaneDialog` 클래스입니다. 이 예제는의 일부를 [창 크기 설정 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog

처리를 [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) 메시지입니다.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*wParam*<br/>
[in] 기본 키보드 포커스를 받을 수는 컨트롤에 대 한 핸들입니다.

*lParam*<br/>
[in] 추가 초기화 데이터를 지정합니다.

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다. TRUE로 지정 된 컨트롤에 키보드 포커스를 설정 하는 또한 합니다 *wParam* 매개 변수입니다. FALSE 기본 키보드 포커스를 설정 하지 않습니다.

### <a name="remarks"></a>설명

프레임 워크는이 메서드를 사용 하 여 컨트롤과 대화 상자의 모양을 초기화 합니다. 프레임 워크는 대화 상자를 표시 하기 전에이 메서드를 호출 합니다.

##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo

OLE 컨트롤 컨테이너의 대화 상자에 대 한 템플릿을 지정 합니다.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>매개 변수

*pOccDialogInfo*<br/>
[in] 대화 상자 개체를 만드는 데 사용 되는 대화 상자 템플릿에 대 한 포인터입니다. 에 전달 된이 매개 변수 값 이후에 합니다 [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) 메서드.

### <a name="return-value"></a>반환 값

항상 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드를 지원 합니다 [COccManager](../../mfc/reference/coccmanager-class.md) OLE 컨트롤 사이트 및 ActiveX 컨트롤을 관리 하는 클래스입니다. _AFX_OCC_DIALOG_INFO 구조 afxocc.h 헤더 파일에 정의 됩니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)<br/>
[창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)
