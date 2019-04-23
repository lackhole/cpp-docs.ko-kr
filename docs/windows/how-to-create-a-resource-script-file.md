---
title: '방법: 리소스를 만듭니다 (C++)'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.resource
- vc.resvw.add.MFC
- vs.resourceview.F1
- vc.editors.insertresource
- vc.editors.newcustomresource
helpviewer_keywords:
- rc files [C++], creating
- .rc files [C++], creating
- resource script files [C++], creating
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
- resource script files [C++], opening in text format
- .rc files [C++], opening in text format
- rc files [C++], opening in text format
- rc files [C++], adding MFC support
- .rc files [C++], adding MFC support
- MFC, adding support to resource scripts files
- resource script files [C++], adding MFC support
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
- Resource View window
- resources [C++], adding
- Add Resource dialog box [C++]
- Custom Resource Type dialog box [C++]
- language-specific template files [C++]
- resource templates
- rct files [C++]
- templates, resource templates
- resources [C++], templates
- .rct files [C++]
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
ms.openlocfilehash: c22df99240c0fa076124e33224a4f6f4ab9a957e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028524"
---
# <a name="how-to-create-resources-c"></a>방법: 리소스를 만듭니다 (C++)

하 여 프로젝트에 대 한 리소스를 만들 수 있습니다.

- 리소스 스크립트 파일을 사용합니다.

   > [!NOTE]
   > 이 단계는 리소스를 추가 하기 전에 필요 합니다.

- 프로젝트에 리소스를 추가 하 고 사용 하 여 **리소스 뷰**합니다.

- 사용자 지정된 리소스를 만드는 리소스 템플릿 사용

## <a name="use-resource-script-files"></a>리소스 스크립트 파일 사용

만들고 프로젝트에 새 리소스를 추가 하기 전에 먼저 리소스 스크립트 (.rc) 파일을 만들어야 합니다.

> [!NOTE]
> Visual Studio IDE에 로드 하는 기존 프로젝트에만 리소스 스크립트 파일을 추가할 수 있습니다. 리소스 템플릿 (.rct) 파일을 언제 든 지 만들 수 있습니다. 하지만 프로젝트 외부 독립 실행형 리소스 스크립트를 만들 수 없습니다.

### <a name="to-create-a-resource-script-file"></a>리소스 스크립트 파일을 만들려면

1. 기존 프로젝트 폴더에 포커스를 둡니다 **솔루션 탐색기**, 예를 들어 *MyProject*합니다.

   > [!NOTE]
   > 프로젝트 폴더의 솔루션 폴더와 혼동 하지 마세요 **솔루션 탐색기**합니다. 에 포커스를 둔 경우 합니다 **솔루션** 폴더를 동일 하지 않아도 **새 항목 추가** 선택 합니다.

1. 메뉴에서로 이동 **프로젝트** > **새 항목 추가**합니다.

1. 선택 합니다 **시각적 C++**  폴더 선택 **리소스 파일 (.rc)** 오른쪽 창에서.

1. 리소스 스크립트 파일에 대 한 이름을 제공 합니다 **이름** 텍스트 상자 **열기**합니다.

### <a name="to-open-a-resource-script-file"></a>리소스 스크립트 파일을 열려면

프로젝트를 열지 않고도 리소스 스크립트 파일에 리소스를 볼 수 있습니다. 스크립트 파일이 아닌 사이트별로 문서 창에 열립니다는 **리소스 뷰**합니다.

> [!NOTE]
> 일부 명령은 파일이 열린된 독립 실행형인지, 첫 번째 프로젝트를 로드 하지 않고 프로젝트 외부에서 즉 사용할 수 있습니다. 예를 들어 사용 하 여 **다른 이름으로 저장** 명령 및 다른 형식 또는 파일 이름으로 파일 저장 파일 열린된 독립 실행형 이어야 합니다.

