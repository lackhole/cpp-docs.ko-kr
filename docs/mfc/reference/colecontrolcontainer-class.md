---
title: COleControlContainer 클래스
ms.date: 11/04/2016
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
helpviewer_keywords:
- COleControlContainer [MFC], COleControlContainer
- COleControlContainer [MFC], AttachControlSite
- COleControlContainer [MFC], BroadcastAmbientPropertyChange
- COleControlContainer [MFC], CheckDlgButton
- COleControlContainer [MFC], CheckRadioButton
- COleControlContainer [MFC], CreateControl
- COleControlContainer [MFC], CreateOleFont
- COleControlContainer [MFC], FindItem
- COleControlContainer [MFC], FreezeAllEvents
- COleControlContainer [MFC], GetAmbientProp
- COleControlContainer [MFC], GetDlgItem
- COleControlContainer [MFC], GetDlgItemInt
- COleControlContainer [MFC], GetDlgItemText
- COleControlContainer [MFC], HandleSetFocus
- COleControlContainer [MFC], HandleWindowlessMessage
- COleControlContainer [MFC], IsDlgButtonChecked
- COleControlContainer [MFC], OnPaint
- COleControlContainer [MFC], OnUIActivate
- COleControlContainer [MFC], OnUIDeactivate
- COleControlContainer [MFC], ScrollChildren
- COleControlContainer [MFC], SendDlgItemMessage
- COleControlContainer [MFC], SetDlgItemInt
- COleControlContainer [MFC], SetDlgItemText
- COleControlContainer [MFC], m_crBack
- COleControlContainer [MFC], m_crFore
- COleControlContainer [MFC], m_listSitesOrWnds
- COleControlContainer [MFC], m_nWindowlessControls
- COleControlContainer [MFC], m_pOleFont
- COleControlContainer [MFC], m_pSiteCapture
- COleControlContainer [MFC], m_pSiteFocus
- COleControlContainer [MFC], m_pSiteUIActive
- COleControlContainer [MFC], m_pWnd
- COleControlContainer [MFC], m_siteMap
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
ms.openlocfilehash: 1d386072b67568ecf58afd0853df2d7fbaeac68d
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504561"
---
# <a name="colecontrolcontainer-class"></a>COleControlContainer 클래스

ActiveX 컨트롤의 컨트롤 컨테이너 역할을 합니다.

## <a name="syntax"></a>구문

