---
title: Visual C++ 언어 참조(C++/CX)
ms.date: 09/15/2017
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
ms.openlocfilehash: ce0272499b653b9077a891e39e9b29797e7e051d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384948"
---
# <a name="visual-c-language-reference-ccx"></a>Visual C++ 언어 참조(C++/CX)

C++/CX는 확장 집합의 C++ Windows 앱 및 Windows 런타임 구성 요소와 최대한 가까이 최신 가까운 만들 수 있는 언어 C++. 사용 하 여 C++Windows 앱 및 네이티브에서 구성 요소 코드는 쉽게 쓸 /CX 시각적 개체 상호 작용 C#, Visual Basic, JavaScript 및 Windows 런타임을 지 원하는 다른 언어입니다. 드물지만 원시 COM 인터페이스 또는 비 예외 코드를 직접 액세스 해야 하는 경우에 사용할 수 있습니다 합니다 [Windows 런타임 C++ 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)합니다.

> [!NOTE]
> **[C++/ WinRT](/windows/uwp/cpp-and-winrt-apis/index) 권장 되는 대신 사용 하는 C++/CX**합니다. 새, 표준 C + + 17 개의 언어 프로젝션 최신 Windows 10 sdk 부터는 버전 1803에서에서 사용할 수 있는 Windows 런타임 Api에 대 한 것입니다. C++/ WinRT 헤더 파일에서 완전히 구현 되 고 최신 Windows API에 대 한 최고 수준의 액세스를 제공 하도록 설계 되었습니다.
>
> 사용 하 여 C++/WinRT를 모두 사용 하는 모든 표준 호환 C + + 17 컴파일러를 사용 하 여 Windows 런타임 Api를 작성 합니다. C++/ WinRT는 일반적으로 더 나은 성능을 제공 하 고 Windows 런타임에 대 한 다른 언어 옵션 보다 더 작은 이진 파일을 생성 합니다. 계속 지원 될 예정 C++/CX 및 WRL, 하지만 새 응용 프로그램에 사용 하는 것이 좋습니다 C++/WinRT 합니다. 자세한 내용은 [ C++/WinRT](/windows/uwp/cpp-and-winrt-apis/index)합니다.

사용 하 여 C++만들면 CX, /:

- C++UWP (유니버설 Windows 플랫폼) 앱 사용자를 정의 하려면 XAML을 사용 하는 인터페이스 및 고 네이티브 스택을 사용 합니다. 자세한 내용은 [에서 "hello world" 앱 만들기 C++ (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)합니다.

- C++JavaScript 기반 Windows 앱에서 사용할 수 있는 Windows 런타임 구성 요소입니다. 자세한 내용은 [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)을 참조하세요.

- Windows DirectX 게임 및 그래픽 위주 앱. 자세한 내용은 [DirectX를 사용 하 여 간단한 UWP 게임을 만들기](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game)합니다.

## <a name="related-articles"></a>관련 문서

|||
|-|-|
|[빠른 참조](../cppcx/quick-reference-c-cx.md)|키워드 및 연산자의 테이블 C++/CX입니다.|
|[형식 시스템](../cppcx/type-system-c-cx.md)|기본에 대해 설명 합니다 C++/CX 형식 및 프로그래밍 구문을 사용 하는 방법 C++를 사용 하 여 Windows 런타임 형식을 만들 /CX입니다.|
|[앱 및 라이브러리 빌드](../cppcx/building-apps-and-libraries-c-cx.md)|IDE를 사용 하 여 앱을 빌드하고 정적 라이브러리 및 Dll에 연결 하는 방법에 설명 합니다.|
|[다른 언어와의 상호 운용](../cppcx/interoperating-with-other-languages-c-cx.md)|에 대해 설명 하는 방법을 사용 하 여 작성 된 구성 요소 C++/CX를 사용할 수 있습니다 JavaScript로 작성 된 구성 요소를 사용 하 여 관리 되는 언어 또는 Windows 런타임 C++ 템플릿 라이브러리입니다.|
|[스레딩 및 마샬링](../cppcx/threading-and-marshaling-c-cx.md)|사용자가 만든 구성 요소의 스레딩 및 마샬링 동작을 지정하는 방법을 설명합니다.|
|[네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)|기본 네임스페이스, Platform 네임스페이스, Platform::Collections 및 관련 네임스페이스에 대한 참조 설명서입니다.|
|[유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows 런타임 앱에서 사용할 수 없는 CRT 함수를 나열합니다.|
|[Windows 10 앱에 대한 방법 가이드](https://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Windows 10 앱에 대한 개략적인 지침 및 자세한 정보에 대한 링크를 제공합니다.|
|[C++/CX 파트 0 / \[n\]: 소개](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C++/CX 1 부 \[n\]: 간단한 클래스](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++/CX 파트 2 \[n\]: 유형](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++3 부 /CX \[n\]: 공사중](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C++4 부 /CX \[n\]: 정적 멤버 함수](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Visual C++ 블로그에서 연재하는 기본 C++/cli CX에 대한 시리즈입니다.|