- 이동할 프로젝트 외부에서 리소스 스크립트 파일로 메뉴에서를 열려면 **파일** > **엽니다**를 선택 하 고 **파일**합니다. 로 리소스 스크립트 파일로 이동 하 고, 파일을 선택 하 고, 선택 **열려**합니다.

    > [!NOTE]
    > 리소스를 열려면 리소스 편집기를 사용 하지 않고 프로젝트의 리소스 스크립트 파일의 내용을 볼 수 있습니다. 예를 들어 리소스 파일에서 각 대화 상자를 별도로 열지 않고 모든 대화 상자에서 문자열을 검색하려고 할 수 있습니다. 텍스트 형식으로 포함 된 모든 리소스 보기 및 텍스트 편집기를 지 원하는 전역 작업을 완료 하려면 리소스 파일을 쉽게 열 수 있습니다.
    >
    > 텍스트 형식으로 리소스 스크립트 파일을 열려면의 오른쪽에 드롭다운 화살표를 사용 합니다 **엽니다** 단추 위의 단계에서 선택한 **프로그램**합니다. 선택 **소스 코드 (텍스트) 편집기** 들어오고를 **형식으로 열기** 드롭 다운 목록에서 **텍스트** 리소스에서 열어서 합니다 **소스 코드** 편집기입니다.

- 스크립트를 여러 리소스를 열려면 열려는, 예를 들어, 각 파일에 대 한 위의 동일한 단계를 수행 *Source1.rc* 하 고 *Source2.rc*합니다. 그런 다음 별도 문서 창에서.rc 파일을 모두 열려 있는 경우 사용 합니다 **창을** 메뉴 또는 파일 중 하나를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 가로 탭 그룹** 또는 **새 세로 탭 그룹** . Windows는 동시에 볼 수 있도록 이제 바둑판식으로 배열 됩니다.

> [!TIP]
> .rc 파일을 마우스 오른쪽 단추로 클릭 하 여 리소스 스크립트 파일을 열 수 있습니다 **솔루션 탐색기**을 선택 하면 **엽니다** 선택 하 고 **소스 코드 (텍스트) 편집기**합니다.

Windows를 사용 하 여 Microsoft Foundation 클래스 (MFC) 응용 프로그램을 작성 하는 경우는 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md), 리소스 스크립트 (.rc) 파일을 비롯 한 파일의 기본 집합을 생성 하는 마법사) MFC의 핵심 기능을 포함 하는 합니다. 그러나 MFC 기반 하지 않는 Windows 응용 프로그램에 대 한.rc 파일을 편집 하는 경우 MFC 관련 기능이 사용할 수 없습니다. 여기에 코드 마법사, 메뉴 프롬프트 문자열, 콤보 상자 컨트롤 및 ActiveX 컨트롤 호스팅에 대 한 콘텐츠를 나열 합니다.

- 에 리소스 스크립트 파일을 열고 MFC 지원 추가 **리소스 뷰**, 리소스 폴더 (예를 들어 *: MFC.rc*). 그런 다음 합니다 [속성 창](/visualstudio/ide/reference/properties-window)설정 **MFC Mode** 에 **True**합니다.

  > [!NOTE]
  > 설정 외에도 **MFC Mode**,.rc 파일에는 MFC 프로젝트의 일부 여야 합니다. 설정만 **MFC Mode** 하 **True** 는.rc에서 Win32 프로젝트에 있는 파일을 제공 하지 않습니다 MFC 기능입니다.

## <a name="create-resources"></a>리소스 만들기

리소스는 서식 파일에 기반 하지 않는 리소스를 의미 하는 새 기본 리소스 또는 템플릿으로 패턴화 된 리소스로 만들 수 있습니다.

사용 된 **리소스 뷰** 창에 프로젝트에 포함 된 리소스 파일을 표시 합니다. 예를 들어, 최상위 폴더를 확장 *: Project1.rc*, 해당 파일 내에서 리소스 종류를 보여 줍니다. 해당 종류의 개별 리소스를 표시 하려면 각 리소스 종류를 확장 합니다.

> [!TIP]
> 열려는 합니다 **리소스 뷰** 메뉴로 이동 창 **보기** > **리소스 뷰** 누르거나 **Ctrl** +  **Shift**+**E**합니다.

마우스 오른쪽 단추 클릭을 사용할 수도 있습니다는 **리소스 뷰** 창을 도킹 하 고 창의 도킹을 해제 하려면 제목 표시줄을 두 번 클릭 또는 명령의 바로 가기 메뉴를 시작 합니다. 창의 동작을 제어 하는 명령에 대 한 제목 표시줄을 마우스 오른쪽 단추로 클릭 합니다. 자세한 내용은 [Windows 관리](/visualstudio/ide/customizing-window-layouts-in-visual-studio)합니다.

