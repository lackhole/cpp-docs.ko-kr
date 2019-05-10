---
title: C/C++ side-by-side 어셈블리 빌드
ms.date: 11/04/2016
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
ms.openlocfilehash: d5d7652b6424177191275f8f80d7b1f6cf02b261
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221137"
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ side-by-side 어셈블리 빌드

[side-by-side-어셈블리](/windows/desktop/SbsCs/about-side-by-side-assemblies-) 리소스의 컬렉션인-Dll, windows 클래스, COM 서버, 형식 라이브러리 또는 인터페이스 그룹-런타임에 사용 하도록 응용 프로그램에서 사용할 수 있습니다. 어셈블리 Dll을 다시 패키징하지의 주요 이점은 업데이트가 릴리스되는 현재 설치 된 서비스 어셈블리에 있기를 동시에 응용 프로그램에서 어셈블리의 여러 버전을 사용할 수 있습니다는.

C++ 응용 프로그램 응용 프로그램의 다른 부분에 하나 이상의 Dll을 사용할 수 있습니다. 런타임 시 Dll은 주 프로세스에 로드 하 고 필요한 코드가 실행 됩니다. 응용 프로그램은 필요한 Dll을 찾는 다른 종속 Dll을 들이 어떻게 로드 되 고 요청된 된 DLL과 함께 로드 합니다 이해를 운영 체제입니다. Windows 운영 체제 버전에서 Windows XP, Windows Server 2003 및 Windows Vista 보다 이전 운영 체제 로더에 검색 응용 프로그램의 로컬 폴더 또는 시스템 경로에 지정 된 다른 폴더에 종속 Dll에 대 한 합니다. Windows XP, Windows Server 2003 및 Windows Vista에서 운영 체제 로더를 사용 하 여 종속 Dll에 대 한 검색할 수도 있습니다는 [매니페스트](/windows/desktop/sbscs/manifests) 파일 및 이러한 Dll을 포함 하는 side-by-side-어셈블리를 검색 합니다.

기본적으로 Visual Studio를 사용 하 여 DLL를 빌드할 때에 [응용 프로그램 매니페스트](/windows/desktop/SbsCs/application-manifests) ID가 2 RT_MANIFEST 리소스로 포함 합니다. 이 매니페스트 파일과 마찬가지로 개발자가 다른 어셈블리에이 DLL의 종속성을 설명합니다. DLL side-by-side-어셈블리의 일부가 아닙니다.이 DLL에 종속 된 응용 프로그램을 로드 하는 대신 운영 체제 로더에 시스템 경로에이 DLL을 찾을 수에 따라 응용 프로그램 매니페스트를 사용 하지 않는 되었다고 가정 합니다.

> [!NOTE]
> ID가 2 인 리소스로 포함 된 매니페스트가 있어야 응용 프로그램 매니페스트를 사용 하는 DLL에 대 한 것입니다. 런타임에 동적으로 DLL을 로드 하는 경우 (예를 들어,를 사용 하 여는 [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya) 함수), 운영 체제 로더에 DLL의 매니페스트에 지정 하는 종속 어셈블리를 로드 합니다. Dll에 대 한 외부 응용 프로그램 매니페스트 하는 동안 선택 하지 않으면는 `LoadLibrary` 호출 합니다. 매니페스트에 포함 되지 않은 경우 로더는 잘못 된 버전의 어셈블리를 로드 하거나 종속 어셈블리를 찾지 못했습니다. 시도할 수 있습니다.

하나 이상의 관련 해당 side-by-side-어셈블리에 Dll을 재구성할 수 있습니다 [어셈블리 매니페스트](/windows/desktop/SbsCs/assembly-manifests)를 설명 하는 다른-side-by-side에 대 한 어셈블리의 종속성 뿐만 아니라 어셈블리를 형성 하는 파일 어셈블리입니다.

> [!NOTE]
> 포함 된 하나의 DLL을 어셈블리, ID가 1 인 리소스로이 DLL에 어셈블리 매니페스트를 포함 하 여 전용 어셈블리는 DLL과 같은 이름을 지정 하는 것이 좋습니다. 예를 들어, DLL의 이름이 mylibrary.dll 인 경우 이름 특성의 값에 사용 된 \<assemblyIdentity > 매니페스트의 요소 mylibrary 수도 있습니다. 경우에 따라 라이브러리 확장명이.dll이 아닌 경우 (예:.ocx 라이브러리를 만듭니다 MFC ActiveX 컨트롤 프로젝트를) 외부 어셈블리 매니페스트를 만들 수 있습니다. 이 경우 어셈블리 및 매니페스트 이름 (예: MyAssembly, MyAssembly.manifest, 및 mylibrary.ocx) DLL의 이름과 달라 야 합니다. 그러나 것이 좋습니다는 extension.dll 있고이 어셈블리의 향후 유지 관리 비용을 줄이기 위해 리소스로 매니페스트를 포함 하는 이러한 라이브러리의 이름을 바꾸려면 합니다. 운영 체제 전용 어셈블리를 검색 하는 방법에 대 한 자세한 내용은 참조 하세요. [어셈블리 검색 시퀀스](/windows/desktop/SbsCs/assembly-searching-sequence)합니다.

이 변경으로 해당 Dll의 배포를 허용할 수 있습니다는 [전용 어셈블리](/windows/desktop/Msi/private-assemblies) 또는 응용 프로그램 로컬 폴더에는 [어셈블리를 공유](/windows/desktop/Msi/shared-assemblies) WinSxS 어셈블리 캐시에 있습니다. 몇 가지 단계를이 새 어셈블리의 정확한 런타임 동작을 달성 하기 위해 수행 해야 합니다. 에 설명 되어 [Creating side-by-side-어셈블리에 대 한 지침](/windows/desktop/SbsCs/guidelines-for-creating-side-by-side-assemblies)합니다. 어셈블리를 올바르게 작성 후 중 하나는 공유 또는 전용 어셈블리에 종속 된 응용 프로그램과 함께 배포 수 있습니다. 중 하나에 설명 된 지침에 따라 공유 어셈블리로 side-by-side-어셈블리를 설치할 때 할 [Windows XP에서 Side-by-side-공유에 대 한 Win32 어셈블리 설치](/windows/desktop/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp) 사용할지 [병합 모듈](/windows/desktop/msi/merge-modules). Side-by-side-어셈블리를 전용 어셈블리로 설치할 때 있습니다 복사 하기만 설치 프로세스의 일부로 해당 DLL, 리소스 및 어셈블리 매니페스트를 대상 컴퓨터의 응용 프로그램 로컬 폴더에이 어셈블리 수 있음을 보장 합니다. 런타임 시 로더가 찾을 (참조 [어셈블리 검색 시퀀스](/windows/desktop/SbsCs/assembly-searching-sequence)). 또 다른 방법은 사용 하는 것 [Windows Installer](/windows/desktop/Msi/windows-installer-portal) 에 설명 된 지침을 따릅니다 [Windows XP에서 응용 프로그램의 개인 용도로 Win32 어셈블리 설치](/windows/desktop/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp)합니다.

## <a name="see-also"></a>참고자료

[ 격리된 응용 프로그램 빌드](building-c-cpp-isolated-applications.md)<br/>
[C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
