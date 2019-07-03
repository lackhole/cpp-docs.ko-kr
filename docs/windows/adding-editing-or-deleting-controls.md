---
title: '방법: Add, Edit, 또는 컨트롤 삭제 (C++)'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.dialog
- vc.controls.activex
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- Dialog Editor [C++], creating controls
- dialog boxes [C++], adding controls to
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
- controls [C++], adding multiple
- dialog box controls [C++], size
- controls [C++], sizing
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
- Insert ActiveX Control dialog box [C++]
- controls [C++], editing properties
- ActiveX controls [C++], properties
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls [C++], editing properties
- dialog box controls [C++], deleting
- controls [C++], deleting
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
- controls [C++], troubleshooting
- Dialog Editor [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: 3c311e44a7e618bf932b0f4abf865a523a7fbead
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400747"
---
# <a name="how-to-add-edit-or-delete-controls-c"></a>방법: Add, Edit, 또는 컨트롤 삭제 (C++)

사용 하는 **대화 상자 편집기**, 추가할 수 있습니다 크기 조정, 편집 및 대화 상자에서 컨트롤을 삭제 합니다. 해당 ID와 같은 컨트롤의 속성을 편집할 수도 있습니다 여부를 런타임에 처음 표시 되 나 합니다.

합니다 **대화 상자 편집기** 탭에 표시 됩니다는 [도구 상자 창](/visualstudio/ide/reference/toolbox) 에서 작업 하는 경우는 **대화 상자 편집기**합니다. 사용자 지정할 수도 있습니다는 **도구 상자** 창을 쉽게 사용할 수 있도록 합니다. 자세한 내용은 [도구 상자를 사용 하 여](/visualstudio/ide/using-the-toolbox) 하 고 [표시 또는 숨기기 도구 상자 창](showing-or-hiding-the-dialog-editor-toolbar.md)합니다.

> [!TIP]
> 사용 하는 동안 합니다 **대화 상자 편집기**, 대부분의 경우 자주 사용 되는 명령의 바로 가기 메뉴를 표시 하려면 마우스 오른쪽 단추를 선택할 수 있습니다.

## <a name="add-controls"></a>컨트롤 추가

### <a name="to-add-a-control"></a>컨트롤을 추가 하려면

1. 대화 상자 탭 창이 편집기 프레임에서 현재 문서인지 확인합니다. 대화 상자에서 현재 문서에 없는 경우 볼 수 없습니다는 **대화 상자 편집기 탭** 에 **도구 상자**합니다.

1. 에 **대화 상자 편집기** 탭의 **도구 상자** 창에서 다음 컨트롤을 선택:

   - 컨트롤을 배치 하려는 위치 대화 상자를 선택 하 고 선택한 위치 컨트롤이 나타납니다.

   - 끌어서 놓기 컨트롤을 **도구 상자** 대화 상자에서 위치를 창입니다. 그런 다음, 컨트롤을 이동 하거나 크기와 셰이프를 변경할 수 있습니다.

   - 컨트롤을 두 번 클릭 합니다 **도구 상자** 창 대화 상자에 표시 합니다. 컨트롤의 위치를 원하는 위치로 변경 합니다.

### <a name="to-add-multiple-controls"></a>여러 컨트롤을 추가 하려면

1. 누른 채 합니다 **Ctrl** 키, 컨트롤을 선택 합니다 **도구 상자** 창입니다.

1. 릴리스를 **Ctrl** 키 및 특정 컨트롤을 추가 하려는 만큼 대화 상자를 선택 합니다.

1. 키를 눌러 **Esc** 컨트롤을 배치를 중지 합니다.

### <a name="to-size-a-control-while-you-add-it"></a>컨트롤을 추가할 때 크기

1. 컨트롤을 선택 합니다 **도구 상자** 창입니다.

1. 대화 상자에 새 컨트롤의 왼쪽 위 모퉁이 만들려는 십자선으로 표시 되는 커서를 놓습니다.

1. 선택 하 고 대화 상자에서 컨트롤의 왼쪽 위 모퉁이 고정 하려면 마우스 단추를 길게 누른 키를 누릅니다. 다음 커서를 오른쪽 아래로 끕니다, 컨트롤의 원하는 크기가 될 때까지 합니다.

   > [!NOTE]
   > 그릴 컨트롤의 네 모퉁이 고정할 수 있습니다. 이 절차 예를 들어 왼쪽 위 모퉁이 사용 합니다.

1. 마우스 단추를 놓습니다. 컨트롤의 대화 상자에서 지정한 크기에 도달 합니다.

> [!TIP]
> 컨트롤의 테두리의 크기 조정 핸들을 이동 하 여 대화 상자에 끌어다 놓으면 후 컨트롤 크기를 조정할 수 있습니다. 자세한 내용은 [개별 컨트롤 크기 조정](../windows/sizing-individual-controls.md)합니다.

### <a name="to-add-a-custom-control"></a>사용자 지정 컨트롤을 추가하려면

대화 상자에 사용자 지정 컨트롤을 추가할 수 있습니다. 선택 합니다 **사용자 지정 컨트롤** 아이콘에는 **도구 상자** 대화 상자에 놓습니다. 추가 하는 `Syslink` 제어, 사용자 지정 컨트롤을 추가한 다음 컨트롤의 변경 **클래스** 속성을 `Syslink`입니다. 이 작업에는 속성을 새로 고치고 표시 하면는 `Syslink` 속성을 제어 합니다. MFC 래퍼 클래스에 대 한 자세한 내용은 [CLinkCtrl](../mfc/reference/clinkctrl-class.md)합니다.

## <a name="edit-controls"></a>Edit 컨트롤

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>컨트롤 또는 컨트롤의 속성을 편집 하려면

1. 대화 상자에서 수정 하려는 컨트롤을 선택 합니다.

   > [!NOTE]
   > 여러 컨트롤을 선택 하면 선택한 컨트롤에 공통 된 속성만 편집할 수 있습니다.

1. 에 [속성 창](/visualstudio/ide/reference/properties-window), 컨트롤의 속성을 변경 합니다.

   > [!NOTE]
   > 설정한 경우 합니다 **비트맵** 단추, 라디오 단추 또는 확인란 컨트롤 같은 속성을 **True**, 스타일을 컨트롤에 대 한 BS_BITMAP 구현 됩니다. 자세한 내용은 [단추 스타일](../mfc/reference/styles-used-by-mfc.md#button-styles)합니다. 컨트롤을 사용 하 여 비트맵을 연결 하는 예제를 보려면 [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap)합니다. 비트맵에 있는 동안 컨트롤에 표시 되지 것입니다 합니다 **대화 상자 편집기**합니다.

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>컨트롤의 속성 변경 내용을 실행 취소 하려면

1. 컨트롤에 포커스를가지고 있는지 확인 합니다 **대화 상자 편집기**합니다.

1. 메뉴로 이동 **편집할** > **취소**합니다. 컨트롤에 포커스가 없으면 합니다 **실행 취소** 명령을 사용할 수 없게 됩니다.

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>(단추 이외의) 대화 상자 컨트롤에 대해 멤버 변수를 정의하려면

> [!NOTE]
> 이 프로세스는 MFC 프로젝트 내의 대화 상자 컨트롤에만 적용 됩니다. ATL 프로젝트를 사용 해야 합니다 **새 Windows 메시지 및 이벤트 처리기** 대화 상자. 자세한 내용은 [메시지 형식 개체와 연결 된 사용자 인터페이스](../mfc/reference/message-types-associated-with-user-interface-objects.md)를 [메시지 처리기 편집](../mfc/reference/editing-a-message-handler.md), 및 [반영메시지의메시지처리기정의](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

1. 에 [대화 상자 편집기](../windows/dialog-editor.md), 컨트롤을 선택 합니다.

1. 누른 채 합니다 **Ctrl** 키, 대화 상자 컨트롤을 두 번 클릭 합니다.

   합니다 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) 나타납니다.

1. 적절 한 정보를 입력 합니다 **멤버 변수 추가** 마법사. 자세한 내용은 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md)합니다.

1. 선택 **확인** 돌아가려면 합니다 **대화 상자 편집기**합니다.

> [!TIP]
> 대화 상자 컨트롤에서 기존 처리기로 이동하려면 컨트롤을 두 번 클릭합니다.

사용할 수도 있습니다는 **멤버 변수** 탭에 [MFC 클래스 마법사](../mfc/reference/mfc-class-wizard.md) , 지정된 된 클래스에 대 한 새 멤버 변수를 추가 하 고 미리 정의 된 멤버 변수를 표시 하 합니다.

## <a name="delete-controls"></a>컨트롤 삭제

대화 상자에서 컨트롤을 선택 키를 누릅니다 합니다 **삭제** 키 또는 메뉴 **편집** > **삭제**합니다.

## <a name="other-issues"></a>기타 문제

### <a name="troubleshooting"></a>문제 해결

대화 상자에는 공용 컨트롤 또는 rich edit 컨트롤을 추가한 후 대화 상자를 테스트 하는 경우 표시 되지 않습니다. 또는 자체 대화 상자 표시 되지 않습니다. 예를 들어:

1. Windows 응용 프로그램 (콘솔 앱)을 만든 하므로 응용 프로그램 설정을 수정 Win32 프로젝트를 만듭니다.

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)를 두 번 클릭 합니다 *.rc* 파일입니다.

