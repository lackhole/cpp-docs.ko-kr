---
title: '방법: 레이아웃 컨트롤 (c + +) | Microsoft Docs'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.grouping
- vc.editors.dialog.combo
helpviewer_keywords:
- controls [C++], positioning
- dialog box controls [C++], placement
- Dialog Editor [C++], arranging controls
- Dialog Editor [C++], guides and margins
- guides, clearing
- guides
- dialog box controls [C++], placement
- controls [C++], guides and margins
- guides, creating
- guides, moving
- margins, moving
- DLUs (dialog units)
- controls [C++], aligning
- Dialog Editor [C++], snap to guides
- guides, tick mark interval
- dialog box controls [C++], placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
- guides, disabling snapping
- controls [C++], snap to guides/grid
- controls [C++], layout grid
- snap to layout grid
- grids, turning on or off
- layout grid in Dialog Editor
- grids, changing size
- grid spacing
- guides, settings
- layout grid in Dialog Editor
- controls [C++], snap to guides/grid
- Guide Settings dialog box (Dialog editor)
- controls [C++], aligning
- controls [C++], positioning
- Space Evenly command
- dialog box controls [C++], placement
- Center in Dialog command
- Arrange Buttons command
- buttons, arranging push buttons in dialog boxes
- push buttons
- member variables, adding to radio button groups
- variables, dialog box control member variables
- dialog box controls [C++], grouping radio buttons
- grouping controls
- radio buttons [C++], grouping on dialog boxes
- controls [C++], tab order
- focus, tab order
- tab controls [C++], tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls [C++], tab order
- Dialog Editor [C++], selecting controls
- dominant controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
- controls [C++], removing from groups
- Dialog Editor [C++], dominant control
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
- Make Same Size command
- combo boxes, sizing
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 832491cf-98af-42e5-a854-2cb135fd45c6
ms.openlocfilehash: 3d79e48411006156ee4682adc736e83e226743af
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57562980"
---
# <a name="how-to-layout-controls-c"></a>방법: 레이아웃 컨트롤 (c + +)

합니다 **대화 상자 편집기** 정렬 컨트롤을 자동으로 크기를 레이아웃 도구를 제공 합니다. 대부분의 작업을 사용 합니다 [대화 상자 편집기 도구 모음](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)합니다. 모든 **대화 상자 편집기** 도구 모음 명령에서 사용할 수 있습니다 합니다 **형식** 메뉴와 대부분 [바로 가기 키](../windows/accelerator-keys-for-the-dialog-editor.md)합니다.

대화 상자에 대 한 대부분의 레이아웃 명령에 하나 이상의 컨트롤을 선택 하는 경우에에 사용할 수 있습니다. 컨트롤 하나 또는 여러 개의 컨트롤을 선택할 수 있습니다 하 고 하나 이상의 컨트롤을 선택 하면 선택한 첫 번째 기준이 되는 기본적으로 컨트롤입니다.

위치, 높이 및 너비 현재 컨트롤의 상태 표시줄의 오른쪽 아래 모서리에 표시 됩니다. 전체 대화 상자를 선택 하면 상태 표시줄 전체 높이 및 너비와 대화 상자의 위치를 표시 합니다.

## <a name="arrange-controls"></a>컨트롤 정렬

사용 하 여 대화 상자에 컨트롤을 정렬할 수 있습니다 합니다 **대화 상자 편집기** 세 가지 상태 중 하나에서:

- 안내선과 여백 기본값으로 설정 됩니다.

- 레이아웃 모눈을 사용 하 여

- 모든 스냅인 또는 맞춤 기능 사용 안 함입니다.

합니다 [대화 상자 편집기 도구 모음](../windows/showing-or-hiding-the-dialog-editor-toolbar.md) 상태를 제어 하는 단추가 포함 되어 있습니다.

- 상태를 변경 하려면 해당 아이콘을 선택 하거나 메뉴로 이동 **형식** > **안내선 설정**합니다.

