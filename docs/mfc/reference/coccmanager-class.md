---
title: COccManager 클래스
ms.date: 11/04/2016
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
helpviewer_keywords:
- COccManager [MFC], CreateContainer
- COccManager [MFC], CreateDlgControls
- COccManager [MFC], CreateSite
- COccManager [MFC], GetDefBtnCode
- COccManager [MFC], IsDialogMessage
- COccManager [MFC], IsLabelControl
- COccManager [MFC], IsMatchingMnemonic
- COccManager [MFC], OnEvent
- COccManager [MFC], PostCreateDialog
- COccManager [MFC], PreCreateDialog
- COccManager [MFC], SetDefaultButton
- COccManager [MFC], SplitDialogTemplate
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
ms.openlocfilehash: a83f58b8de2411577d9fc025f7a8f8dc535ea8b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388269"
---
# <a name="coccmanager-class"></a>COccManager 클래스

`COleControlContainer` 및 `COleControlSite` 개체로 구현된 다양한 사용자 지정 컨트롤 사이트를 관리합니다.

## <a name="syntax"></a>구문

```
class COccManager : public CNoTrackObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COccManager::CreateContainer](#createcontainer)|`COleContainer` 개체를 만듭니다.|
|[COccManager::CreateDlgControls](#createdlgcontrols)|ActiveX 컨트롤을 연결 된 호스트를 만들고 `COleContainer` 개체입니다.|
|[COccManager::CreateSite](#createsite)|`COleClientSite` 개체를 만듭니다.|
|[COccManager::GetDefBtnCode](#getdefbtncode)|기본 단추 코드를 검색합니다.|
|[COccManager::IsDialogMessage](#isdialogmessage)|대화 메시지의 대상을 결정 합니다.|
|[COccManager::IsLabelControl](#islabelcontrol)|지정된 된 컨트롤 레이블 컨트롤을 결정 합니다.|
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|현재 니모닉 지정된 된 컨트롤의 니모닉과 일치 하는 경우를 결정 합니다.|
|[COccManager::OnEvent](#onevent)|지정된 된 이벤트를 처리 하려고 시도 합니다.|
|[COccManager::PostCreateDialog](#postcreatedialog)|대화를 만드는 동안 할당 된 리소스를 해제 합니다.|
|[COccManager::PreCreateDialog](#precreatedialog)|ActiveX 컨트롤에 대 한 대화 상자 템플릿을 처리합니다.|
|[COccManager::SetDefaultButton](#setdefaultbutton)|지정된 된 컨트롤의 기본 상태를 토글합니다.|
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|지정 된 대화 상자 템플릿에 공용 컨트롤에서 모든 기존 ActiveX 컨트롤을 구분합니다.|

## <a name="remarks"></a>설명

기본 클래스 `CNoTrackObject`는 문서화 되지 않은 기본 클래스 (AFXTLS에 있습니다. H)입니다. MFC 프레임 워크에서 사용 하기 위한에서 파생 된 클래스는 `CNoTrackObject` 클래스는 메모리 누수 검색에서 제외 됩니다. 직접 파생 되는 권장 되지 않습니다 `CNoTrackObject`합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CNoTrackObject`

`COccManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxocc.h

##  <a name="createcontainer"></a>  COccManager::CreateContainer

컨트롤 컨테이너를 만들기 위해 프레임 워크에서 호출 됩니다.

```
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
사용자 지정 사이트 컨테이너와 연결 된 창 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

새로 만든된 컨테이너;에 대 한 포인터 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

사용자 지정 사이트를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite)합니다.

##  <a name="createdlgcontrols"></a>  COccManager::CreateDlgControls

지정 된 ActiveX 컨트롤을 만드는 데이 함수를 호출 합니다 *pOccDialogInfo* 매개 변수입니다.

