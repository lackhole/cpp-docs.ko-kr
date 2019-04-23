---
title: '방법: WRL을 사용 하 여 이벤트를 처리 합니다.'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: 959a85d6cf6de666ae56d09035acefe9a3828ae8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033179"
---
# <a name="how-to-handle-events-using-wrl"></a>방법: WRL을 사용 하 여 이벤트를 처리 합니다.

이 문서에서는 Windows 런타임을 사용 하는 방법을 보여 줍니다. C++ 템플릿 라이브러리 (WRL) 구독 하 고 Windows 런타임 개체의 이벤트를 처리 합니다.

해당 구성 요소의 인스턴스를 만들고 속성 값을 검색 하는 보다 기본적인 예제를 보려면 [방법: 활성화 하 고 Windows 런타임 구성 요소를 사용 하 여](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)입니다.

## <a name="subscribing-to-and-handling-events"></a>구독 및 이벤트 처리

다음 단계는 시작을 `ABI::Windows::System::Threading::IDeviceWatcher` 개체 및 이벤트 처리기를 사용 하 여 진행 상황을 모니터링 합니다. `IDeviceWatcher` 인터페이스를 사용 하면 백그라운드에서 비동기적으로 또는 장치를 열거 하 고 장치는 추가, 제거 또는 변경 하는 경우 알림을 받을 수 있습니다. 합니다 [콜백](callback-function-wrl.md) 함수 이므로이 예의 중요 한 부분이 백그라운드 작업의 결과 처리 하는 이벤트 처리기를 지정할 수 있도록 합니다. 다음은 완성된 예제입니다.

> [!WARNING]
> 일반적으로 Windows 런타임 사용 하지만 C++ 유니버설 Windows 플랫폼 앱에서이 예제에서는 템플릿 라이브러리에 대 한 예시 콘솔 앱을 사용 합니다. 와 같은 함수 `wprintf_s` 는 유니버설 Windows 플랫폼 앱에서 사용할 수 없습니다. 형식 및 유니버설 Windows 플랫폼 앱에서 사용할 수 있는 함수에 대 한 자세한 내용은 참조 하세요. [유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) 하 고 [UWP 앱 용 Win32 및 COM](/uwp/win32-and-com/win32-and-com-for-uwp-apps)합니다.

1. 포함 (`#include`) Windows 런타임, Windows 런타임 필요한 C++ 템플릿 라이브러리 또는 C++ 표준 라이브러리 헤더입니다.

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` 장치를 열거 하는 데 필요한 형식을 선언 합니다.

   .cpp 파일의 `using namespace` 지시문을 활용하여 코드를 보다 읽기 쉽게 만드는 것이 좋습니다.

2. 앱에 대 한 로컬 변수를 선언 합니다. 이 예제에서는 열거 된 장치 및 나중에 이벤트를 구독 취소 수 있게 하는 등록 토큰 개수를 포함 합니다.

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. Windows 런타임을 초기화 합니다.

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. 만들기는 [이벤트](event-class-wrl.md) 주 앱은 열거 프로세스 완료를 동기화 하는 개체입니다.

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > 이 이벤트는 콘솔 앱의 일부로 데모입니다. 이 예제에서는 이벤트를 사용 하 여 앱 종료 하기 전에 비동기 작업이 완료 되도록 합니다. 대다수 앱에서 일반적으로 하지 때까지 기다리는 비동기 작업을 완료 합니다.

5. 에 대 한 활성화 팩터리를 만들기는 `IDeviceWatcher` 인터페이스입니다.

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Windows 런타임 형식을 식별 하려면 정규화 된 이름을 사용 합니다. `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` 매개 변수는 Windows 런타임에서 제공 하 고 필요한 런타임 클래스 이름을 포함 하는 문자열입니다.

6. `IDeviceWatcher` 개체를 만듭니다.

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. 사용 합니다 `Callback` 구독할 함수는 `Added`, `EnumerationCompleted`, 및 `Stopped` 이벤트입니다.

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   `Added` 이벤트 처리기에 열거 된 장치 수가 증가 합니다. 10 개의 장치가 발견 되 면 열거형 프로세스를 중지 합니다.

   `Stopped` 이벤트 처리기는 이벤트 처리기를 제거 하 고 완료 이벤트를 설정 합니다.

   `EnumerationCompleted` 열거형 프로세스를 중지 하는 이벤트 처리기입니다. 10 개 이하의 장치가 없는 경우이 이벤트를 처리 했습니다.

   > [!TIP]
   > 이 예제에서는 람다 식 콜백을 정의 합니다. 함수 개체 (함수), 함수 포인터를 이용할 수 있습니다 또는 [std:: function](../../standard-library/function-class.md) 개체입니다. 람다 식에 대한 자세한 내용은 [람다 식](../../cpp/lambda-expressions-in-cpp.md)을 참조하세요.

8. 열거형 프로세스를 시작 합니다.

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. 열거형 프로세스를 완료 한 다음 메시지를 인쇄 될 때까지 기다립니다. 모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

전체 예제는 다음과 같습니다.

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>코드 컴파일

컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 넣습니다 또는 라는 파일에 붙여 넣습니다 `wrl-consume-events.cpp` 다음 명령을 실행 하 고는 **Visual Studio 명령 프롬프트** 창입니다.

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>참고자료

[Windows 런타임 C++ 템플릿 라이브러리(WRL)](windows-runtime-cpp-template-library-wrl.md)