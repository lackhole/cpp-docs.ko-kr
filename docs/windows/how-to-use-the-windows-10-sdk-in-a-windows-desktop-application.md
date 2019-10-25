---
title: '방법: Windows 데스크톱 응용 프로그램에서 Windows 10 SDK 사용'
ms.custom: get-started-article
ms.date: 07/12/2018
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
ms.openlocfilehash: 8dbf18d24c0369507743c3c1da624838f9ab4703
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69513827"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>방법: Windows 데스크톱 응용 프로그램에서 Windows 10 SDK 사용

Visual Studio 2017에 클래식 Windows 데스크톱 프로젝트를 만들 때 설정은 기본적으로 C++ 데스크톱 작업 설치 또는 마지막으로 업데이트되었을 때 설치된 Windows 10 SDK의 버전으로 만들 수 있습니다. 이 Windows SDK 버전은 Windows 7 이상과 호환 됩니다. 특정 버전의 Windows를 대상으로 지정 하는 방법에 대 한 자세한 내용은 [Windows 헤더 사용](/windows/win32/WinProg/using-the-windows-headers) 을 참조 하세요.

이전 버전의 SDK를 대상으로 하려는 경우 프로젝트를 열 수 있습니다. **| 속성** 을 선택 하 고 Windows SDK 버전 드롭다운에서 사용할 수 있는 다른 SDK 버전을 선택 합니다.

Visual Studio 2015 및 Windows 10 SDK부터는 CRT 라이브러리가 두 부분으로 분리되었는데, 하나(ucrtbase)는 유니버설 Windows 앱에서 허용되는 함수를 포함하고 나머지는 이외의 모든 항목이 포함된 다른 부분(vcruntime140)입니다. Windows 10 SDK 이후로는 다수의 C99 함수와 같은 새로운 함수가 있으며, 이러한 함수를 사용하려면 다음 단계를 따라야 합니다. [CRT Library Features](../c-runtime-library/crt-library-features.md)을 참조하세요.

### <a name="to-target-the-windows-10-sdk"></a>Windows 10 SDK를 대상으로 하려면

1. Windows 10 SDK가 설치되었는지 확인합니다. Windows 10 SDK는 워크 로드 **를 사용 하 C++ 여 데스크톱 개발** 의 일부로 설치 됩니다. 독립 실행형 버전은 [Windows 10 용 다운로드 및 도구](https://developer.microsoft.com/windows/downloads)에서 사용할 수 있습니다.

2. 프로젝트 노드에 대한 바로 가기 메뉴를 열고 **SDK 버전 대상 다시 지정**을 선택합니다.

   ![SDK 버전 대상 변경 ](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")

   **솔루션 작업 검토** 대화 상자가 나타납니다.

   ![솔루션 작업 검토](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")

3. 에 **대상 플랫폼 버전** 드롭다운 목록에서 대상으로 하려는 Windows 10 SDK의 버전을 선택합니다. 확인 단추를 선택하여 변경 내용을 적용합니다.

   이 컨텍스트에서 8.1이란 Windows SDK를 말하며 이는 또는 Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 및 Windows Vista와 이전 버전 호환성을 가집니다.

   이 단계에 성공한 경우 출력 창에 다음 텍스트가 나타납니다.

   `Retargeting End: 1 completed, 0 failed, 0 skipped`

4. 프로젝트 속성을 열고 **구성 속성, 일반** 섹션에서 **Windows 대상 플랫폼 버전**의 값을 확인합니다. 여기서 이 값을 변경하면 이 절차를 따르는 것과 효과가 같습니다. [General Property Page (Project)](../build/reference/general-property-page-project.md)을 참조하세요.

   ![대상 플랫폼 버전](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")

   이 작업은 헤더 파일 및 라이브러리 파일에 대한 경로가 포함된 프로젝트 매크로의 값을 변경합니다. 변경 내용을 확인 하려면 **프로젝트 속성** 대화 **상자의 C++ 시각적 디렉터리** 섹션에서 **포함 디렉터리**와 같은 속성 중 하나를 선택 하 고 드롭다운 목록을 \<열고 > 편집을 선택 합니다. **포함 디렉터리** 대화 상자가 나타납니다.

   ![포함 디렉터리 대화 상자](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")

   **매크로 > >** 단추를 선택 하 고 매크로 목록에서 Windows SDK 매크로로 스크롤하여 모든 새 값을 확인 합니다.

   ![Windows SDK 매크로](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")

5. 필요에 따라 다른 프로젝트에 대해 이 작업을 반복하고 솔루션을 다시 빌드합니다.

### <a name="to-target-the-windows-81-sdk"></a>Windows 8.1 SDK를 대상으로 하려면

1. 프로젝트 노드에 대한 바로 가기 메뉴를 열고 **SDK 버전 대상 다시 지정**을 선택합니다.

2. **대상 플랫폼 버전** 드롭다운 목록에서 **8.1**를 선택 합니다.

## <a name="see-also"></a>참고 항목

[Windows 데스크톱 응용 프로그램 (Visual C++)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)