```
class COleControlContainer : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|`COleControlContainer` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|컨테이너에서 호스트 된 컨트롤 사이트를 만듭니다.|
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|앰비언트 속성이 변경 된 모든 호스트 된 컨트롤을 알립니다.|
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|지정된 된 단추 컨트롤을 수정합니다.|
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|그룹의 지정 된 라디오 단추를 선택합니다.|
|[COleControlContainer::CreateControl](#createcontrol)|호스팅된 ActiveX 컨트롤을 만듭니다.|
|[COleControlContainer::CreateOleFont](#createolefont)|OLE 글꼴을 만듭니다.|
|[COleControlContainer::FindItem](#finditem)|지정된 된 컨트롤의 사용자 지정 사이트를 반환합니다.|
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|컨트롤 사이트 이벤트를 수락 하는 경우를 결정 합니다.|
|[COleControlContainer::GetAmbientProp](#getambientprop)|지정된 된 앰비언트 속성을 검색합니다.|
|[COleControlContainer::GetDlgItem](#getdlgitem)|지정 된 대화 상자 컨트롤을 검색합니다.|
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|지정 된 대화 상자 컨트롤의 값을 검색 합니다.|
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|지정 된 대화 상자 컨트롤의 캡션을 검색합니다.|
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|컨테이너 WM_SETFOCUS 메시지를 처리 하는 경우를 결정 합니다.|
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|창 없는 컨트롤에 전송 된 메시지를 처리 합니다.|
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|지정 된 단추의 상태를 확인합니다.|
|[COleControlContainer::OnPaint](#onpaint)|컨테이너의 일부를 다시 그리기 위해 호출 됩니다.|
|[COleControlContainer::OnUIActivate](#onuiactivate)|컨트롤은 현재 위치 활성화 되려고 할 때 호출 됩니다.|
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|컨트롤을 비활성화 하려고 할 때 호출 됩니다.|
|[COleControlContainer::ScrollChildren](#scrollchildren)|자식 창에서 스크롤 메시지를 받을 때 프레임 워크에서 호출 됩니다.|
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|지정된 컨트롤에 메시지를 보냅니다.|
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|지정된 된 컨트롤의 값을 설정 합니다.|
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|지정된 된 컨트롤의 텍스트를 설정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COleControlContainer::m_crBack](#m_crback)|컨테이너의 배경색입니다.|
|[COleControlContainer::m_crFore](#m_crfore)|컨테이너의 전경색입니다.|
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|지원 되는 컨트롤 사이트의 목록입니다.|
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|호스트 된 창 없는 컨트롤의 수입니다.|
|[COleControlContainer::m_pOleFont](#m_polefont)|OLE 글꼴을 사용자 지정 컨트롤 사이트에 대 한 포인터입니다.|
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|캡처 컨트롤 사이트에 대 한 포인터입니다.|
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|현재 입력 포커스가 있는 컨트롤에 대 한 포인터입니다.|
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|내부 활성화 된 현재 컨트롤에 대 한 포인터입니다.|
|[COleControlContainer::m_pWnd](#m_pwnd)|컨트롤 컨테이너를 구현 하는 창에 대 한 포인터입니다.|
|[COleControlContainer::m_siteMap](#m_sitemap)|사이트 맵입니다.|

## <a name="remarks"></a>설명

하나 이상의 ActiveX 컨트롤 사이트에 대 한 지원을 제공 하면 됩니다 (구현한 `COleControlSite`). `COleControlContainer` 완벽 하 게 구현 합니다 [IOleInPlaceFrame](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceframe) 및 [IOleContainer](/windows/desktop/api/oleidl/nn-oleidl-iolecontainer) 인터페이스를 포함 된 ActiveX 컨트롤에 있는 항목으로 해당 조건을 충족 합니다.

이 클래스와 함께 사용 되는 일반적으로 `COccManager` 및 `COleControlSite` 하나 이상의 ActiveX 컨트롤에 대 한 사용자 지정 사이트를 사용 하 여 사용자 지정 ActiveX 컨트롤 컨테이너를 구현 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleControlContainer`

## <a name="requirements"></a>요구 사항

**헤더:** afxocc.h

##  <a name="attachcontrolsite"></a>  COleControlContainer::AttachControlSite

만들기 및 컨트롤 사이트를 연결 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);

void AttachControlSite(
    CWnd* pWnd,
    UINT nIDC = 0);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
`CWnd` 개체에 대한 포인터입니다.

*nIDC*<br/>
연결 된 컨트롤의 ID입니다.

### <a name="remarks"></a>설명

이 프로세스를 사용자 지정 하려는 경우이 함수를 재정의 합니다.

> [!NOTE]
>  MFC 라이브러리에 정적으로 연결 하는 경우이 함수의 첫 번째 형태를 사용 합니다. MFC 라이브러리에 동적으로 연결 하는 경우 두 번째 형태를 사용 합니다.

##  <a name="broadcastambientpropertychange"></a>  COleControlContainer::BroadcastAmbientPropertyChange

앰비언트 속성이 변경 된 모든 호스트 된 컨트롤을 알립니다.

```
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```

### <a name="parameters"></a>매개 변수

*dispid*<br/>
변경 되는 앰비언트 속성의 디스패치 ID입니다.

### <a name="remarks"></a>설명

이 함수는 앰비언트 속성 값 변경 되었을 때 프레임 워크에서 호출 됩니다. 이 동작을 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="checkdlgbutton"></a>  COleControlContainer::CheckDlgButton

단추의 현재 상태를 수정합니다.

```
virtual void CheckDlgButton(
    int nIDButton,
    UINT nCheck);
```

### <a name="parameters"></a>매개 변수

*nIDButton*<br/>
수정할 단추의 ID입니다.

*nCheck*<br/>
단추의 상태를 지정합니다. 다음 중 하나일 수 있습니다.

- BST_CHECKED 집합 단추 상태를 확인합니다.

