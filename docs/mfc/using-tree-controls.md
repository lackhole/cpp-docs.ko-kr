---
title: 트리 컨트롤 사용
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
ms.openlocfilehash: 9cff48018d728ef9578be38c0d94300011265fa1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411450"
---
# <a name="using-tree-controls"></a>트리 컨트롤 사용

트리 컨트롤의 일반적인 사용 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 아래의 패턴을 따릅니다.

- 컨트롤이 만들어집니다. 대화 상자 템플릿에 컨트롤을 지정 하거나 사용 중인 경우 `CTreeView`, 대화 상자 또는 보기를 만들 때 생성은 자동입니다. 일부 다른 창의 자식 창으로 트리 컨트롤을 만들려는 경우 사용 합니다 [만들기](../mfc/reference/ctreectrl-class.md#create) 멤버 함수입니다.

- 트리 컨트롤 이미지를 사용 하 여을 원한다 면 호출 하 여 이미지 목록을 설정할 [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist)합니다. 호출 하 여 들여쓰기를 변경할 수도 있습니다 [SetIndent](../mfc/reference/ctreectrl-class.md#setindent)합니다. 이렇게 하려면 적절 한 시간에 포함 되는지 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (대화 상자에서 컨트롤용) 또는 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (뷰 용).

- 호출 하 여 컨트롤에 데이터를 저장 합니다 `CTreeCtrl`의 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) 각 데이터 항목에 한 번씩 함수입니다. `InsertItem` 자식 항목을 추가 하는 경우와 같이 나중에 참조 하는 데 사용할 수 있는 항목에 핸들을 반환 합니다. 데이터를 초기화 하는 것이 좋습니다 `OnInitDialog` (대화 상자에서 컨트롤용) 또는 `OnInitialUpdate` (뷰 용).

- 사용자가 컨트롤과 상호 작용하여 다양한 알림 메시지가 전송됩니다. 각 컨트롤 창의 메시지 맵에 ON_NOTIFY_REFLECT 매크로 추가 하 여 또는 부모 창의 메시지 맵에 ON_NOTIFY 매크로 추가 하 여 처리 하려는 메시지를 처리 하는 함수를 지정할 수 있습니다. 참조 [트리 컨트롤 알림 메시지](../mfc/tree-control-notification-messages.md) 가능한 목록은이 항목 뒷부분 합니다.

- 다양한 Set 멤버 함수를 호출하여 컨트롤에 대한 값을 설정합니다. 변경 내용을 적용할 수 있는 들여쓰기를 설정 하 고 텍스트, 이미지 또는 항목과 연결 된 데이터 변경 포함 됩니다.

- 컨트롤의 내용을 검사 하는 다양 한 Get 함수를 사용 합니다. 또한 부모, 자식 및 형제의 지정된 된 항목에 대 한 핸들을 검색할 수 있도록 하는 함수를 사용 하 여 트리 컨트롤의 내용을 탐색할 수 있습니다. 특정 노드의 자식을 정렬할 수 있습니다.

- 컨트롤을 사용 하 여 완료 하는 경우 제대로 제거 해야 합니다. 트리 컨트롤은 대화 상자 또는 뷰일 경우이 고 `CTreeCtrl` 개체는 자동으로 소멸 됩니다. 그렇지 않은 경우 컨트롤 및 `CTreeCtrl` 개체가 모두 제대로 소멸되었는지 확인해야 합니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
