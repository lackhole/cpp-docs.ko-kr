---
title: 사용자 인터페이스 개체 및 명령 ID
ms.date: 11/19/2018
helpviewer_keywords:
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
ms.openlocfilehash: 54372facc51062add122c1db2e01e3081127512e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180617"
---
# <a name="user-interface-objects-and-command-ids"></a>사용자 인터페이스 개체 및 명령 ID

메뉴 항목, 도구 모음 단추 액셀러레이터 키와 "사용자 인터페이스 개체" 명령을 생성할 수 있습니다. 이러한 각 사용자 인터페이스 개체는 ID가 있습니다. 명령을 사용 하 여 개체 및 명령에 동일한 ID를 할당 하 여 사용자 인터페이스 개체를 연결 합니다. 에 설명 된 대로 [메시지](../mfc/messages.md), 특별 한 메시지로 명령을 구현 됩니다. 그림 "명령에서 다음 프레임 워크" 프레임 워크 명령을 관리 하는 방법을 보여 줍니다. 사용자 인터페이스 개체를 생성할 때 명령와 같은 `ID_EDIT_CLEAR_ALL`, 명령을 처리 응용 프로그램의 개체 중 하나-문서 개체의 아래 그림에서 `OnEditClearAll` 문서의 메시지 맵을 통해 함수를 호출 합니다.

![프레임 워크에서 명령](../mfc/media/vc385p1.gif "프레임 워크에는 명령") <br/>
프레임워크의 명령

그림 "명령을 업데이트에서 다음 프레임 워크" MFC 메뉴 항목 및 도구 모음 단추와 같은 사용자 인터페이스 개체를 업데이트 하는 방법을 보여 줍니다. 메뉴 또는 도구 모음 단추의 경우 유휴 루프 중 삭제를 전에 MFC update 명령을 라우팅합니다. 아래 그림의 문서 개체는 해당 업데이트 명령 처리기를 호출 `OnUpdateEditClearAll`하 여 사용 하도록 설정 하거나 사용자 인터페이스 개체를 사용 하지 않도록 설정 합니다.

![프레임 워크 업데이트 명령](../mfc/media/vc385p2.png "프레임 워크 업데이트 명령") <br/>
Framework의 명령 업데이트

## <a name="see-also"></a>참고자료

[프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)
