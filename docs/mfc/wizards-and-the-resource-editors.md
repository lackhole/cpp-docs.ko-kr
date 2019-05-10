---
title: 마법사 및 리소스 편집기
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and MFC
- MFC, resource editors
- resource editors, MFC
- MFC Application Wizard
- editors [MFC], resource
- wizards [MFC]
- wizards [MFC], MFC programming
- MFC, wizards
- Class View tool, managing Windows messages
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
ms.openlocfilehash: 41cbb86b4245bd78baecd222b5573ba5e877243a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338300"
---
# <a name="wizards-and-the-resource-editors"></a>마법사 및 리소스 편집기

Visual C++ MFC 프로그래밍의 경우 많은 통합된 리소스 편집기와 함께 사용 하기 위해 몇 가지 마법사를 포함 합니다. ActiveX 컨트롤 프로그래밍에 대 한 합니다 [ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md) MFC 응용 프로그램 마법사는 비슷한 용도로 사용 됩니다. 이러한 도구의 대부분 하지 않고 MFC 응용 프로그램을 작성할 수 있지만 도구 크게 간소화 하 고 작업 속도.

##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a> MFC 응용 프로그램 마법사를 사용 하 여 MFC 응용 프로그램 만들기

사용 된 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md) 시각적 개체에 MFC 프로젝트를 만들려면 C++, OLE를 포함할 수 있으며 데이터베이스 지원 합니다. 프로젝트의 파일에 응용 프로그램, 문서, 뷰 및 프레임 창 클래스를 포함합니다. 메뉴 및 도구는 선택 사항 모음;를 비롯 한 표준 리소스 다른 필수 Windows 파일입니다. 및 프로그램의 도움말 파일을 만들려면 보강 하 여 표준 Windows 도움말 항목을 수정할 수 있는 선택적.rtf 파일 포함 합니다.

##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> 클래스 뷰를 사용 하 여 클래스 및 Windows 메시지 관리

있습니다 Windows 메시지 및 명령에 대 한 처리기 함수를 만들고 관리할 클래스, 클래스 뷰 사용 하면 Automation 메서드 및 속성 만들기, 데이터베이스 클래스 등을 만들 클래스 멤버 변수를 만듭니다.

> [!NOTE]
>  클래스 뷰를 사용 하면 MFC 클래스의 가상 함수를 재정의할 수 있습니다. 클래스 및 가상 함수 재정의를 선택 합니다. 프로세스의 나머지 다음 단락에서 설명한 대로 메시지 처리와 비슷합니다.

Windows에서 실행 중인 응용 프로그램은 [기반 메시지](../mfc/message-handling-and-mapping.md)합니다. 사용자 동작 및 실행 중인 프로그램에서 발생 하는 기타 이벤트 프로그램에 windows 메시지를 보내도록 Windows 발생 합니다. 예를 들어 사용자가 창에서 마우스를 클릭 하면 Windows 마우스 왼쪽된 단추를 누를 때 WM_LBUTTONDOWN 메시지 및 보냅니다 WM_LBUTTONUP 메시지 단추를 놓을 때. 또한 Windows 사용자가 메뉴 모음에서 명령을 선택할 때 WM_COMMAND 메시지를 보냅니다.

MFC 프레임 워크, 문서, 뷰, 프레임 창, 문서 템플릿 및 응용 프로그램 개체와 같은 다양 한 개체 "메시지를 처리할 수"입니다. 이러한 개체는 "처리기 함수" 해당 멤버 중 하나로 기능을 제공 및 프레임 워크는 들어오는 메시지가 해당 처리기에 매핑합니다.

프로그래밍 작업의 많은 부분 개체에 매핑할 메시지 선택 이며 다음 해당 매핑을 구현 됩니다. 이렇게 하려면 속성 창과 클래스 뷰를 사용 합니다.

속성 창의 빈 메시지 처리기 멤버 함수를 만들고 소스 코드 편집기를 사용 하 여 처리기의 본문을 구현 합니다. 만들 수도 있고 (MFC 클래스에서 파생 되지 않은 사용자 지정 클래스 포함) 클래스 및 클래스 뷰를 사용 하 여 해당 멤버를 편집할 수도 있습니다. 클래스 뷰를 사용 하 여 및 프로젝트에 코드를 추가 하는 마법사에 대 한 자세한 내용은 참조 하세요 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)합니다.

##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> 리소스 편집기를 사용 하 여 만들고 리소스를 편집 합니다.

시각적 개체를 사용 하 여 C++ [리소스 편집기](../windows/resource-editors.md) 만들고 메뉴, 대화 상자, 사용자 지정 컨트롤, 액셀러레이터 키, 비트맵, 아이콘, 커서, 문자열 및 버전 리소스를 편집 합니다. 시각적 개체를 기준으로 C++ 버전 4.0을 도구 모음 편집기를 사용 하면 도구 모음을 쉽게 만들기.

를 더욱 수 있도록 Microsoft Foundation Class 라이브러리를 일반적인 라는 파일을 제공 합니다. RES를 일반적인에서 복사할 수 있는 "클립 아트" 리소스를 포함 합니다. RES 및 사용자 고유의 리소스 파일에 붙여 넣습니다. 일반적인 합니다. RES 도구 모음 단추, 일반적인 커서, 아이콘 등을 포함합니다. 사용 하 고, 수정 하 고, 응용 프로그램에서 이러한 리소스를 재배포할 수 있습니다. 일반적인 방법에 대 한 자세한 내용은 합니다. RES를 참조 합니다 [클립 아트 샘플](../overview/visual-cpp-samples.md)합니다.

MFC 응용 프로그램 마법사, 시각적 개체 C++ 마법사, 리소스 편집기와 MFC 프레임 워크를 많은 작업을 수행 및 프로그램 코드를 훨씬 쉽게 관리할 수 있도록 합니다. 응용 프로그램별 코드 대량의 문서 및 뷰 클래스입니다.

## <a name="see-also"></a>참고자료

[클래스를 사용하여 Windows 애플리케이션 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
