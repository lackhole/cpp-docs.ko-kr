---
title: 데스크톱 응용 프로그램 ( C++시각적 개체)
ms.date: 07/28/2019
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
ms.topic: overview
ms.openlocfilehash: 91fcc596a4c30e3fa74043c846eda6f06b666f2c
ms.sourcegitcommit: 7750e4c291d56221c8893120c56a1fe6c9af60d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274730"
---
# <a name="desktop-applications-visual-c"></a>데스크톱 응용 프로그램 ( C++시각적 개체)

C++로 작성된 *데스크톱 응용 프로그램*은 전체 Windows API를 모두 사용할 수 있으며 Windows나 시스템 콘솔 창에서 실행할 수 있는 네이티브 응용 프로그램입니다. C++로 작성된 데스크톱 응용 프로그램은 Windows XP부터 Windows 10에 이르기까지 실행될 수 있습니다(Windows XP는 더 이상 공식적으로 지원되지 않으며 Windows XP 이후에 도입된 많은 Windows API가 존재합니다). 

데스크톱 응용 프로그램은 Windows 10에서 실행되는 PC, XBox, Windows Phone, Surface Hub 및 기타 장치에서 실행할 수 있는 유니버설 Windows 플랫폼(UWP) 앱과는 다릅니다. 데스크톱과 UWP 애플리케이션에 대한 차이점은 [기술 선택](/windows/win32/choose-your-technology)을 참조하세요.

### <a name="desktop-bridge"></a>데스크톱 브리지

Windows 10에서 기존 데스크톱 응용 프로그램 또는 COM 개체를 UWP 응용 프로그램으로 패키징하고 터치와 같은 UWP 기능을 추가하거나 최신 Windows API를 호출할 수 있습니다. 또한 Visual Studio의 데스크톱 솔루션에 UWP 응용 프로그램을 추가하고 단일 패키지로 함께 패키지화하고 Windows API를 사용하여 UWP 응용 프로그램간 통신이 가능합니다.

Visual Studio 2017 버전 15.4 이상에서는 기존 데스크톱 응용 프로그램을 패키징하는 작업을 단순화하는 Windows 응용 프로그램 패키지 프로젝트를 만들 수 있습니다. 데스크톱 응용 프로그램에서 사용하는 레지스트리 호출이나 API와 관련하여 몇 가지 제한이 적용되지만 대부분의 경우 앱 패키지에서 실행되는 동안 유사한 기능을 얻기 위해 대체할 수 있는 코드 경로를 만들 수 있습니다. 자세한 내용은 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.

### <a name="terminology"></a>용어

- *Win32* 응용 프로그램은 네이티브 [Windows C API나 COM API](/windows/win32/apiindex/windows-api-list)와 CRT, 표준 라이브러리 API 및 타사 라이브러리를 사용한 C++로 작성된 데스크톱 응용 프로그램입니다. 창에서 실행되는 Win32 응용 프로그램은 개발자가 Windows 프로시저 함수 내에서 Windows 메시지를 명시적으로 사용하도록 요구합니다. Win32 응용 프로그램이라는 공통된 이름을 사용하지만 32비트(x86) 또는 64비트(x64) 이진 파일로 컴파일할 수 있습니다. Visual Studio IDE에서 x86과 Win32는 동의어입니다.

- [구성 요소 개체 모델(COM)](/windows/win32/com/the-component-object-model)은 다른 언어로 작성된 프로그램 간에 서로 통신을 가능하게 해줍니다. 많은 Windows 구성 요소가 COM 개체로 구현되어 있으며 표준 COM 규칙에 따라 개체가 생성, 검색 및 제거됩니다.  C++ 데스크톱 응용 프로그램의 COM 개체를 사용하는 것은 비교적 간단하지만 고유한 COM 개체를 작성하는 것은 더 높은 수준의 지식이 필요합니다. [라이브러리 ATL(액티브 템플릿)](../atl/atl-com-desktop-components.md)은  COM 개발을 간소화하는 매크로 및 도우미 함수를 제공합니다.

- MFC 응용 프로그램은 [Microsoft Foundation Classes](../mfc/mfc-desktop-applications.md)를 사용하여 사용자 인터페이스를 만드는 Windows 데스크톱 응용 프로그램입니다. MFC 응용 프로그램 역시 CRT 및 표준 라이브러리 API뿐만 아니라 COM 구성 요소를 사용할 수 있습니다. MFC는 창 메시지 C++ 루프 및 Windows api에 대 한 씬 개체 지향 래퍼를 제공 합니다. MFC는 사용자 인터페이스 컨트롤이나 특정 사용자들을 위한 사용자 정의 컨트롤이 많이 포함된 응용 프로그램, 특히 엔터프라이즈 유형 응용 프로그램에서 좋은 선택입니다. MFC 창 관리, 직렬화, 텍스트 조작, 인쇄 및 리본과 같은 최신 사용자 인터페이스 요소들의 편리한 도우미 클래스를 제공합니다. MFC를 효과적으로 사용 하려면 Win32에 대해 잘 알고 있어야 합니다.

