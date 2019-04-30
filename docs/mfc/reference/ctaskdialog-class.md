---
title: CTaskDialog Class
ms.date: 11/19/2018
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
helpviewer_keywords:
- CTaskDialog [MFC], CTaskDialog
- CTaskDialog [MFC], AddCommandControl
- CTaskDialog [MFC], AddRadioButton
- CTaskDialog [MFC], ClickCommandControl
- CTaskDialog [MFC], ClickRadioButton
- CTaskDialog [MFC], DoModal
- CTaskDialog [MFC], GetCommonButtonCount
- CTaskDialog [MFC], GetCommonButtonFlag
- CTaskDialog [MFC], GetCommonButtonId
- CTaskDialog [MFC], GetOptions
- CTaskDialog [MFC], GetSelectedCommandControlID
- CTaskDialog [MFC], GetSelectedRadioButtonID
- CTaskDialog [MFC], GetVerificationCheckboxState
- CTaskDialog [MFC], IsCommandControlEnabled
- CTaskDialog [MFC], IsRadioButtonEnabled
- CTaskDialog [MFC], IsSupported
- CTaskDialog [MFC], LoadCommandControls
- CTaskDialog [MFC], LoadRadioButtons
- CTaskDialog [MFC], NavigateTo
- CTaskDialog [MFC], OnCommandControlClick
- CTaskDialog [MFC], OnCreate
- CTaskDialog [MFC], OnDestroy
- CTaskDialog [MFC], OnExpandButtonClick
- CTaskDialog [MFC], OnHelp
- CTaskDialog [MFC], OnHyperlinkClick
- CTaskDialog [MFC], OnInit
- CTaskDialog [MFC], OnNavigatePage
- CTaskDialog [MFC], OnRadioButtonClick
- CTaskDialog [MFC], OnTimer
- CTaskDialog [MFC], OnVerificationCheckboxClick
- CTaskDialog [MFC], RemoveAllCommandControls
- CTaskDialog [MFC], RemoveAllRadioButtons
- CTaskDialog [MFC], SetCommandControlOptions
- CTaskDialog [MFC], SetCommonButtonOptions
- CTaskDialog [MFC], SetCommonButtons
- CTaskDialog [MFC], SetContent
- CTaskDialog [MFC], SetDefaultCommandControl
- CTaskDialog [MFC], SetDefaultRadioButton
- CTaskDialog [MFC], SetDialogWidth
- CTaskDialog [MFC], SetExpansionArea
- CTaskDialog [MFC], SetFooterIcon
- CTaskDialog [MFC], SetFooterText
- CTaskDialog [MFC], SetMainIcon
- CTaskDialog [MFC], SetMainInstruction
- CTaskDialog [MFC], SetOptions
- CTaskDialog [MFC], SetProgressBarMarquee
- CTaskDialog [MFC], SetProgressBarPosition
- CTaskDialog [MFC], SetProgressBarRange
- CTaskDialog [MFC], SetProgressBarState
- CTaskDialog [MFC], SetRadioButtonOptions
- CTaskDialog [MFC], SetVerificationCheckbox
- CTaskDialog [MFC], SetVerificationCheckboxText
- CTaskDialog [MFC], SetWindowTitle
- CTaskDialog [MFC], ShowDialog
- CTaskDialog [MFC], TaskDialogCallback
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
ms.openlocfilehash: 04c8a60f546700be8eeb2ec8a948e0ea321d12f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324316"
---
# <a name="ctaskdialog-class"></a>CTaskDialog Class

메시지 상자처럼 작동하지만 사용자에게 추가 정보를 표시할 수 있는 팝업 대화 상자입니다. `CTaskDialog` 에는 사용자로부터 정보를 수집하는 기능을 포함합니다.

## <a name="syntax"></a>구문

