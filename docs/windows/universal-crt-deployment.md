---
title: 범용 CRT 배포
ms.date: 05/11/2018
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 7952d2ec6e8f502b0edf776811a492c67f495cce
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857240"
---
# <a name="universal-crt-deployment"></a>범용 CRT 배포

Visual Studio 2013을 통해 Visual Studio .NET에서 C++ 컴파일러 및 도구의 주요 릴리스는 Microsoft CRT(C 런타임) 라이브러리의 새 독립 실행형 버전을 포함합니다. 이러한 독립 실행형 버전의 CRT는 다양한 수준에서 서로에게 독립적이며 호환되지 않습니다. 예를 들어 Visual Studio 2012에서 사용하는 CRT 라이브러리는 msvcr110.dll이라는 버전 11이었으며, Visual Studio 2013에서 사용하는 CRT는 msvcr120.dll이라는 버전 12이었습니다. Visual Studio 2015부터 이제는 그렇지 않습니다. Visual Studio 2015 및 이후 버전의 Visual Studio는 모두 범용 CRT를 사용합니다.

범용 CRT는 Microsoft Windows 운영 체제 구성 요소입니다. 범용 CRT는 Windows 10 운영 체제의 일부로 포함되며, Windows 업데이트를 사용하여 Windows Vista부터 Windows 8.1까지 이전 운영 체제에서 사용할 수 있습니다. 또한 일부 제한 사항으로 범용 CRT의 로컬 배포가 지원됩니다.

## <a name="central-deployment"></a>중앙 배포

