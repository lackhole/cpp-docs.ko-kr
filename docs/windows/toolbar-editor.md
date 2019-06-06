---
title: 도구 모음 편집기 (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.toolbar.F1
- vc.editors.toolbar
- vc.editors.newtoolbarresource
helpviewer_keywords:
- resource editors [C++], Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
- toolbars [C++], creating
- Toolbar editor [C++], creating new toolbars
- Insert Resource
- bitmaps [C++], converting to toolbars
- Toolbar editor [C++], converting bitmaps
- toolbars [C++], converting bitmaps
- New Toolbar Resource dialog box [C++]
- buttons [C++], custom toolbars
- toolbar buttons [C++], editing
- buttons
- toolbar buttons [C++], creating
- Toolbar editor [C++], creating buttons
- toolbar buttons [C++], button image
- toolbar buttons [C++], creating
- toolbar buttons (in Toolbar editor)
- toolbar buttons [C++], moving
- Toolbar editor [C++], moving buttons
- Toolbar editor [C++], copying buttons
- toolbars [C++], copying buttons
- toolbar buttons [C++], copying
- toolbar buttons [C++], deleting
- Toolbar editor [C++], deleting buttons
- Toolbar editor [C++], spacing toolbar buttons
- toolbar buttons [C++], space between buttons
- toolbar controls [MFC], command ID
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- command IDs, toolbar buttons
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
- tool tips [C++], adding to toolbar buttons
- "\n in tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor [C++], creating tool tips
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
ms.openlocfilehash: f0faa93cd4ea1fdc2fad90a5d4d47f2feeef65e6
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504202"
---
# <a name="toolbar-editor-c"></a>도구 모음 편집기 (C++)

합니다 **도구 모음 편집기** 도구 모음 리소스를 만들고 비트맵을 도구 모음 리소스로 변환할 수 있습니다. 합니다 **도구 모음 편집기** 그래픽 표시를 사용 하 여 도구 모음과 비슷한 방법 표시 되는 모양 완성된 된 응용 프로그램에서 결과 생성 하는 단추를 표시 합니다.

합니다 **도구 모음 편집기** 창 동일 단추 이미지 뷰 두 개가 표시 합니다 **이미지 편집기** 창입니다. 분할줄이 두 창을 구분 하 고 창의 상대적 크기를 변경 하는 쪽에서 분할 막대를 끌 수 있습니다. 활성 창에 선택 테두리를 표시 하 고 이미지 뷰 두 개 위에 제목 도구 모음이 표시 됩니다.

![도구 모음 편집기](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")<br/>
**도구 모음 편집기**

합니다 **도구 모음 편집기** 비슷합니다는 **이미지 편집기** 기능 및 메뉴 항목에서 그래픽 도구 및 비트맵 그리드 서로 동일 합니다. 메뉴 명령는 **이미지** 사이 전환 하려면 메뉴의 **도구 모음 편집기** 및 **이미지 편집기**합니다. 사용 하 여 대 한 자세한 내용은 합니다 **그래픽** 도구 모음 **색** 팔레트 또는 **이미지** 메뉴 참조 [이미지 편집기](../windows/image-editor-for-icons.md)합니다.

새 도구 모음을 만들 수 있습니다는 C++ 비트맵을 변환 하 여 프로젝트입니다. 비트맵에서 그래픽 도구 모음 단추 이미지를 변환합니다. 일반적으로 비트맵 각 단추에 대 한 하나의 이미지를 사용 하 여 단일 비트맵에 여러 단추 이미지를 포함합니다. 기본값은 이미지의 높이 및 너비가 16 픽셀 이미지 임의 크기 일 수 있습니다. 단추 이미지의 크기를 지정할 수 있습니다는 **새 도구 모음 리소스** 선택 하면 대화 상자 **도구 모음 편집기** 에서 합니다 **이미지** 에서 메뉴는  **이미지 편집기**합니다.

**새 도구 모음 리소스** 대화 상자를 사용 하면 도구 모음 리소스에 추가 하는 단추의 높이 너비를 지정 하는 C++ 프로젝트입니다. 기본값은 16 × 15 픽셀입니다.

도구 모음을 만드는 데 사용 되는 비트맵 2048의 최대 너비는 설정한 경우는 **단추 너비** 하 *512*, 네 개의 단추 하나만 지정할 수 있습니다. 너비를 설정 하면 *513*, 세 개의 단추 하나만 지정할 수 있습니다.

합니다 **새 도구 모음 리소스** 대화 상자에는 다음 속성이 있습니다.

|속성|설명|
|---|---------------|
|**Button Width**|도구 모음 리소스 비트맵 리소스를 변환 하는 도구 모음 단추에 대 한 너비를 입력할 공간을 제공 합니다.|
|**단추의 높이**|도구 모음 리소스 비트맵 리소스를 변환 하는 도구 모음 단추에 대 한 높이 입력할 공간을 제공 합니다.|

> [!NOTE]
> 이미지 너비와 높이가 지정 된 자르고 색 표준 도구 모음 색 (16 색)을 사용 하도록 조정 됩니다.

기본적으로 도구 모음의 오른쪽 끝에서 공백 또는 새 단추가 표시 됩니다. 편집 하기 전에이 단추를 이동할 수 있습니다. 새 단추를 만들면 다른 빈 단추 편집 단추 오른쪽에 나타납니다. 도구 모음을 저장 하면 빈 단추 저장 되지 않습니다.

도구 모음 단추에는 다음 속성이 있습니다.

|속성|Description|
|--------------|-----------------|
|**ID**|단추에 대 한 ID를 정의합니다. 드롭다운 목록에는 일반적인 나와 **ID** 이름입니다.|
|**너비**|단추의 너비를 설정합니다. 16 픽셀을 사용 하는 것이 좋습니다.|
|**높이**|단추의 높이 설정합니다. 도구 모음에서 모든 단추의 높이 변경 하는 하나의 단추의 높이입니다. 15 픽셀을 사용 하는 것이 좋습니다.|
|**프롬프트**|상태 표시줄에 표시 되는 메시지를 정의 합니다. 추가 *\n* 이름을 추가 하 고는 **도구 설명** 해당 도구 모음 단추입니다. 자세한 내용은 [도구 설명을 만드는](../windows/creating-a-tool-tip-for-a-toolbar-button.md)합니다.|

**너비** 하 고 **높이** 모든 단추에 적용 합니다. 도구 모음을 만드는 데 사용 되는 비트맵 2048의 최대 너비는 단추 너비를 설정 하는 경우 *512*, 네 개의 단추 하나만 지정할 수 있습니다 및 너비를 설정 하는 경우 *513*, 세 개의 단추 하나만 지정할 수 있습니다.

## <a name="how-to"></a>방법

합니다 **도구 모음 편집기** 있습니다.

### <a name="to-create-new-toolbars"></a>새 도구 모음을 만들려면

1. **리소스 뷰**를 마우스 오른쪽 단추로 클릭 하 *.rc* 파일을 선택 **리소스 추가**합니다. 기존 도구 모음에 있는 경우에 *.rc* 단추로 파일을 **도구 모음** 폴더를 선택 **도구 모음 삽입**합니다.

1. 에 **리소스 추가** 대화 상자에서 **도구 모음** 에 **리소스 종류** 목록에서 선택한 **새로 만들기**합니다.

   더하기 기호 ( **+** ) 옆에 표시 되는 **도구 모음** 리소스 종류, 즉 모음 템플릿을 사용할 수 있습니다. 템플릿의 목록을 확장 하는 템플릿을 선택 하 고 선택 하려면 더하기 기호 **새로 만들기**합니다.

### <a name="to-convert-bitmaps-to-toolbar-resources"></a>비트맵을 도구 모음 리소스로 변환

1. 기존 비트맵 리소스를 엽니다는 [이미지 편집기](../windows/image-editor-for-icons.md)합니다. 비트맵에 있지 않은 경우에 *.rc* 파일을 마우스 오른쪽 단추로 클릭 합니다 *.rc* 파일을 선택 **가져오기**를 추가 하려는 비트맵으로 이동에 *.rc*  파일을 선택 **오픈**합니다.

1. 메뉴로 이동 **이미지** > **도구 모음 편집기**합니다.

   합니다 **새 도구 모음 리소스** 대화 상자가 나타납니다. 비트맵에 맞게 아이콘 이미지의 높이 너비를 변경할 수 있습니다. 도구 모음 이미지에 표시 됩니다는 **도구 모음 편집기**합니다.

1. 변환이 완료 명령을 변경 **ID** 사용 하 여 단추를 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 새 입력 *ID* 누르거나는 **ID** 드롭 다운 목록에서.

   > [!TIP]
   > 합니다 **속성** 창 제목 표시줄에 압정 단추를 포함 하 고이 선택 하면 사용 하거나 사용 하지 않도록 설정 **자동 숨기기** 창에 대 한 합니다. 각 속성 창을 다시 열 필요가 없는 모든 도구 모음 단추 속성을 통해 전환, 전환 **자동 숨기기** 해제 하므로 **속성** 창이 고정 합니다.

   사용 하 여 새 도구 모음에서 단추 명령 Id를 변경할 수도 있습니다는 [속성 창](/visualstudio/ide/reference/properties-window)합니다.

### <a name="to-manage-toolbar-buttons"></a>도구 모음 단추를 관리 하려면

#### <a name="to-create-a-new-toolbar-button"></a>새 도구 모음 단추를 만들려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources) 리소스 폴더를 확장 (예를 들어 *: Project1.rc*).

1. 확장 된 **도구 모음** 폴더를 편집 하려면 도구 모음 선택 다음 하나를 수행 중:

   - 도구 모음의 오른쪽 끝에 빈 단추에는 ID를 할당 합니다. 편집 하 여 수행할 수는 **ID** 속성에는 [속성 창](/visualstudio/ide/reference/properties-window)합니다. 예를 들어, 다음 도구 모음 단추 메뉴 옵션으로 동일한 ID를 제공 하는 것이 좋습니다. 이 경우 드롭다운 목록 상자를 사용 하 여 선택 합니다 **ID** 메뉴 옵션입니다.

   - 도구 모음의 오른쪽 끝에 비어 있는 단추를 선택 합니다 **도구 모음 보기** 창 고 그리기를 시작 합니다. 기본 단추 명령 ID가 할당 됩니다 (ID_BUTTON\<n >).

#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>도구 모음에 단추와 이미지를 추가 하려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)를 두 번 클릭 하 여 도구 모음을 엽니다.

1. 다음으로, 도구 모음에 추가 하려는 이미지를 엽니다.

   > [!NOTE]
   > Visual Studio에서 이미지를 열면에서 열립니다는 **이미지 편집기**합니다. 또한 다른 그래픽 프로그램에서 이미지를 열 수 있습니다.

1. 메뉴로 이동 **편집할** > **복사**합니다.

1. 소스 창의 맨 위에 있는 해당 탭을 선택 하 여 도구 모음을 전환 합니다.

1. 메뉴로 이동 **편집할** > **붙여넣기**합니다.

   이미지는 새 단추도 도구 모음에 표시 됩니다.

#### <a name="to-move-a-toolbar-button"></a>도구 모음 단추 이동 하려면

에 **도구 모음 보기** 창 도구 모음에서 새 위치로 이동 하려면 단추를 끌어 옵니다.

- 누른 단추 도구 모음에서 복사할 합니다 **Ctrl** 키 및 합니다 **도구 모음 보기** 창 끌거나 단추 중 하나를 새 위치로 도구 모음에서 위치에 다른 도구 모음에서 합니다.

- 도구 모음 단추를 삭제 하려면 도구 모음 단추를 선택 하 고 도구 모음 밖으로 끕니다.

- 를 삽입 하거나 도구 모음에서 단추 사이의 공백 제거 하거나 끌어에서 또는 다른 쪽으로 도구 모음에서 합니다.

|작업|단계|
|------|------|
|뒤에 공백이 없습니다 단추 앞에 공백을 삽입 하려면|오른쪽 단추를 끌거나 겹치는 다음 단추에 대 한 중간 될 때까지 아래로 합니다.|
|공백 뒤에 나오는 단추 앞에 공백을 삽입 하 고 후행 공백을 유지 합니다.|오른쪽 가장자리나 아래쪽 가장자리 다음 단추 바로 겹쳐질 때까지 단추를 끕니다.|
|다음 해당 공간을 닫고 공백 뒤에 나오는 단추 앞에 공백을 삽입 하려면|오른쪽 단추를 끌거나 겹치는 다음 단추에 대 한 중간 될 때까지 아래로 합니다.|
|도구 모음의 단추 사이 공백을 제거 하려면|중간에 대 한 다음 단추와 겹칠 때까지 공간의 다른 쪽에 있는 단추로 공간 한쪽 단추를 끕니다.|

> [!NOTE]
> 다른 위치로 끌어 온 다음 단추 공간이 없을 경우 끌면 단추 옆에 있는 단추를 반 이상 합니다 **도구 모음 편집기** 드래그 하는 단추의 반대쪽에 공백을 삽입 합니다.

#### <a name="to-change-the-properties-of-a-toolbar-button"></a>도구 모음 단추의 속성을 변경 하려면

1. 에 C++ 프로젝트, 도구 모음 단추를 선택 합니다.

1. 에 새 ID를 입력 합니다 **ID** 속성에는 [속성 창](/visualstudio/ide/reference/properties-window), 드롭 다운 목록을 사용 하 여 새 선택 또는 **ID**합니다.

#### <a name="to-create-a-tool-tip-for-a-toolbar-button"></a>도구 모음 단추에 대 한 도구 설명을 만들려면

1. 도구 모음 단추를 선택 합니다.

1. 에 [속성 창](/visualstudio/ide/reference/properties-window)를 **프롬프트** 필드, 상태 표시줄 및 메시지가 나타나면 단추에 대 한 설명을 추가, 추가 `\n` 및 도구 팁 이름.

예를 들어, 참조에 대 한 도구 설명에는 **인쇄** 단추 **워드 패드**:

1. 오픈 **워드 패드**합니다.

1. 마우스 포인터를 올려 합니다 **인쇄** 도구 모음 단추 및 알림 단어 `Print` 마우스 포인터 아래에 이제 부동 합니다.

1. 맨 아래에 있는 상태 표시줄에는 **워드 패드** 창과 이제 텍스트를 표시 하는 알림 `Prints the active document`합니다.

`Print` 도구 설명 이름 및 `Prints the active document` 상태 표시줄의 단추에 대 한 설명입니다.

사용 하 여이 적용 하려는 경우는 **도구 모음 편집기**로 설정 합니다 **프롬프트** 속성을 `Prints the active document\nPrint`입니다.

## <a name="requirements"></a>요구 사항

MFC 또는 ATL

## <a name="see-also"></a>참고자료

[리소스 편집기](../windows/resource-editors.md)
[메뉴 및 기타 리소스](/windows/desktop/menurc/resources)<br/>
[도구 모음 단추 속성](../windows/toolbar-button-properties.md)<br/>
