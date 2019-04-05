---
title: '연습: WRL 및 Media Foundation을 사용 하 여 UWP 앱 만들기'
ms.date: 09/17/2018
ms.topic: reference
ms.assetid: 0336c550-fbeb-4dc4-aa9b-660f9fc45382
ms.openlocfilehash: e0254be8c6fa185f75c46898d4da51742195550a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036038"
---
# <a name="walkthrough-creating-a-uwp-app-using-wrl-and-media-foundation"></a>연습: WRL 및 Media Foundation을 사용 하 여 UWP 앱 만들기

사용 하는 유니버설 Windows 플랫폼 (UWP) 앱을 만들려면 Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하는 방법을 알아봅니다 [Microsoft 미디어 파운데이션](/windows/desktop/medfound/microsoft-media-foundation-sdk)합니다.

이 예제에서는 웹캠에서 캡처된 이미지에 회색조 효과를 적용하는 사용자 지정 Media Foundation 변형을 만듭니다. 앱에서는 C++를 사용하여 사용자 지정 변환을 정의하고, C#을 사용하여 구성 요소를 통해 캡처된 이미지를 변환합니다.

> [!NOTE]
> C# 대신 JavaScript, Visual Basic 또는 C++를 사용하여 사용자 지정 변환 구성 요소를 사용할 수도 있습니다.

대부분의 경우에서 다음을 사용할 수 있습니다 C + + /cli CX Windows Runtime을 만듭니다. 그러나 때로는 해야 WRL을 사용 합니다. 예를 들어, Microsoft Media Foundation 용 미디어 확장을 만들 때 COM 및 Windows 런타임 인터페이스를 구현 하는 구성 요소를 만들어야 합니다. 때문에 C + + /cli 미디어 확장을 만들려면 사용 해야 COM 및 Windows 런타임 인터페이스의 구현을 수 있기 때문에 WRL 합니다 CX만 Windows 런타임 개체를 만들 수 있습니다.

> [!NOTE]
> 이 코드 예제는 길지만, 유용한 Media Foundation 변환을 만드는 데 필요한 최소한의 코드를 보여 줍니다. 이를 사용자 지정 변형의 시작점으로 사용할 수 있습니다. 이 예제는 합니다 [미디어 확장명 샘플](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096), 비디오에 영향을 적용 하는 사용 하 여 미디어 확장, 비디오, 디코딩 및 미디어 스트림을 생성 하는 스키마 처리기를 만듭니다.

## <a name="prerequisites"></a>전제 조건