1. 대화 상자 옵션에서 두 번 클릭 합니다 **에 대 한** 상자입니다.

1. 추가 된 **IP 주소 컨트롤** 대화 상자.

1. 저장 하 고 **모두 다시 빌드**합니다.

1. 프로그램을 실행 합니다.

1. 대화 상자에서 **도움말** 메뉴를 선택 합니다 **에 대 한** 명령 및 확인 대화 상자가 표시 됩니다.

현재는 **대화 상자 편집기** 때나 끌어다 놓으면 다음과 같은 일반적인 컨트롤 서식 있는 편집 대화 상자 컨트롤 프로젝트에 코드를 추가 자동으로 하지 않습니다. 도 Visual Studio 제공 오류 또는 경고가 발생이 문제가 발생 합니다. 를 해결 하려면 컨트롤에 대 한 코드를 수동으로 추가 합니다.

||||
|-|-|-|
|슬라이더 컨트롤|트리 컨트롤|날짜 시간 선택|
|스핀 컨트롤|탭 컨트롤|Month Calendar|
|진행률 컨트롤|애니메이션 컨트롤|IP 주소 컨트롤|
|바로 가기 키|Rich Edit 컨트롤|확장 된 콤보 상자|
|목록 컨트롤|Rich Edit 2.0 컨트롤|사용자 지정 컨트롤|

