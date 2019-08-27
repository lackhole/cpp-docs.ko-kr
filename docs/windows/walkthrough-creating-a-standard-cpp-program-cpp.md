---
title: '연습: 표준 C++ 프로그램 만들기(C++)'
ms.custom: get-started-article
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: b3172dd6ed4c438bacedd6760da5ab65228396f3
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400915"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>연습: 표준 C++ 프로그램 만들기(C++)

Visual Studio를 사용하여 표준 C++ 프로그램을 만들 수 있습니다. 프로젝트 생성, 프로젝트에 새 파일 추가, 파일을 수정하여 C++ 코드 추가, 그리고 컴파일과 실행의 일련의 과정을 Visual Studio를 사용하여 단계별로 진행합니다.

C++ 프로그램을 직접 입력하거나 샘플 프로그램 중 하나를 이용할 수 있습니다. 이 연습에서 샘플 프로그램은 콘솔 응용 프로그램입니다. 이 응용 프로그램에서는 C++ 표준 라이브러리의 `set` 컨테이너를 사용합니다.

> [!NOTE]
> 특정 버전의 C++ 언어 표준(예: C++ 14 또는 C++ 17)을 준수해야 하는 경우, `/std:C++14` 또는 `/std:c++17` 컴파일러 옵션을 사용합니다. (Visual Studio 2017 이상)

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 C++ 언어의 기본적인 사항을 알고 있어야 합니다.

### <a name="to-create-a-project-and-add-a-source-file"></a>프로젝트를 만들고 소스 파일을 추가 하려면

다음 단계는 사용 중인 Visual Studio 버전에 따라 다릅니다. 이 페이지의 왼쪽 위에 있는 버전 선택기가 올바르게 설정되어 있는지 확인합니다.

::: moniker range="vs-2019"

### <a name="to-create-a-c-project-in-visual-studio-2019"></a>Visual Studio 2019에서 C++ 프로젝트 만들기

1. 주 메뉴에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 **새 프로젝트 만들기** 대화 상자를 엽니다.

1. 대화 상자 맨 위에서 **언어**를 **C++** 로 설정하고 **플랫폼**을 **Windows**로 설정하후 **프로젝트 형식**을 **콘솔**로 설정합니다. 

1. 필터링된 프로젝트 형식 목록에서 **콘솔 앱**을 선택한 후 **다음**을 선택합니다. 다음 페이지에서 프로젝트의 이름을 입력하고 원하는 경우 프로젝트 위치를 지정합니다.

1. **만들기** 단추를 선택하여 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-project-in-visual-studio-2017"></a>Visual Studio 2019에서 C++ 프로젝트 만들기

1. 메뉴의 **파일**에서 **새로만들기**를 클릭한 다음 **프로젝트**를 선택하여 새 프로젝트를 만듭니다.

1. **Visual C++** 의 프로젝트 형식 창에서 **Windows Desktop**을 클릭하고 **Windows 콘솔 응용 프로그램**을 클릭합니다.

1. 프로젝트 이름을 입력합니다. 기본적으로 프로젝트를 포함하는 솔루션에 프로젝트와 동일한 이름이 허용되지만 다른 이름을 입력하는 것을 권장합니다. 프로젝트 위치를 변경할 수 있습니다.

1. **확인**을 클릭해 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-project-in-visual-studio-2015"></a>Visual Studio 2019에서 C++ 프로젝트 만들기

1. 메뉴의 **파일**에서 **새로만들기**를 클릭한 다음 **프로젝트**를 선택하여 새 프로젝트를 만듭니다.

1. **Visual C++** 의 프로젝트 형식 창에서 **Windows Desktop**을 클릭하고 **Windows 콘솔 응용 프로그램**을 클릭합니다.

1. **새 프로젝트**의 대화 상자에서 **설치됨**  >  **템플릿**  >  **시각적 C++** , **Win32**를 선택합니다. 가운데 창에서 **Win32 콘솔 애플리케이션**을 선택합니다.

1. 프로젝트 이름을 입력합니다. 기본적으로 프로젝트를 포함하는 솔루션에 프로젝트와 동일한 이름이 허용되지만 다른 이름을 입력하는 것을 권장합니다. 프로젝트 위치를 변경할 수 있습니다.

1. **확인**을 클릭해 프로젝트를 만듭니다.


1. **Win32 응용 프로그램 마법사**를 완료합니다.


1. **다음**을 클릭합니다. **콘솔 응용 프로그램**을 선택하고 **미리 컴파일된 헤더**를 클릭합니다.

1. **마침**을 클릭합니다.

::: moniker-end

## <a name="add-a-new-source-file"></a>새 소스 파일을 추가 합니다.

1. **솔루션 탐색기**가 표시되지 않는 경우 **뷰** 메뉴에서 **솔루션 탐색기**를 클릭합니다.

1. 다음과 같이 새 소스 파일을 프로젝트에 추가 합니다.

   1. **솔루션 탐색기**에서 **소스 파일** 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭 후 **새 항목**을 선택합니다.

   1. **코드** 노드에서 **C++ 파일(.cpp)**을 클릭하고, 파일 이름을 입력한 다음 **추가**를 클릭합니다.

   **솔루션 탐색기**의 **소스 파일** 폴더에 .cpp 파일이 보이고 파일이 Visual Studio 편집기에서 열립니다.

1. 편집기의 파일에서 C++ 표준 라이브러리를 사용하는 올바른 C++ 프로그램을 입력하거나, 샘플 프로그램 중 하나를 복사하여 파일에 붙여넣습니다.

1. 파일을 저장합니다.

1. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   **출력** 창에서는 빌드 로그 및 빌드 상태를 나타내는 메시지와 같은 컴파일 진행 상황을 안내합니다.

1. **디버그** 메뉴를 클릭하여 **디버깅하지 않고 시작**을 선택합니다.

   샘플 프로그램을 사용하는 경우 명령 창이 표시되고 `set`에서 특정 정수를 찾았는지를 보여줍니다.

## <a name="next-steps"></a>다음 단계

**이전:** [Visual C++의 콘솔 애플리케이션](../windows/console-applications-in-visual-cpp.md)<br/>
**다음:** [연습: 명령줄에서 네이티브 C++ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)

## <a name="see-also"></a>참고자료

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
