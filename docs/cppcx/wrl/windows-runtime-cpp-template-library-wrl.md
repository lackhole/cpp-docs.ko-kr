---
title: Windows 런타임 C++ 템플릿 라이브러리(WRL)
ms.date: 11/04/2016
ms.topic: overview
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
ms.openlocfilehash: 41b8b45f89e94b8de2ddcb9c87bfd72122db8e1a
ms.sourcegitcommit: 27d9db019f6d84c94de9e6aff0170d918cee6738
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75676940"
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows 런타임 C++ 템플릿 라이브러리(WRL)

WRL(Windows 런타임 C++ 템플릿 라이브러리)은 Windows 런타임 구성 요소를 만들고 사용하기 위한 간단한 방법을 제공하는 템플릿 라이브러리입니다.

> [!NOTE]
> WRL은 이제 Windows 런타임 Api C++에 대 한 표준 c + + 17 언어 프로젝션 인/winrt로 대체 되었습니다. C++/WinRT는 Windows 10 SDK에서 버전 1803 이후 버전으로 제공 됩니다. C++/WinRT는 헤더 파일에 완전히 구현 되며 최신 Windows API에 대 한 최고 수준의 액세스를 제공 하도록 설계 되었습니다.
>
> C++/Winrt를 사용 하면 표준 규격 c + + 17 컴파일러를 사용 하 여 Windows 런타임 api를 사용 하 고 제작할 수 있습니다. C++/WinRT는 일반적으로 더 잘 수행 되며 Windows 런타임에 대 한 다른 언어 옵션 보다 작은 이진 파일을 생성 합니다. C++/CX와 WRL도 계속 지원되지만, 새 애플리케이션에서는 C++/WinRT를 사용하는 것이 좋습니다. 자세한 내용은 [C++/WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index) 참조하세요.

## <a name="benefits"></a>이점

Windows 런타임 C++ 템플릿 라이브러리를 사용 하면 COM (구성 요소 개체 모델) 구성 요소를 보다 쉽게 구현 하 고 사용할 수 있습니다. 개체의 수명을 관리 하 고 HRESULT 값을 테스트 하 여 작업이 성공 또는 실패 했는지 여부를 확인 하는 참조 계산과 같은 정리 기술을 제공 합니다. Windows 런타임 C++ 템플릿 라이브러리를 성공적으로 사용 하려면 이러한 규칙과 기술을 신중 하 게 따라야 합니다.

C++/Cx는 Windows 런타임 구성 요소를 사용 하는 높은 수준의 언어 기반 방법입니다. Windows 런타임 C++ 템플릿 라이브러리와 C++/cx는 모두 사용자를 대신 하 여 자동으로 정리 작업을 수행 하 여 Windows 런타임에 대 한 코드 작성을 간소화 합니다.

Windows 런타임 C++ 템플릿 라이브러리와 C++/cx는 서로 다른 이점을 제공 합니다. 다음은 C++ C++/Cx 대신 Windows 런타임 템플릿 라이브러리를 사용할 수 있는 몇 가지 이유입니다.

- Windows 런타임 C++ 템플릿 라이브러리는 ABI (Windows 런타임 응용 프로그램 이진 인터페이스)에 약간의 추상화를 추가 하므로 기본 코드를 제어 하 여 Windows 런타임 api를 보다 효율적으로 만들거나 사용할 수 있습니다.

- C++/CX는 COM HRESULT 값을 예외로 나타냅니다. COM을 사용 하는 코드 베이스 나 예외를 사용 하지 않는 코드 베이스를 상속한 경우 예외를 사용할 필요가 없기 때문 C++ 에 Windows 런타임 템플릿 라이브러리가 Windows 런타임를 사용 하는 데 보다 자연스럽 게 도움이 될 수 있습니다.

   > [!NOTE]
   > Windows 런타임 C++ 템플릿 라이브러리는 HRESULT 값을 사용 하며 예외를 throw 하지 않습니다. 또한 Windows 런타임 C++ 템플릿 라이브러리는 스마트 포인터와 RAII 패턴을 사용 하 여 응용 프로그램 코드에서 예외를 throw 할 때 개체가 올바르게 제거 되도록 합니다. 스마트 포인터와 RAII에 대 한 자세한 내용은 [스마트 포인터](../../cpp/smart-pointers-modern-cpp.md) 및 [개체 자체 리소스 (RAII)](../../cpp/objects-own-resources-raii.md)를 참조 하세요.

- Windows 런타임 C++ 템플릿 라이브러리의 목적과 디자인은 COM 개체의 프로그래밍을 간소화 하는 템플릿 기반 C++ 클래스 집합인 ATL (액티브 템플릿 라이브러리)에 의해 결정 됩니다. Windows 런타임 C++ 템플릿 라이브러리는 표준을 C++ 사용 하 여 WINDOWS 런타임를 래핑하여, ATL로 작성 된 많은 기존 COM 구성 요소를 Windows 런타임으로 보다 쉽게 이식 하 고 조작할 수 있습니다. ATL을 이미 알고 있는 경우 Windows 런타임 C++ 템플릿 라이브러리 프로그래밍이 더 쉬울 수 있습니다.

