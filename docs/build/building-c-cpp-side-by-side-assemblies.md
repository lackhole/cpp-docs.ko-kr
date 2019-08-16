---
title: C/C++ side-by-side 어셈블리 빌드
ms.date: 11/04/2016
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
ms.openlocfilehash: 6e49ba72a397efb97437a2f7e6d721c782875c48
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493335"
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ side-by-side 어셈블리 빌드

[Side-by-side 어셈블리](/windows/win32/SbsCs/about-side-by-side-assemblies-) 는 런타임에 사용할 응용 프로그램에 사용할 수 있는 리소스 (예를 들어, dll 그룹, windows 클래스, COM 서버, 형식 라이브러리 또는 인터페이스)의 컬렉션입니다. 어셈블리에서 다시 패키지 Dll의 주요 이점은 응용 프로그램에서 여러 버전의 어셈블리를 동시에 사용할 수 있으며 업데이트 릴리스가 있을 경우 현재 설치 된 어셈블리를 서비스 하는 것입니다.

응용 C++ 프로그램은 응용 프로그램의 여러 부분에서 하나 이상의 dll을 사용할 수 있습니다. 런타임에 Dll이 주 프로세스로 로드 되 고 필요한 코드가 실행 됩니다. 응용 프로그램은 운영 체제를 사용 하 여 요청 된 Dll을 찾고, 로드 해야 하는 다른 종속 Dll을 이해 한 다음 요청 된 DLL과 함께 로드 해야 합니다. Windows XP, Windows Server 2003, Windows Vista 이전 버전의 Windows 운영 체제에서는 운영 체제 로더가 응용 프로그램의 로컬 폴더 또는 시스템 경로에 지정 된 다른 폴더에서 종속 Dll을 검색 합니다. Windows XP, Windows Server 2003 및 Windows Vista에서 운영 체제 로더는 [매니페스트](/windows/win32/sbscs/manifests) 파일을 사용 하 여 종속 dll을 검색 하 고 이러한 dll을 포함 하는 side-by-side 어셈블리를 검색할 수도 있습니다.

기본적으로 Visual Studio를 사용 하 여 DLL을 빌드하면 ID가 2 인 RT_MANIFEST 리소스로 [응용 프로그램 매니페스트가](/windows/win32/SbsCs/application-manifests) 포함 됩니다. 실행 파일의 경우와 마찬가지로이 매니페스트는 다른 어셈블리의이 DLL에 대 한 종속성을 설명 합니다. 이는 DLL이 side-by-side 어셈블리의 일부가 아니고이 DLL에 종속 된 응용 프로그램에서 응용 프로그램 매니페스트를 사용 하 여 로드 하지 않고 시스템 경로에서이 DLL을 찾기 위해 운영 체제 로더를 사용 하는 것으로 가정 합니다.

> [!NOTE]
> 응용 프로그램 매니페스트를 사용 하는 DLL에서 ID가 2 인 리소스로 매니페스트를 포함 하는 것이 중요 합니다. DLL이 런타임에 동적으로 로드 되는 경우 (예: [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) 함수 사용) 운영 체제 로더는 dll의 매니페스트에 지정 된 종속 어셈블리를 로드 합니다. Dll에 대 한 외부 응용 프로그램 매니페스트는 `LoadLibrary` 호출 중에 검사 되지 않습니다. 매니페스트가 포함 되지 않은 경우 로더에서 잘못 된 버전의 어셈블리를 로드 하려고 시도 하거나 종속 어셈블리를 찾을 수 없습니다.

하나 또는 여러 개의 관련 Dll을 해당 [어셈블리 매니페스트](/windows/win32/SbsCs/assembly-manifests)를 사용 하 여 side-by-side 어셈블리로 다시 패키지 할 수 있습니다 .이 어셈블리는 어셈블리를 구성 하는 파일과 다른 side-by-side 어셈블리에 대 한 어셈블리의 종속성을 설명 합니다.

> [!NOTE]
> 어셈블리에 하나의 DLL이 포함 되어 있는 경우이 DLL에 ID가 1 인 리소스로 어셈블리 매니페스트를 포함 하 고 전용 어셈블리의 이름을 DLL과 동일 하 게 지정 하는 것이 좋습니다. 예를 들어 dll 이름이 mylibrary .dll 인 경우 매니페스트의 \<assemblyIdentity > 요소에 사용 된 name 특성의 값은 mylibrary 일 수도 있습니다. 라이브러리에 .dll 이외의 확장이 있는 경우 (예: MFC ActiveX 컨트롤 프로젝트에서 .ocx 라이브러리를 만드는 경우) 외부 어셈블리 매니페스트를 만들 수 있습니다. 이 경우 어셈블리의 이름과 해당 매니페스트는 DLL의 이름 (예: MyAssembly, MyAssembly 및 mylibrary .ocx)과 달라 야 합니다. 그러나 확장명 .dll을 포함 하도록 이러한 라이브러리의 이름을 바꾸고 매니페스트를 리소스로 포함 하는 것이 좋습니다. 운영 체제에서 전용 어셈블리를 검색 하는 방법에 대 한 자세한 내용은 [어셈블리 검색 시퀀스](/windows/win32/SbsCs/assembly-searching-sequence)를 참조 하세요.

이렇게 변경 하면 해당 Dll을 응용 프로그램 로컬 폴더에 [전용 어셈블리로](/windows/win32/Msi/private-assemblies) 배포 하거나 WinSxS 어셈블리 캐시의 [공유 어셈블리로](/windows/win32/Msi/shared-assemblies) 배포할 수 있습니다. 이 새 어셈블리의 올바른 런타임 동작을 수행 하기 위해 몇 가지 단계를 수행 해야 합니다. [Side-by-side 어셈블리를 만드는 방법에 대 한 지침](/windows/win32/SbsCs/guidelines-for-creating-side-by-side-assemblies)에 설명 되어 있습니다. 어셈블리를 올바르게 작성 한 후에는 해당 어셈블리에 종속 된 응용 프로그램과 함께 공유 또는 전용 어셈블리로 배포할 수 있습니다. Side-by-side 어셈블리를 공유 어셈블리로 설치할 때 [WINDOWS XP에서 Side-by-side 공유를 위해 Win32 어셈블리 설치](/windows/win32/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp) 에 설명 된 지침을 따르거나 [병합 모듈](/windows/win32/msi/merge-modules)을 사용할 수 있습니다. Side-by-side 어셈블리를 전용 어셈블리로 설치 하는 경우 설치 프로세스의 일부로 해당 DLL, 리소스 및 어셈블리 매니페스트를 대상 컴퓨터의 응용 프로그램 로컬 폴더에 복사 하 여이 어셈블리를 사용할 수 있도록 할 수 있습니다. 런타임에 로더에서 검색 됩니다 ( [어셈블리 검색 시퀀스](/windows/win32/SbsCs/assembly-searching-sequence)참조). 또 다른 방법은 [Windows Installer](/windows/win32/Msi/windows-installer-portal) 를 사용 하 고 [Windows XP에서 응용 프로그램을 개인적으로 사용 하기 위해 Win32 어셈블리 설치](/windows/win32/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp)에 설명 된 지침을 따르는 것입니다.

## <a name="see-also"></a>참고자료

[ 격리된 응용 프로그램 빌드](building-c-cpp-isolated-applications.md)<br/>
[C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