- 경험이 합니다 [Windows 런타임](https://msdn.microsoft.com/library/windows/apps/br211377.aspx)합니다.

- COM 경험

- 웹캠

## <a name="key-points"></a>주요 사항

- 사용자 지정 Media Foundation 구성 요소를 만들려면 MIDL(Microsoft Interface Definition Language) 정의 파일을 사용하여 인터페이스를 정의하고 해당 인터페이스를 구현한 후 다른 구성 요소에서 활성화할 수 있도록 합니다.

- 합니다 `namespace` 하 고 `runtimeclass` 특성 및 `NTDDI_WIN8` [버전](/windows/desktop/Midl/version) 특성 값은 WRL을 사용 하는 Media Foundation 구성 요소에 대 한 MIDL 정의의 중요 한 부분입니다.

- [Microsoft::WRL::RuntimeClass](runtimeclass-class.md) 사용자 지정 Media Foundation 구성 요소에 대 한 기본 클래스입니다. 합니다 [Microsoft::WRL::RuntimeClassType::WinRtClassicComMix](runtimeclasstype-enumeration.md) 템플릿 인수로 제공 하는 열거형 값을 사용 하 여 Windows 런타임 클래스 및 클래식 COM 런타임 클래스 둘 다에 대 한 클래스를 표시 합니다.

- 합니다 [InspectableClass](inspectableclass-macro.md) 매크로 참조 계산과 같은 기본 COM 기능을 구현 하며 `QueryInterface` 메서드 및 런타임 클래스 이름 및 신뢰 수준을 설정 합니다.

- microsoft:: wrl을 사용 하 여::[모듈 클래스](module-class.md) 과 같은 DLL 진입점 함수를 구현 하려면 [DllGetActivationFactory](https://msdn.microsoft.com/library/br205771.aspx)를 [DllCanUnloadNow](/windows/desktop/api/combaseapi/nf-combaseapi-dllcanunloadnow), 및 [ DllGetClassObject](/windows/desktop/api/combaseapi/nf-combaseapi-dllgetclassobject)합니다.

- 구성 요소 DLL을 runtimeobject.lib에 연결합니다. 또한 지정할 [/WINMD](../../cppcx/compiler-and-linker-options-c-cx.md) Windows 메타 데이터를 생성할 링커 줄에 있습니다.

- WRL 구성 요소를 UWP 앱에 액세스할 수 있도록 하려면 프로젝트 참조를 사용 합니다.

### <a name="to-use-the-wrl-to-create-the-media-foundation-grayscale-transform-component"></a>사용 하는 Media Foundation 회색조를 만들려면 WRL 구성 요소를 변환

1. Visual Studio에서 만들기를 **빈 솔루션** 프로젝트입니다. 예를 들어, 프로젝트 이름을 *MediaCapture*합니다.

1. 추가 된 **DLL (유니버설 Windows)** 프로젝트를 솔루션입니다. 예를 들어, 프로젝트 이름을 *GrayscaleTransform*합니다.

1. 추가 된 **Midl 파일 (.idl)** 프로젝트 파일입니다. 예를 들어, 파일 이름을 *GrayscaleTransform.idl*합니다.

1. 이 코드를 GrayscaleTransform.idl에 추가 합니다.

   [!code-cpp[wrl-media-capture#1](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_1.idl)]

1. 다음 코드를 사용 하 여의 내용을 바꿉니다 `pch.h`:

   [!code-cpp[wrl-media-capture#2](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_2.h)]

1. 새 헤더 파일을 프로젝트에 추가 하 고 이름을 `BufferLock.h`, 내용을이 코드로 바꿉니다.

   [!code-cpp[wrl-media-capture#3](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_3.h)]

1. `GrayscaleTransform.h` 이 예제에서 사용 되지 않습니다. 원하는 경우 프로젝트에서 제거할 수 있습니다.

1. 다음 코드를 사용 하 여의 내용을 바꿉니다 `GrayscaleTransform.cpp`:

   [!code-cpp[wrl-media-capture#4](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_4.cpp)]

1. 새 모듈 정의 파일을 프로젝트에 추가 하 고 이름을 `GrayscaleTransform.def`,이 코드를 추가 합니다.

   ```
   EXPORTS
       DllCanUnloadNow                     PRIVATE
       DllGetActivationFactory             PRIVATE
       DllGetClassObject                   PRIVATE
   ```

1. 다음 코드를 사용 하 여의 내용을 바꿉니다 `dllmain.cpp`:

   [!code-cpp[wrl-media-capture#6](../codesnippet/CPP/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_6.cpp)]

1. 프로젝트의 **속성 페이지** 대화 상자에서 다음 설정 **링커** 속성입니다.

   1. 아래 **입력**에 대 한 합니다 **모듈 정의 파일**를 지정 `GrayScaleTransform.def`합니다.

   1. 또한 아래에 있는 **입력**, 추가 `runtimeobject.lib`, `mfuuid.lib`, 및 `mfplat.lib` 에 **추가 종속성** 속성입니다.

   1. 아래 **Windows 메타 데이터**설정 **Windows 메타 데이터 생성** 하 **예 (/ WINMD)** 합니다.

### <a name="to-use-the-wrl-the-custom-media-foundation-component-from-a-c-app"></a>WRL C# 앱에서 사용자 지정 Media Foundation 구성 요소를 사용 하려면

1. 새 **C# 빈 앱 (유니버설 Windows)** 프로젝트를 `MediaCapture` 솔루션입니다. 예를 들어, 프로젝트 이름을 *MediaCapture*합니다.

1. 에 **MediaCapture** 프로젝트에 대 한 참조를 추가 합니다는 `GrayscaleTransform` 프로젝트입니다. 자세한 내용은 [방법: 참조 관리자를 사용하여 참조 추가 또는 제거](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager).

1. `Package.appxmanifest`에 **기능** 탭을 선택 **마이크** 하 고 **웹캠**. 두 기능 모두 웹캠에서 사진을 캡처하는 데 필요합니다.

1. `MainPage.xaml`, 루트에이 코드를 추가 [Grid](https://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.grid.aspx) 요소:

   [!code-xml[wrl-media-capture#7](../codesnippet/Xaml/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_7.xaml)]

1. 다음 코드를 사용 하 여의 내용을 바꿉니다 `MainPage.xaml.cs`:

   [!code-cs[wrl-media-capture#8](../codesnippet/CSharp/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation_8.cs)]

다음 그림에 표시 된 `MediaCapture app`합니다.

![사진을 캡처하는 MediaCapture 앱](../media/wrl_media_capture.png "WRL_Media_Capture")

## <a name="next-steps"></a>다음 단계

이 예제에서는 기본 웹캠에서 한 번에 하나씩 사진을 캡처하는 방법을 보여 줍니다. 합니다 [미디어 확장명 샘플](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096) 많은 기능을 수행 합니다. 웹캠 장치를 열거하고 로컬 스키마 처리기를 사용하는 방법을 보여 주며, 개별 사진과 비디오 스트림 모두에서 작동하는 추가 미디어 효과를 보여 줍니다.

## <a name="see-also"></a>참고자료

[Windows 런타임 C++ 템플릿 라이브러리(WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft Media Foundation](/windows/desktop/medfound/microsoft-media-foundation-sdk)<br/>
[미디어 확장명 샘플](http://code.msdn.microsoft.com/windowsapps/Media-extensions-sample-7b466096)