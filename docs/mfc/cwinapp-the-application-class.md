---
title: 'CWinApp: Application 클래스'
ms.date: 11/04/2016
f1_keywords:
- CWinApp
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
ms.openlocfilehash: d9f0d4f5ba6b6b070b23ce98ecda8c7accf44934
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241564"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: Application 클래스

MFC의 기본 응용 프로그램 클래스 초기화, 실행 및 Windows 운영 체제에 대 한 응용 프로그램의 종료를 캡슐화합니다. 프레임 워크에서 빌드된 응용 프로그램을 하나 있어야 하며에서 파생 된 클래스의 개체를 하나만 [CWinApp](../mfc/reference/cwinapp-class.md)합니다. 이 개체는 windows 생성 되기 전에 생성 됩니다.

`CWinApp` 파생 된 `CWinThread`, 응용 프로그램에 대해 하나 이상의 스레드를 사용할 수는 실행의 주 스레드를 나타내는입니다. MFC의 최신 버전에는 `InitInstance`, **실행**, `ExitInstance`, 및 `OnIdle` 멤버 함수는 클래스에서 실제로 `CWinThread`합니다. 이러한 함수 여기에 설명 되어 있는 것 처럼 `CWinApp` 멤버 대신 초점은 주 스레드가 아닌 응용 프로그램 개체와 개체의 역할 때문입니다.

> [!NOTE]
>  응용 프로그램 클래스에는 응용 프로그램의 주 실행 스레드를 구성합니다. Win32 API 함수를 사용 하 여 보조 스레드 방식의 실행도 만들 수 있습니다. 이러한 스레드는 MFC 라이브러리를 사용할 수 있습니다. 자세한 내용은 [다중 스레딩](../parallel/multithreading-support-for-older-code-visual-cpp.md)합니다.

Windows 운영 체제에 대 한 다른 프로그램과 마찬가지로 framework 응용 프로그램에 `WinMain` 함수입니다. 그러나 프레임 워크 응용 프로그램에서는 쓰지 않아도 `WinMain`합니다. 클래스 라이브러리에서 제공 하 고 응용 프로그램이 시작 될 때 호출 됩니다. `WinMain` 창 클래스 등록 등의 표준 서비스를 수행 합니다. 멤버 함수의 응용 프로그램 개체를 초기화 하 고 응용 프로그램을 실행 한 다음 호출 합니다. (사용자 지정할 수 있습니다 `WinMain` 재정의 하 여 합니다 `CWinApp` 멤버 함수는 `WinMain` 호출 합니다.)

응용 프로그램을 초기화할 `WinMain` 응용 프로그램 개체의 호출 `InitApplication` 및 `InitInstance` 멤버 함수입니다. 응용 프로그램의 메시지 루프를 실행 하려면 `WinMain` 호출을 **실행** 멤버 함수입니다. 종료 `WinMain` 응용 프로그램 개체의 호출 `ExitInstance` 멤버 함수입니다.

> [!NOTE]
>  에 표시 되는 이름과 **굵게** 이 설명서에서는 Microsoft Foundation Class 라이브러리 및 시각적 개체에서 제공 하는 요소를 나타내는 C++합니다. 에 표시 되는 이름과 `monospaced` 형식을 만들거나 재정의 하는 요소를 나타냅니다.

## <a name="see-also"></a>참고자료

[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[CWinApp 및 MFC 애플리케이션 마법사](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[재정의 가능 CWinApp 멤버 함수](../mfc/overridable-cwinapp-member-functions.md)<br/>
[특수 CWinApp 서비스](../mfc/special-cwinapp-services.md)