- /Cli C++응용 프로그램 또는 구성 요소는 C++ 표준 C++ 에서 허용 하는 확장 구문을 사용 하 여 .net 및 네이티브 C + + 코드 간의 상호 작용을 사용 하도록 설정 합니다.  /Cli C++응용 프로그램은 기본적으로 실행 되는 파트와 .NET Framework에서 실행 되는 파트를 .Net 기본 클래스 라이브러리에 액세스할 수 있습니다. C++/CLI는 C# 또는 Visual Basic 작성 된 코드로 작업 해야 C++ 하는 네이티브 코드가 있는 경우 기본 설정 된 옵션입니다. 사용자 인터페이스 코드가 아닌 .NET Dll에서 사용 하기 위한 것입니다. 자세한 내용은 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)을 참조하세요.

C++로 만든 Windows 데스크톱 응용 프로그램이라면 CRT(C 런타임), 표준 라이브러리 클래스 및 함수, COM 개체 및 공용 Windows API라고 통칭하는 Windows 함수를 사용할 수 있습니다. C++로 작성된 Windows 데스크톱 응용 프로그램에 대한 소개는 [Win32 및 C++ 시작](/windows/win32/LearnWin32/learn-to-program-for-windows)을 참조합니다.

## <a name="in-this-section"></a>단원 내용

|제목|설명|
|-----------|-----------------|
|[C++의 Windows 콘솔 애플리케이션](console-applications-in-visual-cpp.md)|콘솔 앱에 대한 정보가 들어 있습니다. Win32 또는 Win64 콘솔 애플리케이션에는 고유의 창이나 메시지 루프가 없습니다. 콘솔 창에서 실행되고 입력 및 출력이 명령줄을 통해 처리됩니다.|
|[연습: Windows 데스크톱 애플리케이션 만들기(C++)](walkthrough-creating-windows-desktop-applications-cpp.md)|간단한 Windows 데스크톱 응용 프로그램을 만듭니다.|
|[빈 Windows 데스크톱 애플리케이션 만들기](creating-an-empty-windows-desktop-application.md)|기본 파일이 없는 Windows 데스크톱 프로젝트를 만드는 방법|
|[빈 Win32 애플리케이션에 파일 추가](adding-files-to-an-empty-win32-applications.md)|빈 프로젝트에 파일을 추가 하는 방법|
|[리소스 파일 작업](working-with-resource-files.md)|데스크톱 응용 프로그램에 이미지, 아이콘, 문자열 테이블 및 기타 리소스를 추가 하는 방법입니다.|
|[DirectX를 사용 하 여 게임을 만들기C++위한 리소스 ()](resources-for-creating-a-game-using-directx.md)|에서 C++게임을 만들기 위한 콘텐츠에 대 한 링크입니다.|
|[연습: 정적 라이브러리 만들기 및 사용](walkthrough-creating-and-using-a-static-library-cpp.md)|.Lib 이진 파일을 만드는 방법|
|[방법: Windows 데스크톱 애플리케이션에서 Windows 10 SDK 사용](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK를 사용하여 빌드할 프로젝트를 설정하는 단계를 설명합니다.|

## <a name="related-articles"></a>관련 문서

|제목|설명|
|-----------|-----------------|
|[Windows Development](/windows/win32/index)|Windows API 및 COM에 대한 정보를 제공합니다. 일부 Windows API 및 타사 DLL이 COM 개체로 구현됩니다.|
|[Hilo Windows C++ 7 용 응용 프로그램 개발](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)|Windows Animation 및 Direct2D를 사용하는 리치 클라이언트 Windows 데스크톱 애플리케이션을 만들어서 캐러셀 기반 사용자 인터페이스를 만드는 방법에 대해 설명합니다.  이 자습서는 Windows 7부터 업데이트 되지 않았지만 Win32 프로그래밍에 대 한 철저 한 소개를 제공 합니다.|
|[C++의 Windows 프로그래밍 개요](overview-of-windows-programming-in-cpp.md)|Windows 데스크톱 C++에서 프로그래밍의 주요 기능을 설명 합니다.|

## <a name="see-also"></a>참고 항목

[Visual Studio의 C++](../overview/visual-cpp-in-visual-studio.md)