중앙에 범용 CRT를 설치하기 위해 선호하는 메서드는 Microsoft Windows Update를 사용하는 것입니다. 범용 CRT는 지원되는 모든 Microsoft Windows 운영 체제에 대해 권장되는 업데이트이므로 기본적으로 대부분의 컴퓨터가 정기 업데이트 프로세스의 일부로 를 이를 설치합니다. 범용 CRT의 초기 릴리스가 [KB2999226](https://support.microsoft.com/kb/2999226)이었고, 다양한 버그가 수정된 이후 업데이트는 [KB3118401](https://support.microsoft.com/kb/3118401)에서 이뤄졌으며, 추가 버그 수정과 새 기능을 통한 추가 업데이트가 있습니다. 최신 업데이트는 [support.microsoft.com](https://support.microsoft.com)에서 유니버설 C 런타임 또는 범용 CRT를 검색합니다.

일부 Microsoft Windows 컴퓨터는 Windows Update를 사용하여 정기적으로 업데이트를 설치하고, 일부는 모든 권장 업데이트를 설치하지 않을 수도 있습니다. 이러한 컴퓨터에서 Visual Studio 2015 및 최신 C++ 도구 집합을 사용하여 빌드된 애플리케이션의 사용을 지원하려면 오프라인 배포에 사용할 수 있는 범용 CRT 재배포 가능 패키지가 있습니다. 위의 KB 링크 중 하나에서 이러한 재배포 가능 패키지를 다운로드할 수 있습니다. 범용 CRT 재배포 가능 패키지는 컴퓨터가 현재 서비스 팩으로 업데이트될 것을 요구합니다. 따라서 예를 들어 Windows 7용 재배포 가능 패키지는 Windows 7 RTM이 아닌 Windows 7 SP1에만 설치됩니다.

유니버설 CRT의 기본 종속성 이므로 C++ 시각적 개체 라이브러리 C++ 재배포 가능 패키지 (VCRedist)는 버전이 이미 설치 되어 있지 않은 컴퓨터에서 유니버설 CRT (버전 10.0.10240)의 초기 버전을 설치 합니다. 이 버전을 충족 하기에 충분 합니다 C++ 라이브러리 종속성입니다. 응용 프로그램을 최신 버전의 유니버설 CRT에 의존 하는 경우에 완벽 하 게 최신 컴퓨터를 Windows 업데이트를 사용 하거나 명시적으로 해당 버전을 설치 해야 합니다. 가 이미 MSU 또는 Windows Update를 통해 방지 하 여 VCRedist를 설치 하기 전에 설치 된 유니버설 C 런타임 필요한 여러 번 다시 부팅 하는 것이 좋습니다.

일부 운영 체제는 Windows Update를 통해 최신 유니버설 C 런타임에 대 한 적합합니다. Windows 10에서 중앙에서 배포 된 버전의 운영 체제 버전을 찾습니다. 또한 유니버설 C 런타임 업데이트를 운영 체제를 업데이트 해야 합니다. Windows 8.1 통해 Windows Vista에 대 한 최신 사용 가능한 유니버설 C 런타임 추가 수정 (버전 10.0.14393)를 사용 하 여 Windows 10 1 주년 업데이트에 포함 된 버전에 따라 현재 됩니다.

## <a name="local-deployment"></a>로컬 배포

범용 UCRT의 로컬 배포가 지원되지만 성능 및 보안상의 이유로 권장되지 않습니다.  로컬 배포용 DLL은 컴퓨터 아키텍처에 의해 Windows Kits\\10\\Redist\\ucrt\\DLLs 하위 디렉터리에서 Windows SDK의 일부로 포함됩니다. 필요한 DLL에는 ucrtbase.dll 및 api-ms-win-\*.dll이라는 APISet 전달자 DLL 집합이 포함됩니다. 각 운영 체제에서 필요한 DLL 집합은 다르므로 로컬로 배포할 경우 모든 DLL을 포함하는 것이 매우 좋습니다.

주의해야 할 로컬 배포에 대한 두 가지 제한 사항이 있습니다.

- 애플리케이션이 범용 CRT의 애플리케이션 로컬 복사본을 포함하는 경우라도 Windows 10에서 시스템 디렉터리의 범용 CRT는 항상 사용됩니다. 범용 CRT의 로컬 복사본이 최신인 경우라도 마찬가지입니다. 이는 범용 CRT가 Windows 10에서 핵심 운영 체제 구성 요소이기 때문입니다.

- Windows 8 이전 Windows 버전에서 범용 CRT는 앱에 대한 주 실행 파일을 포함하는 디렉터리 이외 다른 디렉터리에 위치한 플러그인과 로컬로 패키지될 수 없습니다. 이 경우 APISet 전달자 DLL은 ucrtbase.dll을 성공적으로 해결할 수 없습니다. 일부 권장된 대체 솔루션은 다음과 같습니다.

  - 정적으로 범용 CRT에 연결하고,
  - 중앙에서 범용 CRT를 배포하거나
  - 범용 CRT 파일을 앱과 같은 디렉터리에 배치합니다.

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP에서 배포

Visual Studio 2015 및 Visual Studio 2017는 Microsoft Windows XP에서 사용을 위해 소프트웨어 개발을 계속 지원합니다. 이를 지원하려면 범용 CRT의 버전이 Microsoft Windows XP에서 작동해야 합니다. Microsoft Windows XP 운영 체제는 더 이상 기본 또는 확장 지원에 있지 않으므로 Microsoft Windows XP에서 범용 CRT의 중앙 배포는 다른 운영 체제와는 다릅니다.

Windows XP에 Visual C++ 재배포 가능 패키지가 설치될 때 모든 Windows 업데이트에 의존하거나 설지하지 않고 직접 범용 CRT 및 모든 해당 종속성을 시스템 디렉터리에 설치합니다. 재배포 가능 병합 모듈인 Microsoft_VC*버전*_CRT_\*.msm 파일은 동일한 작업을 수행 합니다.

Windows XP에서 범용 CRT의 로컬 배포는 다른 지원 운영 체제에서도 동일합니다.

## <a name="see-also"></a>참고자료

- [Visual C++의 개발](deployment-in-visual-cpp.md)
