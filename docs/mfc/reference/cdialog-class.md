---
title: CDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CDialog
- AFXWIN/CDialog
- AFXWIN/CDialog::CDialog
- AFXWIN/CDialog::Create
- AFXWIN/CDialog::CreateIndirect
- AFXWIN/CDialog::DoModal
- AFXWIN/CDialog::EndDialog
- AFXWIN/CDialog::GetDefID
- AFXWIN/CDialog::GotoDlgCtrl
- AFXWIN/CDialog::InitModalIndirect
- AFXWIN/CDialog::MapDialogRect
- AFXWIN/CDialog::NextDlgCtrl
- AFXWIN/CDialog::OnInitDialog
- AFXWIN/CDialog::OnSetFont
- AFXWIN/CDialog::PrevDlgCtrl
- AFXWIN/CDialog::SetDefID
- AFXWIN/CDialog::SetHelpID
- AFXWIN/CDialog::OnCancel
- AFXWIN/CDialog::OnOK
helpviewer_keywords:
- CDialog [MFC], CDialog
- CDialog [MFC], Create
- CDialog [MFC], CreateIndirect
- CDialog [MFC], DoModal
- CDialog [MFC], EndDialog
- CDialog [MFC], GetDefID
- CDialog [MFC], GotoDlgCtrl
- CDialog [MFC], InitModalIndirect
- CDialog [MFC], MapDialogRect
- CDialog [MFC], NextDlgCtrl
- CDialog [MFC], OnInitDialog
- CDialog [MFC], OnSetFont
- CDialog [MFC], PrevDlgCtrl
- CDialog [MFC], SetDefID
- CDialog [MFC], SetHelpID
- CDialog [MFC], OnCancel
- CDialog [MFC], OnOK
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
ms.openlocfilehash: 9918b1ae38caacf2b2355ace6337e8e5e6260605
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168325"
---
# <a name="cdialog-class"></a>CDialog 클래스