- BST_INDETERMINATE 집합 단추 상태에 회색으로 표시 되지 않은 상태를 나타내는입니다. 단추 모양이 BS_3STATE 또는 BS_AUTO3STATE 스타일 하는 경우에이 값을 사용 합니다.

- BST_UNCHECKED 집합 단추 상태를 선택 취소 합니다.

##  <a name="checkradiobutton"></a>  COleControlContainer::CheckRadioButton

그룹에 지정 된 라디오 단추를 선택 하 고 그룹의 나머지 단추를 지웁니다.

```
virtual void CheckRadioButton(
    int nIDFirstButton,
    int nIDLastButton,
    int nIDCheckButton);
```

### <a name="parameters"></a>매개 변수

*nIDFirstButton*<br/>
그룹의 첫 번째 라디오 단추의 식별자를 지정합니다.

*nIDLastButton*<br/>
그룹의 마지막 라디오 단추의 식별자를 지정합니다.

*nIDCheckButton*<br/>
검사할 라디오 단추의 식별자를 지정 합니다.

##  <a name="colecontrolcontainer"></a>  COleControlContainer::COleControlContainer

`COleControlContainer` 개체를 생성합니다.

```
explicit COleControlContainer(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨트롤 컨테이너의 부모 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

개체가 성공적으로 만든 후 추가 사용자 지정 컨트롤 사이트에 대 한 호출을 사용 하 여 `AttachControlSite`입니다.

##  <a name="createcontrol"></a>  COleControlContainer::CreateControl

지정 된 호스트 된 ActiveX 컨트롤을 만들고 `COleControlSite` 개체입니다.

```
BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);

BOOL CreateControl(
    CWnd* pWndCtrl,
    REFCLSID clsid,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const POINT* ppt,
    const SIZE* psize,
    UINT nID,
    CFile* pPersist =NULL,
    BOOL bStorage =FALSE,
    BSTR bstrLicKey =NULL,
    COleControlSite** ppNewSite =NULL);
