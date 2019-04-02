---
title: 유니버설 Windows 앱(C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.openlocfilehash: fbd5366ee52dfe32baef9458a82c16914666699e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784823"
---
# <a name="universal-windows-apps-c"></a>유니버설 Windows 앱(C++)

유니버설 Windows 플랫폼 (UWP)는 Windows에 대 한 최신 프로그래밍 인터페이스입니다. UWP를 사용 하 여는 응용 프로그램 또는 구성 요소 한 번 작성 하 고 모든 Windows 10 장치에 배포 합니다. C + +에서 구성 요소를 작성할 수 있습니다 하 고 다른 UWP 호환 언어로 작성 된 응용 프로그램에서 사용할 수 있습니다.

대부분의 UWP 설명서는 Windows 콘텐츠 트리에서 [유니버설 Windows 플랫폼 문서](/windows/uwp/)합니다. 여기서 시작 자습서를 찾을 수 있습니다 구성 파일 뿐만 아니라 참조 설명서입니다. 

새 UWP 앱 및 구성 요소를 사용 하는 권장 [C + + /cli WinRT](/windows/uwp/cpp-and-winrt-apis/), 새 표준 C + + 17 개의 언어 프로젝션 Windows 런타임 Api에 대 한 합니다. C + + /cli WinRT는 Windows 10 SDK 부터는 버전 1803에서에서 사용할 수 있습니다. C + + /cli WinRT 헤더 파일에서 완전히 구현 되 고 최신 Windows API에 대 한 최고 수준의 액세스를 제공 하도록 설계 되었습니다. 와 달리 C + + /cli CX 구현 합니다. C + + /cli WinRT 비표준 구문 또는 Microsoft 언어 확장을 사용 하지 않는 및 활용 전체 c + + 컴파일러가 최적화 된 출력을 만듭니다. 자세한 내용은 [소개 C + + /cli WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)합니다.

Microsoft Store 통해 배포할 기존의 데스크톱 응용 프로그램 패키지를 데스크톱 브리지 앱 변환기를 사용할 수 있습니다. 자세한 내용은 [Centennial 프로젝트에서 사용 하 여 Visual c + + 런타임](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) 하 고 [데스크톱 브리지](/windows/uwp/porting/desktop-to-uwp-root)합니다.

## <a name="uwp-apps-that-use-ccx"></a>UWP 앱을 사용 하 여 C + + /cli CX

|||
|-|-|
|[Visual C++ 언어 참조(C++/CX)](visual-c-language-reference-c-cx.md)|Windows 런타임 Api의 c + + 사용을 간소화 하 고 예외 기반 오류 처리를 사용 하도록 설정 하는 확장 집합을 설명 합니다.|
|[응용 프로그램 및 라이브러리 빌드(C++/CX)](building-apps-and-libraries-c-cx.md)|C++/CX 앱이나 구성 요소에서 액세스할 수 있는 DLL 및 정적 라이브러리를 만드는 방법을 설명합니다.|
|[자습서: UWP 만들기 "Hello, World" 앱에서 C + + /cli CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C +의 UWP 앱 개발의 기본 개념을 소개 하는 연습은 + CX 합니다. |
|[C + Windows 런타임 구성 요소 만들기 + CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|다른 UWP 앱 및 구성 요소를 사용할 수 있는 Dll을 만드는 방법을 설명 합니다.|
|[UWP 게임 프로그래밍](/windows/uwp/gaming/)|DirectX 및 C +를 사용 하는 방법에 설명 합니다. + 게임을 만들려면 CX 합니다.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하는 UWP 앱

Windows Runtime c + + 템플릿 라이브러리는 ISO c + + 코드가 예외 없는 환경에서 Windows 런타임 액세스할 수 있는 하위 수준 COM 인터페이스를 제공 합니다. 대부분의 경우에서 것이 좋습니다를 사용 하는 C + + /cli WinRT 또는 C + + UWP 앱 개발을 위한 Windows Runtime c + + 템플릿 라이브러리 대신 CX 합니다. Windows Runtime c + + 템플릿 라이브러리에 대 한 정보를 참조 하세요 [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md)합니다.

## <a name="see-also"></a>참고자료

[Visual Studio에서 c + +](../overview/visual-cpp-in-visual-studio.md)<br/>
[C++의 Windows 프로그래밍 개요](../windows/overview-of-windows-programming-in-cpp.md)<br/>