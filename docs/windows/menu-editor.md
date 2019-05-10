---
title: 메뉴 편집기 (C++)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.menu.F1
- vc.editors.menu
helpviewer_keywords:
- resource editors [C++], Menu editor
- editors, menus
- Menu editor
- menus [C++], Menu editor
- mnemonics [C++], associating menu items
- menus [C++], associating commands with mnemonic keys
- menus [C++], creating
- menus [C++], adding items
- commands [C++], adding to menus
- menu items, adding to menus
- submenus
- submenus [C++], creating
- menus [C++], creating
- context menus [C++], Menu Editor
- pop-up menus [C++], creating
- menus [C++], pop-up
- menus [C++], creating
- shortcut menus [C++], creating
- pop-up menus [C++], displaying
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- shortcut menus [C++], connecting to applications
- pop-up menus
- menu commands [C++], selecting
- menus [C++], selecting
- commands [C++], menu commands
- commands [C++], copying on menus
- menu items, moving
- commands [C++], moving on menus
- menu items, copying
- menu items, deleting
- commands [C++], deleting from menus
- menus [C++], deleting
ms.assetid: 421fb215-6e12-4ec9-a3af-82d77f87bfa6
ms.openlocfilehash: b5d809fa4e0f608d4c0e6cbdaf8697688c6d3f9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376781"
---
# <a name="menu-editor-c"></a>메뉴 편집기 (C++)

메뉴를 통해 논리적이고 찾기 쉬운 방식으로 명령을 정렬할 수 있습니다. 사용 하 여 합니다 **메뉴 편집기**, 만들 수 있습니다 및 완성 된 응용 프로그램의 편집 메뉴는 밀접 하 게 메뉴 모음을 사용 하 여 직접 작업 하 여 유사 합니다.

> [!TIP]
> 사용 하는 동안 합니다 **메뉴 편집기**, 자주 사용 되는 명령의 팝업 메뉴에 표시할 단추로 경우가 많습니다. 사용할 수 있는 명령은 포인터가 가리키는 내용에 따라 달라집니다.

## <a name="how-to"></a>방법

합니다 **메뉴 편집기** 있습니다.

### <a name="to-create-a-standard-menu"></a>표준 메뉴를 만들려면

1. 메뉴로 이동 **뷰** > **리소스 뷰** 마우스 오른쪽 단추로 클릭 합니다 **메뉴** 제목입니다. 선택할 **리소스 추가**, 한 다음 **메뉴**합니다.

1. 선택 된 **새 항목** 상자 (포함 된 사각형 *여기에 입력*) 메뉴 모음에서.

   ![메뉴 편집기에서 새 항목 상자가](../windows/media/vcmenueditornewitembox.gif "vcMenuEditorNewItemBox")<br/>
   **새 항목** 상자

1. 예를 들어, 새 메뉴의 이름을 입력 *파일*합니다.

   입력 한 텍스트를 둘 다에 표시 됩니다는 **메뉴 편집기** 및 합니다 **캡션** 상자에 [속성 창](/visualstudio/ide/reference/properties-window). 한 위치에서 새 메뉴에 대한 속성을 편집할 수 있습니다.

   메뉴 모음에서 새 메뉴에 이름을 지정하면 새 항목 상자가 오른쪽으로 이동하고(다른 메뉴를 추가할 수 있도록), 메뉴 명령을 추가할 수 있도록 또 다른 새 항목 상자가 첫 번째 메뉴 아래에 열립니다.

   ![확장 된 새 항목 상자가](../windows/media/vcmenueditornewitemboxexpanded.gif "vcMenuEditorNewItemBoxExpanded")<br/>
   **새 항목** 메뉴 이름을 입력 한 후 이동 하 여 포커스를 사용 하 여 상자

   > [!NOTE]
   > 메뉴 모음에서 단일 항목 메뉴를 만들려면 다음을 설정 합니다 **팝업** 속성을 **False**합니다.

### <a name="to-create-a-submenu"></a>하위 메뉴를 만들려면

1. 하위 메뉴를 만들려는 메뉴 명령을 선택 합니다.

1. 오른쪽에 표시되는 **새 항목** 상자에 새 메뉴 명령의 이름을 입력합니다. 이 새로운 명령이 하위 메뉴에서 첫 번째로 표시됩니다.

