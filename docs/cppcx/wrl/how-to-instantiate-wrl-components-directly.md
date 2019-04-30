---
title: '방법: 직접 WRL 구성 요소 인스턴스화'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: 3f622a79aed6a1e42feccb92e1a01b3bc1277151
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398305"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>방법: 직접 WRL 구성 요소 인스턴스화

Windows 런타임을 사용 하는 방법을 알아봅니다 C++ 템플릿 라이브러리 (WRL)[Microsoft::WRL::Make](make-function.md) 하 고 [Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md) 모듈에서 구성 요소를 인스턴스화하는 함수 정의합니다.

구성 요소를 직접 인스턴스화한 줄일 수 있습니다 오버 헤드가 클래스 팩터리 또는 다른 메커니즘이 필요 하지 않을 때입니다. 구성 요소 모두 유니버설 Windows 플랫폼 앱 및 데스크톱 앱에서 직접 인스턴스화할 수 있습니다.

Windows 런타임을 사용 하는 방법을 알아보려면 C++ 클래식 COM 구성 요소를 만들고 외부 데스크톱 앱에서 인스턴스화할 템플릿 라이브러리 참조 [방법: 클래식 COM 구성 요소를 만드는](how-to-create-a-classic-com-component-using-wrl.md)합니다.

이 문서에서는 두 가지 예제를 보여 줍니다. 사용 하 여 첫 번째 예제는 `Make` 구성 요소를 인스턴스화하는 함수입니다. 사용 하 여 두 번째 예제는 `MakeAndInitialize` 를 생성 하는 동안 실패할 수 있는 구성 요소를 인스턴스화하는 함수입니다. (일반적으로 COM 예외 대신 HRESULT 값을 사용 하 여, 때문에 오류를 나타내지만 COM 형식이 일반적으로 throw 하지 않습니다 해당 생성자에서. `MakeAndInitialize` 구성 요소를 통해 생성 인수 유효성 검사를 사용 하도록 설정 된 `RuntimeClassInitialize` 메서드.) 두 예제 모두 기본로 거 인터페이스를 정의 하 고 콘솔에 메시지를 기록 하는 클래스를 정의 하 여 해당 인터페이스를 구현 합니다.

> [!IMPORTANT]
> 사용할 수 없습니다는 `new` 연산자 Windows 런타임 인스턴스화를 C++ 템플릿 라이브러리 구성 요소입니다. 항상 사용 하는 권장 따라서 `Make` 또는 `MakeAndInitialize` 구성 요소를 직접 인스턴스화할 수 있습니다.

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>만들고 기본로 거 구성 요소 인스턴스화

1. Visual Studio에서 만들기를 **Win32 콘솔 응용 프로그램** 프로젝트입니다. 예를 들어, 프로젝트 이름을 *WRLLogger*합니다.

2. 추가 **Midl 파일 (.idl)** 파일을 프로젝트, 파일 이름을 `ILogger.idl`,이 코드를 추가 합니다.

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. 다음 코드를 사용 하 여의 내용을 바꿉니다 `WRLLogger.cpp`합니다.

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>기본로 거 구성 요소에 대 한 생성 오류를 처리 하려면

1. 다음 코드를 사용 하 여 정의 바꾸려면는 `CConsoleWriter` 클래스입니다. 이 버전 보유 개인 문자열 멤버 변수와 재정의 `RuntimeClass::RuntimeClassInitialize` 메서드. `RuntimeClassInitialize` 실패에 대 한 호출 `SHStrDup` 실패 합니다.

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. 다음 코드를 사용 하 여 정의 바꾸려면 `wmain`합니다. 이 버전은 사용 `MakeAndInitialize` 인스턴스화하는 `CConsoleWriter` 개체 및 HRESULT 결과 확인 합니다.

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>참고자료

[Windows 런타임 C++ 템플릿 라이브러리(WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft::WRL::Make](make-function.md)<br/>
[Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md)