```

### <a name="parameters"></a>매개 변수

*pWndCtrl*<br/>
컨트롤을 나타내는 window 개체에 대 한 포인터입니다.

*clsid*<br/>
컨트롤의 고유 클래스 ID입니다.

*lpszWindowName*<br/>
컨트롤에 표시할 텍스트 포인터입니다. (해당 되는 경우) 컨트롤의 캡션 또는 텍스트 속성의 값을 설정 합니다. NULL 인 경우 컨트롤의 캡션 또는 텍스트 속성이 변경 되지 않습니다.

*dwStyle*<br/>
Windows 스타일입니다. 사용 가능한 스타일 아래에 나열 됩니다는 **주의** 섹션입니다.

*rect*<br/>
컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 `CRect` 개체 또는 `RECT` 구조입니다.

*nID*<br/>
컨트롤의 자식 창 ID를 지정합니다.

*pPersist*<br/>
에 대 한 포인터를 `CFile` 컨트롤에 대 한 영구 상태를 포함 합니다. 기본값은 컨트롤 모든 영구 저장소에서 해당 상태를 복원 하지 않고 자체 초기화를 나타내는 NULL입니다. NULL이 아닌 경우에 대 한 포인터 여야 합니다는 `CFile`-스트림 또는 저장소의 형태로 컨트롤의 영구 데이터를 포함 하는 개체를 파생 합니다. 이 데이터는 클라이언트의 이전 정품에서 저장할 수 없습니다. 합니다 `CFile` 다른 데이터를 포함할 수 있지만 영구 데이터의 첫 번째 바이트에 대 한 호출 시에 설정 하는 읽기 / 쓰기 포인터 있어야 `CreateControl`합니다.

*bStorage*<br/>
나타냅니다 여부의 데이터 *pPersist* 로 해석 되어야 `IStorage` 또는 `IStream` 데이터. 경우에 데이터 *pPersist* 는 저장소가 *bStorage* TRUE 여야 합니다. 경우에 데이터 *pPersist* 는 스트림이 *bStorage* FALSE 여야 합니다. 기본값은 FALSE입니다.

*bstrLicKey*<br/>
선택적 라이선스 키 데이터입니다. 이 데이터는 런타임 라이선스 키를 필요로 하는 컨트롤을 만드는 데만 필요 합니다. 컨트롤 라이선스를 지 원하는 경우에 성공 하려면 컨트롤에 대 한 라이선스 키를 제공 해야 합니다. 기본값은 NULL입니다.

*ppNewSite*<br/>
만들려는 컨트롤을 호스트 하는 기존 컨트롤 사이트에 대 한 포인터입니다. 기본값은는 새 컨트롤 사이트를 자동으로 생성 되며 새 컨트롤에 연결을 나타내는 NULL입니다.

*ppt*<br/>
에 대 한 포인터를 `POINT` 컨트롤의 왼쪽 위 모퉁이 포함 하는 구조입니다. 컨트롤의 크기 값에 의해 결정 됩니다 *psize*합니다. 합니다 *ppt* 하 고 *psize* 값은 크기와 컨트롤의 위치를 지정 하는 선택적 메서드입니다.

*psize*<br/>
에 대 한 포인터를 `SIZE` 컨트롤의 크기를 포함 하는 구조입니다. 왼쪽 위 모퉁이의 값에 따라 결정 됩니다 *ppt*합니다. 합니다 *ppt* 하 고 *psize* 값은 크기와 컨트롤의 위치를 지정 하는 선택적 메서드입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Windows의 하위 집합만 *dwStyle* 에서 지원 되는 플래그 `CreateControl`:

- WS_VISIBLE에 처음 표시 되는 창을 만듭니다. 일반 창과 마찬가지로 즉시 표시 되도록 컨트롤을 원하는 경우 필요 합니다.

- WS_DISABLED 처음부터 사용할 수 있는 창을 만듭니다. 사용할 수 없는 창의 사용자 로부터 입력을 받을 수 없습니다. 컨트롤에 속성을 사용 하는 경우 설정할 수 있습니다.

- WS_BORDER 씬 줄 테두리가 있는 창을 만듭니다. 컨트롤에 BorderStyle 속성을 설정할 수 있습니다.

- WS_GROUP은 컨트롤 그룹의 첫 번째 컨트롤을 지정합니다. 방향 키를 사용 하 여 다음 그룹의 한 컨트롤에서 키보드 포커스를 변경할 수는 사용자. 모든 컨트롤을 동일한 그룹에 속하는 첫 번째 컨트롤 후 WS_GROUP 스타일을 사용 하 여 정의 합니다. WS_GROUP 스타일을 사용 하 여 다음 컨트롤 그룹을 종료 하 고 그룹을 시작 합니다.

- WS_TABSTOP TAB 키를 누를 때 키보드 포커스를 받을 수 있는 컨트롤을 지정 합니다. TAB 키를 눌러 WS_TABSTOP 스타일의 다음 컨트롤에 키보드 포커스를 변경 합니다.

기본 크기의 컨트롤을 만들려면 두 번째 오버 로드를 사용 합니다.

##  <a name="createolefont"></a>  COleControlContainer::CreateOleFont

OLE 글꼴을 만듭니다.

```
void CreateOleFont(CFont* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
컨트롤 컨테이너에서 사용할 글꼴에 대 한 포인터입니다.

##  <a name="finditem"></a>  COleControlContainer::FindItem

지정된 된 항목을 호스트 하는 사용자 지정 사이트를 찾습니다.

```
virtual COleControlSite* FindItem(UINT nID) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
찾을 항목의 식별자입니다.

### <a name="return-value"></a>반환 값

지정된 된 항목의 사용자 지정 사이트에 대 한 포인터입니다.

##  <a name="freezeallevents"></a>  COleControlContainer::FreezeAllEvents

컨테이너는 연결 된 컨트롤 사이트에서 이벤트를 무시 또는 동의 하는 경우를 결정 합니다.

```
void FreezeAllEvents(BOOL bFreeze);
```

### <a name="parameters"></a>매개 변수

*bFreeze*<br/>
0이 아닌 이벤트 처리 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤이는 컨트롤 컨테이너에서 요청 하는 경우에 이벤트를 발생 시키고 중지 필요 하지 않습니다. 실행을 계속할 수 있지만 컨트롤 컨테이너에서 후속 이벤트를 모두 무시 됩니다.

##  <a name="getambientprop"></a>  COleControlContainer::GetAmbientProp

지정된 된 앰비언트 속성의 값을 검색 합니다.

```
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,
    DISPID dispid,
    VARIANT* pvarResult);