1. 하위 메뉴에 메뉴 명령을 더 추가합니다.

### <a name="to-insert-a-new-menu-between-existing-menus"></a>기존 메뉴 사이에 새 메뉴를 삽입하려면

기존 메뉴 이름 및 키를 눌러 선택 합니다 **삽입** 키 또는 메뉴 모음에서 마우스 오른쪽 단추로 클릭 하 고 선택 **새로 삽입**합니다.

   합니다 **새 항목** 상자 선택한 항목 앞에 삽입 됩니다.

### <a name="to-add-commands-to-a-menu"></a>메뉴에 명령을 추가하려면

1. 메뉴를 만듭니다. 예를 들어 같은 메뉴 이름을 선택 **파일**합니다.

   각 메뉴가 확장되고 명령에 대한 새 항목 상자가 표시됩니다. 예를 들어 명령을 추가할 수 있습니다 **새로 만들기**, **열려**, 및 **닫기** 하는 **파일** 메뉴.

1. 새 항목 상자에 새 메뉴 명령에 대한 이름을 입력합니다.

   > [!NOTE]
   > 입력 한 텍스트를 둘 다에 표시 됩니다는 **메뉴 편집기** 및 합니다 **캡션** 상자에 [속성 창](/visualstudio/ide/reference/properties-window). 한 위치에서 새 메뉴에 대한 속성을 편집할 수 있습니다.

   > [!TIP]
   > 사용자가 메뉴 명령을 선택할 수 있도록 니모닉 키(바로 가기 키)를 정의할 수 있습니다. 앰퍼샌드를 입력 (`&`) 니모닉으로 지정 하려면 문자 앞에 있습니다. 사용자는 해당 문자를 입력하여 메뉴 명령을 선택할 수 있습니다.

1. 에 **속성** 창에서 메뉴 명령을 적용 되는 속성입니다. 자세한 내용은 참조 하세요 [메뉴 명령 속성](../windows/menu-command-properties.md)합니다.

1. 에 **프롬프트** 상자에 **속성** 창 응용 프로그램의 상태 표시줄에 표시할 프롬프트 문자열을 입력 합니다.

   이 단계에서 만든 메뉴 명령과 동일한 리소스 식별자를 사용 하 여 문자열 테이블 항목을 만듭니다.

   > [!NOTE]
   > 프롬프트 메뉴 항목에만 적용할 수는 **팝업** 속성을 **True**합니다. 예를 들어 최상위 메뉴 항목은 하위 메뉴 항목이 있는 경우 프롬프트가 적용됩니다. 용도 **프롬프트** 어떤 동작이 발생 했다는 것을 사용자가 메뉴 항목을 선택 합니다.

1. 키를 눌러 **Enter** 메뉴 명령을 완료 합니다.

   새 항목 상자를 선택하여 추가 메뉴 명령을 만들 수 있습니다.

### <a name="to-select-multiple-menu-commands-to-run-bulk-operations-such-as-deleting-or-changing-properties"></a>속성 삭제 또는 변경과 같은 대량 작업을 실행 하기 위해 여러 메뉴 명령을 선택 합니다.

누른 채 합니다 **Ctrl** 키, 메뉴 또는 하위 메뉴 명령을 선택 합니다.

### <a name="to-move-and-copy-menus-and-menu-commands"></a>메뉴 및 메뉴 명령 이동 및 복사 하려면

- 끌어서 놓기 방법을 사용 합니다.

   1. 이동하려는 항목을 다음 위치로 끌거나 복사합니다.

      - 현재 메뉴의 새 위치.

      - 다른 메뉴. 다른 메뉴 위로 마우스 포인터를 끌어 이동할 수 있습니다.

   1. 삽입 가이드에 원하는 위치가 표시되면 메뉴 명령을 놓습니다.

- 바로 가기 메뉴 명령을 사용 합니다.

   1. 선택한 하나 이상의 메뉴 또는 메뉴 명령을 마우스 오른쪽 단추로 클릭 **잘라내기** (이동할) 또는 **복사**합니다.

   1. 다른 메뉴 항목을 이동 하는 경우 리소스나 리소스 스크립트 파일로 [다른 창에서 열](/visualstudio/ide/customizing-window-layouts-in-visual-studio)합니다.

   1. 이동하거나 복사하려는 메뉴 또는 메뉴 명령의 위치를 선택합니다.

   1. 바로 가기 메뉴에서 **붙여넣기**를 선택합니다. 이동하거나 복사한 항목은 선택한 항목 앞에 배치됩니다.

