---
title: '방법: 사용자 인터페이스 개체 업데이트'
ms.date: 11/04/2016
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
ms.openlocfilehash: 0dee9bb48c11cf061af60ebaf9a80c0123d339be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160278"
---
# <a name="how-to-update-user-interface-objects"></a>방법: 사용자 인터페이스 개체 업데이트

일반적으로 메뉴 항목 및 도구 모음 단추에 둘 이상의 상태. 예를 들어 있는 컨텍스트에서 사용할 수 없는 경우 메뉴 항목을 흐리게 흐리게 표시 됩니다. 메뉴 항목 선택 하거나 선택을 취소할 수 있습니다. 확인할 수 있습니다 하거나 사용할 수 없게 하는 경우에 도구 모음 단추를 비활성화할 수 있습니다.

메뉴 항목에 의해 처리 됩니다 하는 명령을 생성 하는 경우 상태가 변경 될를 논리적으로 프로그램으로 이러한 항목, 예를 들어, 문서 상태를 업데이트 하는 것이 합리적 문서가 메뉴 항목을 업데이트 합니다. 문서에는 업데이트의 기반이 되는 정보를 포함 될 것입니다.

명령에 여러 사용자 인터페이스 개체 (메뉴 항목 및 도구 모음 단추)를 둘 다 동일한 처리기 함수에 라우팅됩니다. 이 모두 한 곳에서 해당 사용자 인터페이스 개체에 대 한 사용자 인터페이스 업데이트 코드를 캡슐화합니다.

프레임 워크 사용자 인터페이스 개체를 자동으로 업데이트 하는 편리한 인터페이스를 제공 합니다. 몇 가지 다른 방법으로 업데이트를 수행 하도록 선택할 수 있습니다 이지만 제공 된 인터페이스를 효율적이 고 쉽게 사용할 수 있습니다.

업데이트 처리기의 사용을 설명 하는 다음 항목:

- [업데이트 처리기가 호출 하는 경우](../mfc/when-update-handlers-are-called.md)

- [ON_UPDATE_COMMAND_UI 매크로](../mfc/on-update-command-ui-macro.md)

- [CCmdUI 클래스](../mfc/the-ccmdui-class.md)

## <a name="see-also"></a>참고자료

[메뉴](../mfc/menus-mfc.md)
