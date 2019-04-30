---
title: 명령 ID
ms.date: 11/04/2016
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
ms.openlocfilehash: 76071105e72f1ca4a851b9cdb76d5f1a96f44edb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219901"
---
# <a name="command-ids"></a>명령 ID

명령을 자세히만 해당 명령 ID로 설명 되어 있습니다. (인코딩된 합니다 **WM_COMMAND** 메시지). 이 ID는 명령을 생성 하는 사용자 인터페이스 개체에 할당 됩니다. 일반적으로 할당 된 사용자 인터페이스 개체의 기능에 대 한 Id 라고 합니다.

예를 들어 편집 메뉴에서 항목을 모두 지우기 할당 될 수 있습니다 ID와 같은 **ID_EDIT_CLEAR_ALL**합니다. 클래스 라이브러리를 처리 하는 프레임 워크 자체와 같은 명령에 대 한 특히 일부 Id 미리 정의 **ID_EDIT_CLEAR_ALL** 하거나 **ID_FILE_OPEN**합니다. 다른 명령 Id를 직접 만들 됩니다.

시각적 개체에 직접 메뉴를 만들 때 C++ 나온 것 처럼 클래스 라이브러리를 수행 하는 것이 좋습니다의 명명 규칙은 메뉴 편집기를 해당 **ID_FILE_OPEN**합니다. [표준 명령](../mfc/standard-commands.md) 클래스 라이브러리에서 정의 하는 일반적인 명령에 설명 합니다.

## <a name="see-also"></a>참고자료

[사용자 인터페이스 개체 및 명령 ID](../mfc/user-interface-objects-and-command-ids.md)
