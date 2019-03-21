---
title: C++를 이용한 Windows 프로그래밍 개요
ms.date: 11/15/2018
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: 6338b390b11c58f3ebac2af1bb568ea3c3470cd1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810447"
---
# <a name="overview-of-windows-programming-in-c"></a>C++를 이용한 Windows 프로그래밍 개요

C++를 사용하면 다양한 종류의 Windows 응용 프로그램을 만들 수 있습니다. 프로그램은 각각 고유한 프로그래밍 모델과 Windows 관련 라이브러리 집합으로 구성되지만, C++ 표준 라이브러리나 타사 C++라이브러리도 물론 사용할 수 있습니다. 

## <a name="command-line-console-applications"></a>명령줄 (콘솔) 응용 프로그램

C++ 콘솔 응용 프로그램은 콘솔 창의 명령줄에서 실행되고 텍스트 출력만 표시할 수 있습니다. 자세한 내용은 [콘솔 응용 프로그램](console-applications-in-visual-cpp.md)을 참조하세요.
 
## <a name="native-desktop-client-applications"></a>네이티브 데스크톱 클라이언트 응용 프로그램

*데스크톱 네이티브 클라이언트 응용 프로그램*은 원래 Windows Win32 API를 사용하여 운영체제에 액세스하는 C/C++ 윈도우 응용 프로그램을 가리킵니다. 이러한 API 자체는 주로 C 언어로 작성됩니다. 응용 프로그램을 만들 때 운영 체제 이벤트를 처리하는 C 스타일의 메시지 루프를 직접 프로그래밍하거나 다소 객체 지향적인 방식으로 Win32를 래핑한 *Microsoft Foundation Classes* (MFC)를 사용할 수 있습니다. 두 접근 방식에는 "최신" 유니버설 Windows 플랫폼 (아래 참조) 비교할 수 있지만 모두 여전히 완전히 지원되며 현재 환경에서 실행되는 코드의 줄에 수백만 개의 으로 간주됩니다.

기존의 Windows C++ 프로그래밍을 시작하려면 [Win32 및 C++ 시작](/windows/desktop/LearnWin32/learn-to-program-for-windows)을 참조하세요. Win32에 대해 이해를 하면 [MFC 데스크톱 응용 프로그램](/mfc/mfc-desktop-applications)에 대해 더 쉽게 배울 수 있습니다. 기존 c + + 데스크톱 응용 프로그램의 정교한 그래픽을 사용 하는 예제를 참조 하세요. [Hilo: Windows 용 c + + 응용 프로그램 개발](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)합니다.

### <a name="c-or-net"></a>C++? .NET? 

UWP를 대상으로 하지 않는 대부분의 데스크톱 응용 프로그램 시나리오의 경우 C# 및 .NET 사용을 고려하십시오. 이는 .NET 프로그래밍이 일반적으로 덜 복잡하고 오류가 적게 발생하며 Win32나 MFC 보다 현대적인 객체 지향 API를 이용하기 때문에 대부분의 상황에서 적합한 성능을 얻을 수 있기 때문입니다. .NET은 풍부한 그래픽 표현을 위한 WPF(Windows Presentation Foundation), 최신 Windows 런타임 API(아래의 UWP 참조)뿐만 아니라 Win32도 사용할 수 있습니다. 아래의 경우 일반적으로 데스크탑 응용 프로그램에 C++를 사용할 것을 권장합니다.

- 메모리 사용량에 대한 정밀한 제어
- 전력 소비 효율의 극대화
- GPU 사용한 일반 연산
- DirectX에 대한 액세스
- 표준 C++ 라이브러리의 대량 사용

## <a name="com-components"></a>COM 구성 요소

Windows 운영 체제의 많은 부분은 프로그래밍 언어에 관계없이 모든 응용 프로그램에서 구성 요소를 사용할 수 있도록 하는 이진 표준을 정의한 구성 요소 개체 모델 (COM)을 기반으로 합니다. C++는 액티브 템플릿 라이브러리(ATL)를 사용하여 COM 구성 요소를 만드는 작업을 단순화할 수 있습니다. 자세한 내용은 [구성 요소 개체 모델 (COM)](/windows/desktop/com/component-object-model--com--portal)과 [ATL COM 데스크톱 구성 요소](../atl/atl-com-desktop-components.md)를 참조하세요.

