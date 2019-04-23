---
title: Visual C++ 응용 프로그램의 종속성 이해
ms.date: 11/04/2016
helpviewer_keywords:
- application deployment [C++], dependencies
- Dependency Walker
- dependencies [C++], application deployment and
- deploying applications [C++], dependencies
- DUMPBIN utility
- DLLs [C++], dependencies
- depends.exe
- libraries [C++], application deployment issues
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
ms.openlocfilehash: 92db11778de7d31bbab67e649cd58e264da331e6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58786476"
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Visual C++ 응용 프로그램의 종속성 이해

애플리케이션이 종속된 Visual C++ 라이브러리를 확인하려면 프로젝트 속성을 보면 됩니다. (이렇게 하려면 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택하여 **속성 페이지** 대화 상자를 엽니다.) Windows 8 및 이전 버전에서는 종속성에 대 한 더 종합적인 그림을 제공 하는 Dependency Walker (depends.exe)를 사용할 수도 있습니다. Windows의 최신 버전의 [lucasg/종속성](https://github.com/lucasg/Dependencies) (Microsoft에 의해 보증 되지 타사 도구입니다.)와 유사한 기능을 제공 하는 도구

**속성 페이지** 대화 상자에서 **구성 속성**의 다양한 페이지를 검사하여 종속성을 확인할 수 있습니다. 예를 들어 프로젝트가 MFC 라이브러리를 사용하고 **MFC 사용**, **구성 속성**, **일반** 페이지의 **공유 DLL에서 MFC 사용**을 선택하는 경우, 런타임의 애플리케이션은 mfc\<version&gt;.dll 등의 MFC DLL에 종속됩니다. 애플리케이션에서 MFC를 사용하지 않더라도 **다중 스레드 디버그 DLL(/MDd)** 의 **런타임 라이브러리** 값 또는 **구성 속성**, **C/C++**, **코드 생성** 페이지의 **다중 스레드 DLL(/MD)** 을 선택하면 CRT 라이브러리에 종속될 수 있습니다.

depends.exe를 사용하여 로드 시 응용 프로그램에 연결되는 DLL 목록과 지연 로드되는 DLL 목록을 확인할 수 있습니다. 런타임에 동적으로 로드되는 DLL의 전체 목록을 가져오려면 depends.exe의 프로파일링 기능을 사용하여 모든 코드 경로를 사용할 때까지 응용 프로그램을 테스트할 수 있습니다. 프로파일링 세션을 종료하면 depends.exe에서 런타임에 동적으로 로드된 DLL을 표시합니다.

depends.exe를 사용하여 종속성을 확인할 때 DLL이 다른 DLL이나 특정 DLL 버전에 대해 종속성을 가질 수도 있다는 점에 유의해야 합니다. depends.exe는 개발 컴퓨터 또는 대상 컴퓨터에서 사용할 수 있습니다. 개발 컴퓨터에서 depends.exe를 실행하면 응용 프로그램을 지원하는 데 필요한 DLL 목록이 표시됩니다. 대상 컴퓨터에서 실행할 응용 프로그램을 가져오는 데 문제가 있으면 depends.exe를 컴퓨터에 복사한 다음 도구에서 응용 프로그램을 열어 누락되거나 올바르지 않은 필수 DLL이 있는지 확인할 수 있습니다.

응용 프로그램이 종속된 DLL을 확인하면 응용 프로그램을 다른 컴퓨터에 배포할 때 이 응용 프로그램과 함께 재배포할 DLL을 이 목록 중에서 확인할 수 있습니다. 대부분의 경우 시스템 DLL은 재배포할 필요가 없지만 Visual C++ 라이브러리용 DLL은 다시 배포해야 할 수 있습니다. 자세한 내용은 [재배포할 DLL 확인](determining-which-dlls-to-redistribute.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[데스크톱 응용 프로그램 배포](deploying-native-desktop-applications-visual-cpp.md)
