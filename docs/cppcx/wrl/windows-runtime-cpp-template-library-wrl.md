---
title: Windows 런타임 C++ 템플릿 라이브러리(WRL)
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
ms.openlocfilehash: 5c1a4e7df424499f400dbd70d675956deef6bc5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404600"
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows 런타임 C++ 템플릿 라이브러리(WRL)

WRL(Windows 런타임 C++ 템플릿 라이브러리)은 Windows 런타임 구성 요소를 만들고 사용하기 위한 간단한 방법을 제공하는 템플릿 라이브러리입니다.

> [!NOTE]
> WRL은 이제로 대체 됩니다. C++/WinRT, 표준 C + + 17 개의 언어 프로젝션 Windows 런타임 Api에 대 한 합니다. C++/ WinRT는 Windows 10 SDK 부터는 버전 1803에서에서 사용할 수 있습니다. C++/ WinRT 헤더 파일에서 완전히 구현 되 고 최신 Windows API에 대 한 최고 수준의 액세스를 제공 하도록 설계 되었습니다.
>
> 사용 하 여 C++/WinRT를 모두 사용 하는 모든 표준 호환 C + + 17 컴파일러를 사용 하 여 Windows 런타임 Api를 작성 합니다. C++/ WinRT는 일반적으로 더 나은 성능을 제공 하 고 Windows 런타임에 대 한 다른 언어 옵션 보다 더 작은 이진 파일을 생성 합니다. 계속 지원 될 예정 C++/CX 및 WRL, 하지만 새 응용 프로그램에 사용 하는 것이 좋습니다 C++/WinRT 합니다. 자세한 내용은 [ C++/WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index)합니다.

## <a name="benefits"></a>이점

Windows 런타임 C++ 템플릿 라이브러리를 사용 하면 보다 쉽게 구현 하 고 구성 요소 개체 모델 (COM) 구성 요소를 사용할 수 있습니다. 참조 카운팅을 개체의 수명을 관리 하 고 작업 성공 또는 실패 여부를 결정 하는 HRESULT 값 테스트와 같은 관리 기술을 제공 합니다. Windows 런타임을 사용 하 여 C++ 템플릿 라이브러리를 신중 하 게 따라야 이러한 규칙과 기법입니다.

C++/CX가는 상위 수준 언어 기반 방식으로 Windows 런타임 구성 요소를 사용 합니다. 두 Windows 런타임 C++ 템플릿 라이브러리 및 C++/CX 자동으로 사용자를 대신해 관리 작업을 수행 하 여 Windows 런타임에 대 한 코드 작성을 간소화 합니다.

Windows 런타임 C++ 템플릿 라이브러리 및 C++/CX 서로 다른 이점을 제공 합니다. Windows 런타임을 사용 하려는 일부 원인은 다음과 같습니다 C++ 대신 템플릿 라이브러리 C++/CX:

- Windows 런타임 C++ 템플릿 라이브러리 추가 약간의 추상화를 통해 Windows 런타임 응용 프로그램 이진 인터페이스 (ABI) 보다 잘 만들기 또는 Windows 런타임 Api를 사용 하는 기본 코드를 제어 하는 기능을 제공 합니다.

- C++/CX 예외로 COM HRESULT 값을 나타냅니다. COM, 또는 예외를 사용 하지 않는 하나를 사용 하는 코드 베이스를 상속 받을 경우 볼 수 있습니다 하는 Windows 런타임 C++ 템플릿 라이브러리는 더 자연 스러운 방법 예외를 사용 하는 것이 없기 때문에 Windows 런타임과 함께 작동 합니다.

   > [!NOTE]
   > Windows 런타임 C++ 템플릿 라이브러리 HRESULT 값을 사용 하 고 예외를 throw 하지 않습니다. 또한 Windows 런타임 C++ 템플릿 라이브러리는 개체가 제대로 삭제 응용 프로그램 코드는 예외를 throw 하도록 스마트 포인터와 RAII 패턴을 사용 합니다. 스마트 포인터와 RAII에 대 한 자세한 내용은 참조 하세요. [스마트 포인터](../../cpp/smart-pointers-modern-cpp.md) 하 고 [개체 자체 리소스 (RAII)](../../cpp/objects-own-resources-raii.md)합니다.

- 용도 디자인 Windows 런타임 C++ 템플릿 라이브러리에서의 라이브러리 ATL (액티브 템플릿), 템플릿 기반 집합인 영감을 얻은 C++ COM 개체의 프로그래밍을 단순화 하는 클래스입니다. 때문에 Windows 런타임 C++ standard를 사용 하는 템플릿 라이브러리 C++ Windows 런타임, wrap를 보다 쉽게 포트를 Windows 런타임 쓸 ATL에서 많은 기존 COM 구성 요소와 상호 작용 합니다. ATL를 이미 알고 있는 경우 해당 Windows 런타임 C++ 템플릿 라이브러리 프로그램이 더욱 쉬워집니다.