합니다 **안내선 설정** 대화 상자에는 다음 속성이 있습니다.

|속성|설명|
|---|---|
|**레이아웃 안내선**|레이아웃 안내선에 대 한 설정을 표시합니다.|
|**없음**|레이아웃 도구를 숨깁니다.|
|**눈금자 및 안내선**|사용 하도록 설정 하는 경우 레이아웃 도구 눈금자를 추가 하 고 가이드 눈금자에 배치할 수 있습니다. 기본 가이드는 여백입니다.|
|**눈금**|레이아웃 표를 만듭니다. 새 컨트롤 표에 자동으로 정렬 됩니다.|
|**모눈 간격**|대화 상자 단위 (Dlu) 모눈 간격에 대 한 설정을 표시합니다.|
|**너비: DLUs**|Dlu의 레이아웃 모눈의 너비를 설정합니다. 가로 DLU는 4로 나눈 값 대화 상자 글꼴의 평균 너비입니다.|
|**Height: DLUs**|Dlu의 레이아웃 모눈의 높이 설정합니다. 세로 DLU은 평균 8로 나눈 대화 상자 글꼴 높이입니다.|

### <a name="guides-and-margins"></a>안내선과 여백

컨트롤을 추가 컨트롤을 이동 하 든 현재 레이아웃 다시 정렬 안내선과 여백 도움이 컨트롤 대화 상자 내에서 정확 하 게 맞춥니다.

대화 상자를 만들 때 여백 라는 4 명의 수정된 지침 제공 및 파란색 점선으로 표시 합니다.

- 여백 이동할 여백을 새 위치로 끕니다.

- 사라집니다 여백을 있도록 여백을 0의 위치로 이동 합니다.

- 가져오고 다시 여백, 0 위치는 여백 위에 포인터를 놓고 여백을 위치로 이동 합니다.

안내선 나타나고 파란색 점선 대화 상자 편집기 및 해당 화살표의 왼쪽 맨 위에 있는 눈금자를 표시 합니다 **대화 상자 편집기**합니다. 컨트롤의 크기 조정 핸들 컨트롤을 이동 하 고 이전에 가이드에 맞춰진 컨트롤이 없는 경우 가이드 컨트롤 맞춤 안내선에 맞춤 합니다. 가이드 이동 될 때 컨트롤에 모눈을 이동 합니다. 둘 이상의 가이드에 맞춰진 컨트롤 가이드 중 하나를 이동 하면 크기가 조정 됩니다.

- 눈금자 내 가이드를 만들려면 지침을 만들려면 한 번 선택 하거나 시작 하려면 두 번 클릭 합니다 **안내선 설정** 가이드 설정을 지정할 수 있는 대화 상자.

- 대화 상자에서 지침을 설정 하려면 선택 가이드 및를 새 위치로 끌어다 놓습니다 또는 관련된 가이드를 끌어서 눈금자의 화살표를 선택 합니다.

   가이드의 좌표에는 가이드의 정확한 위치를 표시 하려면 눈금자 화살표 위로 포인터를 이동 또는 눈금자 창의 아래쪽 상태 표시줄에 표시 됩니다.

- 지침을 삭제, 가이드 대화 상자에서 끌거나 눈금자 해제 대응 하는 화살표를 끌어 옵니다.

안내선과 컨트롤의 간격을 결정 하는 눈금자의 눈금은 대화 상자 단위 (Dlu)로 정의 됩니다. DLU는 일반적으로 8 포인트 MS Shell Dlg 대화 상자 글꼴 크기를 기반으로 합니다. 가로 DLU는 4로 나눈 대화 상자 글꼴의 평균 너비입니다. 세로 DLU은 평균 8로 나눈 글꼴 높이입니다.

- 눈금 표시의 간격을 변경 하려면 메뉴로 이동 **형식** > **안내선 설정**, 그런 다음 합니다 **모눈 간격** 필드, Dlu의 새 너비와 높이 지정 합니다.

### <a name="layout-grid"></a>레이아웃 모눈