## <a name="windows-universal-apps"></a>Windows 유니버설 앱

유니버설 Windows 플랫폼(UWP)은 최신 Windows API입니다. UWP 응용 프로그램은 Windows 10이 설치된 장치라면 모두 실행 가능하며 사용자 인터페이스에 XAML을 사용하고, 터치 동작을 완전하게 지원합니다. UWP에 대한 자세한 내용은 [유니버설 Windows 플랫폼(UWP) 앱이란?](/windows/uwp/get-started/whats-a-uwp)과 [Windows 유니버설 앱 가이드](/windows/uwp/get-started/universal-application-platform-guide)를 참조하세요.

UWP에 대한 종전의 C++ 지원은 (1) C++언어의 구문 확장을 사용하는 C++/CX와  C++의 언어 또는 (2) 표준 C++ 및 COM을 기반으로 하는 Windows 런타임 라이브러리(WRL)로 구성됩니다. C++/CX와 WRL은 계속 사용할 수 있지만, 새 프로젝트의 경우 완전한 표준 C++에 기반하며 더 빠른 성능을 제공하는 [C++/WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)를 권장합니다. 

Windows 10용으로 Microsoft Store를 통해 배포하기 위해 기존 C++ 데스크톱 응용 프로그램을 패키지할 수 있습니다. 자세한 내용은 [데스크톱 응용 프로그램 (데스크톱 브리지) 패키지](/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.

## <a name="games"></a>게임

DirectX 게임은 PC 또는 Xbox에서 실행할 수 있습니다. 자세한 내용은 [DirectX 그래픽 및 게임](/windows/desktop/directx)을 참조하세요.

## <a name="net-wrappers-for-c-libraries"></a>C++ 라이브러리를 위한 .NET 래퍼

C++/CLI를 사용하여 .NET 코드에서 네이티브 C++ 라이브러리를 사용할 수 있는 상호 운용(interop) 계층을 만들 수 있습니다. 자세한 내용은 [C++/CLI를 이용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)을 참조하세요.

## <a name="sql-server-database-clients"></a>SQL Server 데이터베이스 클라이언트

네이티브 코드에서 SQL Server 데이터베이스에 액세스하려면 ODBC 또는 OLE DB를 사용합니다. 자세한 내용은 [SQL Server 네이티브 클라이언트](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)를 참조하세요.

## <a name="windows-device-drivers"></a>Windows 디바이스 드라이버

드라이버는 응용 프로그램 및 기타 운영 체제 구성 요소가 액세스할 수 있는 하드웨어 장치의 데이터를 만드는 하위 수준의 구성 요소입니다. 자세한 내용은 [Windows Driver Kit(WDK)](/windows-hardware/drivers/index)을 참조하세요.

## <a name="windows-services"></a>Windows 서비스

Windows *서비스* 는 사용자 상호 작용이 거의 또는 전혀 없이 백그라운드에서 실행할 수 있는 프로그램입니다. 유닉스에서는 이를 *데몬(Daemon)* 이라고 부릅니다. 자세한 내용은 [서비스](/windows/desktop/services/services)를 참조하세요.

## <a name="sdks-libraries-and-header-files"></a>SDK, 라이브러리 및 헤더 파일

Visual Studio에는 C 런타임 라이브러리(CRT), C++ 표준 라이브러리 및 기타 Microsoft 전용 라이브러리가 포함되어 있습니다. 이러한 라이브러리의 헤더 파일이 포함된 폴더는 \VC\ 폴더 하에 있는 Visual Studio 설치 디렉터리, CRT의 경우 Windows SDK 설치 폴더에 있습니다.

[Vcpkg 패키지 관리자](../vcpkg.md)를 사용하면 수백 개의 Windows용 타사 오픈 소스 라이브러리를 편리하게 설치할 수 있습니다.

Microsoft 라이브러리에는 다음이 포함됩니다.

- Microsoft Foundation 클래스 (MFC). 기존 Windows 프로그램 만들기에 대 한 개체 지향 프레임 워크-특히 엔터프라이즈 응용 프로그램-해당 기능 단추, 목록 상자, 트리 뷰 및 기타 컨트롤 있는 풍부한 사용자 인터페이스입니다. 자세한 내용은 [MFC 데스크톱 응용 프로그램](../mfc/mfc-desktop-applications.md)을 참조하세요.

- 액티브 템플릿 라이브러리 (ATL): COM 구성 요소를 만들기 위한 강력한 도우미 라이브러리입니다. 자세한 내용은 [ATL COM 데스크톱 구성요소](../atl/atl-com-desktop-components.md)를 참조하세요.

- C + + AMP (c + + Accelerated Massive Parallelism): GPU에서 고성능 일반 계산 작업을 수 있게 해 주는 라이브러리입니다. 자세한 내용은 [C++ AMP(C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)를 참조하세요.

- 동시성 런타임: 다중 코어 및 다중 코어 장치에 대 한 병렬 및 비동기 프로그래밍의 작업을 간소화 하는 라이브러리입니다. 자세한 내용은 [동시성 런타임](../parallel/concrt/concurrency-runtime.md)을 참조하세요.

많은 Windows 프로그래밍 시나리오에는 Windows 운영 체제 구성 요소에 액세스할 수 있는 헤더 파일을 포함하는 Windows SDK도 필요합니다. 기본적으로 Visual Studio는 유니버설 Windows 앱을 개발할 수 있도록 하는 C++ 데스크톱 워크로드의 구성 요소로 Windows SDK를 설치합니다. UWP 앱을 개발하려면 Windows 10 버전의 Windows SDK가 필요합니다. 자세한 내용은 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)를 참조하세요. (이전 버전 Windows의 Windows SDK에 대한 자세한 내용은 [Windows SDK 아카이브](https://developer.microsoft.com/windows/downloads/sdk-archive)를 참조하세요.)

**Program Files (x86)\Windows Kits**는 모든 Windows SDK 버전에 대한 기본 위치입니다.

Xbox, Azure 등 다른 플랫폼은 설치가 필요한 고유의 SDK가 있습니다. 자세한 내용은 DirectX 개발자 센터 및 Azure 개발자 센터를 참조하세요.

## <a name="development-tools"></a>개발 도구

Visual Studio는 네이티브 코드에 대한 강력한 디버거, 정적 분석 도구, 그래픽 디버깅 도구, 완벽한 기능을 갖춘 코드 편집기, 유닛 테스트 지원 및 다른 많은 도구와 유틸리티를 포함합니다. 자세한 내용은 [Visual Studio를 사용 하 여 개발 시작 하기](/visualstudio/ide/get-started-developing-with-visual-studio), 및 [Visual Studio에서 c + + 개요 개발](../overview-of-cpp-development.md)합니다.

## <a name="in-this-section"></a>단원 내용
|제목|설명|
|-----------|-----------------|
|[C++의 Windows 데스크톱 응용 프로그램](desktop-applications-visual-cpp.md)| 기존 데스크톱 응용 프로그램을 만드는 방법입니다.|
|[ATL(액티브 템플릿 라이브러리)](../atl/TOC.md)|C++에서 COM 구성 요소를 만들려면 ATL 라이브러리를 사용합니다.|
|[MFC(Microsoft Foundation Class)](../mfc/TOC.md)|MFC를 사용하여 대화상자 및 컨트롤이 포함된 크고 작은 Windows 응용 프로그램을 만드는 방법입니다.|
|[ATL 및 MFC 공유 클래스](../atl-mfc-shared/TOC.md)|CString 같은 ATL 및 MFC에서 공유하는 클래스를 사용합니다.|
|[C++/CLI를 사용한 .NET 개발](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET 응용 프로그램 및 구성 요소와의 상호운용이 가능하도록 네이티브 C++ 라이브러리의 래퍼를 만듭니다.|
|[.NET 및 UWP용 구성 요소 확장](component-extensions-for-runtime-platforms.md)|C++/CX 및 C++/CLI에서 공유하는 구문요소에 대한 참조입니다.|
|[유니버설 Windows 앱(C++)](universal-windows-apps-cpp.md)|C++/CX 또는 Windows 런타임 템플릿 라이브러리(WRL)를 이용한 UWP 응용 프로그램 개발하기.|
|[COM 및 .NET에 대한 C++ 특성](attributes/cpp-attributes-com-net.md)|.NET 또는 COM을 사용할 때의 Windows 전용 프로그래밍용 비표준 특성|

## <a name="related-articles"></a>관련 문서

|제목|설명|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual C++ 개발자 콘텐츠에 대한 부모 항목입니다.|