```
class CTaskDialog : public CObject
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[CTaskDialog::CTaskDialog](#ctaskdialog)|`CTaskDialog` 개체를 생성합니다.|

### <a name="methods"></a>메서드

|||
|-|-|
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|명령 단추 컨트롤을 추가 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::AddRadioButton](#addradiobutton)|라디오 단추를 추가 하 여 `CTaskDialog`입니다.|
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|프로그래밍 방식으로 명령 단추 컨트롤 또는 일반 단추를 클릭합니다.|
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|프로그래밍 방식으로 라디오 단추를 클릭합니다.|
|[CTaskDialog::DoModal](#domodal)|`CTaskDialog`를 표시합니다.|
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|사용할 수 있는 일반적인 단추의 수를 검색합니다.|
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|Windows 단추를 일반 단추 형식에 연결 된 표준 변환 된 `CTaskDialog` 클래스입니다.|
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|와 관련 된 일반적인 단추 형식 중 하나를 변환 합니다 `CTaskDialog` 클래스는 표준 Windows 단추를 합니다.|
|[CTaskDialog::GetOptions](#getoptions)|이 옵션 플래그를 반환 합니다. `CTaskDialog`합니다.|
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|선택한 명령 단추 컨트롤을 반환합니다.|
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|선택한 라디오 단추를 반환합니다.|
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|확인 확인란의 상태를 검색 합니다.|
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|명령 단추 컨트롤 또는 일반 단추 사용 되는지 여부를 결정 합니다.|
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|라디오 단추를 사용할 수 있는지 여부를 결정 합니다.|
|[CTaskDialog::IsSupported](#issupported)|응용 프로그램을 실행 하는 컴퓨터를 지원 하는지 여부를 결정 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|문자열 테이블에서 데이터를 사용 하 여 명령 단추 컨트롤을 추가 합니다.|
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|문자열 테이블에서 데이터를 사용 하 여 라디오 단추를 추가 합니다.|
|[CTaskDialog::NavigateTo](#navigateto)|포커스를 다른 전송 `CTaskDialog`합니다.|
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|프레임 워크는 명령 단추 컨트롤을 클릭할 때이 메서드를 호출 합니다.|
|[CTaskDialog::OnCreate](#oncreate)|프레임 워크를 만든 후이 메서드를 호출 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::OnDestroy](#ondestroy)|프레임 워크를 즉시 제거 하기 전에이 메서드를 호출 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|프레임 워크 확장 단추를 클릭할 때이 메서드를 호출 합니다.|
|[CTaskDialog::OnHelp](#onhelp)|프레임 워크는 사용자가 도움말을 요청 하는 경우이 메서드를 호출 합니다.|
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|프레임 워크는 사용자가 하이퍼링크를 클릭할 때이 메서드를 호출 합니다.|
|[CTaskDialog::OnInit](#oninit)|이 메서드를 호출 하는 프레임 워크 때는 `CTaskDialog` 초기화 됩니다.|
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|프레임 워크의 제어와 관련 하 여 포커스를 이동할 때이 메서드를 호출 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|프레임 워크는 사용자가 라디오 단추 컨트롤을 선택 하면이 메서드를 호출 합니다.|
|[CTaskDialog::OnTimer](#ontimer)|타이머가 만료 되 면이 메서드를 호출 하는 프레임 워크입니다.|
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|프레임 워크는 사용자가 확인 확인란을 클릭할 때이 메서드를 호출 합니다.|
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|명령 컨트롤을 모두 제거 된 `CTaskDialog`합니다.|
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|모든 라디오 단추를 제거 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|명령 단추 컨트롤에서 업데이트를 `CTaskDialog`입니다.|
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|사용 하도록 설정 하 고 UAC 권한 상승이 필요한 일반적인 단추의 하위 집합을 업데이트 합니다.|
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|일반 단추를 추가 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::SetContent](#setcontent)|콘텐츠를 업데이트 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|기본 명령 단추 컨트롤을 지정합니다.|
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|기본 라디오 단추를 지정합니다.|
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|너비를 조정 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|확장 영역의 업데이트는 `CTaskDialog`합니다.|
|[CTaskDialog::SetFooterIcon](#setfootericon)|바닥글 아이콘에 대 한 업데이트는 `CTaskDialog`합니다.|
|[CTaskDialog::SetFooterText](#setfootertext)|바닥글에 텍스트를 업데이트 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::SetMainIcon](#setmainicon)|주 아이콘 업데이트는 `CTaskDialog`합니다.|
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|기본 명령 업데이트는 `CTaskDialog`합니다.|
|[CTaskDialog::SetOptions](#setoptions)|에 대 한 옵션을 구성 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|움직이는 텍스트 모음을 구성 합니다 `CTaskDialog` 대화 상자에 추가 합니다.|
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|진행률 표시줄의 위치를 조정 합니다.|
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|진행률 표시줄의 범위를 조정합니다.|
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|진행률 표시줄의 상태를 설정 하 고에 표시 된 `CTaskDialog`합니다.|
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|사용 하거나 라디오 단추를 사용 하지 않도록 설정 합니다.|
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|확인 확인란의 선택된 상태를 설정합니다.|
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|확인 확인란 오른쪽에 텍스트를 설정합니다.|
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|제목을 설정 합니다 `CTaskDialog`합니다.|
|[CTaskDialog::ShowDialog](#showdialog)|만들고 표시를 `CTaskDialog`입니다.|
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|프레임 워크는 다양 한 Windows 메시지에 대 한 응답에서이 호출합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|`m_aButtons`|명령 단추 컨트롤에 대 한 배열을 `CTaskDialog`합니다.|
|`m_aRadioButtons`|배열에 대 한 라디오 단추 컨트롤을 `CTaskDialog`입니다.|
|`m_bVerified`|`TRUE` 확인 확인란 선택은 나타냅니다. `FALSE` 은 의미 합니다.|
|`m_footerIcon`|바닥글에 아이콘을 `CTaskDialog`입니다.|
|`m_hWnd`|에 대 한 창 핸들을 `CTaskDialog`입니다.|
|`m_mainIcon`|기본 아이콘의 `CTaskDialog`합니다.|
|`m_nButtonDisabled`|일반 단추를 나타내는 마스크를 사용할 수 없습니다.|
|`m_nButtonElevation`|일반 단추를 나타내는 마스크 UAC 권한 상승이 필요 합니다.|
|`m_nButtonId`|선택한 명령 단추 컨트롤의 ID입니다.|
|`m_nCommonButton`|일반 단추를 나타내는 마스크에 표시 되는 `CTaskDialog`합니다.|
|`m_nDefaultCommandControl`|명령 단추의 ID를 제어 하는 경우 선택 된 `CTaskDialog` 표시 됩니다.|
|`m_nDefaultRadioButton`|라디오 단추의 ID를 제어 하는 경우 선택 된 `CTaskDialog` 표시 됩니다.|
|`m_nFlags`|에 대 한 옵션을 지정 하는 마스크를 `CTaskDialog`입니다.|
|`m_nProgressPos`|진행률 표시줄의 현재 위치입니다.  이 값은 `m_nProgressRangeMin`와 `m_nProgressRangeMax` 사이의 값이어야 합니다.|
|`m_nProgressRangeMax`|진행률 표시줄에 대 한 최대값입니다.|
|`m_nProgressRangeMin`|진행률 표시줄에 대 한 최소값입니다.|
|`m_nProgressState`|진행률 표시줄의 상태입니다. 자세한 내용은 [CTaskDialog::SetProgressBarState](#setprogressbarstate)합니다.|
|`m_nRadioId`|선택한 라디오 단추 컨트롤의 ID입니다.|
|`m_nWidth`|`CTaskDialog`의 너비(픽셀)입니다.|
|`m_strCollapse`|문자열을 `CTaskDialog` 확장 된 정보는 숨겨져 확장 상자 오른쪽에 표시 됩니다.|
|`m_strContent`|문자열 콘텐츠는 `CTaskDialog`합니다.|
|`m_strExpand`|문자열을 `CTaskDialog` 확장 된 정보를 표시할 때 확장 상자 오른쪽에 표시 됩니다.|
|`m_strFooter`|바닥글을 `CTaskDialog`입니다.|
|`m_strInformation`|에 대 한 확장 된 정보는 `CTaskDialog`합니다.|
|`m_strMainInstruction`|기본 명령은 `CTaskDialog`합니다.|
|`m_strTitle`|제목의 `CTaskDialog`합니다.|
|`m_strVerification`|문자열을는 `CTaskDialog` 확인 확인란 오른쪽에 표시 됩니다.|

## <a name="remarks"></a>설명

`CTaskDialog` 클래스 표준 Windows 메시지 상자를 대체 하 고 사용자 로부터 정보를 수집할 새 컨트롤과 같은 추가 기능이 있습니다. 이 클래스는 Visual Studio 2010 이상 MFC 라이브러리입니다. `CTaskDialog` Windows Vista부터 사용할 수 있습니다. 이전 버전의 Windows 표시할 수 없습니다는 `CTaskDialog` 개체입니다. 사용 하 여 `CTaskDialog::IsSupported` 에 현재 사용자는 작업 대화 상자를 표시할 수 있는지 여부를 런타임에 결정 합니다. 표준 Windows 메시지 상자는 계속 지원 됩니다.

`CTaskDialog` 는 빌드할 때 응용 프로그램이 유니코드 라이브러리를 사용 하 여 사용할 수 있습니다.

`CTaskDialog` 서로 다른 두 명의 생성자가 있습니다. 생성자가 하나를 사용 하면 명령 단추 두 개 및 최대 6 개의 일반 단추 컨트롤을 지정할 수 있습니다. 만든 후에 추가 명령 단추를 추가할 수는 `CTaskDialog`합니다. 두 번째 생성자는 모든 명령 단추를 지원 하지 않습니다 하지만 일반 단추 컨트롤의 무제한 추가할 수 있습니다. 생성자에 대 한 자세한 내용은 참조 하세요. [CTaskDialog::CTaskDialog](#ctaskdialog)합니다.

다음 이미지는 예제를 보여 줍니다. `CTaskDialog` 일부 컨트롤의 위치를 보여 줍니다.

![CTaskDialog의 예](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialog의 예") <br/>
샘플 CTaskDialog

## <a name="requirements"></a>요구 사항

**필요한 최소 운영 체제:** Windows Vista

**헤더:** afxtaskdialog.h

##  <a name="addcommandcontrol"></a>  CTaskDialog::AddCommandControl

새 명령 단추 컨트롤을 추가 합니다 `CTaskDialog`합니다.

```
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>매개 변수

*nCommandControlID*<br/>
[in] 명령 컨트롤 id.

*strCaption*<br/>
[in] 문자열을는 `CTaskDialog` 사용자에 게 표시 합니다. 명령의 용도 설명 하기에이 문자열을 사용 합니다.

*bEnabled*<br/>
[in] 새 단추를 사용 하도록 설정 되었거나 사용 하지 않도록 설정 하는 경우를 나타내는 부울 매개 변수입니다.

*bRequiresElevation*<br/>
[in] 명령에 권한 상승이 필요한 지 여부를 나타내는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

`CTaskDialog Class` 개수에 제한 없이 명령 단추 컨트롤을 표시할 수 있습니다. 그러나 경우에 `CTaskDialog` 명령 단추 컨트롤에 표시할, 최대 6 개의 단추를 표시할 수 있습니다. 경우는 `CTaskDialog` 없습니다 명령 단추 컨트롤에 단추 개수에 제한 없이 표시할 수 있습니다.

