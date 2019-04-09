---
title: 대화 상자 편집기 (c + +)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
- vc.editors.dialog
helpviewer_keywords:
- resource editors [C++], Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes [C++], editing
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog Editor [C++], showing or hiding toolbar
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog Editor [C++], accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog Editor [C++], switching between controls and code
- Dialog Editor [C++], shortcut keys
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
ms.openlocfilehash: dc5a823951e07af96efceec52d2aa23552c2d002
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029488"
---
# <a name="dialog-editor-c"></a>대화 상자 편집기 (c + +)

합니다 **대화 상자 편집기** 만들거나 대화 상자 리소스를 편집할 수 있습니다.

- 대화 상자의.rc 파일에서 두 번 클릭 편집기를 열려면 합니다 **리소스 뷰** 창 또는 메뉴로 이동 **뷰** > **리소스 뷰**합니다.

새 대화 상자 또는 대화 상자 템플릿에 첫 번째 단계 중 하나는 컨트롤을 추가 합니다. 에 **대화 상자 편집기**, 특정 크기, 모양 또는 맞춤에 맞게 컨트롤을 정렬할 수 있습니다 또는 대화 상자에서 작업 하기 위한 해결 방법은 이동할 수 있습니다. 또한 컨트롤을 쉽게 삭제할 수 있습니다.

대화 상자를 템플릿으로 저장하여 다시 사용할 수 있습니다. 대화 상자 디자인과 이를 구현하는 코드 편집 간을 쉽게 전환할 수도 있습니다.

여러 컨트롤 또는 단일 속성을 편집할 수 이기도 합니다 **대화 상자 편집기**합니다. 탭 순서를 변경할 수 있습니다, 컨트롤에 대 한 나타나는 순서 즉, 포커스를 **탭** 키를 누르면 하거나 액세스 키 또는 키보드를 사용 하 여 컨트롤을 선택할 수 있게 해 주는 키 조합을 정의할 수 있습니다.

합니다 **대화 상자 편집기** ActiveX 컨트롤을 비롯 하 여 사용자 지정 컨트롤을 사용할 수 있습니다. 편집할 수도 있습니다는 [폼 보기](../mfc/reference/cformview-class.md)를 [기록 보기](../data/record-views-mfc-data-access.md), 또는 [대화 상자 모음](../mfc/dialog-bars.md)합니다.

Visual Studio 2015부터 사용할 수는 **대화 상자 편집기** 사용자가 대화 상자 크기 조정 컨트롤 이동 하는 방법을 지정 하는 동적 레이아웃 및 크기 조정 정의입니다. 자세한 내용은 [Dynamic Layout](../mfc/dynamic-layout.md)을 참조하세요.

리소스에 대 한 자세한 내용은 참조 하는 방법 [대화 상자를 만들려면](../windows/creating-a-new-dialog-box.md) 및 [대화 상자 컨트롤](../windows/controls-in-dialog-boxes.md)합니다.

> [!TIP]
> 사용 하는 동안 합니다 **대화 상자 편집기**, 대부분의 경우 선택할 수 있습니다 마우스 오른쪽 단추를 사용 하 여 자주 사용 되는 명령의 바로 가기 메뉴를 표시 합니다.

## <a name="dialog-editor-toolbar"></a>대화 상자 편집기 도구 모음

합니다 **대화 상자 편집기** 도구 모음 단추가 대화 상자에서 예를 들어 크기 및 맞춤에서 컨트롤의 레이아웃을 정렬 합니다. **대화 상자 편집기** 도구 모음 단추에 명령에 해당 합니다 **형식** 메뉴.

