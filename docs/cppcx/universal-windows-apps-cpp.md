---
title: 유니버설 Windows 앱(C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.openlocfilehash: fbd5366ee52dfe32baef9458a82c16914666699e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392065"
---
# <a name="universal-windows-apps-c"></a>유니버설 Windows 앱(C++)

유니버설 Windows 플랫폼 (UWP)는 Windows에 대 한 최신 프로그래밍 인터페이스입니다. UWP를 사용 하 여는 응용 프로그램 또는 구성 요소 한 번 작성 하 고 모든 Windows 10 장치에 배포 합니다. 구성 요소를 작성할 수 있습니다 C++ 다른 UWP 호환 언어로 작성 된 응용 프로그램에서 사용할 수 있습니다.

대부분의 UWP 설명서는 Windows 콘텐츠 트리에서 [유니버설 Windows 플랫폼 문서](/windows/uwp/)합니다. 여기서 시작 자습서를 찾을 수 있습니다 구성 파일 뿐만 아니라 참조 설명서입니다. 

새 UWP 앱 및 구성 요소를 사용 하는 권장 [ C++/WinRT](/windows/uwp/cpp-and-winrt-apis/)에 새 표준 C + + 17 개의 언어 프로젝션 Windows 런타임 Api에 대 한 합니다. C++/ WinRT는 Windows 10 SDK 부터는 버전 1803에서에서 사용할 수 있습니다. C++/ WinRT 헤더 파일에서 완전히 구현 되 고 최신 Windows API에 대 한 최고 수준의 액세스를 사용 하 여 제공 하도록 설계 되었습니다. 달리는 C++/CX 구현 합니다. C++/ WinRT 비표준 구문 또는 Microsoft 언어 확장을 사용 하지 않는 및 활용 전체는 C++ 컴파일러 최적화 된 출력을 만듭니다. 자세한 내용은 [소개 C++/WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)합니다.

Microsoft Store 통해 배포할 기존의 데스크톱 응용 프로그램 패키지를 데스크톱 브리지 앱 변환기를 사용할 수 있습니다. 자세한 내용은 참조 하세요. [Visual를 사용 하 여 C++ Centennial 프로젝트에서 런타임](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) 하 고 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root)합니다.

## <a name="uwp-apps-that-use-ccx"></a>UWP 앱을 사용 하는 C++/CX

|||
|-|-|
|[Visual C++ 언어 참조(C++/CX)](visual-c-language-reference-c-cx.md)|간소화 하는 확장 집합에 설명 합니다 C++ 예외를 기반으로 하는 오류 처리를 사용 하 고 Windows 런타임 Api의 소비 합니다.|
|[응용 프로그램 및 라이브러리 빌드(C++/CX)](building-apps-and-libraries-c-cx.md)|C++/CX 앱이나 구성 요소에서 액세스할 수 있는 DLL 및 정적 라이브러리를 만드는 방법을 설명합니다.|
|[자습서: UWP 만들기에서 "Hello, World" 앱 C++/CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C +의 UWP 앱 개발의 기본 개념을 소개 하는 연습은 + CX 합니다. |
|[C + Windows 런타임 구성 요소 만들기 + CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|다른 UWP 앱 및 구성 요소를 사용할 수 있는 Dll을 만드는 방법을 설명 합니다.|
|[UWP 게임 프로그래밍](/windows/uwp/gaming/)|DirectX 및 C +를 사용 하는 방법에 설명 합니다. + 게임을 만들려면 CX 합니다.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows 런타임을 사용 하는 UWP 앱 C++ 템플릿 라이브러리 (WRL)

Windows 런타임 C++ 는 ISO에서 낮은 수준의 COM 인터페이스를 제공 하는 템플릿 라이브러리 C++ 코드는 Windows 런타임 예외 없는 환경에서 액세스할 수 있습니다. 대부분의 경우에서 사용 하는 권장 C++/WinRT 또는 C++Windows 런타임 대신 /CX C++ UWP 앱 개발을 위한 템플릿 라이브러리입니다. Windows 런타임에 대 한 내용은 C++ 템플릿 라이브러리 참조 [Windows 런타임 C++ 템플릿 라이브러리 (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md)합니다.

## <a name="see-also"></a>참고자료

[Visual Studio의 C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[C++의 Windows 프로그래밍 개요](../windows/overview-of-windows-programming-in-cpp.md)<br/>