때 배치 또는 레이아웃 모눈을 사용 하 여 보다 정확한 위치에 대 한 대화 상자에서 컨트롤을 정렬 합니다. 표에서 켜져 자석 처럼 컨트롤 그리드의 점선은에 맞춰집니다.

- 레이아웃 모눈을 끄거나로 이동 메뉴 **형식** > **안내선 설정** 선택 하거나 선택을 취소 하 고는 **표** 단추입니다.

   개별 메서드는 눈금을 제어할 수 있습니다 **대화 상자 편집기** 사용 하 여 windows를 **눈금 설정/해제** 단추를 [대화 상자 편집기 도구 모음](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)합니다.

- 레이아웃 모눈의 크기를 변경 하려면 메뉴로 이동 **형식** > **안내선 설정** 표의 셀에 대 한 Dlu 높이 너비를 입력 합니다. 최소 높이 또는 너비는 4입니다.

### <a name="disable-guides"></a>지침 사용 안 함

안내선의 맞춤 효과 사용 하지 않도록 설정 하려면 마우스와 함께에서 특수 키를 사용할 수 있습니다. 사용 하는 **Alt** 키 선택이 가이드의 맞춤 효과 사용 하지 않도록 설정 합니다. 지침을 사용 하 여 이동 합니다 **Shift** 키 가이드를 사용 하 여 이동 모눈된 컨트롤을 방지 합니다.

- 안내선의 맞춤 효과 해제 하려면 컨트롤 채로 끕니다 합니다 **Alt** 키입니다.

- 안내선 맞춰진된 컨트롤을 이동 하지 않고 이동할 가이드 채로 끕니다 합니다 **Shift** 키입니다.

- 메뉴로 이동 가이드를 사용 하지 않으려면 **형식** > **안내선 설정**합니다. 그런 다음 **레이아웃 안내선**를 선택 **None**합니다.

   > [!TIP]
   > 바로 가기 메뉴에서 사용할 수도 있습니다 **형식** > **안내선 설정/해제**합니다.

## <a name="select-controls"></a>컨트롤 선택

컨트롤 크기를 선택, 정렬, 이동, 복사 또는 삭제할 수 및 다음 작업을 완료 합니다. 대부분의 경우에서에서 크기 조정 및 맞춤 도구를 사용 하려면 둘 이상의 컨트롤을 선택 해야 합니다 [대화 상자 편집기 도구 모음](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)합니다.

컨트롤을 선택 하면 해당 회색 테두리가 실선 (활성)를 사용 하 여 또는 비어 있는 (비활성) 크기 조정 핸들을 선택 테두리에 표시 되는 작은 사각형입니다. 여러 컨트롤을 선택 하면 기준 컨트롤에 단색 크기 조정 핸들 있고 다른 선택된 된 컨트롤이 모두 속이 빈 크기 조정 핸들입니다.

- 컨트롤에서 선택 하는 [도구 상자 창](/visualstudio/ide/reference/toolbox)를 선택 합니다 **포인터** 도구를 선택 하는 다음 단계 중 하나를 사용:

  - 대화 상자에서 선택 하려는 컨트롤 주위의 선택 상자에 대 한 포인터를 끕니다. 마우스 단추를 놓으면 모든 내부 및 선택 상자는 선택한 교차 제어 합니다.

  - 누른 합니다 **Shift** 키 및 선택 영역에 포함 하려는 컨트롤을 선택 합니다.

  - 누른 합니다 **Ctrl** 키 및 선택 영역에 포함 하려는 컨트롤을 선택 합니다.

- 누른를 추가 하거나 선택한 컨트롤의 그룹에서 컨트롤을 제거 하는 **Shift** 키를 추가 하거나 제거 하려는 컨트롤을 선택 합니다.

### <a name="dominant-controls"></a>기준 컨트롤

크기를 조정 하거나 여러 개의 컨트롤을 정렬 하는 경우는 **대화 상자 편집기** 기준 컨트롤을 사용 하 여 다른 컨트롤의 크기와 정렬 하는 방법을 결정 합니다. 기본적으로 주요 컨트롤에는 선택한 첫 번째 컨트롤이입니다.