**리소스 뷰** windows 포함 합니다 **리소스 추가** 리소스를 추가 하려면 다음 속성을 사용 하 여 대화 상자를 C++ Windows 데스크톱 응용 프로그램 프로젝트:

| 속성 | 설명 |
|---|---|
| **리소스 종류** | 만들려는 리소스의 종류를 지정 합니다.<br/><br/>커서와 대화 상자 리소스 범주에 있는 추가 리소스를 확장할 수 있습니다 *... \Microsoft visual Studio \<버전\>\VC\VCResourceTemplates\\< LCID\>\mfc.rct*합니다. .Rct 파일을 추가 해야 할 경우 여기에 해당 또는 다른 지정 [경로가 포함](../windows/how-to-specify-include-directories-for-resources.md)합니다. 트리 컨트롤의 최상위 수준에서 표시 하는 리소스는 Visual Studio에서 제공 되는 기본 리소스입니다. .Rct 파일의 리소스는 해당 범주의 두 번째 수준에 나타납니다. 추가할 수 있습니다.rct 파일의 수는 미리 설정 된 제한은 없습니다.<br/><br/> |
| **새로 만들기** | 선택한 형식을 기반으로 리소스 만들기를 **리소스 종류** 상자 하 고 적절 한 편집기에서 리소스를 엽니다.<br/><br/>예를 들어 대화 상자 리소스를 만드는 경우 열릴 리소스에는 [대화 상자 편집기](../windows/dialog-editor.md)합니다. |
| **Import** | 엽니다는 **가져올** 현재 프로젝트로 가져올 리소스 이동 대화 상자.<br/><br/>비트맵, 아이콘, 커서를 가져올 수 있습니다 HTML, 사운드 (합니다. WAV) 또는 사용자 지정 리소스 파일입니다. |
| **사용자 지정** | 엽니다는 **새 사용자 지정 리소스** 대화 상자 사용자 지정 리소스를 만듭니다.<br/><br/>또한를 **리소스 종류** 사용자 지정 리소스 종류의 이름을 입력할 텍스트 상자를 제공 하는 속성입니다. Visual C++ 자동으로 종료 하면 이름을 대문자로 시작 합니다. 사용자 지정 리소스만 편집할 수는 [바이너리 편집기](../windows/binary-editor.md)합니다. |

새 리소스를 만들면 Visual C++은 `IDD_Dialog1`과 같은 고유 이름을 할당합니다. 연결된 된 리소스 편집기에서 또는 리소스 속성을 편집 하 여이 리소스 ID를 사용자 지정할 수 있습니다 합니다 [속성 창](/visualstudio/ide/reference/properties-window)합니다.

> [!NOTE]
> 리소스 이름 또는 Visual Studio에서 예약 된 ID를 지정 하지 마세요. 예약 된 이름이 `DESIGNINFO`, `HWB`, 및 `TEXTINCLUDE`, 예약된 ID 이며 `255`합니다.

### <a name="to-create-a-resource"></a>리소스를 만들려면

- **리소스 뷰**.rc 파일을 선택한 후 사용 하 여 **편집** > **리소스 추가** 프로젝트에 추가할 리소스 형식을 선택 합니다.

   > [!TIP]
   > .rc 파일을 마우스 오른쪽 단추로 클릭 **리소스 뷰** 선택한 **리소스 추가** 바로 가기 메뉴에서.

- **솔루션 탐색기**프로젝트 폴더를 마우스 오른쪽 단추로 클릭, 선택 **추가** > **리소스 추가** 프로젝트에 추가할 리소스 형식을 선택 합니다.

   > [!NOTE]
   > 프로젝트에.rc 파일이 없는 경우이 단계에서는 하나 만듭니다. 그런 다음 이 단계를 반복하여 새.rc 파일에 특정 리소스 형식을 추가할 수 있습니다.

- [클래스 뷰](/visualstudio/ide/viewing-the-structure-of-code)클래스를 마우스 오른쪽 단추로 클릭, 선택 **추가** > **리소스 추가** 프로젝트에 추가할 리소스 형식을 선택 합니다.

