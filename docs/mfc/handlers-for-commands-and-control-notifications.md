---
title: 명령 및 컨트롤 알림에 대한 처리기
ms.date: 11/04/2016
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
ms.openlocfilehash: 6c92660c67fa91c27bb094111cebfef57904cdc7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358996"
---
# <a name="handlers-for-commands-and-control-notifications"></a>명령 및 컨트롤 알림에 대한 처리기

명령 또는 컨트롤 알림 메시지에 대 한 기본 처리기가 없는 경우 따라서 메시지의 이러한 범주에 대 한 처리기를 명명 규칙만 적용 됩니다. 명령 또는 컨트롤 알림 처리기에 매핑할 때는 속성 창에서는 명령 ID 또는 알림 컨트롤 코드를 기반으로 이름을 제안 합니다. 제안 된 이름을 지정, 변경 하거나 바꿉니다.

규칙 나타내는 사용자 인터페이스 개체에 대 한 두 범주에는 처리기 이름을 제안 합니다. 편집 메뉴에서 Cut 명령에 대 한 처리기 이름이 될 수 있으므로

[!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]

프레임 워크와 Cut 명령에 대 한 명령 ID는 미리 정의 Cut 명령은 응용 프로그램에서 구현 되므로 일반적으로, 되므로 **ID_EDIT_CUT**합니다. 모든 미리 정의 된 명령 Id의 목록을 AFXRES 파일을 참조 하세요. 8. 자세한 내용은 [표준 명령](../mfc/standard-commands.md)입니다.

또한 규칙에 대 한 처리기를 제안 합니다 **BN_CLICKED** "My Button" 레이블이 붙은 단추에서 알림 메시지를 이름일 수 있습니다

[!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]

이 명령은 ID가 할당할 수 있습니다 **IDC_MY_BUTTON** 이므로 응용 프로그램 관련 사용자 인터페이스 개체와 동일 합니다.

메시지의 두 범주 인수를 가져오지 않고 및 아무 값도 반환 합니다.

## <a name="see-also"></a>참고자료

[메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