```

### <a name="parameters"></a>매개 변수

*pSite*<br/>
앰비언트 속성을 검색할 컨트롤 사이트에 대 한 포인터입니다.

*dispid*<br/>
원하는 앰비언트 속성의 디스패치 ID입니다.

*pVarResult*<br/>
앰비언트 속성의 값에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="getdlgitem"></a>  COleControlContainer::GetDlgItem

대화 상자에서 지정된 된 컨트롤이 나 자식 창 또는 다른 창에 대 한 포인터를 검색합니다.

```
virtual CWnd* GetDlgItem(int nID) const;

virtual void GetDlgItem(
    int nID,
    HWND* phWnd) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
검색 대화 상자 항목의 식별자입니다.

*phWnd*<br/>
지정 된 대화 상자 항목의 창 개체의 핸들에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

대화 상자 항목의 창에 대 한 포인터입니다.

##  <a name="getdlgitemint"></a>  COleControlContainer::GetDlgItemInt

지정된 된 컨트롤의 번역된 된 텍스트의 값을 검색 합니다.

```
virtual UINT GetDlgItemInt(
    int nID,
    BOOL* lpTrans,
    BOOL bSigned) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤의 식별자입니다.

*lpTrans*<br/>
함수가 성공/실패 값을 수신 하는 부울 변수에 대 한 포인터 (성공한 TRUE, FALSE 이면 실패).

*bSigned*<br/>
함수 시작 부분에 빼기 기호에 대 한 텍스트를 검토 하며 발견 되 면 부호 있는 정수 값을 반환 하는지 여부를 지정 합니다. 경우는 *bSigned* 매개 변수가 TRUE 이면 반환 값을 캐스팅 값을 검색할 수는 부호 있는 정수 인지를 지정 하는 **int** 형식입니다. 확장 오류 정보를 가져오기, 호출 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror)합니다.

### <a name="return-value"></a>반환 값

경우 성공 하면 변수에서 가리키는 *lpTrans* TRUE로 설정 되 고 반환 값은 컨트롤 텍스트의 번역 된 값.

함수가 실패할 경우 변수 가리키는 *lpTrans* FALSE로 설정 되어 및 반환 값은 0입니다. Note는 가능한 번역 된 값을 0 이므로 반환 값이 0 자체적으로 나타내지 실패 합니다.

하는 경우 *lpTrans* 가 null 인 경우 함수 반환 성공 또는 실패 하는 방법에 대 한 정보가 없습니다.

### <a name="remarks"></a>설명

함수는 텍스트의 시작 부분에 추가 공백을 제거 하 고 다음 10 진수 숫자를 변환 하 여 검색된 텍스트를 변환 합니다. 함수 변환가 숫자가 아닌 문자를 발견 하거나 텍스트의 끝에 도달할 때 중지 합니다.

이 함수는 변환 된 값 (부호 있는 숫자)에 대 한 INT_MAX 또는 UINT_MAX (부호 없는 숫자)에 대 한 보다 큰 경우 0을 반환 합니다.

##  <a name="getdlgitemtext"></a>  COleControlContainer::GetDlgItemText

지정된 된 컨트롤의 텍스트를 검색합니다.

```
virtual int GetDlgItemText(
    int nID,
    LPTSTR lpStr,
    int nMaxCount) const;
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤의 식별자입니다.

*lpStr*<br/>
컨트롤의 텍스트에 대 한 포인터입니다.

*nMaxCount*<br/>
문자를 가리키는 버퍼에 복사할 문자열의 최대 길이 지정 *lpStr*합니다. 문자열의 길이 제한을 초과 하면 문자열이 잘립니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 null 종결 문자를 포함 하지 않습니다, 버퍼에 복사 하는 문자 수를 지정 합니다.

함수가 실패하면 반환 값은 0입니다. 확장 오류 정보를 가져오기, 호출 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror)합니다.

##  <a name="handlesetfocus"></a>  COleControlContainer::HandleSetFocus