```
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    LPCTSTR lpszResourceName,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

virtual BOOL CreateDlgControls(
    CWnd* pWndParent,
    void* lpResource,
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
대화 상자 개체의 부모에 대 한 포인터입니다.

*lpszResourceName*<br/>
만들려는 리소스의 이름입니다.

*pOccDialogInfo*<br/>
대화 상자 개체를 만드는 데 대화 상자 템플릿에 대 한 포인터입니다.

*lpResource*<br/>
리소스에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

컨트롤을 성공적으로 만들어진 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="createsite"></a>  COccManager::CreateSite

컨트롤 사이트를 가리키는 컨테이너에서 호스트를 만드는 프레임 워크에서 호출 *pCtrlCont*합니다.

```
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```

### <a name="parameters"></a>매개 변수

*pCtrlCont*<br/>
새 컨트롤 사이트를 호스팅하는 컨트롤 컨테이너에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

새로 만든된 컨트롤 사이트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

사용자 지정 컨트롤을 만드는이 함수를 재정의 사용 하 여 사이트에 [COleControlSite](../../mfc/reference/colecontrolsite-class.md)-클래스를 파생 합니다.

각 컨트롤 컨테이너는 여러 사이트를 호스트할 수 있습니다. 에 대 한 여러 호출을 사용 하 여 사이트를 추가로 만들어 `CreateSite`합니다.

##  <a name="getdefbtncode"></a>  COccManager::GetDefBtnCode

기본 누름 단추 컨트롤 인지 확인 하려면이 함수를 호출 합니다.

```
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
단추 컨트롤이 포함 된 창 개체입니다.

### <a name="return-value"></a>반환 값

다음 값 중 하나입니다.

- DLGC_DEFPUSHBUTTON 컨트롤에는 대화 상자에서 기본 단추입니다.

- DLGC_UNDEFPUSHBUTTON 컨트롤은 대화 상자의 기본 단추가 없습니다.

- **0** 컨트롤이 단추가 아닙니다.

##  <a name="isdialogmessage"></a>  COccManager::IsDialogMessage

있는지 확인 하는 메시지는 지정된 된 대화 상자를 위한, 인 경우 메시지를 처리 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,
    LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*pWndDlg*<br/>
메시지의 의도 한 대상 대화 상자에 대 한 포인터입니다.

*lpMsg*<br/>
에 대 한 포인터는 `MSG` 검사할 메시지를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

0이 아닌 메시지를 처리 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 동작은 `IsDialogMessage` 키보드 메시지를 확인 하 고 해당 대화 상자에 대 한 선택 항목으로 변환 하는 것입니다. 예를 들어, TAB 키를 누르면 다음 컨트롤 또는 컨트롤 그룹을 선택 합니다.

지정 된 대화에 전송 된 메시지에 대 한 사용자 지정 동작을 제공 하려면이 함수를 재정의 합니다.

##  <a name="islabelcontrol"></a>  COccManager::IsLabelControl

지정된 된 컨트롤 레이블 컨트롤을 확인 하려면이 함수를 호출 합니다.

```
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨트롤이 포함 된 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

컨트롤 레이블이; 경우 0이 아닌 값 그렇지 않으면 0

### <a name="remarks"></a>설명

Label 컨트롤은 다음 순서에 관계 없이 컨트롤에 대 한 레이블과 같은 역할입니다.

##  <a name="ismatchingmnemonic"></a>  COccManager::IsMatchingMnemonic

현재 니모닉 컨트롤을 나타내는 일치 하는지 확인 하려면이 함수를 호출 합니다.

```
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,
    LPMSG lpMsg);

static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,
    LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨트롤이 포함 된 창에 대 한 포인터입니다.

*lpMsg*<br/>
일치 하는 니모닉을 포함 하는 메시지에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

니모닉 컨트롤 일치 하는 경우 0이 아닌 값 그렇지 않으면 0

### <a name="remarks"></a>설명

##  <a name="onevent"></a>  COccManager::OnEvent

지정된 된 이벤트를 처리 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,
    UINT idCtrl,
    AFX_EVENT* pEvent,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>매개 변수

*pCmdTarget*<br/>
에 대 한 포인터를 `CCmdTarget` 개체 이벤트를 처리 하려고 합니다.

*idCtrl*<br/>
컨트롤의 리소스 ID입니다.

*pEvent*<br/>
처리 되는 이벤트입니다.

*pHandlerInfo*<br/>
NULL이 아닌 경우 `OnEvent` 채웁니다 합니다 `pTarget` 및 `pmf` 의 멤버는 `AFX_CMDHANDLERINFO` 명령 디스패치 하는 대신 구조입니다. 일반적으로이 매개 변수는 NULL 이어야 합니다.

### <a name="return-value"></a>반환 값