> [!NOTE]
> 다른 메뉴 창에 있는 다른 메뉴로 끌거나 복사하고 붙여 넣을 수도 있습니다.

### <a name="to-delete-a-menu-or-menu-command"></a>메뉴 또는 메뉴 명령을 삭제하려면

메뉴 이름 또는 명령을 마우스 오른쪽 단추로 클릭 하 고 선택 **삭제**합니다.

> [!NOTE]
> 마찬가지로 바로 가기 메뉴를 사용하여 복사, 잘라내기, 붙여넣기, 새로 삽입, 구분 기호 삽입, ID 편집, 팝업으로 보기, 니모닉 확인 등의 다른 작업을 수행할 수 있습니다.

## <a name="pop-up-menus"></a>팝업 메뉴

[팝업 메뉴](../mfc/menus-mfc.md) 에는 자주 사용되는 명령이 표시됩니다. 포인터 위치에 대한 상황에 맞는 메뉴일 수 있습니다. 애플리케이션에서 팝업 메뉴를 사용하려면 메뉴 자체를 빌드한 후 애플리케이션 코드에 연결해야 합니다.

메뉴 리소스를 만든 후에 응용 프로그램 코드 메뉴 리소스를 로드 하 여 사용 해야 [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) 를 메뉴를 표시 합니다. 사용자가 팝업 메뉴 바깥쪽을 선택 하 여 해제 된 또는 명령을 선정 되 면 해당 함수가 반환 됩니다. 사용자가 명령을 선택하는 경우 해당 명령 메시지가 핸들이 전달된 창으로 전송됩니다.

> [!NOTE]
> Microsoft Foundation 클래스 (MFC) 라이브러리 프로그램 및 ATL 프로그램을 사용 하 여 **코드 마법사** 코드에 메뉴 명령을 연결 합니다. 자세한 내용은 [이벤트를 추가](../ide/adding-an-event-visual-cpp.md) 하 고 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)합니다.

- 팝업 메뉴를 만들려면 빈 제목을 사용 하 여 메뉴를 만들고 제공 하지는 *캡션*합니다. 그런 다음 새 메뉴에 메뉴 명령을 추가, 임시 캡션 사용 하 여 빈 메뉴 제목 아래 첫 번째 메뉴 명령을 이동 *여기에 입력* 입력을 *캡션* 및 기타 정보입니다.

   팝업 메뉴에서 다른 모든 메뉴 명령에 대 한이 프로세스를 반복 하 고 메뉴 리소스를 저장 해야 합니다.

- 응용 프로그램에 팝업 메뉴 연결 하려면 WM_CONTEXTMENU에 대 한 메시지 처리기를 추가 합니다. 예를 들어 다음 메시지 처리기에 다음 코드를 추가 합니다.

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > 합니다 [CPoint](../atl-mfc-shared/reference/cpoint-class.md) 전달 된 메시지 처리기는 화면 좌표입니다.

일반적으로 작업는 **메뉴 편집기**, 메뉴 리소스 메뉴 모음으로 표시 됩니다. 그러나 프로그램이 실행되는 동안 응용 프로그램의 메뉴 모음에 메뉴 리소스가 추가될 수 있습니다.

- 팝업 메뉴로 메뉴 리소스를 보려면 메뉴를 마우스 오른쪽 단추로 클릭 하 고 선택 **팝업으로 보기**합니다.

   이 옵션 보기 설정 이며 메뉴를 수정 하지 않습니다.

> [!TIP]
> 메뉴 모음 보기로 다시 변경 하려면 **팝업으로 보기** 다시 합니다. 이 작업 확인 표시를 제거 하 고 메뉴 모음 보기를 반환 합니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[리소스 편집기](../windows/resource-editors.md)<br/>
[메뉴 명령](../windows/menu-command-properties.md)<br/>

<!--
[User-Interface Objects and Command IDs](../mfc/user-interface-objects-and-command-ids.md)<br/>
[Menus](../mfc/menus-mfc.md)<br/>
[Menus](https://msdn.microsoft.com/library/windows/desktop/ms646977.aspx)-->