- 기준 컨트롤을 지정 하려면 누른 합니다 **Ctrl** 키 및 크기와 다른 컨트롤의 위치를 정하는 데 사용 하려는 컨트롤을 선택 *첫 번째*입니다. 누른 합니다 **Ctrl** 키 및 선택 영역 내의 컨트롤 선택도 하 게 선택에서 기준 컨트롤을 제어 하는 합니다.

- 기준 컨트롤을 변경 하려면 현재 선택된 된 컨트롤이 모두 외부를 선택 하 여 현재 선택을 취소 하 고 다른 컨트롤을 선택 하는 위의 절차를 반복 *첫 번째*입니다.

> [!NOTE]
> 기준 컨트롤의 크기 조정 핸들은 하위 컨트롤의 핸들은 속이 빈 실선입니다. 모든 크기 조정 이나 맞춤 기준 컨트롤을 기반으로 합니다.

## <a name="size-controls"></a>컨트롤 크기 조정

컨트롤의 크기를 조정 하려면 크기 조정 핸들을 사용 합니다. 크기 조정 핸들의 포인터가 셰이프 컨트롤을 조정할 수 있는 방향을 가리키도록 변경 됩니다. 현재 크기 조정 핸들 단색 이며 컨트롤 크기 조정 핸들을 속이 빈 경우 해당 축을 조정할 수 없습니다.

- 컨트롤 크기 조정 컨트롤을 선택 하 고 크기 조정 핸들을 끌어 크기를 변경 합니다.

  - 위와 옆에 있는 크기 핸들 가로 또는 세로 크기를 변경 합니다.

  - 모퉁이에 크기 핸들 가로 및 세로 크기를 변경합니다.

   > [!TIP]
   > 누른 여 한 번에 하나의 대화 상자 단위 (DLU) 컨트롤을 조정할 수 있습니다는 **Shift** 키 및 사용 하 여를 **오른쪽** 하 고 **아래로** 화살표 키입니다.

- 그 텍스트에 맞게 컨트롤을 자동으로 크기를 메뉴로 이동 **형식** 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 선택 하거나 **콘텐츠 크기를 조정**합니다.

- 컨트롤을 같은 크기로, 메뉴로 이동 하 고 크기를 조정 하려는 컨트롤 선택 **형식** > **같은 크기로**, 선택 **둘 다**를 **높이**, 또는 **너비**합니다.

   시리즈의 처음 선택 된 컨트롤에는 주요 컨트롤의 크기에 따라 컨트롤 그룹 크기를 조정 하는 합니다. 그룹에 있는 컨트롤의 최종 크기 기준 컨트롤의 크기에 따라 달라 집니다.

- 가이드를 사용 하 여 컨트롤 그룹의 크기를 하려면 컨트롤 (또는 컨트롤)의 한 쪽 안내선에 맞춤 컨트롤 (또는 컨트롤)의 다른 쪽에 대 한 가이드를 드래그 합니다. 이제 두 가이드 컨트롤 (또는 컨트롤)의 크기를 이동할 수 있습니다.

   여러 컨트롤을 사용 하 여 필요한 경우에 두 번째 가이드는 각 크기입니다.

### <a name="other-controls"></a>다른 컨트롤

대화 상자에 추가할 때 콤보 상자 크기. 또한 드롭다운 목록 상자의 크기를 지정할 수 있습니다. 자세한 내용은 [콤보 상자 컨트롤에 추가 값](../windows/adding-values-to-a-combo-box-control.md)합니다.

