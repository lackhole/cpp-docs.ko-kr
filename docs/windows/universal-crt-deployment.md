---
title: 범용 CRT 배포
ms.date: 05/11/2018
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 1f6e685cca65c4b31ac2e6147341c4b5a3fe8228
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344455"
---
# <a name="universal-crt-deployment"></a>범용 CRT 배포

Visual Studio 2013을 통해 Visual Studio .NET에서 C++ 컴파일러 및 도구의 주요 릴리스는 Microsoft CRT(C 런타임) 라이브러리의 새 독립 실행형 버전을 포함합니다. 이러한 독립 실행형 버전의 CRT는 다양한 수준에서 서로에게 독립적이며 호환되지 않습니다. 예를 들어 Visual Studio 2012에서 사용하는 CRT 라이브러리는 msvcr110.dll이라는 버전 11이었으며, Visual Studio 2013에서 사용하는 CRT는 msvcr120.dll이라는 버전 12이었습니다. Visual Studio 2015부터 더 이상 경우. Visual Studio 2015 및 이후 버전의 Visual Studio는 모두 범용 CRT를 사용합니다.

유니버설 CRT는 Windows 10 운영 체제의 일부로 포함 된 Microsoft Windows 운영 체제 구성 요소입니다. 이 제품은 Windows 8.1 통해 Windows Vista 이전 운영 체제에 대 한 Windows 업데이트를 사용 하 여입니다. 유니버설 CRT의 로컬 배포는 몇 가지 제한 사항이 지원 됩니다.

## <a name="central-deployment"></a>중앙 배포