컨테이너 WM_SETFOCUS 메시지를 처리 하는 경우를 결정 합니다.

```
virtual BOOL HandleSetFocus();
```

### <a name="return-value"></a>반환 값

컨테이너 WM_SETFOCUS 메시지를 처리 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="handlewindowlessmessage"></a>  COleControlContainer::HandleWindowlessMessage

창 없는 컨트롤에 대 한 창 메시지를 처리합니다.

```
virtual BOOL HandleWindowlessMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* plResult);
```

### <a name="parameters"></a>매개 변수

*message*<br/>
Windows에서 제공 된 창 메시지에 대 한 식별자입니다.

*wParam*<br/>
메시지 매개 변수 Windows에서 제공합니다. 추가 메시지 관련 정보를 지정 합니다. 값에 종속 되는이 매개 변수의 콘텐츠는 *메시지* 매개 변수입니다.

*lParam*<br/>
메시지 매개 변수 Windows에서 제공합니다. 추가 메시지 관련 정보를 지정 합니다. 값에 종속 되는이 매개 변수의 콘텐츠는 *메시지* 매개 변수입니다.

*plResult*<br/>
Windows 결과 코드입니다. 메시지 처리의 결과 지정 하 고 전송 된 메시지에 따라 달라 집니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

창 없는 제어 메시지의 처리를 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="isdlgbuttonchecked"></a>  COleControlContainer::IsDlgButtonChecked

지정 된 단추의 상태를 확인합니다.

```
virtual UINT IsDlgButtonChecked(int nIDButton) const;
```

### <a name="parameters"></a>매개 변수

*nIDButton*<br/>
단추 컨트롤의 식별자입니다.

### <a name="return-value"></a>반환 값

BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON, 또는 BS_3STATE 스타일을 사용 하 여 만든 단추에서 반환 값입니다. 다음 중 하나일 수 있습니다.

- BST_CHECKED 단추가 선택 됩니다.

- (단추가 BS_3STATE 또는 BS_AUTO3STATE 스타일 하는 경우에 적용 됨)는 결정 되지 않은 상태를 나타내는 BST_INDETERMINATE 단추의 흐리게 표시 됩니다.

- BST_UNCHECKED 단추 지워집니다.

### <a name="remarks"></a>설명

단추를 세 가지 상태 컨트롤, 멤버 함수에 따라 결정 됩니다 있는지 여부를 해당 흐리게 표시 되 면이 옵션을 선택 하거나 사용 하지 않도록 합니다.

##  <a name="m_crback"></a>  COleControlContainer::m_crBack

컨테이너의 배경색입니다.

```
COLORREF m_crBack;
```

##  <a name="m_crfore"></a>  COleControlContainer::m_crFore

컨테이너의 전경색입니다.

```
COLORREF m_crFore;
```

##  <a name="m_listsitesorwnds"></a>  COleControlContainer::m_listSitesOrWnds

목록 컨테이너에서 호스트 되는 컨트롤 사이트입니다.

```
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;
```

##  <a name="m_nwindowlesscontrols"></a>  COleControlContainer::m_nWindowlessControls

창 없는 컨트롤은 컨트롤 컨테이너에서 호스트의 수입니다.

```
int m_nWindowlessControls;
```

##  <a name="m_polefont"></a>  COleControlContainer::m_pOleFont

OLE 글꼴을 사용자 지정 컨트롤 사이트에 대 한 포인터입니다.

```
LPFONTDISP m_pOleFont;
```

##  <a name="m_psitecapture"></a>  COleControlContainer::m_pSiteCapture

캡처 컨트롤 사이트에 대 한 포인터입니다.

```
COleControlSite* m_pSiteCapture;
```

##  <a name="m_psitefocus"></a>  COleControlContainer::m_pSiteFocus

현재 입력 포커스가 있는 컨트롤 사이트에 대 한 포인터입니다.

```
COleControlSite* m_pSiteFocus;
```

##  <a name="m_psiteuiactive"></a>  COleControlContainer::m_pSiteUIActive

내부 활성화 하는 컨트롤 사이트에 대 한 포인터입니다.

```
COleControlSite* m_pSiteUIActive;
```