1. 콤보 상자의 오른쪽에 있는 드롭다운 화살표 단추를 선택 합니다.

   ![MFC 프로젝트에서 콤보 상자에서 화살표](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")

   드롭다운 목록에서 영역이 확장을 사용 하 여 콤보 상자의 크기를 표시 하려면 해당 컨트롤의 개요입니다.

1. 드롭다운 목록에서 영역의 초기 크기를 변경 하려면 아래쪽 크기 조정 핸들을 사용 합니다.

   ![콤보&#45;MFC 프로젝트의 상자 크기 조정](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")

1. 콤보 상자의 드롭다운 목록에서 일부를 다시 드롭다운 화살표를 선택 합니다.

> [!NOTE]
> MFC를 사용 하 여 대화 상자에 가로 스크롤 막대를 사용 하 여 목록 상자에 추가한 경우 스크롤 막대를 응용 프로그램에 자동으로 나타나지 않습니다.
>
> 호출 하 여 광범위 한 요소에 대 한 최대 너비를 설정할 [CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) 코드에서. 이 값을 설정 하지 않고 스크롤 막대 표시 되지도 목록 상자의 항목 상자 보다 넓을 경우.

## <a name="align-controls"></a>컨트롤 맞춤

- 컨트롤을 맞추려면 정렬 하려는 컨트롤을 선택 합니다. 메뉴로 이동 **형식** > **Align** 맞춤 다음 방법 중 하나를 선택 합니다.

   |맞춤|설명|
   |-----|-----------|
   |**왼쪽**|선택한 컨트롤을 왼쪽으로 맞춥니다.|
   |**센터**|선택한 컨트롤의 가운데 일렬로 가로로 맞춥니다.|
   |**권한**|선택한 컨트롤의 오른쪽 면 일렬로 정렬합니다.|
   |**위쪽**|위쪽 가장자리를 따라 선택한 컨트롤을 맞춥니다.|
   |**중간**|선택한 컨트롤의 중간 일렬로 세로로 맞춥니다.|
   |**아래쪽**|아래쪽 가장자리를 따라 선택한 컨트롤을 맞춥니다.|

   먼저 기준 되도록 하려는 컨트롤을 선택 하도록 맞춤 실행 또는 컨트롤 그룹의 최종 위치 기준 컨트롤의 위치를 종속 명령 크기를 조정 하기 전에 주요 컨트롤 수로 설정 합니다.

- 균등 하 게 공간 컨트롤에 다시 정렬 하려면 컨트롤을 선택 합니다. 메뉴로 이동 **형식** > **균등 하 게 공간** 다음 간격 맞춤 중 하나를 선택 합니다.

   |간격|설명|
   |---|---|
   |**Across**|왼쪽 및 오른쪽에 있는 선택 된 컨트롤 간에 균등 하 게 공간 제어 합니다.|
   |**아래로**|맨 위 및 맨 아래 선택 된 컨트롤 간에 균등 하 게 공간 제어 합니다.|

- 컨트롤을 가운데에 컨트롤 또는 컨트롤 다시 정렬 하려면 선택 합니다. 메뉴로 이동 **형식** > **센터에서 대화 상자** 다음 배치 방법 중 하나를 선택 합니다.

   |정렬|설명|
   |---|---|
   |**세로**|대화 상자에서 세로로 가운데 제어 합니다.|
   |**가로**|대화 상자에서 가로 방향으로 가운데 제어 합니다.|

- 누름 단추 정렬 하려면 하나 이상의 푸시 단추를 선택 합니다. 메뉴로 이동 **형식** > **단추 정렬**, 다음 배치 방법 중 하나를 선택 합니다.

   |정렬|설명|
   |---|---|
   |**오른쪽**|대화 상자의 오른쪽 가장자리를 따라 누름 단추를 배치 합니다.|
   |**아래쪽**|대화 상자의 아래쪽 가장자리를 따라 누름 단추를 배치 합니다.|

   누름 단추 이외의 컨트롤을 선택할 위치로 영향을 받지 않습니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고 항목

[대화 상자 컨트롤 관리](controls-in-dialog-boxes.md)<br/>
[방법: 추가, 편집 또는 삭제 컨트롤](adding-editing-or-deleting-controls.md)<br/>
[방법: 액세스 제어 및 값 정의](defining-mnemonics-access-keys.md)<br/>