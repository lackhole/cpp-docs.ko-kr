---
title: Visual Studio C++ 에서 코딩 기본 설정 지정
ms.description: Customize C++ formatting, colors, layout, line numbers, menus and more in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: 90c9f39135b90a2c5015861a78dd8760b9a8aeed
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686949"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>Visual Studio C++ 에서 코딩 기본 설정 지정

Visual Studio를 개인 C++ 설정 하 여 코딩 환경을 더 편리 하 고 생산적인 방식으로 pleasurable 수 있습니다. 메뉴와 도구 모음을 사용자 지정 하 고, 창 레이아웃을 정렬 하 고, 색 C++ 테마를 설정 하 고, 다양 한 ClangFormat 유형을 비롯 한 서식 지정 규칙을 지정 하 고, 사용자 지정 바로 가기 키를 만들 수 여러 컴퓨터에 대 한 기본 설정을 동기화 할 수 있으며, 여러 기본 설정 집합을 만들어 저장 하 고 동료와 공유할 수 있습니다. Visual Studio Marketplace에서 확장을 설치 하 여 추가 사용자 지정 동작을 제공할 수 있습니다. 이러한 옵션은 대부분 [Visual STUDIO IDE 개인 설정에](/visualstudio/ide/personalizing-the-visual-studio-ide)설명 되어 있습니다.

## <a name="arrange-window-layout"></a>창 레이아웃 정렬

Visual Studio 창 내에서 공간은 주 메뉴, 도구 모음, 코드 편집기 (또는 문서 창) 및 도구 창 (**솔루션 탐색기**, **오류 목록**등)으로 구분 됩니다. 일부 창은 동일한 위치에서 서로 겹칩니다. 예를 들어 **솔루션 탐색기**, **클래스 뷰**, **리소스 뷰**및 **소스 제어 탐색기** 모두 동일한 기본 위치를 공유 합니다. 프레임 맨 아래에 있는 탭을 클릭 하 여 두 항목 사이를 전환 합니다. 이러한 창 중 두 개 이상을 동시에 표시 하려면 제목 표시줄 중 하나를 새 위치로 끌어 놓기만 하면 됩니다. Visual Studio 주 창 테두리 중 하나에 도킹 하거나 부동으로 만들 수 있습니다. 다음 그림에서는 기본 위치에서 코드 편집기의 왼쪽에 있는 도킹 된 새 위치로 끌어 오는 프로세스의 **팀 탐색기** 창을 보여 줍니다. 파란색 음영 영역에는 마우스 단추를 놓을 때 창이 배치 되는 위치가 표시 됩니다.

![창 레이아웃 수정](media/window-layout-move-team-explorer.png)

문서 창에서 열려 있는 각 파일은 탭 프레임에 포함 되어 있습니다. 도구 창과 마찬가지로 이러한 탭을 고정 하거나 잠글 수 있습니다. 자세한 내용은 [Visual Studio에서 창 레이아웃 사용자 지정](/visualstudio/ide/customizing-window-layouts-in-visual-studio)을 참조하세요.

모든 도구 창을 숨기고 코드 편집기 창을 최대화 하려면 **Alt** + **Shift** + **enter** 키를 눌러 *전체 화면 모드*를 설정/해제 합니다.

## <a name="set-c-coding-styles-and-formatting"></a>코딩 C++ 스타일 및 서식 설정

