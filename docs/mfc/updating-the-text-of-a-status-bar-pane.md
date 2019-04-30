---
title: 상태 표시줄 창의 텍스트 업데이트
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
ms.openlocfilehash: baf5013e34f262dd3bfed82941697ab9ca21e637
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180787"
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>상태 표시줄 창의 텍스트 업데이트

이 문서에서는 MFC 상태 표시줄 창에 표시 되는 텍스트를 변경 하는 방법에 설명 합니다. 상태 표시줄-클래스의 창 개체 [CStatusBar](../mfc/reference/cstatusbar-class.md) -여러 개의 "창이 있습니다."를 포함 합니다. 각 창에 정보를 표시 하는 데 사용할 수 있는 상태 표시줄의 사각형 영역입니다. 예를 들어, 대부분의 응용 프로그램 맨 오른쪽 창에는 CAPS LOCK, NUM LOCK 및 기타 키의 상태를 표시합니다. 응용 프로그램 "메시지 창입니다." 라고 있는 왼쪽 창에서 (0), 정보 텍스트를 종종 표시 예를 들어, 기본 MFC 상태 표시줄 메시지 창을 사용 하 여 현재 선택 된 메뉴 항목이 나 도구 모음 단추를 설명 하는 문자열을 표시 합니다. 에 있는 그림과 [상태 표시줄](../mfc/status-bar-implementation-in-mfc.md) MFC 응용 프로그램 마법사가 만든 응용 프로그램에서 상태 표시줄을 보여 줍니다.

기본적으로 MFC 사용 되지 않습니다는 `CStatusBar` 창을 만들 때 창입니다. 창을 활성화 하려면 ON_UPDATE_COMMAND_UI 매크로 사용 하 여 각 창의 상태 표시줄에를 창 업데이트 해야 합니다. 창 WM_COMMAND 메시지를 보내지 않는 때문에 (그렇지 않으면 도구 모음 단추와 같은) 코드를 수동으로 입력 해야 합니다.

예를 들어, 하나의 창에 `ID_INDICATOR_PAGE` 문서의 현재 페이지 번호를 포함 하며 해당 명령 식별자입니다. 다음 절차에는 상태 표시줄에 새 창을 만드는 방법을 설명 합니다.

### <a name="to-make-a-new-pane"></a>새 창을 표시 하려면

1. 정의 된 창의 명령 id입니다.

   에 **뷰** 메뉴에서 클릭 **리소스 뷰**합니다. 프로젝트 리소스를 마우스 오른쪽 단추로 클릭 하 고 클릭 **리소스 기호**합니다. 리소스 기호 대화 상자에서 클릭 `New`합니다. 명령 ID 이름을 입력 합니다: 예를 들어 `ID_INDICATOR_PAGE`합니다. ID에 대 한 값을 지정 하거나 리소스 기호 대화 상자에서 제안한 값을 허용 합니다. 예를 들어 `ID_INDICATOR_PAGE`, 기본값을 그대로 적용 합니다. 리소스 기호 대화 상자를 닫습니다.

1. 창에 표시할 기본 문자열을 정의 합니다.

   리소스 뷰 열기를 두 번 클릭 **문자열 테이블** 응용 프로그램에 대 한 리소스 종류를 나열 하는 창에서. 사용 하 여는 **문자열 테이블** 편집기를 열면 **새 문자열** 에서 **삽입** 메뉴. 문자열 속성 창에서 선택 창에 명령 ID (예를 들어 `ID_INDICATOR_PAGE`) "페이지"와 같은 기본 문자열 값을 입력 하 고 있습니다. 문자열 편집기를 닫습니다. (컴파일러 오류를 방지 하려면 기본 문자열을 해야 합니다.)

1. 창을 추가 합니다 *표시기* 배열입니다.

   에 해당 합니다. CPP로 찾을 합니다 *표시기* 배열입니다. 이 배열의 모든 왼쪽에서 오른쪽 순서로 상태 표시줄의 지표에 대 한 명령 Id를 나열합니다. 배열에서 적절 한 시점에 창의 명령 ID에 대 한 다음과 같은 입력 `ID_INDICATOR_PAGE`:

   [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]

창에 텍스트를 표시 하는 권장된 방법은 호출 하는 것을 `SetText` 클래스의 멤버 함수 `CCmdUI` 창의 업데이트 처리기 함수에 있습니다. 정수 변수를 설정 하려는 하는 예를 들어 *m_nPage* 사용 하 여 확인 하 고 현재 페이지 번호를 포함 하는 `SetText` 해당 숫자의 문자열 버전으로 창의 텍스트를 설정 합니다.

> [!NOTE]
>  `SetText` 접근 방식을 사용 하는 것이 좋습니다. 호출 하 여 약간 낮은 수준에서이 작업을 수행 하는 것이 불가능 합니다 `CStatusBar` 멤버 함수 `SetPaneText`합니다. 이 경우에 업데이트 처리기를 여전히 필요합니다. 창에 대 한 이러한 처리기 없이 MFC 자동으로 사용 하지 않도록 설정 된 창 내용을 지우고 합니다.

다음 절차에는 텍스트 창에 표시할 업데이트 처리기 함수를 사용 하는 방법을 보여 줍니다.

#### <a name="to-make-a-pane-display-text"></a>텍스트를 표시 하는 창을 표시 하려면

1. 명령에 대 한 명령 업데이트 처리기를 추가 합니다.

   수동으로 처리기에 대 한 프로토타입이 다음과 같이 추가 대 한 `ID_INDICATOR_PAGE` (에 해당 합니다. H):

   [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]

1. 에 해당 합니다. CPP 파일에서 처리기의 정의 다음과 같이 추가 대 한 `ID_INDICATOR_PAGE` (에 해당 합니다. CPP):

   [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]

   이 처리기의 마지막 세 줄은 텍스트를 표시 하는 코드입니다.

1. 적절 한 메시지 맵에서 ON_UPDATE_COMMAND_UI 매크로 대 한 다음과 같은 추가 `ID_INDICATOR_PAGE` (에 해당 합니다. CPP):

   [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]

값을 정의 하 고 나면 합니다 *m_nPage* 멤버 변수 (클래스의 `CMainFrame`),이 방법을 사용 하면 응용 프로그램 업데이트 다른 표시기는 동일한 방식으로 유휴 처리 하는 동안 창에 표시할 페이지 번호입니다. 하는 경우 *m_nPage* 변경, 다음 유휴 루프 중 변경 내용을 표시 합니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [사용자 인터페이스 개체 업데이트 (프로그램의 조건 변화에 따라 도구 모음 단추 및 메뉴 항목을 업데이트 하는 방법)](../mfc/how-to-update-user-interface-objects.md)

## <a name="see-also"></a>참고자료

[MFC의 상태 표시줄 구현](../mfc/status-bar-implementation-in-mfc.md)<br/>
[CStatusBar 클래스](../mfc/reference/cstatusbar-class.md)