중앙에 범용 CRT를 설치하기 위해 선호하는 메서드는 Microsoft Windows Update를 사용하는 것입니다. 범용 CRT는 지원되는 모든 Microsoft Windows 운영 체제에 대해 권장되는 업데이트이므로 기본적으로 대부분의 컴퓨터가 정기 업데이트 프로세스의 일부로 를 이를 설치합니다. 유니버설 CRT의 초기 릴리스 이었습니다 [KB2999226](https://support.microsoft.com/kb/2999226)합니다. 다양 한 버그 수정을 이후의 업데이트에서 만들어졌습니다 [KB3118401](https://support.microsoft.com/kb/3118401), 및 추가 버그 수정 및 새로운 기능을 사용 하 여 추가 업데이트 되었습니다. 최신 업데이트는 [support.microsoft.com](https://support.microsoft.com)에서 유니버설 C 런타임 또는 범용 CRT를 검색합니다.

일부 Microsoft Windows 컴퓨터는 Windows Update를 사용하여 정기적으로 업데이트를 설치하고, 일부는 모든 권장 업데이트를 설치하지 않을 수도 있습니다. Visual Studio 2015를 사용 하 여 작성 되 고 이후 응용 프로그램의 사용을 지원 하도록 C++ 도구 집합 해당 컴퓨터에서 가지 유니버설 CRT 재배포 가능 파일이 오프 라인 배포를 위해 사용할 수 있습니다. 위의 KB 링크 중 하나에서 이러한 재배포 가능 파일을 다운로드할 수 있습니다. 유니버설 CRT 재배포 가능 패키지는 컴퓨터는 현재 서비스 팩으로 업데이트 된는 필요 합니다. 따라서 예를 들어 Windows 7용 재배포 가능 패키지는 Windows 7 RTM이 아닌 Windows 7 SP1에만 설치됩니다.

유니버설 CRT의 기본 종속성 이므로 C++ 시각적 개체 라이브러리 C++ 재배포 가능 패키지 (VCRedist)는 유니버설 CRT (버전 10.0.10240)의 초기 버전 없는 설치 된 컴퓨터에 설치 합니다. 이 버전을 충족 하기에 충분 합니다 C++ 라이브러리 종속성입니다. 응용 프로그램을 최신 버전의 유니버설 CRT에 의존 하는 경우에 완벽 하 게 최신 컴퓨터를 Windows 업데이트를 사용 하거나 명시적으로 해당 버전을 설치 해야 합니다. 다시 부팅 필요 잠재적인 여러 하지 않으려면 VCRedist를 설치 하기 전에 Windows 업데이트 또는 MSU를 통해 유니버설 C 런타임을 설치 하는 것이 좋습니다.

일부 운영 체제는 Windows Update를 통해 최신 유니버설 C 런타임에 대 한 적합합니다. Windows 10에서 중앙에서 배포 된 버전의 운영 체제 버전을 찾습니다. 또한 유니버설 C 런타임 업데이트를 운영 체제를 업데이트 해야 합니다. Windows 8.1 통해 Windows Vista에 대 한 최신 사용 가능한 유니버설 C 런타임 추가 수정 (버전 10.0.14393)를 사용 하 여 Windows 10 1 주년 업데이트에 포함 된 버전에 따라 현재 됩니다.

## <a name="local-deployment"></a>로컬 배포

범용 UCRT의 로컬 배포가 지원되지만 성능 및 보안상의 이유로 권장되지 않습니다. 로컬 배포용 DLL은 컴퓨터 아키텍처에 의해 Windows Kits\\10\\Redist\\ucrt\\DLLs 하위 디렉터리에서 Windows SDK의 일부로 포함됩니다. 필요한 DLL에는 ucrtbase.dll 및 api-ms-win-\*.dll이라는 APISet 전달자 DLL 집합이 포함됩니다. 각 운영 체제에서 필요한 Dll 집합이 달라 집니다. 포함 하는 모든 Dll 로컬로 배포 하는 경우 것이 좋습니다.

주의해야 할 로컬 배포에 대한 두 가지 제한 사항이 있습니다.

- 애플리케이션이 범용 CRT의 애플리케이션 로컬 복사본을 포함하는 경우라도 Windows 10에서 시스템 디렉터리의 범용 CRT는 항상 사용됩니다. 로컬 복사본은 유니버설 CRT에 Windows 10에서 핵심 운영 체제 구성 요소 이므로, 경우에 그렇습니다.

- Windows 8 이전 Windows 버전에서 유니버설 CRT 패키지할 수 없습니다 로컬 플러그 인을 사용 하 여 실행 하면 주 응용 프로그램의 디렉터리 아닌 디렉터리에 있는 경우. 이 경우 APISet 전달자 DLL은 ucrtbase.dll을 성공적으로 해결할 수 없습니다. 일부 권장된 대체 솔루션은 다음과 같습니다.

  - 정적으로 범용 CRT에 연결하고,
  - 중앙에서 범용 CRT를 배포하거나
  - 범용 CRT 파일을 앱과 같은 디렉터리에 배치합니다.

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP에서 배포

Visual Studio 2015 및 Visual Studio 2017는 Microsoft Windows XP에서 사용을 위해 소프트웨어 개발을 계속 지원합니다. 이 개발을 지원 하려면 유니버설 crt 버전을 Microsoft Windows XP에서 작동 합니다. Microsoft Windows XP 운영 체제는 더 이상 기본 또는 확장 지원에 있지 않으므로 Microsoft Windows XP에서 범용 CRT의 중앙 배포는 다른 운영 체제와는 다릅니다.

때 시각적 개체 C++ Windows XP에 설치 된 재배포 가능 패키지, 직접 시스템 디렉터리에 모든 종속성 및 유니버설 CRT를 설치 합니다. 설치 또는 Windows 업데이트에 종속 되지 않습니다. 재배포 가능 병합 모듈인 Microsoft_VC*버전*_CRT_\*.msm 파일은 동일한 작업을 수행 합니다.

Windows XP에서 범용 CRT의 로컬 배포는 다른 지원 운영 체제에서도 동일합니다.

## <a name="see-also"></a>참고자료

- [Visual C++의 개발](deployment-in-visual-cpp.md)
