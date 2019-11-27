---
title: Visual Studio C++ 에서 코딩 기본 설정 지정
ms.description: Customize C++ formatting, colors, layout, line numbers, and menus in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: f1d222dc38720ea897cfbf2fb9fa0dd2727e7720
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816567"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>Visual Studio C++ 에서 코딩 기본 설정 지정

Visual Studio를 개인 C++ 설정 하 여 코딩 환경을 더 편리 하 고 생산적인 방식으로 pleasurable 수 있습니다. 다음을 할 수 있습니다.

- 메뉴와 도구 모음을 사용자 지정 합니다.
- 창 레이아웃을 정렬 합니다.
- 색 테마를 설정 합니다.
- 여러 C++ 스타일의 ClangFormat을 포함 하 여 서식 지정 규칙을 지정 합니다.
- 사용자 지정 바로 가기 키를 만듭니다.

여러 컴퓨터에 대 한 기본 설정을 동기화 할 수 있으며, 여러 기본 설정 집합을 만들어 저장 하 고 동료와 공유할 수 있습니다. Visual Studio Marketplace에서 확장을 설치 하 여 동작을 사용자 지정 하는 추가 옵션을 제공할 수 있습니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.

## <a name="arrange-window-layout"></a>창 레이아웃 정렬

Visual Studio 창 내에서 공간은 주 메뉴, 도구 모음, 코드 편집기 (또는 문서 창) 및 도구 창 (예: 솔루션 탐색기 및 오류 목록)으로 구분 됩니다. 일부 창은 동일한 위치에서 서로 겹칩니다. 예를 들어 솔루션 탐색기, 클래스 뷰, 리소스 뷰 및 소스 제어 탐색기 모두 동일한 기본 위치를 공유 합니다. 프레임 아래쪽의 탭을 선택 하 여 서로 전환 합니다. 이러한 창 중 두 개 이상을 동시에 표시 하려면 제목 표시줄 중 하나를 새 위치로 끌어 놓기만 하면 됩니다. Visual Studio 주 창 테두리 중 하나에 도킹 하거나 부동으로 만들 수 있습니다.

다음 스크린샷에서는 기본 위치에서 코드 편집기 왼쪽의 도킹 된 새 위치로 끄는 **팀 탐색기** 창을 보여 줍니다. 파란색 음영 영역에는 마우스 단추를 놓을 때 창이 배치 되는 위치가 표시 됩니다.

![레이아웃 변화가 강조 표시 된 Visual Studio 팀 탐색기 창의 스크린샷](media/window-layout-move-team-explorer.png)

문서 창에서 열려 있는 각 파일은 탭 프레임에 포함 되어 있습니다. 도구 창과 마찬가지로 이러한 탭을 고정 하거나 잠글 수 있습니다. 자세한 내용은 [Visual Studio에서 창 레이아웃 사용자 지정](/visualstudio/ide/customizing-window-layouts-in-visual-studio)을 참조하세요.

모든 도구 창을 숨기고 코드 편집기 창을 최대화 하려면 **Alt** + **shift** ** + enter 키를 눌러** *전체 화면 모드*를 설정/해제 합니다.

## <a name="set-c-coding-styles-and-formatting"></a>코딩 C++ 스타일 및 서식 설정