**도구** > **옵션** > **텍스트 편집기** > **C/C++**  > **서식** (또는 형식)으로 이동 하 여 들여쓰기 및 중괄호와 같은 여러 개별 코드 서식 옵션을 지정할 수 있습니다. **Ctrl + Q** 를 누르고 "형식 지정"을 검색 합니다. 또는 [Clangformat](https://clang.llvm.org/docs/ClangFormat.html) 스타일 (또는 고유한 사용자 지정 clangformat 스타일) 중 하나를 지정할 수 있습니다.

![ClangFormat 옵션](media/clang-format-ide.png)

모든 서식 옵션에 대 한 자세한 내용은 [옵션, 텍스트 편집기, C/C++, 서식 지정](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting)을 참조 하세요.

## <a name="set-the-color-theme"></a>색 테마 설정

밝은 배경 또는 어두운 배경을 설정 하려면 **Ctrl + Q** 를 입력 하 고 "색 테마"를 검색 합니다. **도구** > **옵션** > **환경** 으로 이동 하 고 **색 테마**를 선택할 수도 있습니다.

![색 테마](media/tools-options-color-theme.png)

다음 이미지는 짙은 테마를 보여줍니다.

![어두운 테마](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>코드 색 지정 사용자 지정

Visual Studio 2019에서는 편집기에서 코드 요소의 색을 지정 하는 방법을 지정 하는 미리 정의 된 세 가지 *색 구성표* 를 선택할 수 있습니다. 테마를 선택 하려면 **도구** > **옵션** > **텍스트 편집기** > **C/C++**  > **보기로** 이동한 후 **색 구성표**를 선택 합니다.

![C++색 구성표](media/color-schemes.png)

**Visual Studio 2017** 색 구성표에서 대부분의 코드 요소는 간단 하 게 검은색입니다. **향상** 된 색 구성표에서 함수, 지역 변수, 매크로 및 기타 요소는 색이 있습니다. @No__t-0Enhanced (Globals 및 멤버) ** 체계, 전역 함수 및 변수는 클래스 멤버와 대조 되는 색으로 되어 있습니다. 기본 모드는 **향상** 되었으며 다음과 같습니다.

![향상 된 색 구성표](media/color-scheme-enhanced.png)

활성화 된 테마나 색 구성표에 관계 없이 **도구** > **옵션** > **환경** > **글꼴 및 색** (또는 형식 **)으로 이동 하 여 개별 코드 요소의 글꼴과 색을 사용자 지정할 수 있습니다. Ctrl + Q** 를 누르고 "Fonts"를 검색 합니다. C++ 옵션이 표시 될 때까지 표시 항목 목록을 아래로 스크롤합니다.

![C++글꼴 및 색 옵션](media/tools-options-cpp-colors.png)

여기서 설정한 색은 색 구성표에 대해 정의 된 값을 재정의 합니다. 색 구성표를 변경한 경우 색 구성표의 기본 색을 사용 하려는 경우에는 색을 **기본값으로** 다시 설정 해야 합니다.

## <a name="customize-the-toolbars"></a>도구 모음 사용자 지정

도구 모음은 메뉴 또는 바로 가기 키를 사용 하는 대신 마우스 클릭 한 번으로 명령을 실행 하는 편리한 방법을 제공 합니다. Visual Studio에는 표준 도구 모음 집합이 포함 되어 있습니다. 표준 C++ 개발의 경우 가장 유용한 도구 모음은 표준, 텍스트 편집기, 빌드, 디버그, 소스 제어 및 파일 비교를 사용할 수 있습니다. Windows 개발의 경우 대화 상자 편집기와 이미지 편집기는 대화 상자를 배치 하 고 아이콘을 편집 하는 데 유용 합니다.

도구 모음에 있는 아이콘을 마우스로 가리켜 해당 아이콘이 나타내는 명령을 확인 합니다.

![도구 모음 QuickInfo](media/toolbar-mouse-hover.png)

아래쪽 화살표를 클릭 하 여 명령을 추가 하거나 제거 하거나 사용자 지정 도구 모음을 만들 수 있습니다. 도구 모음을 새 위치로 이동 하려면 왼쪽의 점선 막대로 끌어 놓습니다.

![도구 모음 사용자 지정 또는 이동](media/toolbar-move-edit.png)을 선택합니다.

자세한 내용은 [방법: Visual Studio @ no__t에서 메뉴 및 도구 모음 사용자 지정-0

## <a name="show-or-hide-line-numbers"></a>줄 번호 표시 또는 숨기기

줄 번호가 편집기 창의 왼쪽에 표시 되는지 여부를 지정 하려면로 이동 하 여 **줄 번호**를 확인 하거나 검사를 취소 합니다.

![줄 번호](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>바로 가기 키 만들기

Visual Studio의 모든 명령은 Ctrl, Alt 및 Shift 키를 사용 하 여 다양 한 키 조합을 사용 하는 바로 가기 키를 사용 하 여 만들 수 있습니다. **도구** > **옵션** > **환경** > **키보드** 로 이동 하 여 바로 가기를 만들 수 있습니다. 또는 **Ctrl + Q** 를 입력 하 고 "바로 가기"를 검색 합니다. 자세한 내용은 [Visual Studio에서 바로 가기 키 식별 및 사용자 지정](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)을 참조 하세요.