사용자가 명령 단추 컨트롤을 선택 합니다 `CTaskDialog` 닫습니다. 응용 프로그램에서 사용 하 여 대화 상자를 표시 하는 경우 [CTaskDialog::DoModal](#domodal), `DoModal` 반환 된 *nCommandControlID* 선택한 명령 단추 컨트롤의 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="addradiobutton"></a>  CTaskDialog::AddRadioButton

라디오 단추를 추가 하 여 `CTaskDialog`입니다.

```
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>매개 변수

*nRadioButtonID*<br/>
[in] 라디오 단추의 id 번호입니다.

*strCaption*<br/>
[in] 문자열을는 `CTaskDialog` 라디오 단추 옆에 표시 됩니다.

*bEnabled*<br/>
[in] 라디오 단추를 사용할 수 있는지 여부를 나타내는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

에 대 한 라디오 단추를 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md) 사용자 로부터 정보를 수집할 수 있도록 합니다. 함수를 사용 하 여 [CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid) 라디오 단추 선택 되었는지 확인 하려면.

합니다 `CTaskDialog` 것을 요구 하지 않는 합니다 *nRadioButtonID* 매개 변수는 각 라디오 단추에 대 한 고유 합니다. 그러나 각 라디오 단추에 대 한 고유 식별자를 사용 하지 않는 경우 예기치 않은 동작이 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="clickcommandcontrol"></a>  CTaskDialog::ClickCommandControl

프로그래밍 방식으로 명령 단추 컨트롤 또는 일반 단추를 클릭합니다.

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>매개 변수

*nCommandControlID*<br/>
[in] 클릭 컨트롤의 명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 TDM_CLICK_BUTTON windows 메시지를 생성합니다.

##  <a name="clickradiobutton"></a>  CTaskDialog::ClickRadioButton

프로그래밍 방식으로 라디오 단추를 클릭합니다.

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>매개 변수

*nRadioButtonID*<br/>
[in] 라디오 단추를 클릭의 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 TDM_CLICK_RADIO_BUTTON windows 메시지를 생성합니다.

##  <a name="ctaskdialog"></a>  CTaskDialog::CTaskDialog

인스턴스를 만듭니다는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다.

```
CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));

CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>매개 변수

*strContent*<br/>
[in] 내용에 사용 하는 문자열을 `CTaskDialog`입니다.

*strMainInstruction*<br/>
[in] 기본 명령은 `CTaskDialog`합니다.

*strTitle*<br/>
[in] 제목의 `CTaskDialog`합니다.

*nCommonButtons*<br/>
[in] 추가할 일반적인 단추의 마스크는 `CTaskDialog`합니다.

*nTaskDialogOptions*<br/>
[in] 사용 하는 옵션의 집합을 `CTaskDialog`입니다.

*strFooter*<br/>
[in] 바닥글을 사용 하는 문자열입니다.

*nIDCommandControlsFirst*<br/>
[in] 첫 번째 명령의 문자열 ID입니다.

*nIDCommandControlsLast*<br/>
[in] 마지막 명령은의 문자열 ID입니다.

### <a name="remarks"></a>설명

