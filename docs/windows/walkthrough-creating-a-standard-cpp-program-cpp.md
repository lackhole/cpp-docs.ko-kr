---
title: '연습: 표준 만들기 C++ 프로그램 (C++)'
ms.custom: get-started-article
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: ed9c19dad029f8fc9495d38ab6e5c0ba8ad6d529
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877411"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>연습: 표준 만들기 C++ 프로그램 (C++)

Visual Studio를 사용 하 여 표준을 만들려면 C++ 프로그램입니다. 이 연습의 단계를 수행 하 여 프로젝트 만들기에 추가할 수 있습니다 새 파일을 프로젝트에 추가할 파일을 수정 C++ 코드를 다음 컴파일 및 Visual Studio를 사용 하 여 프로그램을 실행 합니다.

C++ 프로그램을 직접 입력하거나 샘플 프로그램 중 하나를 이용할 수 있습니다. 이 연습에서는 샘플 프로그램은 콘솔 응용 프로그램입니다. 이 응용 프로그램에서는 C++ 표준 라이브러리 컨테이너 `set`을 사용합니다.

> [!NOTE]
> 경우의 특정 버전을 사용 하 여 규정 준수를 C++ 언어 표준 (예: C + + 14 또는 C + + 17)가 필요를 사용 합니다 `/std:C++14` 또는 `/std:c++17` 컴파일러 옵션입니다. (Visual Studio 2017 이상입니다.)

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 C++ 언어의 기본적인 사항을 알고 있어야 합니다.

### <a name="to-create-a-project-and-add-a-source-file"></a>프로젝트를 만들고 소스 파일을 추가 하려면

다음 단계를 사용 중인 Visual Studio의 버전에 따라 달라 집니다. 버전 선택기 왼쪽 위에 있는이 페이지의 올바르게 설정 되어 있는지 확인 합니다.

::: moniker range="vs-2019"

### <a name="to-create-a-c-project-in-visual-studio-2019"></a>만들려는 C++ Visual Studio 2019에 프로젝트

1. 주 메뉴에서 선택 **파일** > **새로 만들기** > **프로젝트** 열려는 합니다 **새 프로젝트를 만들** 대화 상자입니다.

1. 설정 대화 상자 맨 **언어** 를 **C++** 설정 **플랫폼** 하 **Windows**, 설정 및 **프로젝트 형식을** 하 **콘솔**합니다. 

1. 필터링된 된 프로젝트 형식 목록에서 선택 **콘솔 앱** 선택한 **다음**합니다. 다음 페이지에서 프로젝트의 이름을 입력 하 고 원하는 경우 프로젝트 위치를 지정 합니다.

1. 선택 된 **만들기** 프로젝트를 만들려면 단추입니다.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-project-in-visual-studio-2017"></a>만들려는 C++ Visual Studio 2017의 프로젝트

1. 메뉴의 **파일**에서 **새로만들기**를 클릭한 다음 **프로젝트**를 선택하여 새 프로젝트를 만듭니다.

1. 에 **Visual C++**  프로젝트 형식 창에서 클릭 **Windows Desktop**를 클릭 하 고 **Windows 콘솔 응용 프로그램**.

1. 프로젝트 이름을 입력합니다.  기본적으로 프로젝트를 포함하는 솔루션에 프로젝트와 동일한 이름이 허용되지만 다른 이름을 입력하는 것을 권장합니다. 프로젝트 위치를 변경할 수 있습니다.

1. **확인**을 클릭해 프로젝트를 만듭니다.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-project-in-visual-studio-2015"></a>만들려는 C++ Visual Studio 2015에서 프로젝트

1. 메뉴의 **파일**에서 **새로만들기**를 클릭한 다음 **프로젝트**를 선택하여 새 프로젝트를 만듭니다.

1. 에 **Visual C++**  프로젝트 형식 창에서 클릭 **Windows Desktop**를 클릭 하 고 **Windows 콘솔 응용 프로그램**.

1. 에 **새 프로젝트** 대화 상자에서 **설치 됨** > **템플릿** > **시각적 C++** , 및 선택한 **Win32**합니다. 가운데 창에서 **Win32 콘솔 애플리케이션**을 선택합니다.

1. 프로젝트 이름을 입력합니다.  기본적으로 프로젝트를 포함하는 솔루션에 프로젝트와 동일한 이름이 허용되지만 다른 이름을 입력하는 것을 권장합니다. 프로젝트 위치를 변경할 수 있습니다.

1. **확인**을 클릭해 프로젝트를 만듭니다.

1. 완료 합니다 **Win32 응용 프로그램 마법사**합니다. 

1. 클릭 **다음**에 있는지 확인 합니다 **콘솔 응용 프로그램** 을 선택 하 고 선택 취소 합니다 **미리 컴파일된 헤더** 상자. 

1. **마침**을 클릭합니다.

::: moniker-end

## <a name="add-a-new-source-file"></a>새 소스 파일을 추가 합니다.

1. 하는 경우 **솔루션 탐색기** 에 표시 되지 않으면 합니다 **뷰** 메뉴에서 클릭 **솔루션 탐색기**합니다.

1. 다음과 같이 새 소스 파일을 프로젝트에 추가 합니다.

   1. **솔루션 탐색기**에서 **소스 파일** 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭 후 **새 항목**을 선택합니다.

   1. **코드** 노드에서 **C++ 파일(.cpp)** 을 클릭하고, 파일 이름을 입력한 다음 **추가**를 클릭합니다.

   .Cpp 파일이 합니다 **소스 파일** 폴더에서 **솔루션 탐색기**, 파일을 Visual Studio 편집기에서 연 합니다.

1. 편집기의 파일에서 C++ 표준 라이브러리를 사용하는 올바른 C++ 프로그램 입력 샘플 프로그램 중 하나를 복사하여 파일에 붙여넣습니다.


1. 파일을 저장합니다.

1. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

   **출력** 창에서는 빌드 로그 및 빌드 상태를 나타내는 메시지와 같은 컴파일 진행 상황을 안내합니다.

1. **디버그** 메뉴를 클릭하여 **디버깅하지 않고 시작**을 선택합니다.

   샘플 프로그램을 사용하는 경우 명령 창이 표시되고 `set`에서 특정 정수를 찾았는지를 보여줍니다.

## <a name="next-steps"></a>다음 단계

**이전:** [Visual C++의 콘솔 애플리케이션](../windows/console-applications-in-visual-cpp.md)<br/>
**다음:** [연습: 명령줄에서 네이티브 C++ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>

## <a name="see-also"></a>참고자료

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