- 메뉴를 사용 하 여 **프로젝트** > **리소스 추가**합니다.

## <a name="use-resource-templates"></a>리소스 템플릿 사용

리소스 템플릿은.rct 파일로 저장 한 사용자 지정된 리소스입니다. 리소스 템플릿 리소스를 만들기 위한 시작 지점으로 사용 됩니다. 리소스 템플릿 리소스 추가 또는 표준 컨트롤과 같은 기능을 공유 하거나 요소를 반복 하는 리소스 그룹을 개발 시간을 저장 합니다. 예를 들어 여러 대화 상자에 회사 로고 아이콘을 사용 하 여 도움말 단추를 포함 하려는 경우 새 대화 상자 템플릿을 만들고 도움말 단추 및 로고를 사용 하 여 사용자 지정 합니다.

리소스 템플릿을 사용자 지정 후의 변경 사항을 저장할 템플릿 폴더 또는 포함 경로에 지정 된 위치의 리소스 형식에 새 리소스 템플릿이 표시 되도록 합니다 **리소스 추가** 대화 상자. 이제 필요에 따라 새 리소스 템플릿을 만큼 사용할 수 있습니다.

> [!NOTE]
> 리소스 편집기에서 자동으로 고유한 리소스 ID를 제공합니다. 수정할 수는 [리소스 속성](../windows/changing-the-properties-of-a-resource.md) 필요에 따라 합니다.

> [!NOTE]
> 주 템플릿 디렉터리의 하위 디렉터리에 언어별 템플릿 파일을 배치 합니다. 영어 전용 템플릿 파일을 이동 하는 예를 들어 *... \\< 리소스 템플릿 디렉터리\>\1033*합니다.
>
> Visual Studio에서 새.rct 파일을 검색 *Visual Studio \Program Files\Microsoft \<버전\>\VC\VCResourceTemplates*하십시오 *\Program Files\Microsoft Visual Studio \< 버전 > \VC\VCResourceTemplates\\< LCID\>*  (예: LCID 1033 영어), 또는 아무 곳 이나 합니다 [포함 경로](../windows/how-to-specify-include-directories-for-resources.md)합니다. 다른 위치에.rct 파일을 저장 하려는 경우에 포함 경로에 위치를 추가 해야 합니다.

### <a name="to-create-and-use-a-resource-template"></a>만들고 리소스 템플릿을 사용 하 여

1. **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 **추가** > **새 항목 추가**합니다.

1. 에 **템플릿:** 창 **리소스 템플릿 파일 (.rct)** 합니다.

1. 새 이름 및 위치를 제공 *.rct* 파일을 선택 **오픈**합니다.

   새 *.rct* 파일을 프로젝트에 추가 되 고 나타나는 **솔루션 탐색기** 아래 합니다 **리소스** 폴더입니다.

1. 두 번 클릭 합니다 *.rct* 문서 창에서 열려는 파일입니다. 리소스를 추가 하려면 문서 창에서 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **리소스 추가**합니다.

   추가 리소스를 사용자 지정 하 고 저장 합니다 *.rct* 파일입니다.

1. 에 **리소스 뷰** 창 마우스 오른쪽 단추로 클릭 합니다 *.rc* 파일을 선택 **리소스 추가**합니다.

1. 더하기 기호 (**+**) 리소스 노드를 확장 하 고 해당 리소스에 대 한 사용 가능한 템플릿을 보려면 리소스 옆에 있는 합니다.

1. 사용할 템플릿을 두 번 클릭합니다.

   리소스 편집기에서 필요에 따라 추가 리소스를 수정할 수 있습니다.

### <a name="to-convert-an-existing-resource-file-to-a-template"></a>기존 리소스 파일을 템플릿으로 변환 하려면

이동할 리소스 스크립트 파일로 메뉴에서 열기 **파일** > **저장 \< *filename*>으로**입니다. 위치를 지정 하 고 선택 **확인**합니다.

## <a name="requirements"></a>요구 사항

Win32

## <a name="see-also"></a>참고자료

[리소스 파일](../windows/resource-files-visual-studio.md)<br/>
[방법: 리소스 관리](../windows/how-to-copy-resources.md)<br/>
[방법: 컴파일 시간에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)<br/>