추가할 수 있는 두 가지는 `CTaskDialog` 응용 프로그램입니다. 첫 번째 방법은 생성자 중 하나를 만드는 데는 `CTaskDialog` 를 사용 하 여이 표시할 [CTaskDialog::DoModal](#domodal)합니다. 두 번째 방법은 정적 함수를 사용 하는 것 [CTaskDialog::ShowDialog](#showdialog)를 표시할 수 있습니다를 `CTaskDialog` 명시적으로 만들지 않고는 `CTaskDialog` 개체입니다.

두 번째 생성자는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 명령 단추 컨트롤을 만듭니다. 리소스 파일에 문자열 테이블에 연결 된 문자열 Id 사용 하 여 여러 문자열입니다. 이 메서드 간에 문자열 테이블의 유효한 각 항목에 대 한 명령 단추 컨트롤을 추가 *nIDCommandControlsFirst* 하 고 *nCommandControlsLast*(포함). 이러한 명령 단추 컨트롤에 대 한 문자열 테이블의 문자열은 컨트롤의 캡션 및 문자열 ID는 컨트롤의 id입니다.

참조 [CTaskDialog::SetOptions](#setoptions) 목록을 사용할 수 있는 옵션에 대 한 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="domodal"></a>  CTaskDialog::DoModal

표시 된 `CTaskDialog` 고 모달 합니다.

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>매개 변수

*hParent*<br/>
[in] 부모 창입니다는 `CTaskDialog`합니다.

### <a name="return-value"></a>반환 값

사용자가 선택한 옵션에 해당 하는 정수입니다.

### <a name="remarks"></a>설명

이 인스턴스를 표시 합니다 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md)합니다. 그런 다음 응용 프로그램 대화 상자를 닫으려면 사용자를 기다립니다.

합니다 `CTaskDialog` 명령 링크 컨트롤, 일반적인 단추를 선택 하거나 닫을 때 닫습니다는 `CTaskDialog`합니다. 반환 값에는 사용자 대화 상자를 닫은 방법을 나타내는 식별자입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="getcommonbuttoncount"></a>  CTaskDialog::GetCommonButtonCount

일반 단추 수를 검색합니다.

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>반환 값

사용할 수 있는 일반적인 단추의 수입니다.

### <a name="remarks"></a>설명

기본 단추를 제공 하는 일반적인 단추가 [CTaskDialog::CTaskDialog](#ctaskdialog)합니다. 합니다 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md) 대화 상자의 아래쪽 단추를 표시 합니다.

열거 목록은 단추 CommCtrl.h에 제공 됩니다.

##  <a name="getcommonbuttonflag"></a>  CTaskDialog::GetCommonButtonFlag

Windows 단추를 일반 단추 형식에 연결 된 표준 변환 합니다 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다.

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>매개 변수

*nButtonId*<br/>
[in] 표준 Windows 단추 값입니다.

### <a name="return-value"></a>반환 값

해당 변수의 `CTaskDialog` 공용 단추입니다. 해당 공용 단추가 제공 되지 않음 인 경우 0을 반환 합니다.

##  <a name="getcommonbuttonid"></a>  CTaskDialog::GetCommonButtonId

와 관련 된 일반적인 단추 형식 중 하나를 변환 합니다 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md) 표준 Windows 단추를 합니다.

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>매개 변수

*nFlag*<br/>
[in] 와 관련 된 일반적인 단추 종류를 `CTaskDialog` 클래스입니다.

### <a name="return-value"></a>반환 값

해당 표준 Windows 단추의 값입니다. 해당 Windows 단추가 제공 되지 않음 인 경우 메서드는 0을 반환 합니다.

##  <a name="getoptions"></a>  CTaskDialog::GetOptions

이 옵션 플래그를 반환 합니다. `CTaskDialog`합니다.

```
int GetOptions() const;
```

### <a name="return-value"></a>반환 값

에 대 한 플래그를 `CTaskDialog`입니다.

### <a name="remarks"></a>설명

사용할 수 있는 옵션에 대 한 자세한 합니다 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)를 참조 하세요 [CTaskDialog::SetOptions](#setoptions).

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="getselectedcommandcontrolid"></a>  CTaskDialog::GetSelectedCommandControlID

선택한 명령 단추 컨트롤을 반환합니다.

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>반환 값

현재 선택한 명령 단추 컨트롤의 ID입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 사용자가 선택한 명령 단추의 ID를 검색할 필요가 없습니다. 해당 ID가 반환 [CTaskDialog::DoModal](#domodal) 하거나 [CTaskDialog::ShowDialog](#showdialog)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="getselectedradiobuttonid"></a>  CTaskDialog::GetSelectedRadioButtonID

선택한 라디오 단추를 반환합니다.

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>반환 값

선택된 된 라디오 단추의 ID입니다.

### <a name="remarks"></a>설명

사용자 선택된 된 라디오 단추를 검색 하는 대화 상자를 닫은 후이 메서드를 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="getverificationcheckboxstate"></a>  CTaskDialog::GetVerificationCheckboxState

확인 확인란의 상태를 검색 합니다.

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>반환 값

확인란을 선택한 경우 FALSE 있지 않으면 TRUE입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="iscommandcontrolenabled"></a>  CTaskDialog::IsCommandControlEnabled

명령 단추 컨트롤 또는 단추 사용 되는지 여부를 결정 합니다.

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>매개 변수

*nCommandControlID*<br/>
[in] 테스트 단추 명령 단추 컨트롤의 ID입니다.

### <a name="return-value"></a>반환 값

컨트롤을 사용 하는 경우 FALSE 있지 않으면 TRUE입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여의 공통 단추 및 명령 단추 컨트롤을 모두의 가용성을 확인 하는 `CTaskDialog` 클래스 * 합니다.

하는 경우 *nCommandControlID* 은 유효한 식별자가 아닙니다에 대 한 일반적 `CTaskDialog` 단추 또는 명령 단추 컨트롤을이 메서드가 예외를 throw 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="isradiobuttonenabled"></a>  CTaskDialog::IsRadioButtonEnabled

라디오 단추를 사용할 수 있는지 여부를 결정 합니다.

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>매개 변수

*nRadioButtonID*<br/>
[in] 테스트 라디오 단추의 ID입니다.

### <a name="return-value"></a>반환 값

라디오 단추를 사용 하는 경우 FALSE 있지 않으면 TRUE입니다.

### <a name="remarks"></a>설명

하는 경우 *nRadioButtonID* 유효한 식별자가 아닙니다 라디오 단추의 경우,이 메서드는 예외를 throw 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="issupported"></a>  CTaskDialog::IsSupported

응용 프로그램을 실행 하는 컴퓨터를 지원 하는지 여부를 결정 합니다 `CTaskDialog`합니다.

```
static BOOL IsSupported();
```

### <a name="return-value"></a>반환 값

컴퓨터에서 지 원하는 경우 TRUE를 `CTaskDialog`; FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 응용 프로그램을 실행 하는 컴퓨터에서 지 원하는 경우 런타임 시 결정 하는 `CTaskDialog` 클래스입니다. 컴퓨터를 지원 하지 않는 경우는 `CTaskDialog`, 사용자에 게 정보를 전달 하는 또 다른 방법을 제공 해야 합니다. 사용 하려는 경우 응용 프로그램 충돌을 `CTaskDialog` 지원 하지 않는 컴퓨터를 `CTaskDialog` 클래스입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

##  <a name="loadcommandcontrols"></a>  CTaskDialog::LoadCommandControls

문자열 테이블에서 데이터를 사용 하 여 명령 단추 컨트롤을 추가 합니다.

```
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>매개 변수

*nIDCommandControlsFirst*<br/>
[in] 첫 번째 명령의 문자열 ID입니다.

*nIDCommandControlsLast*<br/>
[in] 마지막 명령은의 문자열 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 명령 단추 컨트롤을 만듭니다. 리소스 파일에 문자열 테이블에 연결 된 문자열 Id 사용 하 여 여러 문자열입니다. 이 메서드를 사용 하 여 추가 된 새 명령 단추 컨트롤 컨트롤의 캡션 및 문자열 ID에 대 한 컨트롤의 id 문자열을 사용 선택 하는 문자열의 범위에서 제공 하는 *nIDCommandControlsFirst* 하 고 *nCommandControlsLast*(포함). 범위에 빈 항목이 있으면 메서드는 해당 항목에 대 한 명령 단추 컨트롤을 추가 하지 않습니다.

기본적으로 새 명령 단추 컨트롤을 사용 및 권한 상승 필요 하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="loadradiobuttons"></a>  CTaskDialog::LoadRadioButtons

문자열 테이블에서 데이터를 사용 하 여 라디오 단추 컨트롤을 추가 합니다.

```
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>매개 변수

*nIDRadioButtonsFirst*<br/>
[in] 문자열의 ID는 첫 번째 라디오 단추입니다.

*nIDRadioButtonsLast*<br/>
[in] 마지막 라디오 단추의 문자열 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 라디오 단추를 만듭니다. 리소스 파일에 문자열 테이블에 연결 된 문자열 Id 사용 하 여 여러 문자열입니다. 이 메서드를 사용 하 여 추가 된 새 라디오 단추 라디오 단추의 캡션과 문자열 ID에 대 한 라디오 단추의 id 문자열을 사용 선택 하는 문자열의 범위에서 제공 하는 *nIDRadioButtonsFirst* 하 고 *nRadioButtonsLast*(포함). 범위에 빈 항목이 있으면 메서드는 해당 항목에 대 한 라디오 단추를 추가 하지 않습니다.

기본적으로 새 라디오 단추가 활성화 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="navigateto"></a>  CTaskDialog::NavigateTo

포커스를 다른 전송 `CTaskDialog`합니다.

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>매개 변수

*oTaskDialog*<br/>
[in] `CTaskDialog` 포커스를 받는 합니다.

### <a name="remarks"></a>설명

이 메서드는 현재 숨깁니다 `CTaskDialog` 표시 되는 경우는 *oTaskDialog*합니다. 합니다 *oTaskDialog* 현재와 동일한 위치에 표시 됩니다 `CTaskDialog`합니다.

##  <a name="oncommandcontrolclick"></a>  CTaskDialog::OnCommandControlClick

프레임 워크는 명령 단추 컨트롤을 클릭할 때이 메서드를 호출 합니다.

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>매개 변수

*nCommandControlID*<br/>
[in] 사용자가 선택한 명령 단추 컨트롤의 ID입니다.

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="oncreate"></a>  CTaskDialog::OnCreate

프레임 워크를 만든 후이 메서드를 호출 합니다 `CTaskDialog`합니다.

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="ondestroy"></a>  CTaskDialog::OnDestroy

프레임 워크를 즉시 제거 하기 전에이 메서드를 호출 합니다 `CTaskDialog`합니다.

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="onexpandbuttonclick"></a>  CTaskDialog::OnExpandButtonClick

프레임 워크 확장 단추를 클릭할 때이 메서드를 호출 합니다.

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>매개 변수

*bExpanded*<br/>
[in] 0이 아닌 값에 추가 정보가 표시 됩니다. 0 추가 정보 숨겨져 있음을 나타냅니다.

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="onhelp"></a>  CTaskDialog::OnHelp

프레임 워크는 사용자가 도움말을 요청 하는 경우이 메서드를 호출 합니다.

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="onhyperlinkclick"></a>  CTaskDialog::OnHyperlinkClick

프레임 워크는 사용자가 하이퍼링크를 클릭할 때이 메서드를 호출 합니다.

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>매개 변수

*strHref*<br/>
[in] 하이퍼링크를 나타내는 문자열입니다.

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [ShellExecute](/windows/desktop/api/shellapi/nf-shellapi-shellexecutea) S_OK를 반환 하기 전에 합니다.

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="oninit"></a>  CTaskDialog::OnInit

이 메서드를 호출 하는 프레임 워크 때는 `CTaskDialog` 초기화 됩니다.

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="onnavigatepage"></a>  CTaskDialog::OnNavigatePage

프레임 워크에 대 한 응답에서이 메서드를 호출 합니다 [CTaskDialog::NavigateTo](#navigateto) 메서드.

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="onradiobuttonclick"></a>  CTaskDialog::OnRadioButtonClick

프레임 워크는 사용자가 라디오 단추 컨트롤을 선택 하면이 메서드를 호출 합니다.

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>매개 변수

*nRadioButtonID*<br/>
[in] 사용자가 클릭 한 라디오 단추 컨트롤의 ID입니다.

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="ontimer"></a>  CTaskDialog::OnTimer

타이머가 만료 되 면이 메서드를 호출 하는 프레임 워크입니다.

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>매개 변수

*lTime*<br/>
[in] 시간 이후의 밀리초를 `CTaskDialog` 만든 또는 타이머 다시 설정 되었습니다.

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="onverificationcheckboxclick"></a>  CTaskDialog::OnVerificationCheckboxClick

프레임 워크는 사용자가 확인 확인란을 클릭할 때이 메서드를 호출 합니다.

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>매개 변수

*bChecked*<br/>
[in] TRUE 이면 확인 확인란을 선택 하 고 있습니다. FALSE 이면 아닙니다.

### <a name="return-value"></a>반환 값

기본 구현은 S_OK를 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 동작을 구현 하는 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="removeallcommandcontrols"></a>  CTaskDialog::RemoveAllCommandControls

명령 단추 컨트롤을 모두 제거 된 `CTaskDialog`합니다.

```
void RemoveAllCommandControls();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="removeallradiobuttons"></a>  CTaskDialog::RemoveAllRadioButtons

모든 라디오 단추를 제거 합니다 `CTaskDialog`합니다.

```
void RemoveAllRadioButtons();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setcommandcontroloptions"></a>  CTaskDialog::SetCommandControlOptions

명령 단추 컨트롤에서 업데이트를 `CTaskDialog`입니다.

```
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>매개 변수

*nCommandControlID*<br/>
[in] 업데이트 명령 컨트롤의 ID입니다.

*bEnabled*<br/>
[in] 지정한 명령 단추 컨트롤이 사용 하도록 설정 되었거나 사용 하지 않도록 설정 하는 경우를 나타내는 부울 매개 변수입니다.

*bRequiresElevation*<br/>
[in] 지정 된 명령 단추 컨트롤에 권한 상승이 필요한 경우를 나타내는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 명령 단추 컨트롤을 사용 하도록 설정할지 또는에 추가한 후에 권한 상승이 필요한 지 여부를 변경 합니다 `CTaskDialog` 클래스입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="setcommonbuttonoptions"></a>  CTaskDialog::SetCommonButtonOptions

사용 하도록 설정 하 고 UAC 권한 상승을 요구 하는 일반적인 단추의 하위 집합을 업데이트 합니다.

```
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>매개 변수

*nDisabledButtonMask*<br/>
[in] 일반 단추를 사용 하지 않도록 설정에 대 한 마스크입니다.

*nElevationButtonMask*<br/>
[in] 권한 상승 해야 하는 일반 단추에 대 한 마스크입니다.

### <a name="remarks"></a>설명

인스턴스를 사용할 수 있는 일반적인 단추가 설정할 수 있습니다 합니다 [CTaskDialog Class](../../mfc/reference/ctaskdialog-class.md) 생성자를 사용 하 여 [CTaskDialog::CTaskDialog](#ctaskdialog) 방법과 [CTaskDialog::SetCommonButtons ](#setcommonbuttons). `CTaskDialog::SetCommonButtonOptions` 새 일반 단추 추가 지원 하지 않습니다.

이 메서드를 사용 하지 않도록 설정 하거나이 제공 되지 않는 일반적인 단추 상승 사용 하는 경우 `CTaskDialog`,이 메서드를 사용 하 여 예외를 throw 합니다 [확인](diagnostic-services.md#ensure) 매크로입니다.

이 메서드를 사용할 수 있는 모든 단추를 활성화 합니다 `CTaskDialog` 아닌에 *nDisabledButtonMask*이전에 비활성화 된 경우에 합니다. 이 메서드는 비슷한 방식으로 권한 상승 처리: 사용할 수 있지만에 포함 되지 않고 공용 단추가 있는 경우 권한 상승이 필요 하지 않은 일반적인 단추 기록 *nElevationButtonMask*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

##  <a name="setcommonbuttons"></a>  CTaskDialog::SetCommonButtons

일반 단추를 추가 합니다 `CTaskDialog`합니다.

```
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>매개 변수

*nButtonMask*<br/>
[in] 추가할 단추의 마스크는 `CTaskDialog`합니다.

*nDisabledButtonMask*<br/>
[in] 단추를 사용 하지 않도록 설정 하는 마스크입니다.

*nElevationButtonMask*<br/>
[in] 권한 상승 해야 하는 단추는 마스크입니다.

### <a name="remarks"></a>설명

이 인스턴스에 대 한 표시 창을 후이 메서드를 호출할 수 없습니다는 `CTaskDialog` 클래스가 만들어집니다. 이렇게 하면이 메서드는 예외가 throw 됩니다.

단추에 나타난 *nButtonMask* 재정의를 이전에 추가한 일반적인 단추는 `CTaskDialog`합니다. 에 표시 된 단추만 *nButtonMask* 사용할 수 있습니다.

경우 *nDisabledButtonMask* 또는 *nElevationButtonMask* 이 아닌 단추를 포함 *nButtonMask*,이 메서드는 사용하여예외를throw[확인](diagnostic-services.md#ensure) 매크로입니다.

기본적으로 모든 공용 단추 설정 되어 있고 권한 상승이 필요 하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

##  <a name="setcontent"></a>  CTaskDialog::SetContent

콘텐츠를 업데이트 합니다 `CTaskDialog`합니다.

```
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>매개 변수

*strContent*<br/>
[in] 사용자에 게 표시할 문자열입니다.

### <a name="remarks"></a>설명

콘텐츠는 `CTaskDialog` 클래스 대화 상자의 주 섹션에서 사용자에 게 표시 되는 텍스트입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setdefaultcommandcontrol"></a>  CTaskDialog::SetDefaultCommandControl

기본 명령 단추 컨트롤을 지정합니다.

```
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>매개 변수

*nCommandControlID*<br/>
[in] 기본 명령 단추 컨트롤의 ID입니다.

### <a name="remarks"></a>설명

기본 명령 단추 컨트롤은 컨트롤에 선택 하는 경우는 `CTaskDialog` 사용자에 게 먼저 표시 됩니다.

이 메서드는 지정 된 명령 단추 컨트롤을 찾을 수 없는 경우 예외를 throw *nCommandControlID*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

##  <a name="setdefaultradiobutton"></a>  CTaskDialog::SetDefaultRadioButton

기본 라디오 단추를 지정합니다.

```
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>매개 변수

*nRadioButtonID*<br/>
[in] 기본 라디오 단추의 ID입니다.

### <a name="remarks"></a>설명

기본 라디오 단추는 단추입니다 경우 선택 된 `CTaskDialog` 사용자에 게 먼저 표시 됩니다.

이 메서드는 지정 된 라디오 단추를 찾을 수 없으면 예외를 throw *nRadioButtonID*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setdialogwidth"></a>  CTaskDialog::SetDialogWidth

너비를 조정 합니다 `CTaskDialog`합니다.

```
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
[in] 대화 상자의 픽셀에서 너비입니다.

### <a name="remarks"></a>설명

매개 변수 *nWidth* 0 보다 크거나 이어야 합니다. 그렇지 않은 경우이 메서드는 예외가 throw 됩니다.

하는 경우 *nWidth* 이 메서드 설정 대화 상자 기본 크기를 0으로 설정 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setexpansionarea"></a>  CTaskDialog::SetExpansionArea

확장 영역의 업데이트는 `CTaskDialog`합니다.

```
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>매개 변수

*strExpandedInformation*<br/>
[in] 문자열을는 `CTaskDialog` 확장 단추를 클릭할 때 대화 상자의 본문에 표시 됩니다.

*strCollapsedLabel*<br/>
[in] 문자열을는 `CTaskDialog` 확장 된 영역을 축소 되는 경우 확장 단추 옆에 표시 됩니다.

*strExpandedLabel*<br/>
[in] 문자열을는 `CTaskDialog` 확장 된 영역에 표시 되 면 확장 단추 옆에 표시 됩니다.

### <a name="remarks"></a>설명

확장 영역의 `CTaskDialog` 클래스를 사용 하면 사용자에 게 추가 정보를 제공할 수 있습니다. 확장 영역은의 주요 부분에는 `CTaskDialog`제목 및 콘텐츠 문자열의 바로 아래 있는 합니다.

경우는 `CTaskDialog` 첫 번째는 확장 된 정보는 표시 되지 않습니다 및 배치 표시 `strCollapsedLabel` 확장 단추 옆에 있는 합니다. 확장 단추를 클릭할 때 합니다 `CTaskDialog` 표시 *strExpandedInformation* 레이블을 변경 하 고 *strExpandedLabel*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setfootericon"></a>  CTaskDialog::SetFooterIcon

바닥글 아이콘 업데이트는 `CTaskDialog`합니다.

```
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>매개 변수

*hFooterIcon*<br/>
[in] 새 아이콘의 `CTaskDialog`합니다.

*lpszFooterIcon*<br/>
[in] 새 아이콘의 `CTaskDialog`합니다.

### <a name="remarks"></a>설명

바닥글 아이콘의 맨 아래에 표시 되는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다. 이 바닥글 텍스트에 연결할 수 있습니다. 바닥글 텍스트를 변경할 수 있습니다 [CTaskDialog::SetFooterText](#setfootertext)합니다.

이 메서드에서 사용 하 여 예외를 throw 합니다 [확인](diagnostic-services.md#ensure) 매크로 경우는 `CTaskDialog` 표시 됩니다 입력된 매개 변수는 NULL 또는 합니다.

A `CTaskDialog` 받아들일 수 있습니다는 `HICON` 또는 `LPCWSTR` 바닥글 아이콘으로 합니다. 생성자에서 TDF_USE_HICON_FOOTER 옵션을 설정 하 여 구성 됨 또는 [CTaskDialog::SetOptions](#setoptions)합니다. 기본적으로 `CTaskDialog` 사용 하도록 구성 된 `LPCWSTR` 바닥글 아이콘에 대 한 입력된 형식으로 합니다. 이 메서드는 부적절 한 형식을 사용 하 여 아이콘을 설정 하려고 하면 예외가 발생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setfootertext"></a>  CTaskDialog::SetFooterText

바닥글에 텍스트를 업데이트 합니다 `CTaskDialog`합니다.

```
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>매개 변수

*strFooterText*<br/>
[in] 바닥글에 대 한 새 텍스트입니다.

### <a name="remarks"></a>설명

바닥글 아이콘 아래에 바닥글 텍스트 옆에 표시 됩니다는 `CTaskDialog`합니다. 바닥글 아이콘을 사용 하 여 변경할 수 있습니다 [CTaskDialog::SetFooterIcon](#setfootericon)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setmainicon"></a>  CTaskDialog::SetMainIcon

주 아이콘 업데이트는 `CTaskDialog`합니다.

```
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>매개 변수

*hMainIcon*<br/>
[in] 새 아이콘입니다.

*lpszMainIcon*<br/>
[in] 새 아이콘입니다.

### <a name="remarks"></a>설명

이 메서드에서 사용 하 여 예외를 throw 합니다 [확인](diagnostic-services.md#ensure) 매크로 경우는 `CTaskDialog` 표시 됩니다 입력된 매개 변수는 NULL 또는 합니다.

A `CTaskDialog` 받아들일 수 있습니다는 `HICON` 또는 `LPCWSTR` 주 아이콘으로 합니다. 생성자에서 TDF_USE_HICON_MAIN 옵션을 설정 하거나에서 구성할 수 있습니다 합니다 [CTaskDialog::SetOptions](#setoptions) 메서드. 기본적으로 `CTaskDialog` 사용 하도록 구성 된 `LPCWSTR` 주 아이콘에 대 한 입력된 형식으로 합니다. 이 메서드는 부적절 한 형식을 사용 하 여 아이콘을 설정 하려고 하면 예외가 발생 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setmaininstruction"></a>  CTaskDialog::SetMainInstruction

기본 명령 업데이트는 `CTaskDialog`합니다.

```
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>매개 변수

*strInstructions*<br/>
[in] 새 기본 명령입니다.

### <a name="remarks"></a>설명

기본 명령을 `CTaskDialog` 클래스는 큰 굵은 글꼴에서 사용자에 게 표시 되는 텍스트입니다. 대화 상자의 제목 표시줄 아래에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setoptions"></a>  CTaskDialog::SetOptions

에 대 한 옵션을 구성 합니다 `CTaskDialog`합니다.

```
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>매개 변수

*nOptionFlag*<br/>
[in] 사용 하는 플래그 집합을 `CTaskDialog`입니다.

### <a name="remarks"></a>설명

이 메서드는에 대 한 현재 옵션을 모두를 해제 합니다 `CTaskDialog`합니다. 현재 옵션을 유지 하려면 먼저 검색 해야을 사용 하 여 [CTaskDialog::GetOptions](#getoptions) 설정 하려는 옵션을 사용 하 여 결합 합니다.

다음 표에서 유효한 모든 옵션을 나열합니다.

|||
|-|-|
|TDF_ENABLE_HYPERLINKS|하이퍼링크를 사용 하도록 설정 된 `CTaskDialog`합니다.|
|TDF_USE_HICON_MAIN|구성 된 `CTaskDialog` 사용 하는 `HICON` 주 아이콘에 대 한 합니다. 대신 사용 하는 것을 `LPCWSTR`입니다.|
|TDF_USE_HICON_FOOTER|구성 된 `CTaskDialog` 사용 하는 `HICON` 바닥글 아이콘에 대 한 합니다. 대신 사용 하는 것을 `LPCWSTR`입니다.|
|TDF_ALLOW_DIALOG_CANCELLATION|사용자가 닫을 수 있습니다는 `CTaskDialog` 키보드를 사용 하 여 또는 대화 상자의 오른쪽 위 모퉁이에서 아이콘을 사용 하 여 경우에 합니다 **취소** 단추가 활성화 되지 않습니다. 이 플래그가 설정 되지 않은 경우 및 **취소** 단추가 활성화 되지 않으면, 사용자 alt+f4, Esc 키를 사용 하 여 대화 상자를 닫을 수 없습니다 또는 제목 표시줄의 닫기 단추.|
|TDF_USE_COMMAND_LINKS|구성 된 `CTaskDialog` 명령 단추 컨트롤을 사용 하 합니다.|
|TDF_USE_COMMAND_LINKS_NO_ICON|구성 된 `CTaskDialog` 컨트롤 옆의 아이콘을 표시 하지 않고 명령 단추 컨트롤을 사용 하 합니다. TDF_USE_COMMAND_LINKS TDF_USE_COMMAND_LINKS_NO_ICON를 재정의합니다.|
|TDF_EXPAND_FOOTER_AREA|현재 확장 되어 확장 영역을 나타냅니다.|
|TDF_EXPANDED_BY_DEFAULT|확장 영역 기본적으로 확장 되는지 여부를 결정 합니다.|
|TDF_VERIFICATION_FLAG_CHECKED|확인 확인란 현재 선택 된 것을 나타냅니다.|
|TDF_SHOW_PROGRESS_BAR|구성 된 `CTaskDialog` 진행률 표시줄을 표시 합니다.|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|움직이는 진행률 표시줄이 되도록 진행률 표시줄을 구성 합니다. 이 옵션을 사용 하도록 설정 하면 TDF_SHOW_PROGRESS_BAR 예상 동작을 설정 해야 합니다.|
|TDF_CALLBACK_TIMER|나타내는 `CTaskDialog` 콜백 간격은 약 200 밀리초로 설정 됩니다.|
|TDF_POSITION_RELATIVE_TO_WINDOW|구성 된 `CTaskDialog` 부모 창을 기준으로 가운데 맞춤 될 합니다. 이 플래그를 사용 하지 않는 경우는 `CTaskDialog` 모니터를 기준으로 가운데 맞춤 됩니다.|
|TDF_RTL_LAYOUT|구성 된 `CTaskDialog` 오른쪽에서 왼쪽 읽기 모드에 대 한 합니다.|
|TDF_NO_DEFAULT_RADIO_BUTTON|없음 라디오 단추가 선택 되어 있는지를 나타내는 경우는 `CTaskDialog` 나타납니다.|
|TDF_CAN_BE_MINIMIZED|최소화 하기 위해 사용자를 사용 하도록 설정 된 `CTaskDialog`합니다. 이 옵션을 지원 하 여 `CTaskDialog` 모달 일 수 없습니다. MFC MFC는 모덜리스를 지원 하지 않으므로이 옵션을 지원 하지 않습니다 `CTaskDialog`합니다.|

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="setprogressbarmarquee"></a>  CTaskDialog::SetProgressBarMarquee

움직이는 텍스트 모음을 구성 합니다 `CTaskDialog` 대화 상자에 추가 합니다.

```
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>매개 변수

*bEnabled*<br/>
[in] 움직이는 텍스트 모음;를 사용 하도록 설정 움직이는 텍스트 모음을 사용 하지 않도록 설정 하 고에서 제거 하려는 경우 FALSE를 `CTaskDialog`입니다.

*nMarqueeSpeed*<br/>
[in] 움직이는 텍스트 막대의 속도 나타내는 정수입니다.

### <a name="remarks"></a>설명

움직이는 텍스트 막대의 기본 텍스트 아래에 나타납니다는 `CTaskDialog` 클래스입니다.

사용 하 여 *nMarqueeSpeed* 움직이는 표시줄의 속도를 설정 값이 클수록 더 느린 속도 나타냅니다. 값이 0에 대 한 *nMarqueeSpeed* 움직이는 텍스트 모음에 대 한 Windows의 기본 속도로 이동 합니다.

이 방법을 사용 하 여 예외를 throw 합니다 [확인 하세요](diagnostic-services.md#ensure) 매크로 경우 *nMarqueeSpeed* 0 보다 작습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarposition"></a>  CTaskDialog::SetProgressBarPosition

진행률 표시줄의 위치를 조정 합니다.

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>매개 변수

*nProgressPos*<br/>
[in] 진행률 표시줄의 위치입니다.

### <a name="remarks"></a>설명

이 방법을 사용 하 여 예외를 throw 합니다 [확인 하세요](diagnostic-services.md#ensure) 매크로 경우 *nProgressPos* 진행률 표시줄 범위에 있지 않습니다. 진행률 표시줄의 범위를 변경할 수 있습니다 [CTaskDialog::SetProgressBarRange](#setprogressbarrange)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarrange"></a>  CTaskDialog::SetProgressBarRange

진행률 표시줄의 범위를 조정합니다.

```
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>매개 변수

*nRangeMin*<br/>
[in] 진행률 표시줄의 하한값입니다.

*nRangeMax*<br/>
[in] 진행률 표시줄의 상한입니다.

### <a name="remarks"></a>설명

기준으로 진행률 표시줄의 위치가 *nRangeMin* 하 고 *nRangeMax*합니다. 예를 들어 경우 *nRangeMin* 은 50 및 *nRangeMax* 은 100, 75 위치는 진행률 표시줄 짝수가 있습니다. 사용 하 여 [CTaskDialog::SetProgressBarPosition](#setprogressbarposition) 진행률 표시줄의 위치를 설정 합니다.

진행률 표시줄을 표시 하려면 TDF_SHOW_PROGRESS_BAR를 사용 하도록 설정 하는 옵션 및 TDF_SHOW_MARQUEE_PROGRESS_BAR 사용 되지 않아야 합니다. 이 메서드는 자동으로 TDF_SHOW_PROGRESS_BAR를 설정 하 고 TDF_SHOW_MARQUEE_PROGRESS_BAR 지웁니다. 사용 하 여 [CTaskDialog::SetOptions](#setoptions) 수동으로이 인스턴스에 대 한 옵션을 변경 하는 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다.

이 메서드에서 사용 하 여 예외를 throw 합니다 [확인](diagnostic-services.md#ensure) 매크로 경우 *nRangeMin* 은 보다 작지 않음 *nRangeMax*합니다. 이 메서드는 또한 예외를 throw 하는 경우는 `CTaskDialog` 이미 표시 되어 움직이는 진행률 표시줄이 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setprogressbarstate"></a>  CTaskDialog::SetProgressBarState

진행률 표시줄의 상태를 설정 하 고에 표시 된 `CTaskDialog`합니다.

```
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>매개 변수

*nState*<br/>
[in] 진행률 표시줄의 상태입니다. 가능한 값에 대 한 설명 섹션을 참조 합니다.

### <a name="remarks"></a>설명

이 방법을 사용 하 여 예외를 throw 합니다 [확인](diagnostic-services.md#ensure) 매크로 경우는 `CTaskDialog` 이미 표시 되어 움직이는 진행률 표시줄이 합니다.

다음 표에서 대 한 가능한 값 *nState*합니다. 이러한 모든 경우 지정 된 중지 위치에 도달할 때까지 진행률 표시줄 일반 색으로 채워집니다. 이때 상태를 기반으로 하는 색을 변경 됩니다.

|||
|-|-|
|PBST_NORMAL|진행률 표시줄 채우는, `CTaskDialog` 막대의 색을 변경 되지 않습니다. 기본적으로 일반 색은 녹색입니다.|
|PBST_ERROR|진행률 표시줄 채우는, `CTaskDialog` 오류 색 막대의 색을 변경 합니다. 기본적으로 빨간색입니다.|
|PBST_PAUSED|진행률 표시줄 채우는, `CTaskDialog` 일시 중지 된 색 막대의 색을 변경 합니다. 기본적으로 노란색입니다.|

진행률 표시줄을 사용 하 여 중지할 위치를 설정할 수 있습니다 [CTaskDialog::SetProgressBarPosition](#setprogressbarposition)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

##  <a name="setradiobuttonoptions"></a>  CTaskDialog::SetRadioButtonOptions

사용 하거나 라디오 단추를 사용 하지 않도록 설정 합니다.

```
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>매개 변수

*nRadioButtonID*<br/>
[in] 라디오 단추 컨트롤의 ID입니다.

*bEnabled*<br/>
[in] 라디오 단추를 사용 하도록 설정 라디오 단추를 사용 하지 않도록 설정 하려면 FALSE입니다.

### <a name="remarks"></a>설명

이 방법을 사용 하 여 예외를 throw 합니다 [확인 하세요](diagnostic-services.md#ensure) 매크로 경우 *nRadioButtonID* 라디오 단추에 대 한 올바른 ID가 아닙니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

##  <a name="setverificationcheckbox"></a>  CTaskDialog::SetVerificationCheckbox

확인 확인란의 선택된 상태를 설정합니다.

```
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>매개 변수

*bChecked*<br/>
[in] True 이면 확인 확인란 선택한 경우는 `CTaskDialog` 후보가 표시 됩니다. 확인란을 확인 하려면 FALSE를 선택 하는 경우 취소는 `CTaskDialog` 표시 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="setverificationcheckboxtext"></a>  CTaskDialog::SetVerificationCheckboxText

확인 확인란 오른쪽에 표시 되는 텍스트를 설정 합니다.

```
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>매개 변수

*strVerificationText*<br/>
[in] 확인 확인란 옆에 표시 되는이 메서드는 텍스트입니다.

### <a name="remarks"></a>설명

이 메서드에서 사용 하 여 예외가 throw 됩니다는 [확인](diagnostic-services.md#ensure) 이 매크로의 인스턴스를 `CTaskDialog` 클래스가 이미 표시 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

##  <a name="setwindowtitle"></a>  CTaskDialog::SetWindowTitle

제목을 설정 합니다 `CTaskDialog`합니다.

```
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>매개 변수

*strWindowTitle*<br/>
[in] 새 제목을 `CTaskDialog`합니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

##  <a name="showdialog"></a>  CTaskDialog::ShowDialog

만들고 표시를 `CTaskDialog`입니다.

```
static INT_PTR ShowDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>매개 변수

*strContent*<br/>
[in] 내용에 사용 하는 문자열을 `CTaskDialog`입니다.

*strMainInstruction*<br/>
[in] 기본 명령은 `CTaskDialog`합니다.

*strTitle*<br/>
[in] 제목의 `CTaskDialog`합니다.

*nIDCommandControlsFirst*<br/>
[in] 첫 번째 명령의 문자열 ID입니다.

*nIDCommandControlsLast*<br/>
[in] 마지막 명령은의 문자열 ID입니다.

*nCommonButtons*<br/>
[in] 추가할 단추의 마스크는 `CTaskDialog`합니다.

*nTaskDialogOptions*<br/>
[in] 사용 하는 옵션의 집합을 `CTaskDialog`입니다.

*strFooter*<br/>
[in] 바닥글을 사용 하는 문자열입니다.

### <a name="return-value"></a>반환 값

사용자가 선택한 옵션에 해당 하는 정수입니다.

### <a name="remarks"></a>설명

이 정적 메서드를 사용 하면 인스턴스를 만들 수 있습니다 합니다 `CTaskDialog` 명시적으로 만들지 않고 클래스를 `CTaskDialog` 코드의 개체입니다. 있기 때문에 없습니다 `CTaskDialog` 개체의 다른 메서드를 호출할 수 없습니다 합니다 `CTaskDialog` 표시 하려면이 메서드를 사용 하는 경우는 `CTaskDialog` 사용자에 게 합니다.

이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 명령 단추 컨트롤을 만듭니다. 리소스 파일에 문자열 테이블에 연결 된 문자열 Id 사용 하 여 여러 문자열입니다. 이 메서드 간에 문자열 테이블의 유효한 각 항목에 대 한 명령 단추 컨트롤을 추가 *nIDCommandControlsFirst* 하 고 *nCommandControlsLast*(포함). 이러한 명령 단추 컨트롤에 대 한 문자열 테이블의 문자열은 컨트롤의 캡션 및 문자열 ID는 컨트롤의 id입니다.

참조 [CTaskDialog::SetOptions](#setoptions) 목록을 사용할 수 있는 옵션에 대 한 합니다.

합니다 `CTaskDialog` 명령 링크 컨트롤, 일반적인 단추를 선택 하거나 닫을 때 닫습니다는 `CTaskDialog`합니다. 반환 값에는 사용자 대화 상자를 닫은 방법을 나타내는 식별자입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

##  <a name="taskdialogcallback"></a>  CTaskDialog::TaskDialogCallback

프레임 워크는 다양 한 Windows 메시지에 대 한 응답에서이 메서드를 호출합니다.

```
friend:
HRESULT TaskDialogCallback(
    HWND hWnd,
    UINT uNotification,
    WPARAM wParam,
    LPARAM lParam,
    LONG_PTR dwRefData);
```

### <a name="parameters"></a>매개 변수

*hwnd*<br/>
[in] 에 대 한 핸들을 `m_hWnd` 의 구조는 `CTaskDialog`합니다.

*uNotification*<br/>
[in] 생성된 된 메시지를 지정 하는 알림 코드입니다.

*wParam*<br/>
[in] 메시지에 대 한 자세한 정보입니다.

*lParam*<br/>
[in] 메시지에 대 한 자세한 정보입니다.

*dwRefData*<br/>
[in] 에 대 한 포인터를 `CTaskDialog` 콜백 메시지에 적용 되는 개체입니다.

### <a name="return-value"></a>반환 값

특정 알림 코드에 따라 달라 집니다. 자세한 내용은 설명 부분을 참조하세요.

### <a name="remarks"></a>설명

기본 구현의 `TaskDialogCallback` 특정 메시지를 처리 한 다음 적절 한 방법을 합니다 [CTaskDialog 클래스](../../mfc/reference/ctaskdialog-class.md)합니다. TDN_BUTTON_CLICKED 메시지에 대 한 응답의 예를 들어 `TaskDialogCallback` 호출 [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)합니다.

에 대 한 값 *wParam* 하 고 *lParam* 생성된 된 특정 메시지에 따라 달라 집니다. 이러한 값을 비워 둘 중 하나 또는 모두에 대 한 것 같습니다. 다음 표에서 지원 되는 기본 알림 및 값 *wParam* 하 고 *lParam* 나타냅니다. 파생된 클래스에서이 메서드를 재정의 하는 경우에 다음 표에 각 메시지에 대 한 콜백 코드를 구현 해야 합니다.

|알림 메시지|*wParam* Value|*lParam* Value|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|사용되지 않습니다.|사용되지 않습니다.|
|TDN_NAVIGATED|사용되지 않습니다.|사용되지 않습니다.|
|TDN_BUTTON_CLICKED|명령 단추 컨트롤 id입니다.|사용되지 않습니다.|
|TDN_HYPERLINK_CLICKED|사용되지 않습니다.|A [LPCWSTR](/windows/desktop/WinProg/windows-data-types) 링크가 포함 된 구조입니다.|
|TDN_TIMER|시간 이후의 밀리초를 `CTaskDialog` 만든 또는 타이머 다시 설정 되었습니다.|사용되지 않습니다.|
|TDN_DESTROYED|사용되지 않습니다.|사용되지 않습니다.|
|TDN_RADIO_BUTTON_CLICKED|라디오 단추 id입니다.|사용되지 않습니다.|
|TDN_DIALOG_CONSTRUCTED|사용되지 않습니다.|사용되지 않습니다.|
|TDN_VERIFICATION_CLICKED|확인란을 선택 하는 경우 1, 있지 않으면 0입니다.|사용되지 않습니다.|
|TDN_HELP|사용되지 않습니다.|사용되지 않습니다.|
|TDN_EXPANDO_BUTTON_CLICKED|확장 영역 축소 되는 경우에 0 확장 텍스트가 표시 하는 경우에 0이 아닙니다.|사용되지 않습니다.|

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[연습: 애플리케이션에 CTaskDialog 추가](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)