|아이콘|의미|아이콘|의미|
|----------|-------------|----------|-------------|
|![테스트 대화 상자 단추](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|대화 상자 테스트|![전체 공간 단추](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|옆으로|
|![왼쪽 맞춤 단추](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|왼쪽 맞춤|![아래 공간 단추](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|아래로|
|![오른쪽 맞춤 단추](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|오른쪽 맞춤|![확인 같은 너비로 단추](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|같은 너비로|
|![위쪽 맞춤 단추](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|위쪽 맞춤|![확인 같은 높이로 단추](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|같은 높이로|
|![아래쪽 맞춤 단추](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|아래쪽 맞춤|![확인 같은 크기로 단추](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|같은 크기로|
|![세로 가운데 단추](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|세로|![눈금 단추를 토글](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|모눈 설정/해제|
|![가로 가운데 단추](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|가로|![안내선 설정/해제 단추](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|안내선 설정/해제|

- 표시 하거나 숨기려면 합니다 **대화 상자 편집기** 메뉴로 이동 도구 모음 **뷰** > **도구 모음** > **대화 상자 편집기**합니다.

그러나 열면 합니다 **대화 상자 편집기** c + + 프로젝트에는 **대화 상자 편집기** 솔루션의 맨 위에 있는 도구 모음 자동으로 표시 되 면 도구 모음을 명시적으로 닫으면 해야 호출는 다음으로 열면 합니다 **대화 상자 편집기**합니다. 사용 가능한 도구 모음 및 창 목록에서 선택 하 여 해당 표시를 전환할 수 있습니다.

## <a name="switch-between-dialog-box-controls-and-code"></a>대화 상자 컨트롤과 코드 사이의 스위치

MFC 응용 프로그램에서 대화 상자 컨트롤 처리기 코드로 이동할 또는 신속 하 게 만들 스텁 처리기 함수에 두 번 클릭 수 있습니다.

선택한 컨트롤을 선택 합니다 **컨트롤 이벤트** 단추 또는 **메시지** 단추를 [속성 창](/visualstudio/ide/reference/properties-window) Windows 메시지 및 이벤트의 전체 목록을 보려면 선택한 항목에 대해 사용할 수 있습니다. 목록에서 만들기 또는 편집 처리기 함수를 선택 합니다.

- 코드로 이동할 수는 **대화 상자 편집기**, 가장 최근에 구현된 해당 메시지 처리 기능에 대 한 선언으로 이동 대화 상자 내에 있는 컨트롤을 두 번 클릭 합니다.

   ATL 기반 대화 상자 클래스에 대해 항상 생성자 정의로 이동합니다.

- 컨트롤을 선택 하 고, 컨트롤에 대 한 이벤트를 보려면 선택 합니다 **컨트롤 이벤트** 단추를 **속성** 창입니다.

   마우스 오른쪽 단추로 클릭 하 고 선택할 수, 단일 컨트롤을 대화 상자에 포커스가 있으면 **이벤트 처리기 추가**합니다. 이 처리기가 추가 되는 클래스를 지정할 수 있습니다. 자세한 내용은 [이벤트 처리기를 추가](../ide/adding-an-event-handler-visual-cpp.md)합니다.

   > [!NOTE]
   > 선택 된 **컨트롤 이벤트** 단추 대화 상자에 포커스가 있을 때 개별 컨트롤에 대 한 이벤트를 편집 하려면 다음 확장할 수 있는 대화 상자에서 모든 컨트롤의 목록을 표시 합니다.

- 선택 대화 상자를 사용 하 여 대화 상자에 대 한 메시지를 보려면 선택 합니다 **메시지** 단추를 **속성** 창입니다.

## <a name="accelerator-keys"></a>액셀러레이터 키

기본 액셀러레이터 키가 같습니다 합니다 **대화 상자 편집기** 명령입니다.  

|명령|키|설명|
|-------------|----------|-----------------|
|Format.AlignBottoms|**Ctrl** + **Shift** + **아래쪽 화살표**|기준 컨트롤을 사용 하 여 선택한 컨트롤의 아래쪽 가장자리를 맞춥니다.|
|Format.AlignCenters|**Shift** + **F9**|기준 컨트롤을 사용 하 여 선택한 컨트롤의 세로 가운데에 맞춥니다.|
|Format.AlignLefts|**Ctrl** + **Shift** + **왼쪽 화살표**|기준 컨트롤을 사용 하 여 선택한 컨트롤의 왼쪽된 가장자리를 맞춥니다.|
|Format.AlignMiddles|**F9**|기준 컨트롤을 사용 하 여 선택한 컨트롤의 가로 가운데에 맞춥니다.|
|Format.AlignRights|**Ctrl** + **Shift** + **오른쪽 화살표**|기준 컨트롤을 사용 하 여 선택한 컨트롤의 오른쪽 가장자리를 맞춥니다.|
|Format.AlignTops|**Ctrl** + **Shift** + **위쪽 화살표**|기준 컨트롤을 사용 하 여 선택한 컨트롤의 위쪽 가장자리를 맞춥니다.|
|Format.ButtonBottom|**Ctrl** + **B**|선택한 대화 상자의 아래쪽 가운데 단추를 배치합니다.|
|Format.ButtonRight|**Ctrl** + **R**|대화 상자의 오른쪽 위 모서리에 선택한 단추를 배치합니다.|
|Format.CenterHorizontal|**Ctrl** + **Shift** + **F9**|컨트롤이 대화 상자에서 가로 방향으로 가운데에 맞춥니다.|
|Format.CenterVertical|**Ctrl** + **F9**|컨트롤이 대화 상자에서 세로 방향으로 가운데에 맞춥니다.|
|Format.CheckMnemonics|**Ctrl** + **M**|니모닉의 고유성을 확인합니다.|
|Format.SizeToContent|**Shift** + **F7**|선택한 컨트롤의 캡션 텍스트에 맞게 크기가 조정 됩니다.|
|Format.SpaceAcross|**Alt** + **왼쪽 화살표**|선택한 컨트롤을 가로로 공간 균등 하 게 합니다.|
|Format.SpaceDown|**Alt** + **아래쪽 화살표**|선택한 컨트롤을 세로로 공간 균등 하 게 합니다.|
|Format.TabOrder|**Ctrl** + **D**|대화 상자 내에서 컨트롤의 순서를 설정합니다.|
|Format.TestDialog|**Ctrl** + **T**|모양 및 동작을 테스트 하는 대화 상자를 실행 합니다.|
|Format.ToggleGuides|**Ctrl** + **G**|대화 상자 편집을 위해 없습니다 표, 지침 및 표 간에 순환 합니다.|

- 메뉴로 이동 바로 가기 키를 변경 하려면 **도구** > **옵션**를 선택 하 고 **키보드** 아래를 **환경** 폴더입니다.

   자세한 내용은 [바로 가기 키 식별 및 사용자 지정](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)을 참조하세요.

- 메뉴로 이동 하 여 설정을 변경 하려면 **도구가** > **설정 가져오기 및 내보내기**합니다.

   대화 상자, 이름 및 위치를 표시 하는 메뉴 명령에 사용할 수 있는 옵션에 설명 된 것과 다를 수 **도움말** 활성 설정이 나 버전에 따라 합니다.  자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[리소스 편집기](../windows/resource-editors.md)<br/>
[방법: 대화 상자를 만들려면](../windows/creating-a-new-dialog-box.md)<br/>
[대화 상자 컨트롤](../windows/controls-in-dialog-boxes.md)<br/>
<!--
[Controls](../mfc/controls-mfc.md)<br/>
[Control Classes](../mfc/control-classes.md)<br/>
[Dialog Box Classes](../mfc/dialog-box-classes.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)-->