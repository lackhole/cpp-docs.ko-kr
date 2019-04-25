---
title: '컨테이너: 클라이언트 항목 상태'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
ms.openlocfilehash: 1453ba3f96e49cefc9014a93ebcfbcfe5c6bc905
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152854"
---
# <a name="containers-client-item-states"></a>컨테이너: 클라이언트 항목 상태

이 문서에서는 다양 한 수명 중에 통과 한 클라이언트 항목 상태를 설명 합니다.

클라이언트 항목을 생성, 활성화, 수정 및 저장은 처럼 여러 상태를 통과 합니다. 항목의 상태 변경, 프레임 워크 호출 될 때마다 [COleClientItem::OnChange](../mfc/reference/coleclientitem-class.md#onchange) 사용 하 여 합니다 **OLE_CHANGED_STATE** 알림. 두 번째 매개 변수는 값은 `COleClientItem::ItemState` 열거형입니다. 다음 중 하나일 수 있습니다.

- *COleClientItem::emptyState*

- *COleClientItem::loadedState*

- *COleClientItem::openState*

- *COleClientItem::activeState*

- *COleClientItem::activeUIState*

비어 있는 상태에서 클라이언트 항목을 아직 완전히는 항목이 아닙니다. 메모리를 할당 하지만 아직 OLE 항목의 데이터를 사용 하 여 초기화 되지 않았습니다. 이 호출을 통해 만들어진 경우에 클라이언트 항목은 상태 **새** 있지만 일반적인 2 단계 생성의 두 번째 단계를 아직 받지 않았습니다.

두 번째 단계에서 호출을 통해 수행 `COleClientItem::CreateFromFile` 또는 다른 `CreateFrom` *xxxx* 함수 항목이 완전히 만들어집니다. OLE 데이터로 (파일 또는 클립보드 등의 다른 소스) 연관 된는 `COleClientItem`-파생 개체입니다. 이제 항목 로드 된 상태입니다.

항목에 된 서버 창에서 열을 하지 않고 컨테이너의 문서에서 열 때 엽니다 (또는 완전 개방) 상태입니다. 이 상태에서 크로스-빗살 무늬를 일반적으로 위에 그려집니다 항목이 활성화 되어 있음을 나타내려면 다른 곳에서 컨테이너의 창에서 항목의 표현입니다.

위치에 항목을 활성화 하는 경우 전달, 일반적으로 활성 상태를 통해 간단 하 게 합니다. UI 활성 상태가 고 해당 메뉴, 도구 모음 및 컨테이너를 사용 하 여 다른 사용자 인터페이스 구성 요소 서버 병합에 입력 합니다. 이러한 사용자 인터페이스 구성 요소가 있는지를 활성 상태에서 UI 활성 상태를 구분합니다. 그렇지 않으면 활성 상태로 UI 활성 상태와 유사합니다. 서버에서 실행 취소를 지 원하는 경우 서버는 로드 또는 열린 상태에 도달할 때까지 OLE 항목의 실행 취소 상태 정보를 유지 하는 일을 해야 합니다.

## <a name="see-also"></a>참고자료

[컨테이너](../mfc/containers.md)<br/>
[활성화](../mfc/activation-cpp.md)<br/>
[컨테이너: 클라이언트 항목 알림](../mfc/containers-client-item-notifications.md)<br/>
[추적기](../mfc/trackers.md)<br/>
[CRectTracker 클래스](../mfc/reference/crecttracker-class.md)