대화 상자에서 공용 컨트롤을 사용 하려면 호출 [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) 또는 `AFXInitCommonControls` 대화 상자를 만들어야 합니다.

RichEdit 컨트롤을 사용 하려면 `LoadLibrary`합니다. 자세한 내용은 [Rich Edit 컨트롤](/windows/desktop/Controls/about-rich-edit-controls) Windows sdk에서 및 [서식 있는 편집 컨트롤의 개요](../mfc/overview-of-the-rich-edit-control.md)합니다.

> [!NOTE]
> MFC에서 RichEdit 컨트롤을 사용 하려면 먼저 불러와야 [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) RichEdit 2.0 컨트롤 (RICHED20 로드 하려면. DLL)를 호출 하거나 [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) 이전에 RichEdit 1.0 컨트롤 (RICHED32 로드 하려면. DLL)입니다.
>
> 현재 사용할 수 있습니다 [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) 이전 RichEdit 1.0 컨트롤을 사용 하 여 클래스 이지만 `CRichEditCtrl` RichEdit 2.0 제어를 지원 하도록 디자인 되었습니다. RichEdit 1.0 및 2.0 RichEdit 유사한 이기 때문에 대부분의 메서드가 작동 합니다. 그러나 일부의 차이점이 1.0 및 2.0 컨트롤 간의 일부 메서드 제대로 작동 하지 않을 수 있습니다 하거나 전혀 작동 하지 않습니다.

### <a name="activex-controls"></a>ActiveX 컨트롤

Visual Studio에서는 ActiveX 컨트롤을 대화 상자에 삽입할 수 있습니다. 자세한 내용은 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md) 하 고 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)합니다.

합니다 **ActiveX 컨트롤 삽입** 대화 상자를 사용 하면 사용 하는 동안 대화 상자에 ActiveX 컨트롤을 삽입 하는 [대화 상자 편집기](../windows/dialog-editor.md)합니다. 이 대화 상자에는 다음 속성이 포함 됩니다.

