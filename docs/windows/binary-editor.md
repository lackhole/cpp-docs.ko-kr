---
title: 바이너리 편집기 (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.binary.F1
- vc.editors.binary
helpviewer_keywords:
- editors, Binary
- resources [C++], editing
- resource editors [C++], Binary editor
- Binary editor
- binary data, editing
- resources [C++], opening for binary editing
- binary data
- hexadecimal bytes in binary data
- strings [C++], searching for
- file searches [C++]
- binary data, finding
- ASCII characters, finding in binary data
- custom resources [C++]
- data resources [C++]
- resources [C++], creating
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
ms.openlocfilehash: 832dbf711307b81527bcaff0d1e1b8138f208e46
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407047"
---
# <a name="binary-editor-c"></a>바이너리 편집기 (C++)

> [!CAUTION]
> 대화 상자, 이미지 또는 메뉴와 같은 리소스를 편집 합니다 **바이너리 편집기** 은 위험 합니다. 잘못된 편집으로 리소스가 손상되어 해당 네이티브 편집기에서 읽지 못하게 될 수 있습니다.

합니다 **바이너리 편집기** 16 진수 또는 ASCII 형식으로 바이너리 수준에서 모든 리소스를 편집할 수 있습니다. 또한 [찾기 명령](/visualstudio/ide/reference/find-command) 을 사용하여 ASCII 문자열 또는 16진수 바이트를 검색할 수도 있습니다. 사용 된 **바이너리 편집기** 사용자 지정 리소스 또는 리소스 형식이 Visual Studio 환경에서 지원 되지 않습니다에 변경 내용을 보거나 부 확인 해야 할 때만 합니다. 합니다 **바이너리 편집기** 를 Express 버전에서는 사용할 수 없습니다.

- 열려는 합니다 **바이너리 편집기** 메뉴에 새 파일을 이동 **파일** > **새로 만들기** > **파일**, 유형을 선택 파일을 편집 하 고 다음 드롭다운 화살표를 선택 합니다 **열려** 단추를 선택한 **연결** > **바이너리 편집기**합니다.

- 열려는 **바이너리 편집기** 기존 파일을 메뉴로 이동 **파일** > **엽니다** > **파일**을 선택 합니다 파일을 편집 하 고 다음 드롭다운 화살표를 선택 합니다 **열려** 단추를 선택한 **연결** > **바이너리 편집기**합니다.

   ![Binary Editor](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")<br/>
   에 표시 되는 대화 상자에 대 한 이진 데이터는 **바이너리 편집기**

에 특정 ASCII 값만 표시 됩니다는 **바이너리 편집기** (0x20 ~ 0x7E). 오른쪽 패널 ASCII 값 섹션에서 확장 된 문자 마침표로 표시 됩니다는 **바이너리 편집기**합니다. 인쇄 가능한 문자는 ASCII 값 32 ~ 126입니다.

> [!TIP]
> 사용 하는 동안 합니다 **바이너리 편집기**, 리소스별 명령의 바로 가기 메뉴를 표시할 단추로 경우가 많습니다. 사용할 수 있는 명령은 커서가 가리키는 내용에 따라 달라집니다. 예를 들어 가리키는 동안 마우스 오른쪽 단추로 클릭 합니다 **바이너리 편집기** 선택한 16 진수 값을 사용 하 여 바로 가기 메뉴에 표시 합니다 **잘라내기**, **복사**, 및 **붙여넣기** 명령입니다.

## <a name="how-to"></a>방법

합니다 **바이너리 편집기** 있습니다.

### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>이진 편집을 위해 Windows 데스크톱 리소스를 열려면

1. [리소스 뷰](how-to-create-a-resource-script-file.md#create-resources)에서 편집할 특정 리소스 파일을 선택합니다.

1. 리소스를 마우스 오른쪽 단추로 누르고 **이진 데이터 열기**합니다.

> [!NOTE]
> 사용 하는 경우는 **리소스 뷰** 리소스를 열려면 Visual Studio에서 인식 하지 못하는 되는 형식의 창 예: RCDATA 또는 사용자 지정 리소스는 리소스는에서 자동으로 열립니다 합니다 **바이너리 편집기**합니다.

### <a name="to-open-a-managed-resource-for-binary-editing"></a>이진 편집을 위해 관리되는 리소스를 열려면

1. **솔루션 탐색기**, 편집할 특정 리소스 파일을 선택 합니다.

1. 리소스를 마우스 오른쪽 단추로 누르고 **연결 프로그램**합니다.

1. **연결 프로그램** 대화 상자에서 **바이너리 편집기**를 선택합니다.

> [!NOTE]
> 사용할 수는 [이미지 편집기](../windows/image-editor-for-icons.md) 하며 **바이너리 편집기** 관리 되는 프로젝트에서에서 리소스 파일을 사용 하 합니다. 편집할 관리되는 리소스는 연결된 리소스여야 합니다. Visual Studio 리소스 편집기에서는 포함된 리소스를 편집할 수 없습니다.

### <a name="to-edit-a-resource"></a>리소스를 편집하려면

사용 하려는 경우는 **바이너리 편집기** 이미 다른 편집기 창에서 편집 중인 리소스에는 다른 먼저 편집기 창을 닫아야 합니다.

1. 편집 하려는 바이트를 선택 합니다.

   합니다 **탭** 키의 16 진수 및 ASCII 섹션 간에 포커스를 이동 합니다 **바이너리 편집기**합니다. 사용할 수는 **Page Up** 하 고 **Page Down** 한 번에 하나의 리소스 화면을 통해 이동 하는 키입니다.

1. 새 값을 입력합니다.

   값이 16 진수 및 ASCII 섹션 모두에서 즉시 변경 되 고 줄에서 다음 값으로 포커스가 이동 합니다.

> [!NOTE]
> 합니다 **바이너리 편집기** 편집기를 닫을 때 자동으로 변경 내용을 적용 합니다.

### <a name="to-find-binary-data"></a>이진 데이터를 찾으려면

ASCII 문자열 또는 16 진수 바이트를 검색할 수 있습니다. 예를 들어 찾으려는 *Hello*, 문자열에 대 한 검색할 수 있습니다 *Hello* 또는 16 진수 값 *48 65 6C 6c 6F*합니다.

1. 메뉴로 이동 **편집할** > [찾을](/visualstudio/ide/reference/find-command)합니다.

1. 에 **찾을 내용** 상자, 드롭 다운 목록에서 이전에 검색 문자열을 선택 하거나 찾으려는 데이터를 입력 합니다.

1. 중 하나를 선택 합니다 **찾을** 선택한 옵션 **다음 찾기**합니다.

### <a name="to-create-a-new-custom-or-data-resource"></a>새 사용자 지정 또는 데이터 리소스를 만들려면

프로젝트를 마우스 오른쪽 단추로 클릭 하 여 기본 리소스 스크립트 (.rc) 파일 구문을 사용 하 여 별도 파일에 다음 파일을 포함 하는 리소스를 배치 하 여 새 사용자 지정 또는 데이터 리소스를 만들 수 있습니다 **솔루션 탐색기** 를선택하고 **리소스 내용**합니다.

1. 사용자 지정 또는 데이터 리소스가 포함된[.rc 파일을 만듭니다](../windows/how-to-create-a-resource-script-file.md) .

   null로 끝나는 따옴표가 붙은 문자열이나 10진수, 16진수 또는 8진수 형식의 정수로 .rc 파일의 사용자 지정 데이터를 입력할 수 있습니다.

1. **솔루션 탐색기**, 프로젝트의.rc 파일을 마우스 오른쪽 단추로 **리소스 내용**합니다.

1. 에 **컴파일 시간 지시문** 상자에 입력을 `#include` 예를 들어 사용자 지정 리소스를 포함 하는 파일의 이름을 제공 하는 문:

    ```cpp
    #include mydata.rc
    ```

   입력한 구문 및 맞춤법이 정확한지 확인합니다. 콘텐츠를 **컴파일 시간 지시문** 상자 입력 한 대로 정확 하 게 리소스 스크립트 파일에 삽입 됩니다.

1. 선택 **확인** 변경 내용을 기록 합니다.

사용자 지정 리소스를 만드는 또 다른 방법은 사용자 지정 리소스와 외부 파일 가져오기, 참조를 [방법: 리소스 관리](../windows/how-to-import-and-export-resources.md)합니다.

> [!NOTE]
> 새 사용자 지정 또는 데이터 리소스를 만들려면 Win32 필요 합니다.

## <a name="requirements"></a>요구 사항

없음

## <a name="see-also"></a>참고자료

[리소스 편집기](../windows/resource-editors.md)