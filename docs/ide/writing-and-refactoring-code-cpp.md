---
title: 코드 작성 및 리팩터링(C++)
description: Visual Studio의 C++ 코드 편집기를 사용하여 코드를 서식 지정, 탐색, 이해 및 리팩터링합니다.
ms.date: 05/14/2019
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
ms.openlocfilehash: 04f738cd6fdd456c432c334df42f37339e7fa49e
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "66182633"
---
# <a name="writing-and-refactoring-code-c"></a>코드 작성 및 리팩터링(C++)

C++ 코드 편집기 및 Visual Studio IDE에서는 많은 코딩 보조 기능을 제공합니다. 일부는 C++에 고유하고, 일부는 기본적으로 모든 Visual Studio 언어에서 동일합니다. 공유 기능에 대한 자세한 내용은 [코드 및 텍스트 편집기에서 코드 작성](/visualstudio/ide/writing-code-in-the-code-and-text-editor)을 참조하세요. C++ 관련 기능을 사용하고 구성하기 위한 옵션은 **도구 &#124; 옵션 &#124; 텍스트 편집기 &#124; C/C++** 에 있습니다. 설정하려는 옵션을 선택한 후 대화 상자에 초점이 맞춰져 있을 때 **F1** 키를 누르면 추가 도움말을 확인할 수 있습니다. 일반적인 코드 서식 지정 옵션의 경우 **빠른 실행**에 `Editor C++`을 입력합니다.

향후 버전의 Visual Studio에 포함될 수도 포함되지 않을 수 있는 실험적 기능은 [텍스트 편집기 C++ 실험적](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) 대화 상자에 있습니다. Visual Studio 2017의 이 대화 상자에서 **예측 IntelliSense**를 사용하도록 설정할 수 있습니다.

## <a name="adding-new-files"></a>새 파일 추가하는 중

새 파일을 프로젝트에 추가하려면 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **추가 &#124; 새로 만들기**를 선택합니다.

## <a name="formatting-options"></a>서식 지정 옵션

들여쓰기, 중괄호 완성 및 색 지정과 같은 서식 지정 옵션을 설정하려면 **빠른 실행** 창에 “C++ Formatting”을 입력합니다. Visual Studio 2017 버전 15.7 이상은 ClangFormat을 지원합니다. **도구 &#124; 옵션 &#124; 텍스트 편집기 &#124; C/C++ &#124; 서식 지정** 아래 [C/C++ 서식 지정 속성 페이지](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting)에서 구성할 수 있습니다.

![C++ 서식 지정 옵션](media/cpp-formatting-options.png)

## <a name="intellisense"></a>IntelliSense

IntelliSense는 멤버, 형식 및 함수 오버로드에 대한 인라인 정보를 제공하는 기능 집합의 이름입니다. 다음 그림에서는 입력할 때 표시되는 멤버 목록 드롭다운을 보여 줍니다. tab 키를 눌러 선택한 항목 텍스트를 코드 파일에 입력할 수 있습니다.