들여쓰기 및 중괄호 위치와 같은 여러 개별 코드 서식 옵션을 지정할 수 있습니다. 이렇게 하려면 **도구** > **옵션** > **텍스트 편집기** > **C/C++**  > **서식** (또는 **Ctrl + Q** 를 입력 하 고 "서식"을 검색)으로 이동 합니다. 또는 [Clangformat](https://clang.llvm.org/docs/ClangFormat.html) 스타일 (또는 고유한 사용자 지정 clangformat 스타일) 중 하나를 지정할 수 있습니다.

![ClangFormat 옵션의 스크린샷](media/clang-format-ide.png)

모든 서식 옵션에 대 한 자세한 내용은 [옵션, 텍스트 편집기, C/C++, 서식 지정](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting)을 참조 하세요.

## <a name="set-the-color-theme"></a>색 테마 설정

밝은 배경 또는 어두운 배경을 설정 하려면 **Ctrl + Q** 를 입력 하 고 "색 테마"를 검색 합니다. **도구** > **옵션** > **환경**으로 이동 하 고 **색 테마**를 선택 하 여 찾을 수도 있습니다.

![색 테마 스크린샷](media/tools-options-color-theme.png)

예를 들어 다음은 진한 테마입니다.

![어두운 색 테마가 있는 Visual Studio의 스크린샷](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>코드 색 지정 사용자 지정

Visual Studio 2019에서는 미리 정의 된 세 가지 *색 구성표*에서 선택할 수 있습니다. 편집기에서 코드 요소의 색을 지정 하는 방법을 지정 합니다. 테마를 선택 하려면 **도구** > **옵션** > **텍스트 편집기** > **C/C++**  > **보기로**이동한 후 **색 구성표**를 선택 합니다.

![고급 강조 C++ 표시 된 색 구성표 옵션의 스크린샷](media/color-schemes.png)

**Visual Studio 2017**색 구성표에서 대부분의 코드 요소는 간단 하 게 검은색입니다. **향상** 된 색 구성표에서 함수, 지역 변수, 매크로 및 기타 요소는 색이 있습니다. 향상 된 **(Globals 및 Members)** 스키마에서 전역 함수 및 변수는 클래스 멤버와 대조 되는 색으로 되어 있습니다. 기본 **모드는 다음과**같습니다.

![고급 색 구성표의 스크린샷](media/color-scheme-enhanced.png)

활성화 된 테마나 색 구성표에 관계 없이 개별 코드 요소의 글꼴 및 색을 사용자 지정할 수 있습니다. 이렇게 하려면 **도구** > **옵션** > **환경** > **글꼴 및 색** 으로 이동 합니다 (또는 **Ctrl + Q** 를 입력 하 고 "Fonts"를 검색). C++ 옵션이 표시 될 때까지 표시 항목 목록을 아래로 스크롤합니다.

![글꼴 및 C++ 색 옵션의 스크린샷](media/tools-options-cpp-colors.png)

여기서 설정한 색은 색 구성표에 대해 정의 된 값을 재정의 합니다. 색 구성표의 기본 색으로 돌아가려면 색을 **기본값으로**다시 설정 합니다.

## <a name="customize-the-toolbars"></a>도구 모음 사용자 지정

도구 모음은 메뉴 또는 바로 가기 키를 사용 하는 대신 한 번의 클릭으로 명령을 실행 하는 편리한 방법을 제공 합니다. Visual Studio에는 표준 도구 모음 집합이 포함 되어 있습니다. 표준 C++ 개발의 경우 가장 유용한 도구 모음은 표준, 텍스트 편집기, 빌드, 디버그, 소스 제어 및 파일 비교입니다. Windows 개발의 경우 대화 상자 편집기 및 이미지 편집기는 대화 상자를 배치 하 고 아이콘을 편집 하는 데 유용 합니다.

도구 모음에 있는 아이콘을 마우스로 가리켜 해당 아이콘이 나타내는 명령을 확인 합니다.

![가리키기에서 사용할 수 있는 명령 정보의 예를 포함 하는 도구 모음 아이콘의 스크린샷](media/toolbar-mouse-hover.png)

아래쪽 화살표를 선택 하 여 명령을 추가 또는 제거 하거나 사용자 지정 도구 모음을 만들 수 있습니다. 도구 모음을 새 위치로 이동 하려면 왼쪽의 점선 막대로 끕니다.

![아래쪽 화살표 및 점선 막대가 강조 표시 된 도구 모음의 스크린샷](media/toolbar-move-edit.png).

자세한 내용은 [방법: Visual Studio에서 메뉴 및 도구 모음 사용자 지정](/visualstudio/ide/how-to-customize-menus-and-toolbars-in-visual-studio)을 참조 하세요.

## <a name="show-or-hide-line-numbers"></a>줄 번호 표시 또는 숨기기

줄 번호가 편집기 창의 왼쪽에 표시 되는지 여부를 지정할 수 있습니다. **옵션**의 **C/C++** 에서 **일반**을 선택 합니다. **설정** 섹션에서 기본 설정에 따라 **줄 번호**를 선택 하거나 선택 취소 합니다.

![줄 번호가 강조 표시 된 일반 옵션의 스크린샷](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>바로 가기 키 만들기

Visual Studio의 많은 명령에는 Ctrl, Alt 및 Shift 키와 키 조합이 포함 된 *바로 가기*키가 있습니다. 이러한 바로 가기 키를 수정 하거나 Visual Studio에서 직접 새로 만들 수 있습니다. **도구** > **옵션** > **환경** > **키보드** 로 이동 하거나 **Ctrl + Q** 를 입력 하 고 "바로 가기"를 검색 합니다. 자세한 내용은 [Visual Studio에서 바로 가기 키 식별 및 사용자 지정](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)을 참조 하세요.