##  <a name="m_pwnd"></a>  COleControlContainer::m_pWnd

컨테이너와 연결 된 창 개체에 대 한 포인터입니다.

```
CWnd* m_pWnd;
```

##  <a name="m_sitemap"></a>  COleControlContainer::m_siteMap

사이트 맵입니다.

```
CMapPtrToPtr m_siteMap;
```

##  <a name="onpaint"></a>  COleControlContainer::OnPaint

WM_PAINT 요청을 처리 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnPaint(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
컨테이너에서 사용 하는 장치 컨텍스트에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메시지가 처리 된 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

그리기 프로세스를 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="onuiactivate"></a>  COleControlContainer::OnUIActivate

프레임 워크에서 호출 하면 컨트롤 사이트를 가리키는 *pSite*, 되기 직전에 내부 활성화.

```
virtual void OnUIActivate(COleControlSite* pSite);
```

### <a name="parameters"></a>매개 변수

*pSite*<br/>
내부 활성화 되도록 컨트롤 사이트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

내부 활성화는 내부 합성 메뉴를 사용 하 여 컨테이너의 주 메뉴 대체 되도록을 의미 합니다.

##  <a name="onuideactivate"></a>  COleControlContainer::OnUIDeactivate

프레임 워크에서 호출 하면 컨트롤 사이트를 가리키는 *pSite*, 비활성화 되려고 합니다.

```
virtual void OnUIDeactivate(COleControlSite* pSite);
```

### <a name="parameters"></a>매개 변수

*pSite*<br/>
비활성화 해야 컨트롤 사이트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 알림이 수신 되 면 컨테이너는 해당 사용자 인터페이스를 다시 설치 하 고 포커스를 해야 합니다.

##  <a name="scrollchildren"></a>  COleControlContainer::ScrollChildren

자식 창에서 스크롤 메시지를 받을 때 프레임 워크에서 호출 됩니다.

```
virtual void ScrollChildren(
    int dx,
    int dy);
```

### <a name="parameters"></a>매개 변수

*dx*<br/>
X 축의 스크롤의 양, 픽셀입니다.

*dy*<br/>
Y 축의 스크롤의 양, 픽셀입니다.

##  <a name="senddlgitemmessage"></a>  COleControlContainer::SendDlgItemMessage

지정된 컨트롤에 메시지를 보냅니다.

```
virtual LRESULT SendDlgItemMessage(
    int nID,
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
메시지를 받는 컨트롤의 식별자를 지정 합니다.

*message*<br/>
보낼 메시지를 지정 합니다.

*wParam*<br/>
추가 메시지 관련 정보를 지정 합니다.

*lParam*<br/>
추가 메시지 관련 정보를 지정 합니다.

##  <a name="setdlgitemint"></a>  COleControlContainer::SetDlgItemInt

지정된 된 정수 값의 문자열 표현으로 대화 상자에서 컨트롤의 텍스트를 설정합니다.

```
virtual void SetDlgItemInt(
    int nID,
    UINT nValue,
    BOOL bSigned);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤의 식별자입니다.

*nValue*<br/>
표시할 정수 값입니다.

*bSigned*<br/>
지정 여부는 *n 값* 매개 변수는 정수 또는 부호 없는 합니다. 이 매개 변수가 TRUE 이면 *n 값* 서명 됩니다. 이 매개 변수가 TRUE 이면 하 고 *n 값* 이 음수, 빼기 기호 문자열에서 첫 번째 숫자 앞에 배치 됩니다. 이 매개 변수가 FALSE 이면 *n 값* 서명 되지 않았습니다.

##  <a name="setdlgitemtext"></a>  COleControlContainer::SetDlgItemText

에 포함 된 텍스트를 사용 하 여 지정된 된 컨트롤의 텍스트를 설정 *lpszString*합니다.

```
virtual void SetDlgItemText(
    int nID,
    LPCTSTR lpszString);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
컨트롤의 식별자입니다.

*lpszString*<br/>
컨트롤의 텍스트에 대 한 포인터입니다.

## <a name="see-also"></a>참고자료

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite 클래스](../../mfc/reference/colecontrolsite-class.md)<br/>
[COccManager 클래스](../../mfc/reference/coccmanager-class.md)