화면에 대화 상자를 표시 하는 데는 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CDialog : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDialog::CDialog](#cdialog)|`CDialog` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDialog::Create](#create)|초기화는 `CDialog` 개체입니다. 모덜리스 대화 상자를 만들고 연결 하는 `CDialog` 개체입니다.|
|[CDialog::CreateIndirect](#createindirect)|(리소스 기반 아님) 메모리의 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다.|
|[CDialog::DoModal](#domodal)|모달 대화 상자를 호출 하 고 수행 하는 경우를 반환 합니다.|
|[CDialog::EndDialog](#enddialog)|모달 대화 상자를 닫습니다.|
|[CDialog::GetDefID](#getdefid)|대화 상자에 대 한 기본 누름 단추 컨트롤의 ID를 가져옵니다.|
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|대화 상자에서 지정 된 대화 상자 컨트롤에 포커스를 이동합니다.|
|[CDialog::InitModalIndirect](#initmodalindirect)|(리소스 기반 아님) 메모리의 대화 상자 템플릿에서 모달 대화 상자를 만듭니다. 매개 변수를 함수까지 저장 된 `DoModal` 라고 합니다.|
|[CDialog::MapDialogRect](#mapdialogrect)|사각형의 대화 상자 단위 화면 단위로 변환합니다.|
|[CDialog::NextDlgCtrl](#nextdlgctrl)|대화 상자에서 다음 대화 상자 컨트롤에 포커스를 이동합니다.|
|[CDialog::OnInitDialog](#oninitdialog)|대화 상자 초기화를 확대 하도록 재정의 합니다.|
|[CDialog::OnSetFont](#onsetfont)|대화 상자 컨트롤은 텍스트를 그릴 때 사용 하는 글꼴을 지정 하려면 재정의 합니다.|
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|대화 상자에서 이전 대화 상자 컨트롤에 포커스를 이동합니다.|
|[CDialog::SetDefID](#setdefid)|지정 된 누름에 대화 상자에 대 한 기본 누름 단추 컨트롤을 변경합니다.|
|[CDialog::SetHelpID](#sethelpid)|대화 상자에 대 한 상황에 맞는 도움말 ID를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CDialog::OnCancel](#oncancel)|취소 단추 또는 ESC 키 작업을 수행 하려면 재정의 합니다. 기본 대화 상자를 닫고 및 `DoModal` IDCANCEL를 반환 합니다.|
|[CDialog::OnOK](#onok)|모달 대화 상자에서 확인 단추 작업을 수행 하려면 재정의 합니다. 기본 대화 상자를 닫고 및 `DoModal` IDOK를 반환 합니다.|

## <a name="remarks"></a>설명

대화 상자는 두 가지 유형이: 모달 및 모덜리스 합니다. 응용 프로그램을 계속 하기 전에 사용자가 모달 대화 상자를 닫아야 합니다. 모덜리스 대화 상자 사용자를 대화 상자를 표시를 취소 하거나 대화 상자를 제거 하지 않고 다른 작업으로 반환할 수 있습니다.

A `CDialog` 개체는 대화 상자 템플릿의 조합 및 `CDialog`-클래스를 파생 합니다. 대화 상자 편집기를 사용 하 여 대화 상자 템플릿을 만들고 리소스에 저장 하 고 다음에서 파생 된 클래스를 만드는 클래스 추가 마법사를 사용 하 여 `CDialog`입니다.

다른 창과 마찬가지로 대화 상자에서 Windows에서 메시지를 받습니다. 대화 상자에 관심이 특히 대화 상자를 사용 하 여 사용자 상호 작용 하는 방법 이므로 대화 상자의 컨트롤에서 알림 메시지를 처리 합니다. 속성 창을 사용 및 처리 하 시겠습니까 메시지는 적절 한 메시지 맵 항목 및 추가 메시지 처리기 멤버 함수 클래스를 선택 합니다. 처리기 멤버 함수에 응용 프로그램별 코드를 작성 하기만 하면 됩니다.

원한다 면 작성할 수 있습니다 항상 메시지 맵 항목 및 멤버 함수로 수동으로.

가장 간단한 대화 상자를 제외한 모든 사용자가 대화 상자의 컨트롤에 입력 된 데이터를 저장 하거나 사용자에 대 한 데이터를 표시 하려면 파생 된 대화 상자 클래스에 멤버 변수를 추가 합니다. 변수 추가 마법사를 사용 하 여 멤버 변수를 만들고 컨트롤을 사용 하 여 연결할 수 있습니다. 동시에, 변수 형식 및 각 변수에 대해 값의 허용 범위를 선택합니다. 코드 마법사 대화 상자 파생된 클래스에 멤버 변수를 추가합니다.

자동으로 멤버 변수와 대화 상자의 컨트롤 간의 데이터 교환을 처리 하는 데이터 구조가 생성 됩니다. 데이터 맵, 적절 한 값을 사용 하 여 대화 상자 컨트롤을 초기화 하 고, 데이터를 검색 하 고, 데이터 유효성 검사 기능을 제공 합니다.

모달 대화 상자를 만들려면 생성자를 사용 하 여 파생 된 대화 상자 클래스에 대 한 스택의 개체를 생성 하 고 호출 `DoModal` 대화 상자 창 및 해당 컨트롤을 만들려고 합니다. 모덜리스 대화 상자를 만들려는 경우 호출 `Create` 대화 상자 클래스의 생성자에서.

사용 하 여 메모리에서 템플릿을 만들 수도 있습니다는 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Windows SDK에 설명 된 대로 데이터 구조입니다. 생성 한 후는 `CDialog` 개체를 호출 [CreateIndirect](#createindirect) 는 모덜리스 만들려면 대화 상자 또는 호출 [InitModalIndirect](#initmodalindirect) 및 [DoModal](#domodal) 모달을 만들려면 대화 상자입니다.

교환 및 유효성 검사 데이터 맵 재정의 작성 된 `CWnd::DoDataExchange` 는 새 대화 상자 클래스에 추가 됩니다. 참조 된 [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) 멤버 함수 `CWnd` 교환 및 유효성 검사 기능에 대 한 자세한 내용은 합니다.

프로그래머와 프레임 워크 호출 `DoDataExchange` 호출을 통해 간접적으로 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)합니다.

프레임 워크 호출 `UpdateData` 모달 대화 상자를 닫으려면 확인 단추를 클릭할 때입니다. (데이터 검색 되지 않습니다 취소 단추를 클릭할 경우.) 기본 구현의 [OnInitDialog](#oninitdialog) 도 호출 `UpdateData` 컨트롤의 초기 값을 설정 합니다. 일반적으로 재정의 `OnInitDialog` 추가 컨트롤을 초기화 합니다. `OnInitDialog` 모든 대화 상자 컨트롤 생성 되 고 대화 상자 직전 상자가 표시 되 면 후 호출 됩니다.

호출할 수 있습니다 `CWnd::UpdateData` 모달 또는 모덜리스 대화 상자를 실행 하는 동안 언제 든 합니다.

대화 상자를 직접 개발 하는 경우 필요한 멤버 변수 클래스를 추가 하는 파생 된 대화 상자를 직접 및 이러한 값을 가져오거나 설정 하는 멤버 함수를 추가 합니다.

모달 대화 상자를 확인 또는 취소 단추를 누를 때 또는 코드 호출 하는 경우 자동으로 닫습니다는 `EndDialog` 멤버 함수입니다.

모덜리스 대화 상자를 구현 하는 경우 항상 재정의 합니다 `OnCancel` 멤버 함수 및 호출 `DestroyWindow` 에서 그 합니다. 기본 클래스를 호출 하지 마세요 `CDialog::OnCancel`를 호출 하므로, `EndDialog`, 대화 상자를 보이지 않도록 됩니다 있지만 삭제 하지 것입니다. 또한 재정의 해야 `PostNcDestroy` 삭제 하려면 모덜리스 대화 상자에 대 한 **이**모덜리스 대화 상자는 일반적으로 사용 하 여 할당 되므로 **새**합니다. 모달 대화 상자 프레임에 일반적으로 생성 되 고 필요가 없습니다 `PostNcDestroy` 정리 합니다.

에 대 한 자세한 `CDialog`를 참조 하세요 [대화 상자](../../mfc/dialog-boxes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cdialog"></a>  CDialog::CDialog

리소스 기반 모달 대화 상자를 생성 하려면 공용 형식의 생성자를 호출 합니다.

```
explicit CDialog(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd = NULL);

explicit CDialog(
    UINT nIDTemplate,
    CWnd* pParentWnd = NULL);

CDialog();
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름을 나타내는 null로 끝나는 문자열을 포함 합니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

*pParentWnd*<br/>
부모 또는 소유자 창 개체 (형식의 [CWnd](../../mfc/reference/cwnd-class.md)) 대화 상자 개체 속한 합니다. NULL 인 경우 대화 상자 개체의 부모 창 주 응용 프로그램 창으로 설정 됩니다.

### <a name="remarks"></a>설명

한 가지 형태의 생성자 템플릿 이름으로 대화 상자 리소스에 대 한 액세스를 제공합니다. 다른 생성자를 액세스할 템플릿 ID 번호로 일반적으로 사용 하 여는 **IDD_** 접두사 (예를 들어 IDD_DIALOG1).

메모리의 템플릿에서 모달 대화 상자를 생성 하려면 먼저 보호 되는 매개 변수가 없는 생성자를 호출 하 고 호출 `InitModalIndirect`합니다.

위의 방법 중 하나를 사용 하 여 모달 대화 상자를 생성 한 후 호출 `DoModal`합니다.

모덜리스 대화 상자를 생성 하려면 보호 된 형식으로 사용 된 `CDialog` 생성자입니다. 생성자는 모덜리스 대화 상자를 구현 하려면 고유한 대화 상자 클래스를 파생 해야 하기 때문에 보호 됩니다. 모덜리스 대화 상자 생성은 두 단계로 이루어집니다. 첫 번째 호출 된 생성자 다음 호출을 `Create` 멤버 함수는 리소스를 기반으로 대화 상자를 만들려면 호출 또는 `CreateIndirect` 메모리 템플릿에서 대화 상자를 만들려면.

##  <a name="create"></a>  CDialog::Create

호출 `Create` 리소스에서 대화 상자 템플릿을 사용 하 여 모덜리스 대화 상자를 만듭니다.

```
virtual BOOL Create(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd = NULL);

virtual BOOL Create(
    UINT nIDTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszTemplateName*<br/>
대화 상자 템플릿 리소스의 이름을 나타내는 null로 끝나는 문자열을 포함 합니다.

*pParentWnd*<br/>
부모 창 개체 (형식의 [CWnd](../../mfc/reference/cwnd-class.md)) 대화 상자 개체 속한 합니다. NULL 인 경우 대화 상자 개체의 부모 창 주 응용 프로그램 창으로 설정 됩니다.

*nIDTemplate*<br/>
대화 상자 템플릿 리소스의 ID 번호를 포함합니다.

### <a name="return-value"></a>반환 값

두 형태 모두 성공 대화 상자 만들기 및 초기화 된 경우 0이 아닌 반환 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

에 대 한 호출을 넣을 수 있습니다 `Create` 생성자 또는 호출 내의 생성자 뒤 호출 됩니다.

두 가지 형태의 `Create` 멤버 함수에서 제공 하는 대화 상자 템플릿 리소스에 액세스 하기 위한 템플릿 이름 또는 템플릿 ID 번호 (예를 들어 IDD_DIALOG1).

형식 중 하나에 대 한 부모 창 개체에 대 한 포인터를 전달 합니다. 하는 경우 *pParentWnd* 가 null 인 경우 대화 상자는 해당 부모 또는 소유자 창에서 기본 응용 프로그램 창에 설정으로 생성 됩니다.

`Create` 멤버 함수에는 대화 상자를 만든 후에 즉시 반환 합니다.

부모 창을 만들 때 대화 상자를 표시 해야 하는 경우 대화 상자 템플릿에서 WS_VISIBLE 스타일을 사용 합니다. 그렇지 않으면 호출 해야 `ShowWindow`합니다. 추가 대화 상자 스타일 및 응용 프로그램에 대 한 참조를 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Windows SDK의 구조 및 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 에 *MFC 참조*합니다.

사용 합니다 `CWnd::DestroyWindow` 함수에서 만든 대화 상자를 제거 하는 `Create` 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]

##  <a name="createindirect"></a>  CDialog::CreateIndirect

메모리의 대화 상자 템플릿에서 모덜리스 대화 상자를 만들려면이 멤버 함수를 호출 합니다.

```
virtual BOOL CreateIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,
    CWnd* pParentWnd = NULL,
    void* lpDialogInit = NULL);

virtual BOOL CreateIndirect(
    HGLOBAL hDialogTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*lpDialogTemplate*<br/>
만들기 대화 상자를 사용 하는 대화 상자 템플릿의 포함 된 메모리를 가리킵니다. 이 서식 파일의 형태로는 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) 구조 및 제어 정보를 Windows SDK에 설명 된 대로 합니다.

*pParentWnd*<br/>
대화 상자 개체의 부모 창 개체를 가리키는 (형식의 [CWnd](../../mfc/reference/cwnd-class.md)). NULL 인 경우 대화 상자 개체의 부모 창 주 응용 프로그램 창으로 설정 됩니다.

*lpDialogInit*<br/>
DLGINIT 리소스를 가리킵니다.

*hDialogTemplate*<br/>
대화 상자 템플릿을 포함 하는 전역 메모리에 대 한 핸들을 포함 합니다. 이 서식 파일은 형태로 `DLGTEMPLATE` 구조 및 대화 상자에서 각 컨트롤에 대 한 데이터입니다.

### <a name="return-value"></a>반환 값

대화 상자 생성 되어 성공적으로 초기화 되었으면 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`CreateIndirect` 멤버 함수에는 대화 상자를 만든 후에 즉시 반환 합니다.

부모 창을 만들 때 대화 상자를 표시 해야 하는 경우 대화 상자 템플릿에서 WS_VISIBLE 스타일을 사용 합니다. 그렇지 않으면 호출 해야 `ShowWindow` 를 표시 하도록 할 수 있습니다. 템플릿에서 다른 대화 상자 스타일을 지정 하는 방법에 대 한 자세한 내용은 참조는 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Windows SDK에는 구조입니다.

사용 합니다 `CWnd::DestroyWindow` 함수에서 만든 대화 상자를 제거 하는 `CreateIndirect` 함수입니다.

ActiveX 컨트롤을 포함 하는 대화 상자에는 DLGINIT 리소스에서 제공 하는 추가 정보가 필요 합니다.

##  <a name="domodal"></a>  CDialog::DoModal

모달 대화 상자를 호출 하 고 수행 하는 경우 대화 상자 결과 반환 하려면이 멤버 함수를 호출 합니다.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>반환 값

**int** 의 값을 지정 하는 값을 *n 결과* 에 전달 된 매개 변수를 [CDialog::EndDialog](#enddialog) 대화 상자를 사용 하는 멤버 함수입니다. 함수를 만들 수 없는 경우 대화 상자 또는 IDABORT 출력 창에서 오류 정보를 포함 하는 경우, 다른 일부 오류가 발생 한 경우 반환 값은-1 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 대화 상자가 활성화 되는 동안 모든 사용자 상호 작용을 처리 합니다. 이 대화 상자 모달; 사용 즉, 사용자가 대화 상자를 닫을 때까지 다른 windows 상호 작용할 수 없습니다.

사용자가 클릭 하면 확인 또는 취소를, 메시지 처리기 멤버 함수 등 대화 상자의 누름 단추 중 하나 같은 [OnOK](#onok) 또는 [OnCancel](#oncancel), 대화 상자를 닫고 하려고 호출 됩니다. 기본값 `OnOK` 멤버 함수에서 유효성을 검사 하 고 대화 상자 데이터를 업데이트 한 IDOK 결과 사용 하 여 대화 상자를 닫고 기본 `OnCancel` 을 확인 하거나 업데이트 하지 않고 IDCANCEL 결과 사용 하 여 대화 상자를 닫습니다는 멤버 함수는 대화 상자 데이터입니다. 해당 동작을 변경 하려면 이러한 메시지 처리기 함수를 재정의할 수 있습니다.

> [!NOTE]
> `PreTranslateMessage` 모달 대화 상자 메시지 처리를 위해 이제 라고 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]

##  <a name="enddialog"></a>  CDialog::EndDialog

모달 대화 상자를 종료 하려면이 멤버 함수를 호출 합니다.

```
void EndDialog(int nResult);
```

### <a name="parameters"></a>매개 변수

*nResult*<br/>
호출자에 게 대화 상자에서 반환 될 값이 들어 `DoModal`합니다.

### <a name="remarks"></a>설명

이 멤버 함수가 반환 *n 결과* 반환 값으로 `DoModal`입니다. 사용 해야는 `EndDialog` 모달 대화 상자 생성 될 때마다 처리를 완료 하는 함수입니다.

호출할 수 있습니다 `EndDialog` 에 언제 든 지 [OnInitDialog](#oninitdialog), 닫아야 하는 경우 하기 전에 대화 상자를 표시 또는 입력된 포커스를 설정 하기 전에 합니다.

`EndDialog` 대화 상자를 즉시 닫습니다지 않습니다. 대신, 대화 상자를 닫으려면는 현재 메시지 처리기에서 반환 되는 즉시 전달 하는 플래그를 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]

[!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]

##  <a name="getdefid"></a>  CDialog::GetDefID

호출 된 `GetDefID` 멤버 함수는 대화 상자에 대 한 기본 누름 단추 컨트롤의 ID를 가져오려고 합니다.

```
DWORD GetDefID() const;
```

### <a name="return-value"></a>반환 값

32 비트 값 ( `DWORD`). 기본 누름 단추에는 ID 값이 상위 word DC_HASDEFID 포함 되 고 하위 단어는 ID 값을 포함 합니다. 기본 pushbutton ID 값이 없는 경우 반환 값은 0입니다.

### <a name="remarks"></a>설명

이 일반적으로 단추를 확인 합니다.

##  <a name="gotodlgctrl"></a>  CDialog::GotoDlgCtrl

대화 상자에서 지정된 된 컨트롤에 포커스를 이동합니다.

```
void GotoDlgCtrl(CWnd* pWndCtrl);
```

### <a name="parameters"></a>매개 변수

*pWndCtrl*<br/>
포커스를 받을 수 있는 창 (컨트롤)를 식별 합니다.

### <a name="remarks"></a>설명

(자식 창)에 변수로 전달 하는 컨트롤에 대 한 포인터를 가져오려면 *pWndCtrl*를 호출 합니다 `CWnd::GetDlgItem` 에 대 한 포인터를 반환 하는 멤버 함수를 [CWnd](../../mfc/reference/cwnd-class.md) 개체입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [cwnd:: Getdlgitem](../../mfc/reference/cwnd-class.md#getdlgitem)합니다.

##  <a name="initmodalindirect"></a>  CDialog::InitModalIndirect

메모리에서 생성 하는 대화 상자 템플릿을 사용 하 여 모달 대화 상자 개체를 초기화 하려면이 멤버 함수를 호출 합니다.

```
BOOL InitModalIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,
    CWnd* pParentWnd = NULL,
    void* lpDialogInit = NULL);

    BOOL InitModalIndirect(
    HGLOBAL hDialogTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>매개 변수

*lpDialogTemplate*<br/>
만들기 대화 상자를 사용 하는 대화 상자 템플릿의 포함 된 메모리를 가리킵니다. 이 서식 파일의 형태로는 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) 구조 및 제어 정보를 Windows SDK에 설명 된 대로 합니다.

*hDialogTemplate*<br/>
대화 상자 템플릿을 포함 하는 전역 메모리에 대 한 핸들을 포함 합니다. 이 서식 파일은 형태로 `DLGTEMPLATE` 구조 및 대화 상자에서 각 컨트롤에 대 한 데이터입니다.

*pParentWnd*<br/>
부모 또는 소유자 창 개체 (형식의 [CWnd](../../mfc/reference/cwnd-class.md)) 대화 상자 개체 속한 합니다. NULL 인 경우 대화 상자 개체의 부모 창 주 응용 프로그램 창으로 설정 됩니다.

*lpDialogInit*<br/>
DLGINIT 리소스를 가리킵니다.

### <a name="return-value"></a>반환 값

대화 상자 개체 생성 되어 성공적으로 초기화 되었으면 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

모달 대화 상자를 직접 만들려면 전역 메모리 블록을 할당 및 대화 상자 템플릿을 사용 하 여 입력 합니다. 그런 다음 호출 하는 빈 `CDialog` 대화 상자 개체를 생성 하는 생성자입니다. 그런 다음 호출 `InitModalIndirect` 메모리 내 대화 상자 템플릿에 핸들을 저장 합니다. Windows 대화 상자 생성 되어 표시 나중 합니다 [DoModal](#domodal) 멤버 함수를 호출 합니다.

ActiveX 컨트롤을 포함 하는 대화 상자에는 DLGINIT 리소스에서 제공 하는 추가 정보가 필요 합니다.

##  <a name="mapdialogrect"></a>  CDialog::MapDialogRect

사각형의 대화 상자 단위 화면 단위를 변환할 호출 합니다.

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>매개 변수

*lpRect*<br/>
가리키는 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 변환할 조정 대화 상자를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

대화 상자 단위 평균 너비와 높이 대화 상자의 텍스트에 사용 된 글꼴의 문자에서 파생 된 현재 대화 상자 기본 단위를 기준으로 명시 됩니다. 하나의 가로 단위는 1-4 대화 상자 기본 너비 단위 이며 세로 단위 대화 상자 기본 높이 단위의 1 / 8입니다.

`GetDialogBaseUnits` Windows 함수는 시스템 글꼴에 대 한 크기 정보를 반환 하지만 DS_SETFONT 스타일 리소스 정의 파일에서 사용 하는 경우 각 대화 상자에 대 한 다른 글꼴을 지정할 수 있습니다. `MapDialogRect` Windows 함수는이 대화 상자에 대 한 적절 한 글꼴을 사용 합니다.

합니다 `MapDialogRect` 대화 상자 단위를 대체 하는 멤버 함수 *lpRect* 사용 하 여 사각형 상자 내에서 컨트롤을 배치 또는 만들기 대화 상자를 사용할 수 있도록 단위 (픽셀)를 화면.

##  <a name="nextdlgctrl"></a>  CDialog::NextDlgCtrl

대화 상자에서 다음 컨트롤로 포커스를 이동합니다.

```
void NextDlgCtrl() const;
```

### <a name="remarks"></a>설명

대화 상자에서 마지막 컨트롤에 포커스가 있으면 첫 번째 컨트롤 이동 합니다.

##  <a name="oncancel"></a>  CDialog::OnCancel

프레임 워크를 클릭할 때이 메서드를 호출 **취소** 또는 모달 또는 모덜리스 대화 상자에서 ESC 키를 누릅니다.

```
virtual void OnCancel();
```

### <a name="remarks"></a>설명

이 메서드를 재정의 작업 (예: 오래 된 데이터를 복원)를 수행할 사용자를 클릭 하 여 대화 상자를 닫을 때 **취소** ESC 키를 눌러 또는 합니다. 기본값을 호출 하 여 모달 대화 상자를 닫습니다 [EndDialog](#enddialog) 되어 [DoModal](#domodal) IDCANCEL를 반환 합니다.

구현 하는 경우는 **취소** 단추 모덜리스 대화 상자에를 재정의 해야 합니다 `OnCancel` 메서드를 호출 [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) 내부. 호출 하므로 기본 클래스 메서드를 호출 하지 않는 `EndDialog`, 대화 상자를 보이지 않도록 있지만 소멸 시 키 지 것입니다.

> [!NOTE]
>  사용 하는 경우이 메서드를 재정의할 수 없습니다는 `CFileDialog` Windows XP에서 컴파일된 프로그램의 개체입니다. 에 대 한 자세한 내용은 `CFileDialog`를 참조 하세요 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]

##  <a name="oninitdialog"></a>  CDialog::OnInitDialog

에 대 한 응답에서이 메서드는 `WM_INITDIALOG` 메시지입니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>반환 값

설정 여부를 응용 프로그램에 입력된 포커스가 컨트롤 중 하나에 대화 상자에서 지정 합니다. 경우 `OnInitDialog` 반환 되는 0이 아닌 경우 Windows는 기본 위치인 대화 상자에서 첫 번째 컨트롤에 입력된 포커스를을 설정 합니다. 응용 프로그램 대화 상자에서 입력된 포커스가 컨트롤 중 하나를 명시적으로 설정에 해당 하는 경우에 0을 반환할 수 있습니다.

### <a name="remarks"></a>설명

Windows 전송 합니다 `WM_INITDIALOG` 중 대화 상자에 메시지를 [만들기](#create), [CreateIndirect](#createindirect), 또는 [DoModal](#domodal) 상자 바로 전에 발생 하는 호출 표시 됩니다.

대화 상자 초기화 될 때 특수 한 처리를 수행 하려는 경우이 메서드를 재정의 합니다. 재정의 된 버전에서는 기본 클래스를 호출 먼저 `OnInitDialog` 있지만 해당 반환 값을 무시 합니다. 일반적으로 돌아가게 됩니다 `TRUE` 재정의 메서드에서 합니다.

Windows 호출을 `OnInitDialog` 모든 Microsoft Foundation Class 라이브러리 대화 상자에 일반적인 표준 전역 대화 상자 프로시저를 사용 하 여 함수입니다. 에 메시지 맵을 통해이 함수를 호출 하지 않습니다 하 고 따라서 않아도 메시지 맵 항목을이 메서드에 대 한 키를 누릅니다.

> [!NOTE]
> 사용 하는 경우이 메서드를 재정의할 수 없습니다는 `CFileDialog` Windows Vista 또는 이후 운영 체제에서 컴파일된 프로그램의 개체입니다. 변경에 대 한 자세한 내용은 `CFileDialog` Windows vista 이상 버전에서는 참조 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]

##  <a name="onok"></a>  CDialog::OnOK

사용자가 클릭할 때 호출 된 **확인** 단추 (단추는 IDOK ID를 사용 하 여).

```
virtual void OnOK();
```

### <a name="remarks"></a>설명

이 메서드를 재정의 작업을 수행할 때 합니다 **확인** 단추가 활성화 됩니다. 대화 상자에서 자동 데이터 유효성 검사 및 교환에 포함 된 경우이 메서드의 기본 구현은 대화 상자 데이터 유효성을 검사 하 고 응용 프로그램에서 적절 한 변수를 업데이트 합니다.

구현 하는 경우는 **확인** 단추 모덜리스 대화 상자에를 재정의 해야 합니다 `OnOK` 메서드를 호출 [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) 내부. 호출 하므로 기본 클래스 메서드를 호출 하지 마십시오 [EndDialog](#enddialog) 하면 대화 상자가 보이지 않는 있지만 제거 하지 않습니다.

> [!NOTE]
>  사용 하는 경우이 메서드를 재정의할 수 없습니다는 `CFileDialog` Windows XP에서 컴파일된 프로그램의 개체입니다. 에 대 한 자세한 내용은 `CFileDialog`를 참조 하세요 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]

##  <a name="onsetfont"></a>  CDialog::OnSetFont

텍스트를 그릴 때 사용 하는 대화 상자 컨트롤의 글꼴을 지정 합니다.

```
Virtual void OnSetFont(CFont* pFont);
```

### <a name="parameters"></a>매개 변수

*pFont*<br/>
[in] 이 대화 상자에서 모든 컨트롤을 기본 글꼴로 사용할 글꼴에 대 한 포인터를 지정 합니다.

### <a name="remarks"></a>설명

대화 상자의 모든 컨트롤에 대 한 기본값으로 지정 된 글꼴을 사용 합니다.

일반적으로 대화 상자 편집기 대화 상자 템플릿 리소스의 일부로 대화 상자 글꼴을 설정합니다.

> [!NOTE]
> 사용 하는 경우이 메서드를 재정의할 수 없습니다는 `CFileDialog` Windows Vista 또는 이후 운영 체제에서 컴파일된 프로그램의 개체입니다. 변경에 대 한 자세한 내용은 `CFileDialog` Windows vista 이상 버전에서는 참조 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)합니다.

##  <a name="prevdlgctrl"></a>  CDialog::PrevDlgCtrl

대화 상자에서 이전 컨트롤로 포커스를 설정합니다.

```
void PrevDlgCtrl() const;
```

### <a name="remarks"></a>설명

대화 상자에서 첫 번째 컨트롤에 포커스가 있으면이 마지막 컨트롤 상자에서 이동 합니다.

##  <a name="setdefid"></a>  CDialog::SetDefID

대화 상자에 대 한 기본 누름 단추 컨트롤을 변경합니다.

```
void SetDefID(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
기본 될 누름 단추 컨트롤의 ID를 지정 합니다.

##  <a name="sethelpid"></a>  CDialog::SetHelpID

대화 상자에 대 한 상황에 맞는 도움말 ID를 설정합니다.

```
void SetHelpID(UINT nIDR);
```

### <a name="parameters"></a>매개 변수

*nIDR*<br/>
상황에 맞는 도움말 ID를 지정합니다.

## <a name="see-also"></a>참고자료

[MFC Sample DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 DLGTEMPL](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