|속성|설명|
|---|---|
|**ActiveX 컨트롤**|ActiveX 컨트롤의 목록을 표시합니다.<br/><br/>이 대화 상자에서 컨트롤을 삽입 래퍼 클래스를 생성 하지 않습니다. 래퍼 클래스를 해야 하는 경우 사용 하 여 [클래스 뷰](/visualstudio/ide/viewing-the-structure-of-code) 하나를 만들려면 참조 [클래스를 추가](../ide/adding-a-class-visual-cpp.md)합니다.<br/><br/>ActiveX 컨트롤은이 대화 상자에 표시 되지 않으면, 공급 업체의 지침에 따라 컨트롤을 설치 하십시오.|
|**Path**|ActiveX 컨트롤은 찾을 수 있는 파일이 표시 됩니다.|

> [!CAUTION]
> 시스템에 일부 ActiveX 컨트롤을 배포하지 못할 수 있습니다. 컨트롤을 설치 하는 소프트웨어에 대 한 사용권 계약 참조 하거나 소프트웨어 회사에 게 문의 하십시오.

#### <a name="to-add-an-activex-control"></a>ActiveX 컨트롤을 추가 하려면

1. 열기 대화 상자에 **대화 상자 편집기**합니다.

1. 대화 상자의 본문의 아무 곳 이나 마우스 오른쪽 단추로 클릭 하 고 선택 **ActiveX 컨트롤 삽입**합니다.

   합니다 **ActiveX 컨트롤 삽입** 시스템에서 모든 ActiveX 컨트롤을 보여 주는 대화 상자가 나타납니다. 대화 상자 아래쪽에 ActiveX 컨트롤 파일 경로가 표시됩니다.

1. 대화 상자에 추가 하 고 선택 하려는 컨트롤을 선택 **확인**합니다.

   컨트롤이 대화 상자에 표시되고, 이 대화 상자에서 컨트롤을 편집하거나 다른 컨트롤처럼 컨트롤용 처리기를 만들 수 있습니다.

> [!TIP]
> 바로 가기 메뉴를 사용할 수는 **대화 상자 편집기** 신속 하 게 대화 상자에 등록 된 ActiveX 컨트롤을 추가 하거나 ActiveX 컨트롤을 추가 해 보세요 합니다 **도구 상자** 쉬운 액세스를 위해 창.

#### <a name="to-edit-properties-for-an-activex-control"></a>ActiveX 컨트롤에 대 한 속성을 편집 하려면

개별 공급 업체에서 제공 하는 ActiveX 컨트롤 속성 및 특성 자체와 함께 가져올 수 있습니다. 이러한 속성에 표시 되는 **속성** 창입니다. ActiveX 컨트롤의 작성자가 만든 모든 속성 페이지에 표시 되는 **속성 페이지** 대화 상자. (보려는 합니다 **속성 페이지** 특정 ActiveX 컨트롤을 선택 합니다 **속성 페이지** 단추를 [속성 창](/visualstudio/ide/reference/properties-window)).

- 선택 합니다 **ActiveX** 컨트롤을 메뉴로 이동 **보기** > **속성 페이지** 속성을 보려면. 속성 페이지에서 필요에 따라 변경 합니다.

   ActiveX 컨트롤의 일부로 제공 되는 속성 시트에 따라 ActiveX 컨트롤에 대 한 속성 페이지에서 다양 한 탭 표시 됩니다.

> [!NOTE]
> 속성 페이지를 사용 하 여 ActiveX 컨트롤을 편집 하려면이 절차에 적용 됩니다. 또한 이동 하 고 새 ActiveX 속성을 편집할 수 있습니다 **속성** 창입니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[대화 상자 컨트롤 관리](controls-in-dialog-boxes.md)<br/>
[방법: 레이아웃 컨트롤](arrangement-of-controls-on-dialog-boxes.md)<br/>
[방법: 액세스 제어 및 값 정의](defining-mnemonics-access-keys.md)

<!-- excluded links
[Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)<br/>
[Adding Functionality with Code Wizards](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Adding a Class](../ide/adding-a-class-visual-cpp.md)<br/>
[Adding a Member Function](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Overriding a Virtual Function](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler](../mfc/reference/adding-an-mfc-message-handler.md)
[Declaring a Variable Based on Your New Control Class](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)<br/>
-->