이벤트가 처리 된, 그렇지 않으면 0 0이 아닌 지정 합니다.

### <a name="remarks"></a>설명

기본 이벤트 처리 프로세스를 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="precreatedialog"></a>  COccManager::PreCreateDialog

실제 대화 상자를 만들기 전에 ActiveX 컨트롤에 대 한 대화 상자 템플릿을 처리 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,
    const DLGTEMPLATE* pOrigTemplate);
```

### <a name="parameters"></a>매개 변수

*pOccDialogInfo*<br/>
`_AFX_OCC_DIALOG_INFO` 대화 상자 템플릿 및 대화 상자에서 호스트 되는 모든 ActiveX 컨트롤에 대 한 정보를 포함 하는 구조체입니다.

*pOrigTemplate*<br/>
대화 상자를 만드는 데 사용할 대화 상자 템플릿의 포인터입니다.

### <a name="return-value"></a>반환 값

대화 상자를 만드는 데 사용 하는 대화 상자 템플릿 구조에 대 한 포인터입니다.

### <a name="remarks"></a>설명

기본 동작에 대 한 호출을 통해 `SplitDialogTemplate`, 있는 경우 모든 ActiveX 컨트롤을 결정 하 고 다음 결과 대화 상자 템플릿을 반환 합니다.

ActiveX 컨트롤을 호스트 하는 대화 상자를 만드는 프로세스를 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="postcreatedialog"></a>  COccManager::PostCreateDialog

대화 상자 템플릿의에 할당 된 메모리를 확보 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>매개 변수

*pOccDialogInfo*<br/>
`_AFX_OCC_DIALOG_INFO` 대화 상자 템플릿 및 대화 상자에서 호스트 되는 모든 ActiveX 컨트롤에 대 한 정보를 포함 하는 구조체입니다.

### <a name="remarks"></a>설명

이 메모리를 호출 하 여 할당 된 `SplitDialogTemplate`, 대화 상자에서 모든 호스팅된 ActiveX 컨트롤에 대 한 사용 되었습니다.

대화 상자 개체에서 사용 하는 모든 리소스를 정리 프로세스를 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="setdefaultbutton"></a>  COccManager::SetDefaultButton

컨트롤이 기본 단추로 설정 하려면이 함수를 호출 합니다.

```
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,
    BOOL bDefault);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
컨트롤이 포함 된 창에 대 한 포인터입니다.

*bDefault*<br/>
컨트롤이 기본 단추 수 있어야 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  컨트롤에 설정 된 상태 비트 OLEMISC_ACTSLIKEBUTTON 있어야 합니다. OLEMISC 플래그에 대 한 자세한 내용은 참조는 [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) Windows SDK에는 항목입니다.

##  <a name="splitdialogtemplate"></a>  COccManager::SplitDialogTemplate

공용 대화 상자 컨트롤에서 ActiveX 컨트롤을 분할 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,
    DLGITEMTEMPLATE** ppOleDlgItems);
```

### <a name="parameters"></a>매개 변수

*pTemplate*<br/>
대화 상자 템플릿 검사에 대 한 포인터입니다.

*ppOleDlgItems*<br/>
목록 ActiveX 컨트롤이 대화 상자 항목에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

아닌 ActiveX 컨트롤에만 포함 하는 대화 상자 템플릿 구조에 대 한 포인터입니다. ActiveX 컨트롤이 있는 경우에 NULL이 반환 됩니다.

### <a name="remarks"></a>설명

모든 ActiveX 컨트롤이 없으면 서식 파일을 분석 하 고만 비 ActiveX 컨트롤이 포함 된 템플릿을 새로 만들어집니다. 이 프로세스 중에 발견 된 ActiveX 컨트롤에 추가할 *ppOleDlgItems*합니다.

템플릿에서 ActiveX 컨트롤이 없는 경우 NULL이 반환 *합니다.*

> [!NOTE]
>  새 서식 파일은에서 해제에 대 한 할당 된 메모리는 `PostCreateDialog` 함수입니다.

이 프로세스를 사용자 지정 하려면이 함수를 재정의 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleControlSite 클래스](../../mfc/reference/colecontrolsite-class.md)<br/>
[COleControlContainer 클래스](../../mfc/reference/colecontrolcontainer-class.md)