## <a name="getting-started"></a>시작

다음은 Windows 런타임 C++ 템플릿 라이브러리를 즉시 사용 하는 데 도움이 되는 몇 가지 리소스입니다.

[Windows 런타임 라이브러리 (WRL)](https://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)<br/>
이 Channel 9 비디오에서는 Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 UWP (유니버설 Windows 플랫폼) 앱을 작성 하 고 Windows 런타임 구성 요소를 작성 하 고 사용 하는 방법에 대해 알아봅니다.

[방법: Windows 런타임 구성 요소 활성화 및 사용](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)<br/>
Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 Windows 런타임를 초기화 하 고 Windows 런타임 구성 요소를 활성화 하 고 사용 하는 방법을 보여 줍니다.

[방법: 비동기 작업 완료](how-to-complete-asynchronous-operations-using-wrl.md)<br/>
Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 비동기 작업을 시작 하 고 작업이 완료 되 면 작업을 수행 하는 방법을 보여 줍니다.

[방법: 이벤트 처리](how-to-handle-events-using-wrl.md)<br/>
Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 Windows 런타임 개체의 이벤트를 구독 하 고 처리 하는 방법을 보여 줍니다.

[연습: WRL 및 미디어 파운데이션을 사용하여 UWP 앱 만들기](walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)<br/>
[Microsoft 미디어 파운데이션](/windows/win32/medfound/microsoft-media-foundation-sdk)를 사용 하는 UWP 앱을 만드는 방법을 알아봅니다.

[방법: 클래식 COM 구성 요소 만들기](how-to-create-a-classic-com-component-using-wrl.md)<br/>
Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 기본 com 구성 요소를 만드는 방법과 데스크톱 앱에서 com 구성 요소를 등록 및 사용 하는 기본적인 방법을 보여 줍니다.

[방법: 직접 WRL 구성 요소 인스턴스화](how-to-instantiate-wrl-components-directly.md)<br/>
[Microsoft::WRL::Make](make-function.md) 및 [Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md) 함수를 사용하여 구성 요소를 정의하는 모듈의 구성 요소를 인스턴스화하는 방법을 알아봅니다.

[방법: winmdidl.exe 및 midlrt.exe를 사용하여 Windows 메타데이터에서 .h 파일 만들기](use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)<br/>
.winmd 메타데이터에서 IDL 파일을 만들어 WRL의 사용자 지정 Windows 런타임 구성 요소를 사용하는 방법을 살펴봅니다.

[연습: 작업 및 XML HTTP 요청을 사용하여 연결](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
[IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) 및 [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) 인터페이스를 작업과 함께 사용 하 여 HTTP GET 및 POST 요청을 UWP 앱의 웹 서비스에 보내는 방법을 보여 줍니다.

[Bing 지도 여행 최적화 프로그램 샘플](https://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)<br/>
연습: 전체 UWP 앱의 컨텍스트에서 [작업 및 XML HTTP 요청을 사용 하 여 연결](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) 에 정의 된 `HttpRequest` 클래스를 사용 합니다.

[샘플을 사용 하 여 C++ Windows 런타임 DLL 구성 요소 만들기](https://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)<br/>
Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 in-process DLL 구성 요소를 만들고이를/Cx, JavaScript 및 C++ C#에서 사용 하는 방법을 보여 줍니다.

[DirectX 대리석 메 이즈 게임 샘플](https://docs.microsoft.com/samples/microsoft/windows-appsample-marble-maze/directx-marble-maze-game-sample/)<br/>
Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 전체 3 차원 게임의 컨텍스트에서 DirectX 및 미디어 파운데이션 같은 COM 구성 요소의 수명을 관리 하는 방법을 보여 줍니다.

[데스크톱 앱에서 알림 메시지 보내기 샘플](https://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)<br/>
Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 데스크톱 앱에서 알림 메시지를 작업 하는 방법을 보여 줍니다.

## <a name="windows-runtime-c-template-library-compared-to-atl"></a>Windows 런타임 C++ 템플릿 라이브러리와 ATL 비교

Windows 런타임 C++ 템플릿 라이브러리는 작고 빠른 COM 개체를 만드는 데 사용할 수 있으므로 ATL (액티브 템플릿 라이브러리)과 유사 합니다. Windows 런타임 C++ 템플릿 라이브러리 및 ATL은 또한 모듈의 개체 정의, 인터페이스의 명시적 등록, 팩터리를 사용 하 여 개체의 개방형 생성 등의 개념을 공유 합니다. ATL에 대해 잘 알고 있는 C++ 경우 Windows 런타임 템플릿 라이브러리에 익숙해질 수 있습니다.

Windows 런타임 C++ 템플릿 라이브러리는 UWP 앱에 필요한 COM 기능을 지원 합니다. 따라서 다음과 같은 COM 기능에 대한 직접 지원이 생략된다는 점에서 ATL과 구별됩니다.

- 집계

- 재고 구현

- 이중 인터페이스(`IDispatch`)

- 표준 열거자 인터페이스

- 연결 지점

- 분리 인터페이스

- OLE 포함

- ActiveX 컨트롤

- COM+

## <a name="concepts"></a>개념

Windows 런타임 C++ 템플릿 라이브러리는 몇 가지 기본 개념을 나타내는 형식을 제공 합니다. 다음 단원에서는 이러한 형식에 대해 설명합니다.

### <a name="comptr"></a>ComPtr

[ComPtr](comptr-class.md) 은 템플릿 매개 변수를 통해 지정된 인터페이스를 나타내는 *스마트 포인터* 형식입니다. `ComPtr` 을 사용하여 인터페이스에서 파생된 개체의 멤버를 액세스할 수 있는 변수를 정의합니다. `ComPtr`은 기본 인터페이스 포인터의 참조 개수를 자동으로 관리하여 참조 횟수가 0이 되면 인터페이스를 릴리스합니다.

### <a name="runtimeclass"></a>RuntimeClass

[RuntimeClass](runtimeclass-class.md) 는 지정된 인터페이스 집합을 상속받는 인스턴스화된 클래스를 나타냅니다. `RuntimeClass` 개체는 하나 이상의 Windows 런타임 COM 인터페이스에 대 한 지원 또는 구성 요소에 대 한 약한 참조의 조합을 제공할 수 있습니다.

### <a name="module"></a>Module

[Module](module-class.md) 은 관련 개체의 컬렉션을 나타냅니다. `Module` 개체는 개체를 생성하는 클래스 팩터리와, 다른 애플리케이션이 개체를 사용할 수 있도록 하는 등록을 관리합니다.

### <a name="callback"></a>콜백

[Callback](callback-function-wrl.md) 함수는 멤버 함수가 이벤트 처리기(콜백 메서드)인 개체를 생성합니다. `Callback` 함수를 사용하여 비동기 작업을 작성합니다.

### <a name="eventsource"></a>EventSource

[EventSource](eventsource-class.md) 는 *대리자* 이벤트 처리기를 관리하는 데 사용됩니다. Windows 런타임 C++ 템플릿 라이브러리를 사용 하 여 대리자를 구현 하 고 `EventSource`를 사용 하 여 대리자를 추가, 제거 및 호출 합니다.

### <a name="asyncbase"></a>AsyncBase

[Asyncbase](asyncbase-class.md) 는 Windows 런타임 비동기 프로그래밍 모델을 나타내는 가상 메서드를 제공 합니다. 비동기 작업을 시작, 중지하거나 작업의 진행률을 확인할 수 있는 사용자 지정 클래스를 만들려면 이 클래스의 멤버를 재정의합니다.

### <a name="ftmbase"></a>FtmBase

[FtmBase](ftmbase-class.md) 는 자유 스레드된 마샬러 개체를 나타냅니다. `FtmBase`는 GIT(전역 인터페이스 테이블)을 생성하고 마샬링 및 프록시 개체의 관리를 지원합니다.

### <a name="weakref"></a>WeakRef

[WeakRef](weakref-class.md) 는 액세스할 수 있거나 액세스하지 못할 수 있는 개체를 참조하는 *약한 참조*를 나타내는 스마트 포인터 형식입니다. `WeakRef` 개체는 클래식 COM이 아닌 Windows 런타임 에서만 사용할 수 있습니다.

`WeakRef` 개체는 일반적으로 외부 스레드나 애플리케이션에서 제어하는 개체를 나타냅니다. 예를 들어 `WeakRef` 개체는 파일 개체를 참조할 수 있습니다. 파일을 열면 `WeakRef` 가 유효해지고 참조 파일을 액세스할 수 있게 됩니다. 하지만 파일이 닫히면 `WeakRef` 가 무효가 되고 파일을 액세스할 수 없게 됩니다.

## <a name="related-topics"></a>관련 항목

|||
|-|-|
|[범주별 키 Api](key-wrl-apis-by-category.md)|기본 Windows 런타임 C++ 템플릿 라이브러리 형식, 함수 및 매크로를 강조 표시 합니다.|
|[참조](wrl-reference.md)|Windows 런타임 C++ 템플릿 라이브러리에 대 한 참조 정보를 포함 합니다.|
|[빠른 참조(C++/CX)](../../cppcx/quick-reference-c-cx.md)|Windows 런타임를 지 C++원하는/cx 기능을 간략하게 설명 합니다.|
|[시각적 개체에서 Windows 런타임 구성 요소 사용C++](/windows/uwp/winrt-components/walkthrough-creating-a-basic-windows-runtime-component-in-cpp-and-calling-it-from-javascript-or-csharp)|/Cx를 사용 C++하 여 기본 Windows 런타임 구성 요소를 만드는 방법을 보여 줍니다.|
