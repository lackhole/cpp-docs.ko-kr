---
title: 업데이트 처리기가 호출되는 시점
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
ms.openlocfilehash: 4a52c147d1abf02b7c5e89abf868f87a07ab32cc
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346071"
---
# <a name="when-update-handlers-are-called"></a>업데이트 처리기가 호출되는 시점

사용자가 WM_INITMENUPOPUP 메시지를 생성 하는 파일 메뉴에서 마우스를 가정 합니다. 프레임 워크의 업데이트 메커니즘 메뉴 드롭다운 방식으로 펼쳐집니다 사용자가 볼 수 있도록 하려면 먼저 파일 메뉴에서 모든 항목을 전체적으로 업데이트 합니다.

이 위해 프레임 워크 경로 표준 명령 라우팅 따라 팝업 메뉴에서 모든 메뉴 항목에 대 한 명령을 업데이트 합니다. 명령 대상 라우팅에 적절 한 메시지 맵 항목을 사용 하 여 update 명령을 비교 하 여 메뉴 항목을 업데이트할 수 있는 (폼의 `ON_UPDATE_COMMAND_UI`) 및 "업데이트 처리기" 함수를 호출 합니다. 따라서 6 메뉴 항목을 사용 하 여 메뉴에 대 한 6 업데이트 명령으로 전송 됩니다. 업데이트 처리기가 메뉴 항목의 명령 ID에 대 한 업데이트를 수행 하 라고 합니다. 그러지 않으면 프레임 워크는 명령 ID에 대 한 처리기가 있는지 확인 하 고 사용 하거나 적절 하 게 메뉴 항목을 사용 하지 않도록 설정 합니다.

프레임 워크를 찾을 수 없는 경우는 `ON_UPDATE_COMMAND_UI` 명령 라우팅 하는 동안 항목을 자동으로 활성화할 사용자 인터페이스 개체 있으면는 `ON_COMMAND` 항목 어딘가에 동일한 명령 id입니다. 그렇지 않으면 사용자 인터페이스 개체를 해제합니다. 따라서 사용자 인터페이스 개체를 사용 하도록 설정, 개체 생성 하는 명령에 대 한 처리기를 제공 하거나에 대 한 업데이트 처리기를 제공 합니다. 항목의 그림을 참조 하세요 [사용자 인터페이스 개체 및 명령 Id](../mfc/user-interface-objects-and-command-ids.md)합니다.

사용자 인터페이스 개체의 기본 비활성화를 사용 하지 않도록 설정 하는 것이 가능 합니다. 자세한 내용은 참조는 [m_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable) 클래스의 멤버 `CFrameWnd` 에 *MFC 참조*.

메뉴 초기화가 자동 framework에서 응용 프로그램 WM_INITMENUPOPUP 메시지를 받을 때 발생 합니다. 유휴 루프 중 프레임 워크가 명령 라우팅을 업데이트 단추 처리기에 대 한 거의 동일한 방식 메뉴에 대해서와 마찬가지로 검색 합니다.

## <a name="see-also"></a>참고자료

[방법: 사용자 인터페이스 개체 업데이트](../mfc/how-to-update-user-interface-objects.md)
