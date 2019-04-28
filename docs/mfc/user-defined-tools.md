---
title: 사용자 정의 형식
ms.date: 11/19/2018
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
ms.openlocfilehash: 785e37c63653dde91176bedd0321fc58ac122c7e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180842"
---
# <a name="user-defined-tools"></a>사용자 정의 형식

MFC는 사용자 정의 도구를 지원합니다. 사용자 정의 도구에는 외부의 사용자 지정 프로그램을 실행 하는 특수 명령입니다. 사용자 정의 도구를 관리 하는 사용자 지정 프로세스를 사용할 수 있습니다. 그러나 응용 프로그램 개체에서 파생 되지 않은 경우이 과정을 사용할 수 없습니다 [CWinAppEx 클래스](../mfc/reference/cwinappex-class.md)합니다. 사용자 지정에 대 한 자세한 내용은 참조 하세요. [MFC에 대 한 사용자 지정](../mfc/customization-for-mfc.md)합니다.

사용자 정의 형식 지원에 사용 하도록 설정한 사용자 지정 대화 상자를 자동으로 포함 된 **도구** 탭 합니다. 다음 그림에 표시 된 **도구** 페이지입니다.

![사용자 지정 대화 상자의 도구 탭](../mfc/media/custdialogboxtoolstab.png "사용자 지정 대화 상자의 도구 탭") <br/>
사용자 지정 대화 상자의 도구 탭

## <a name="enabling-user-defined-tools-support"></a>사용자 정의 사용 하도록 설정 하면 도구 지원

응용 프로그램에서 사용자 정의 도구를 사용 하려면 호출 [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)합니다. 그러나이 호출에 대 한 매개 변수로 사용 하도록 응용 프로그램의 리소스 파일에 있는 여러 상수를 먼저 정의 해야 있습니다.

리소스 편집기에서 적절 한 명령 ID를 사용 하는 더미 명령 만들기 다음 예에서는 사용 하 여 `ID_TOOLS_ENTRY` 로 명령 id입니다. 이 명령은 ID 프레임 워크는 사용자 정의 도구를 삽입 하는 위치 하나 이상의 메뉴의 위치를 표시 합니다.

에서 설정 해야 따로 일부 연속 Id 사용자 정의 도구를 나타내기 위해 문자열 테이블입니다. 따로 설정 하는 문자열 수가 최대 사용자 수를 정의 하는 사용자 도구와 같습니다. 다음 예제에서에서는 이름이 `ID_USER_TOOL1` 를 통해 `ID_USER_TOOL10`합니다.

제안 도구로 디렉터리와 호출 되는 외부 프로그램에 대 한 인수를 선택할 수 있도록 사용자에 게 제공할 수 있습니다. 이 작업을 수행 하려면 리소스 편집기에서 두 팝업 메뉴를 만듭니다. 다음 예제에서에서는 이름이 `IDR_MENU_ARGS` 고 `IDR_MENU_DIRS`입니다. 이러한 메뉴에 있는 각 명령에 대해 응용 프로그램 문자열 테이블에는 문자열을 정의 합니다. 문자열의 리소스 ID는 명령 id입니다. 동일 해야 합니다.

파생된 된 클래스를 만들 수도 있습니다 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 를 기본 구현으로 바꿉니다. 이렇게 하려면 파생된 클래스에 대 한 런타임 정보 RUNTIME_CLASS 대신 CWinAppEx::EnableUserTools에서 네 번째 매개 변수로 전달 합니다 ([CUserTool 클래스](../mfc/reference/cusertool-class.md)).

적절 한 상수를 정의한 후에 호출 [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) 사용자 정의 도구를 사용 하도록 설정 합니다.

다음 메서드 호출은 이러한 상수를 사용 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]

이 예제에서는 도구 탭에 포함 됩니다는 **사용자 지정** 대화 상자. 프레임 워크 명령 ID와 일치 하는 모든 명령을 대체할 `ID_TOOLS_ENTRY` 사용자가 해당 메뉴를 열 때마다 현재 정의 된 사용자 도구 집합을 사용 하 여 메뉴에 있습니다. 명령 Id `ID_USER_TOOL1` 를 통해 `ID_USER_TOOL10` 사용자 정의 형식에 대해 사용 하도록 예약 합니다. 클래스 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 사용자 도구에 대 한 호출을 처리 합니다. 도구 탭의 **사용자 지정** 인수와 디렉터리 입력 필드의 오른쪽 메뉴에 액세스 하기 단추를 제공 하는 대화 상자 **IDR_MENU_ARGS** 및 **IDR_MENU_DIRS**. 사용자가 이러한 메뉴 중 하나에서 명령의 선택 하면 프레임 워크가 추가 적절 한 텍스트 상자에 명령 id입니다. 같음 리소스 ID를 가진 문자열

### <a name="including-predefined-tools"></a>미리 정의 된 도구를 포함 하 여

응용 프로그램 시작 시 몇 가지 도구를 미리 정의 하려는 경우 재정의 해야 합니다 [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 응용 프로그램의 주 창의 메서드. 메서드에 다음 단계를 수행 해야 합니다.

##### <a name="to-add-new-tools-in-loadframe"></a>LoadFrame에서 새로운 도구를 추가 하려면

1. 에 대 한 포인터를 가져올는 [CUserToolsManager 클래스](../mfc/reference/cusertoolsmanager-class.md) 개체를 호출 하 여 [CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager)합니다.

1. 만들려고 할 수 있는 모든 도구에 대 한 호출 [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)합니다. 이 메서드가 반환에 대 한 포인터를 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 개체 및 도구의 내부 컬렉션에 새로 만든된 사용자 도구를 추가 합니다. 파생된 클래스에 대 한 런타임 정보를 제공 했는지 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 의 네 번째 매개 변수로 [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) 인스턴스화하고 해당 클래스의 인스턴스를 대신 반환 됩니다.

1. 각 도구에 대 한 텍스트 레이블을 설정 하 여 설정할 `CUserTool::m_strLabel` 해당 명령을 호출 하 여 설정 및 `CUserTool::SetCommand`합니다. 기본 구현의 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 에 대 한 호출에 지정 된 프로그램에서 사용 가능한 아이콘을 자동으로 검색 `SetCommand`합니다.

## <a name="see-also"></a>참고자료

[MFC에 대한 사용자 지정](../mfc/customization-for-mfc.md)<br/>
[CUserTool 클래스](../mfc/reference/cusertool-class.md)<br/>
[CUserToolsManager 클래스](../mfc/reference/cusertoolsmanager-class.md)<br/>
[CWinAppEx 클래스](../mfc/reference/cwinappex-class.md)
