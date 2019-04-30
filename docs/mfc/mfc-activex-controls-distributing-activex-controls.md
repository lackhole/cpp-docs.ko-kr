---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤 배포'
ms.date: 09/12/2018
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
helpviewer_keywords:
- MFC ActiveX controls [MFC], ANSI or Unicode versions
- RegSvr32.exe
- MFC ActiveX controls [MFC], distributing
- distributing MFC ActiveX controls
- redistributable files, MFC ActiveX controls
- GetSystemDirectory method [MFC]
- registering ActiveX controls
- MSVCRT40.dll
- registry [MFC], registering controls
- LoadLibrary method, registering ActiveX controls
- MFC40U.DLL
- MFC40.DLL
- GetWindowsDirectory method [MFC]
- installing ActiveX controls
- GetProcAddress method, registering ActiveX controls
- MFC ActiveX controls [MFC], installing
- MFC ActiveX controls [MFC], registering
- registering controls
- OLEPRO32.DLL
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
ms.openlocfilehash: 409ace2197396cf7adbd330cfbd891745a23cf53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392702"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 배포

이 문서에서는 ActiveX 컨트롤 재배포 관련 된 문제를 설명 합니다.

- [ANSI 또는 유니코드 컨트롤 버전](#_core_ansi_or_unicode_control_versions)

- [ActiveX 컨트롤 및 재배포 가능 Dll 설치](#_core_installing_activex_controls_and_redistributable_dlls)

- [컨트롤 등록](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI 또는 유니코드 컨트롤 버전

컨트롤 또는 둘 다의 ANSI 또는 유니코드 버전을 제공할 것인지를 결정 해야 합니다. 이 의사 결정의 ANSI 및 유니코드 문자 집합 이식성 요인을 기반으로 합니다.

모든 Win32 운영 체제에서 작동 하는 ANSI 컨트롤, 다양 한 Win32 운영 체제 간에 이식할 수 있습니다. 유니코드 컨트롤에는 Windows 95 또는 Windows 98에는 없지만 Windows NT (버전 3.51 이상)만에서 작동합니다. 이식성 배송 ANSI 컨트롤, 주요 관심사 인 경우 컨트롤은 Windows NT 에서만 실행 됩니다, 경우에 유니코드 컨트롤을 제공할 수 있습니다. 사용자의 운영 체제에 가장 적합 한 버전을 설치 하는 응용 프로그램을 모두 제공 선택할 수 있습니다.

##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> ActiveX 컨트롤 및 재배포 가능 Dll 설치

ActiveX 컨트롤을 사용 하 여 제공 하는 설치 프로그램을 Windows 디렉터리의 특수 한 하위 만들고 컨트롤의를 설치 해야 합니다. 그 안에 OCX 파일입니다.

> [!NOTE]
>  Windows를 사용 하 여 `GetWindowsDirectory` Windows 디렉터리의 이름을 확인 하려면 설치 프로그램에서 API. 하위 디렉터리 이름을 통해 회사 또는 제품의 이름에서 파생 하려고 합니다.

설치 프로그램을 Windows 시스템 디렉터리에서 필요한 재배포 가능 DLL 파일을 설치 해야 합니다. Dll 중 사용자의 컴퓨터에 이미 있는 경우 설치 프로그램을 설치 하는 버전을 사용 하 여 해당 버전을 비교 해야 합니다. 해당 버전 번호는 이미 설치 된 파일에 보다 높은 경우에 파일을 다시 설치 합니다.

ActiveX 컨트롤을 OLE 컨테이너 응용 프로그램 에서만에서 사용할 수 있습니다, 되므로 컨트롤을 사용 하 여 OLE Dll의 전체 집합을 배포할 필요가 없습니다. 포함 된 응용 프로그램 (또는 운영 체제 자체) 표준 OLE Dll이 설치 되어 있는지를 가정할 수 있습니다.

##  <a name="_core_registering_controls"></a> 컨트롤 등록

컨트롤을 사용 하려면, 먼저 Windows 등록 데이터베이스에 적절 한 항목에 대 한 만들어야 합니다. 일부 ActiveX 컨트롤 컨테이너에 새 컨트롤을 등록 하는 사용자에 대 한 메뉴 항목을 제공 하지만이 기능을 모든 컨테이너에서 사용할 수 없습니다. 따라서 설치 프로그램 설치 될 때 컨트롤을 등록할 수도 있습니다.

원한다 면 대신 컨트롤을 직접 등록 하려면 설치 프로그램을 작성할 수 있습니다.

사용 된 `LoadLibrary` 컨트롤 DLL을 로드 하는 Windows API입니다. 다음을 사용 하 여 `GetProcAddress` "DllRegisterServer" 함수의 주소를 가져옵니다. 마지막으로 호출 된 `DllRegisterServer` 함수입니다. 다음 코드 샘플에는 한 가지 방법을 보여 줍니다 위치 `hLib` 컨트롤 라이브러리의 핸들을 저장 하 고 `lpDllEntryPoint` "DllRegisterServer" 함수의 주소를 저장 합니다.

[!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

컨트롤을 직접 등록의 장점은 필요가 없습니다를 호출 하 고 별도 프로세스 (즉, REGSVR32)를 로드 합니다. 설치 시간을 단축 합니다. 또한 등록 된 내부 프로세스 이기 때문에 설치 프로그램에서 오류를 처리할 수 및 외부 프로세스 보다 더 나은 예측 하지 못한 경우가 있습니다.

> [!NOTE]
>  설치 프로그램에서 ActiveX 컨트롤을 설치 하기 전에 호출 해야 `OleInitialize`합니다. 설치 프로그램 완료 되 면 호출 `OleUnitialize`합니다. 이렇게 하면 OLE 시스템 Dll ActiveX 컨트롤을 등록 하기 위한 적절 한 상태가 됩니다.

MFCx0.DLL 등록 해야 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
