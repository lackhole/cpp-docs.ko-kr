---
title: '방법: 대화 상자를 만들려면 (C++)'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog
helpviewer_keywords:
- dialog boxes [C++], creating
- Dialog Editor [C++], creating dialog boxes
- modal dialog boxes [C++], logon screens
- logon screens
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 303de801-c4f8-42e1-b622-353f6423f688
ms.openlocfilehash: 28ed6c8be262e0446b828cfa3e6e9fe2ba53672a
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344216"
---
# <a name="how-to-create-a-dialog-box-c"></a>방법: 대화 상자를 만들려면 (C++)

크기와 위치는 C++ 대화 상자, 위치 및 안에 있는 컨트롤의 크기 대화 단위로 측정 됩니다. 개별 컨트롤 및 대화 상자에 대 한 값은 Visual Studio 상태를 선택 하면 표시줄의 오른쪽 아래에 나타납니다.

> [!NOTE]
> 참조 프로젝트에.rc 파일이 없으면 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)합니다.

## <a name="how-to"></a>방법

합니다 **대화 상자 편집기** 있습니다.

### <a name="to-create-a-new-dialog-box"></a>새 대화 상자를 만들려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)를 마우스 오른쪽 단추로 클릭 하 *.rc* 파일을 선택 **리소스 추가**합니다.

1. 에 **리소스 추가** 대화 상자에서 **대화** 에 **리소스 종류** 목록에서 선택한 **새로 만들기**합니다.

   더하기 기호 ( **+** ) 옆에 표시 되는 **대화** 리소스 유형에 의미는 대화 상자 템플릿을 사용할 수 있습니다. 템플릿의 목록을 확장 하는 템플릿을 선택 하 고 선택 하려면 더하기 기호 **새로 만들기**합니다.

   새 대화 상자에서 열립니다는 **대화 상자 편집기**합니다.

편집 하기 위한 대화 상자 편집기에서 기존 대화 상자를 열 수 있습니다.

### <a name="to-create-a-dialog-box-that-a-user-cant-exit"></a>사용자가 종료할 수 없는 대화 상자를 만들려면

사용자가 종료할 수 없는 런타임 대화 상자를 만들 수 있습니다. 이 종류의 대화 상자는 로그온에 유용하며, 애플리케이션 또는 문서를 잠그는 데에도 유용합니다.

1. 대화 상자의 **속성** 창에서 **시스템 메뉴** 속성을 **false**로 설정합니다.

   이 설정은 대화 상자의 시스템 메뉴를 사용 하지 않도록 설정 하 고 **닫기** 단추입니다.

1. 대화 상자 폼에서 **취소** 및 **확인** 단추를 삭제합니다.

   런타임 시 사용자는 이러한 특징이 있는 모달 대화 상자를 종료할 수 없습니다.

테스트 대화 상자는 검색 될 때 대화 상자의 이러한 종류의 테스트를 사용 하려면 **Esc** 눌러져 있습니다. **Esc** VK_ESCAPE 가상 키라고도 하는 것이 라고도 합니다. 런타임에 동작 대화 상자는 디자인 하는 방법에 관계 없이 키를 눌러 테스트 모드를 종료할 수 있습니다 **Esc**합니다.

> [!NOTE]
> MFC 응용 프로그램에 대 한 사용자가 종료할 수 없습니다. 대화 상자를 만들려면 재정의 해야의 기본 동작 `OnOK` 하 고 `OnCancel` 키를 눌러 대화 상자를 닫을 여전히 수 연결된 단추를 삭제 하는 경우에 하기 때문에  **입력** 나 **Esc**합니다.

### <a name="to-specify-the-location-and-size-of-a-dialog-box"></a>대화 상자의 크기와 위치를 지정 하려면

설정할 수 있는 속성을 가지는 [속성 창](/visualstudio/ide/reference/properties-window) 지정 대화 상자 화면 표시 됩니다.

- 부울 **Center** 속성입니다.

   값을 설정 하면 **True**, 대화 상자 화면 중앙에 항상 표시 됩니다. 이 속성을 설정 하는 경우 **False**를 설정할 수 있습니다 합니다 **XPos** 하 고 **YPos** 속성.

- 합니다 **XPos** 하 고 **YPos** 화면 위치를 명시적으로 정의 하는 데 사용 되는 속성 대화 상자가 나타납니다.

   이러한 위치 속성은로 정의 된 보기 영역의 왼쪽 위 모서리에서 오프셋된 값 `{X=0, Y=0}`합니다.

- 합니다 **Absolute Align** 위치에 영향을 주는 속성입니다.

   하는 경우 **True**, 좌표는 화면을 기준으로 합니다. 하는 경우 **False**, 좌표가 대화 소유자 창을 기준으로 합니다.

### <a name="to-test-a-dialog-box"></a>대화 상자를 테스트하려면

대화 상자를 디자인할 때 프로그램을 컴파일하지 않고 런타임에 동작을 시뮬레이션 및 테스트할 수 있습니다. 이 모드에서 다음 작업을 수행할 수 있습니다.

- 텍스트 입력, 콤보 상자 목록에서 선택, 옵션 켜기 또는 끄기, 명령 선택

- 탭 순서 테스트

- 라디오 단추 또는 확인란과 같은 컨트롤의 그룹화 테스트

- 대화 상자의 컨트롤에 대한 바로가기 키 테스트

> [!NOTE]
> 연결 마법사를 사용 하 여 대화 상자 코드에는 시뮬레이션에 포함 되지 않습니다.

대화 상자를 테스트할 때는 일반적으로 주 프로그램 창을 기준으로 상대적인 위치에 표시됩니다. 대화 상자를 설정한 경우 **Absolute Align** 속성을 **True**를 화면의 왼쪽 위 모퉁이 기준으로 하는 위치에 있는 대화 상자에 표시 됩니다.

1. 경우는 **대화 상자 편집기** 가 활성 창 메뉴로 이동 **형식** > **테스트 대화 상자**합니다.

1. 시뮬레이션을 종료 하려면 키를 누릅니다 **Esc** 하거나 선택 합니다 **닫기** 테스트 하는 대화 상자에서 단추입니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[대화 상자 편집기](../windows/dialog-editor.md)<br/>
[방법: 대화 상자 컨트롤 관리](../windows/controls-in-dialog-boxes.md)<br/>