![C&#43; &#43; 멤버 목록 드롭다운](../ide/media/vs2015_cpp_statement_completion.png "vs2015_cpp_statement_completion")

자세한 내용은 [Visual C++ IntelliSense](/visualstudio/ide/visual-cpp-intellisense)를 참조하세요.

## <a name="insert-snippets"></a>코드 조각 삽입

코드 조각은 소스 코드의 미리 정의된 조각입니다. 단일 지점이나 선택한 텍스트를 마우스 오른쪽 단추로 클릭하여 코드 조각을 삽입하거나 선택한 텍스트를 코드 조각으로 둘러쌉니다. 다음 그림에서는 선택한 문을 for 루프로 둘러싸는 세 단계를 보여 줍니다. 최종 이미지의 노란색 강조 표시는 tab 키를 사용하여 액세스하는 편집 가능한 필드입니다. 자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.

![Visual C&#43; &#43; 코드 조각 아래로 삽입&#45;down](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

## <a name="add-class"></a>클래스 추가

클래스 마법사를 사용하여 **프로젝트** 메뉴에서 새 클래스를 추가합니다.

![Visual C&#43;&#43;에서 새 클래스 추가](../ide/media/vs2015_cpp_add_class.png "vs2015_cpp_add_class")

기존 클래스를 수정하거나 검사하려면 클래스 마법사를 사용할 수도 있습니다.

![Visual C&#43;&#43; 마법사 클래스](../ide/media/vs2015_cpp_class_wizard.png "vs2015_cpp_class_wizard")

자세한 내용은 [코드 마법사로 기능 추가(C++)](../ide/adding-functionality-with-code-wizards-cpp.md)를 참조하세요.

## <a name="refactoring"></a>리팩터링

리팩터링은 빠른 작업 상황에 맞는 메뉴 아래에서 또는 편집기에서 [전구](/visualstudio/ide/perform-quick-actions-with-light-bulbs)를 클릭하여 사용할 수 있습니다.  일부는 **편집 > 리팩터링** 메뉴에 있습니다.  이러한 기능에는 다음이 포함됩니다.

* [이름 바꾸기](refactoring/rename.md)
* [함수 추출](refactoring/extract-function.md)
* [순수 가상 구현](refactoring/implement-pure-virtuals.md)
* [선언/정의 만들기](refactoring/create-declaration-definition.md)
* [함수 정의 이동](refactoring/move-definition-location.md)
* [원시 문자열 리터럴로 변환](refactoring/convert-to-raw-string-literal.md)
* [시그니처 변경](refactoring/change-signature.md)

## <a name="navigate-and-understand"></a>탐색 및 이해

Visual C++는 많은 코드 탐색 기능을 다른 언어와 공유합니다. 자세한 내용은 [코드 탐색](/visualstudio/ide/navigating-code) 및 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조하세요.

## <a name="quickinfo"></a>QuickInfo

변수를 마우스로 가리켜 형식 정보를 확인합니다.

![Visual C&#43;&#43; 요약 정보](../ide/media/vs2015_cpp_quickinfo.png "vs2015_cpp_quickInfo")

## <a name="open-document-navigate-to-header"></a>문서 열기(헤더로 이동)

`#include` 지시문에서 헤더 이름을 마우스 오른쪽 단추로 클릭하고 헤더 파일을 엽니다.

![Visual C&#43;&#43; 문서 메뉴 옵션 열기](../ide/media/vs2015_cpp_open_document.png "vs2015_cpp_open_document")

## <a name="peek-definition"></a>정의 피킹(Peeking)

변수 또는 함수 선언을 마우스로 가리키고 마우스 오른쪽 단추를 클릭한 다음 **정의 피킹(Peeking)** 을 선택하여 해당 정의의 인라인 뷰를 표시합니다. 자세한 내용은 [정의 피킹(Peeking)(Alt+F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12)을 참조하세요.

![Visual C&#43;&#43; 정의 피킹](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

## <a name="go-to-definition"></a>정의로 이동

변수 또는 함수 선언을 마우스로 가리키고 마우스 오른쪽 단추를 클릭한 다음 **정의로 이동**을 선택하여 개체가 정의된 문서를 엽니다.

## <a name="view-call-hierarchy"></a>호출 계층 구조 보기

함수 호출을 마우스 오른쪽 단추로 클릭하고 함수가 호출하는 모든 함수와 함수를 호출하는 모든 함수의 재귀적 목록을 표시합니다. 목록의 각 함수를 동일한 방식으로 확장할 수 있습니다. 자세한 내용은 [호출 계층 구조](/visualstudio/ide/reference/call-hierarchy)를 참조하세요.

![Visual C&#43;&#43; 호출 계층 구조](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

## <a name="toggle-header--code-file"></a>헤더/코드 파일 전환

마우스 오른쪽 단추를 클릭하고 **헤더/코드 파일 전환**을 선택하여 헤더 파일 및 연결된 코드 파일 간에 전환합니다.

## <a name="outlining"></a>개요

소스 코드 파일의 아무 곳이나 마우스 오른쪽 단추로 클릭하고 **개요**를 선택하여 정의 및/또는 사용자 지정 영역을 축소하거나 확장하면 관심 있는 부분만 쉽게 찾을 수 있습니다. 자세한 내용은 [개요](/visualstudio/ide/outlining)를 참조하세요.

![Visual C&#43;&#43; 개요](../ide/media/vs2015_cpp_outlining.png "vs2015_cpp_outlining")

## <a name="scrollbar-map-mode"></a>스크롤 막대 맵 모드

스크롤 막대 맵 모드를 사용하면 실제로 현재 위치를 벗어나지 않고 코드 파일을 신속하게 스크롤하여 찾아볼 수 있습니다. 또는 코드 맵의 아무 곳이나 클릭하여 해당 위치로 직접 이동합니다. 자세한 내용은 [방법: 스크롤 막대를 사용자 지정하여 코드 추적](/visualstudio/ide/how-to-track-your-code-by-customizing-the-scrollbar)을 참조하세요.

![Visual C&#43;&#43;의 코드 맵](../ide/media/vs2015_cpp_code_map.png "vs2015_cpp_code_map")

## <a name="generate-graph-of-include-files"></a>포함 파일의 그래프 생성

프로젝트에서 코드 파일을 마우스 오른쪽 단추로 클릭하고 **포함 파일의 그래프 생성**을 선택하여 다른 파일에 포함된 파일의 그래프를 표시합니다.

![Visual C&#43;&#43; 포함 파일의 그래프](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

## <a name="f1-help"></a>F1 도움말

형식, 키워드 또는 함수 위나 바로 뒤에 커서를 놓고 F1 키를 눌러 docs.microsoft.com에서 관련된 참조 항목으로 바로 이동합니다. F1 키는 많은 대화 상자와 오류 목록의 항목에서도 작동합니다.

## <a name="quick-launch"></a>빠른 실행

Visual Studio에서 임의 창이나 도구로 쉽게 이동하려면 UI의 오른쪽 위에 있는 빠른 실행 창에 해당 이름을 입력합니다. 입력에 따라 자동 완성 목록이 필터링됩니다.

![Visual Studio 빠른 실행](../ide/media/vs2015_cpp_quick_launch.png "vs2015_cpp_quick_launch")
