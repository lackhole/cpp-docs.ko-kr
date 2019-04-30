---
title: '연습: 표준 만들기 C++ 프로그램 (C++)'
ms.custom: get-started-article
ms.date: 09/18/2018
f1_keywords:
- vcfirstapp
- vccreatefirst
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: d58d23e757a97402985ef60badf551523c0a275e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387801"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>연습: 표준 만들기 C++ 프로그램 (C++)

표준 C++ 프로그램을 만들어 Visual Studio 통합 개발 환경(IDE)에서 Visual C++를 사용할 수 있습니다. 이 연습의 단계를 수행 하 여 프로젝트 만들기에 추가할 수 있습니다 새 파일을 프로젝트에 추가할 파일을 수정 C++ 코드를 다음 컴파일 및 Visual Studio를 사용 하 여 프로그램을 실행 합니다.

C++ 프로그램을 직접 입력하거나 샘플 프로그램 중 하나를 이용할 수 있습니다. 이 연습에서는 샘플 프로그램은 콘솔 응용 프로그램입니다. 이 응용 프로그램에서는 C++ 표준 라이브러리 컨테이너 `set`을 사용합니다.

Visual C++ 은 2003 따릅니다 C++ 이러한 주요 예외를 사용 하 여 표준: 2 단계 이름 조회, 예외 사양 및 내보내기. 또한 Visual C++ 람다 식, auto, static_assert, rvalue 참조 및 extern template과 같은 몇 가지 C++ 0x 기능을 지원합니다.

> [!NOTE]
> 사용 하 여 표준 준수가 필요한 경우를 `/Za` 컴파일러 옵션을 표준 Microsoft 확장을 사용 하지 않도록 설정 합니다. 자세한 내용은 [/Za, /Ze (언어 확장명 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md)합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 완료하려면 C++ 언어의 기본적인 사항을 알고 있어야 합니다.

### <a name="to-create-a-project-and-add-a-source-file"></a>프로젝트를 만들고 소스 파일을 추가 하려면

1. 메뉴의 **파일**에서 **새로만들기**를 클릭한 다음 **프로젝트**를 선택하여 새 프로젝트를 만듭니다.

1. 에 **Visual C++**  프로젝트 형식 창에서 클릭 **Windows Desktop**를 클릭 하 고 **Windows 콘솔 응용 프로그램**.

   > [!NOTE]
   > Visual Studio 2017 년 보다 오래 된 버전에 **새 프로젝트** 대화 상자에서 **설치 됨** > **템플릿**  >  **시각적 C++** 를 선택한 후 **Win32**합니다. 가운데 창에서 **Win32 콘솔 애플리케이션**을 선택합니다.

   프로젝트 이름을 입력합니다. 

   기본적으로 프로젝트를 포함하는 솔루션에 프로젝트와 동일한 이름이 허용되지만 다른 이름을 입력하는 것을 권장합니다. 프로젝트 위치를 변경할 수 있습니다.

   **확인**을 클릭해 프로젝트를 만듭니다.

   > [!NOTE]
   > Visual studio 2017 이전 버전의 경우 완료 합니다 **Win32 응용 프로그램 마법사**합니다. 클릭 **다음**에 있는지 확인 합니다 **콘솔 응용 프로그램** 을 선택 하 고 선택 취소 합니다 **미리 컴파일된 헤더** 상자. **마침**을 클릭합니다.

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
