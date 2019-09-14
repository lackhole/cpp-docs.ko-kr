---
title: MFC DLL 마법사, 애플리케이션 설정
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.appset
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
ms.openlocfilehash: f021f2023af839413306c1e3d56dc741749cf216
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152048"
---
# <a name="application-settings-mfc-dll-wizard"></a>MFC DLL 마법사, 애플리케이션 설정

디자인 및 새로운 MFC DLL 프로젝트에 기본 기능을 추가하기 위해 MFC DLL 마법사의 이 페이지를 사용하세요.

## <a name="dll-type"></a>DLL 형식

생성하려는 DLL의 유형을 선택 합니다.

- **공유 MFC DLL을 사용하는 기본 MFC DLL**

   MFC 라이브러리를 공유 DLL로 프로그램에 연결하려면 이 옵션을 선택 합니다. 이 옵션을 사용하면 DLL 및 호출 응용 프로그램 간의 MFC 개체를 공유할 수 없습니다. 프로그램에서는 런타임에 MFC 라이브러리를 호출합니다. 이 옵션은 MFC 라이브러리를 사용하는 여러 실행파일로 구성된 경우 프로그램의 디스크와 메모리 요구 사항이 줄어듭니다. Win32와 MFC 프로그램 모두 DLL의 함수를 호출할 수 있습니다. 이 유형의 프로젝트를 사용하면 MFC DLL을 재배포 해야 합니다.

- **MFC가 정적으로 링크된 일반 MFC DLL**

   빌드 시간에 정적으로 MFC 라이브러리를 프로그램에 연결하려면 이 옵션을 선택 합니다. Win32와 MFC 프로그램 모두 DLL의 함수를 호출할 수 있습니다. 이 옵션을 사용하면 프로그램의 크기 증가하지만 같은 유형의 프로젝트를 사용하는 MFC DLL을 다시 배포할 필요가 없습니다. DLL과 호출 응용 프로그램간에 MFC 개체를 공유 할 수 없습니다.

- **MFC 확장 DLL**

   프로그램 실행시 MFC 라이브러리를 호출하고 호출 응용 프로그램간에 MFC 오브젝트를 공유하는 경우 이 옵션을 선택합니다. 이 옵션은 프로그램이 모두 MFC 라이브러리를 사용하는 여러 실행 파일로 구성 된 경우 프로그램의 디스크와 메모리 요구사항이 줄어듭니다. MFC 프로그램에만 DLL의 함수를 호출할 수 있습니다. 이 유형의 프로젝트와 함께 MFC DLL을 재배포 해야합니다.

## <a name="additional-features"></a>추가 기능

MFC DLL이 자동화를 지원 및 Windows 소켓 지원 여부를 선택 합니다.

- **자동화**

   프로그램이 다른 프로그램에서 구현된 오브젝트를 조작할 수 있게 하려면 **자동화**를 선택합니다. **자동화**를 선택하면 프로그램이 다른 자동화 클라이언트에도 노출됩니다. 자세한 내용은 [자동화](../../mfc/automation.md)를 참조합니다.

- **Windows 소켓**

   프로그램이 Windows 소켓을 지원하려면 이 옵션을 선택합니다. Windows 소켓을 사용하면 TCP/IP 네트워크를 통해 통신하는 프로그램을 작성할 수 있습니다.

   Windows 소켓을 지원하는 MFC DLL이 만들어지면 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)가 소켓에 대한 지줜을 초기화하고 MFC 헤더 파일 StdAfx.h에 AfxSock.h가 포함됩니다.

## <a name="see-also"></a>참고자료

[MFC DLL 마법사](../../mfc/reference/mfc-dll-wizard.md)<br/>
[MFC DLL 프로젝트 만들기](../../mfc/reference/creating-an-mfc-dll-project.md)
