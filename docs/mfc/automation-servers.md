---
title: 자동화 서버
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
ms.openlocfilehash: 39e870db2f5476a630a8ed3bc68944dbb164d469
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374170"
---
# <a name="automation-servers"></a>자동화 서버

Automation을 사용 하면 다른 응용 프로그램에서 구현 하는 개체를 조작 하거나 조작할 수 있도록 개체를 노출 시키는 응용 프로그램에 대 한 수 있습니다. 자동화 서버는 다른 응용 프로그램 (자동화 개체) 프로그래밍 가능 개체를 노출 하는 응용 프로그램 (호출 [자동화 클라이언트](../mfc/automation-clients.md)). 자동화 서버에는 자동화 구성 요소 라고도 합니다.

개체에 직접 액세스 하 여 특정 절차를 자동화 하는 클라이언트를 통해 자동화 개체를 노출 하 고 서버 기능 사용 가능. 이러한 방식으로 개체를 노출 합니다. 다른 응용 프로그램에 대 한 유용한 기능을 제공할 때 유용 합니다. 예를 들어 워드 프로세서 다른 프로그램에서 사용할 수 있도록 해당 맞춤법 검사 기능을 노출할 수 있습니다. 개체 노출을 다른 응용 프로그램의 기존 기능을 사용 하 여 해당 응용 프로그램의 기능을 개선 하기 위해 공급 업체에 따라서 사용 하도록 설정 합니다.

이 자동화 개체는 속성 및 메서드 외부 인터페이스로 사용 합니다. 속성에는 자동화 개체의 특성 이름이 지정 됩니다. 속성의 데이터 멤버 같습니다는 C++ 클래스입니다. 메서드는 자동화 개체에서 작동 하는 함수입니다. 메서드는 등의 공용 멤버 함수는 C++ 클래스입니다.

> [!NOTE]
>  속성은 유사 하지만 C++ 직접 액세스할 수 없는 데이터 멤버입니다. 투명 한 액세스를 제공 하려면 액세스 하는 데 한 쌍의 get/set 멤버 함수를 사용 하 여 자동화 개체의 내부 변수를 설정 합니다.

일반적이 고 잘 정의 된 인터페이스를 통해 응용 프로그램 기능을 노출 하 여 자동화 가능 하도록 단일 일반 프로그래밍 언어 대신 Microsoft Visual Basic과 같은 다양 한, 응용 프로그램별 매크로에서에서 응용 프로그램 빌드 언어들.

##  <a name="_core_support_for_automation_servers"></a> 자동화 서버에 대 한 지원

Visual C++ MFC 프레임 워크 자동화 서버에 대 한 광범위 한 지원을 제공 합니다. 대부분의 응용 프로그램의 기능에 노력을 집중할 수 있도록 자동화 서버를 만드는 작업의 오버 헤드를 처리 합니다.

자동화를 지원 하기 위한 프레임 워크의 주 메커니즘은 선언과 OLE에 대 한 메서드 및 속성을 노출 하는 데 필요한 호출으로 확장 되는 매크로 집합과 디스패치 맵입니다. 일반적인 디스패치 맵에 모양은 다음과 같습니다.

[!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]

속성 창 및 클래스 뷰 디스패치 맵을 유지 하는 데 지원 합니다. Visual 클래스는 새 메서드 또는 속성을 추가 하면 C++ 해당 추가 `DISP_FUNCTION` 나 `DISP_PROPERTY` 클래스 이름, 메서드 또는 속성 및 데이터 형식의 외부 이름과 내부를 나타내는 매개 변수를 사용 하 여 매크로입니다.

합니다 **클래스 추가** 대화 상자는 해당 속성 및 작업 관리와 자동화 클래스 선언에도 간소화 합니다. 클래스 추가 대화 상자를 사용 하 여 프로젝트에 클래스를 추가할 때 기본 클래스를 지정 합니다. 클래스 추가 대화 상자 표시 "OLE creatable" (즉, 여부 클래스의 개체에 만들 수 있습니다 COM 클라이언트의 요청)는 새 클래스가 자동화를 지원 하는지 여부를 지정 하는 데 사용할 컨트롤 기본 클래스에서 자동화를 허용 하는 경우 및를 사용 하 여 COM 클라이언트에 대 한 외부 이름입니다.

합니다 **클래스 추가** 대화 상자에는 다음 클래스 선언을 만듭니다, 지정 된 OLE 기능에 대 한 적절 한 매크로 포함 합니다. 또한 구현 클래스의 멤버 함수에 대 한 기본 코드를 추가합니다.

MFC 응용 프로그램 마법사 순조로운 자동화 서버 응용 프로그램을 시작 하는 단계를 간소화 합니다. 선택 하는 경우는 **자동화** 에서 확인란 합니다 **고급 기능** 페이지에서 응용 프로그램에 추가 하는 MFC 응용 프로그램 마법사를 `InitInstance` 자동화를 등록 하는 데 필요한 호출 함수 개체 및 응용 프로그램을 자동화 서버로 실행 합니다.

### <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요

- [자동화 클라이언트에 알아봅니다](../mfc/automation-clients.md)

- [CCmdTarget 클래스에 자세히 알아보기](../mfc/reference/ccmdtarget-class.md)

- [COleDispatchDriver 클래스에 자세히 알아보기](../mfc/reference/coledispatchdriver-class.md)

## <a name="see-also"></a>참고자료

[자동화](../mfc/automation.md)<br/>
[MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)