## <a name="getting-started"></a>시작

Windows 런타임과 함께 작업할 수 있는 일부 리소스는 C++ 바로 템플릿 라이브러리입니다.

[Windows 런타임 라이브러리 (WRL)](https://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)<br/>
이 채널 9 비디오에서는 방법에 대해 알아보려면 Windows 런타임 C++ 템플릿 라이브러리를 사용 하면 작성 하 고 Windows 런타임 구성 요소를 사용 하는 방법과 유니버설 Windows 플랫폼 (UWP) 앱을 작성할 수 있습니다.

[방법: 활성화 하 고 Windows 런타임 구성 요소를 사용 하 여](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)<br/>
Windows 런타임을 사용 하는 방법을 보여 줍니다 C++ 는 Windows 런타임을 초기화 및 활성화 하 고 Windows 런타임 구성 요소를 사용 하 여 템플릿 라이브러리입니다.

[방법: 비동기 작업 완료](how-to-complete-asynchronous-operations-using-wrl.md)<br/>
Windows 런타임을 사용 하는 방법을 보여 줍니다 C++ 템플릿 라이브러리 비동기 작업을 시작 하 고 작업 완료 시 작업을 수행 합니다.

[방법: 이벤트 처리](how-to-handle-events-using-wrl.md)<br/>
Windows 런타임을 사용 하는 방법을 보여 줍니다 C++ 구독 하 고 Windows 런타임 개체의 이벤트를 처리 하는 템플릿 라이브러리입니다.

[연습: WRL 및 미디어 파운데이션을 사용하여 UWP 앱 만들기](walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)<br/>
사용 하는 UWP 앱을 만드는 방법을 알아봅니다 [Microsoft 미디어 파운데이션](/windows/desktop/medfound/microsoft-media-foundation-sdk)합니다.

[방법: 클래식 COM 구성 요소 만들기](how-to-create-a-classic-com-component-using-wrl.md)<br/>
Windows 런타임을 사용 하는 방법을 보여 줍니다 C++ 템플릿 라이브러리를 기본 COM 구성 요소를 만들고 등록 하 고 데스크톱 앱에서 COM 구성 요소를 사용 하는 기본적인 방법입니다.

[방법: 직접 WRL 구성 요소 인스턴스화](how-to-instantiate-wrl-components-directly.md)<br/>
[Microsoft::WRL::Make](make-function.md) 및 [Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md) 함수를 사용하여 구성 요소를 정의하는 모듈의 구성 요소를 인스턴스화하는 방법을 알아봅니다.

[방법: winmdidl.exe 및 midlrt.exe를 사용하여 Windows 메타데이터에서 .h 파일 만들기](use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)<br/>
.winmd 메타데이터에서 IDL 파일을 만들어 WRL의 사용자 지정 Windows 런타임 구성 요소를 사용하는 방법을 살펴봅니다.

[연습: 작업 및 XML HTTP 요청을 사용하여 연결](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
사용 하는 방법을 보여 줍니다 합니다 [IXMLHTTPRequest2](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2) 하 고 [IXMLHTTPRequest2Callback](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2callback) UWP 앱에서 웹 서비스에 HTTP GET 및 POST 요청을 보내는 작업 함께 인터페이스.

[Bing Maps Trip Optimizer 샘플](https://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)<br/>
사용 하 여 `HttpRequest` 클래스에 정의 된 [연습: 사용 하 여 작업 및 XML HTTP 요청을 연결](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) 완전 한 UWP 앱의 컨텍스트에서 합니다.

[사용 하 여 Windows 런타임 DLL 구성 요소를 만드는 C++ 샘플](https://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)<br/>
Windows 런타임을 사용 하는 방법을 보여 줍니다 C++ 는 in-process DLL 구성 요소를 만들고에서 사용할 템플릿 라이브러리 C++/CX, JavaScript, 및 C#합니다.

[DirectX marble maze 게임 샘플](https://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)<br/>
Windows 런타임을 사용 하는 방법을 보여 줍니다 C++ 완전 한 3 차원 게임의 컨텍스트에서 DirectX 및 미디어 파운데이션 같은 COM 구성 요소의 수명을 관리 하는 템플릿 라이브러리입니다.

[샘플 데스크톱 앱에서에서 알림 보내기](https://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)<br/>
Windows 런타임을 사용 하는 방법을 보여 줍니다 C++ 데스크톱 앱에서 알림 메시지를 사용 하려면 템플릿 라이브러리입니다.

## <a name="windows-runtime-c-template-library-compared-to-atl"></a>Windows 런타임 C++ 과 ATL의 비교 하는 템플릿 라이브러리

Windows 런타임 C++ 템플릿 라이브러리 작고 빠른 COM 개체를 만들 사용할 수 있으므로 액티브 템플릿 라이브러리 (ATL)와 유사 합니다. Windows 런타임 C++ 템플릿 라이브러리 ATL 모듈, 인터페이스의 명시적 등록의에서 개체 정의 같은 개념을 공유 및 팩터리를 사용 하 여 개체 만들기를 엽니다. Windows 런타임으로 편할 수도 있습니다 C++ atl 익숙하다면 템플릿 라이브러리

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

[RuntimeClass](runtimeclass-class.md) 는 지정된 인터페이스 집합을 상속받는 인스턴스화된 클래스를 나타냅니다. `RuntimeClass` 개체 하나 이상의 Windows 런타임 COM 인터페이스 또는 구성 요소에 대 한 약한 참조에 대 한 지원의 조합을 제공할 수 있습니다.

### <a name="module"></a>Module

[Module](module-class.md) 은 관련 개체의 컬렉션을 나타냅니다. `Module` 개체는 개체를 생성하는 클래스 팩터리와, 다른 애플리케이션이 개체를 사용할 수 있도록 하는 등록을 관리합니다.

### <a name="callback"></a>Callback

[Callback](callback-function-wrl.md) 함수는 멤버 함수가 이벤트 처리기(콜백 메서드)인 개체를 생성합니다. `Callback` 함수를 사용하여 비동기 작업을 작성합니다.

### <a name="eventsource"></a>EventSource

[EventSource](eventsource-class.md) 는 *대리자* 이벤트 처리기를 관리하는 데 사용됩니다. Windows 런타임을 사용 하 여 C++ 대리자를 구현 하 고 사용 템플릿 라이브러리 `EventSource` 추가, 제거 및 대리자를 호출 합니다.

### <a name="asyncbase"></a>AsyncBase

[AsyncBase](asyncbase-class.md) Windows 런타임 비동기 프로그래밍 모델을 나타내는 가상 메서드를 제공 합니다. 비동기 작업을 시작, 중지하거나 작업의 진행률을 확인할 수 있는 사용자 지정 클래스를 만들려면 이 클래스의 멤버를 재정의합니다.

### <a name="ftmbase"></a>FtmBase

[FtmBase](ftmbase-class.md) 는 자유 스레드된 마샬러 개체를 나타냅니다. `FtmBase`는 GIT(전역 인터페이스 테이블)을 생성하고 마샬링 및 프록시 개체의 관리를 지원합니다.

### <a name="weakref"></a>WeakRef

[WeakRef](weakref-class.md) 는 액세스할 수 있거나 액세스하지 못할 수 있는 개체를 참조하는 *약한 참조*를 나타내는 스마트 포인터 형식입니다. `WeakRef` 클래식 COM. 아니라에 의해 Windows 런타임만 개체를 사용할 수 있습니다

`WeakRef` 개체는 일반적으로 외부 스레드나 애플리케이션에서 제어하는 개체를 나타냅니다. 예를 들어 `WeakRef` 개체는 파일 개체를 참조할 수 있습니다. 파일을 열면 `WeakRef` 가 유효해지고 참조 파일을 액세스할 수 있게 됩니다. 하지만 파일이 닫히면 `WeakRef` 가 무효가 되고 파일을 액세스할 수 없게 됩니다.

## <a name="related-topics"></a>관련 항목

|||
|-|-|
|[범주별 키 Api](key-wrl-apis-by-category.md)|기본 Windows 런타임 강조 표시 C++ 템플릿 라이브러리 형식, 함수 및 매크로입니다.|
|[참조](wrl-reference.md)|Windows 런타임에 대 한 참조 정보가 포함 되어 C++ 템플릿 라이브러리입니다.|
|[빠른 참조 (Windows 런타임 및 시각적 개체 C++)](../../cppcx/quick-reference-c-cx.md)|에 대해 간략하게 설명 합니다 C++Windows 런타임을 지 원하는 /CX 기능입니다.|
|[Windows 런타임 구성 요소를 사용 하 여 시각적 개체C++](/windows/uwp/winrt-components/walkthrough-creating-a-basic-windows-runtime-component-in-cpp-and-calling-it-from-javascript-or-csharp)|사용 하는 방법을 보여 줍니다 C++기본 Windows 런타임 구성 요소를 만드는 /CX입니다.|
