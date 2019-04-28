---
title: 바로 가기 키 컨트롤 사용
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
ms.openlocfilehash: d9178fe989e476111a3da55861642e9aa6311872
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180533"
---
# <a name="using-a-hot-key-control"></a>바로 가기 키 컨트롤 사용

바로 가기 키 컨트롤의 일반적인 사용 아래 패턴을 따릅니다.

- 컨트롤이 만들어집니다. 컨트롤이 대화 상자 템플릿에 지정될 경우 대화 상자를 만들 때 자동으로 만들어집니다. (해야는 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) hot key 컨트롤에 해당 하는 대화 상자 클래스의 멤버입니다.) 사용할 수 있습니다 합니다 [만들기](../mfc/reference/chotkeyctrl-class.md#create) 모든 창의 자식 창으로 컨트롤을 만드는 데 멤버 함수입니다.

- 컨트롤에 대 한 기본값을 설정 하려는 경우 호출 된 [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) 멤버 함수입니다. 특정 상태 전환이 금지 하려면 호출 [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules)합니다. 이 작업을 수행할 수 있는 좋은 기회는 대화 상자에서 컨트롤에 대 한 대화 상자에서 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수입니다.

- Hot key 컨트롤에 포커스가 있을 때 바로 가기 키 조합을 눌러 컨트롤을 사용 하 여 사용자 상호 작용 합니다. 사용자 후 어떤 이유로 든이 작업 완료 되었음을 나타냅니다, 아마도 대화 상자에서 단추를 클릭 하 여 합니다.

- 멤버 함수를 사용 해야 프로그램 알림을 받은 사용자가 바로 가기 키를 선택 하는 경우 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) hot key 컨트롤에서 가상 키와 shift 상태 값을 검색 합니다.

- 사용자가 선택한 키를 알고에 설명 된 방법 중 하나를 사용 하 여 바로 가기 키를 설정할 수 있습니다 [바로 가기 키 설정](../mfc/setting-a-hot-key.md)합니다.

- Hot key 컨트롤 대화 상자에 있으면이 고 `CHotKeyCtrl` 개체는 자동으로 소멸 됩니다. 그렇지 않은 경우 컨트롤 및 `CHotKeyCtrl` 개체가 모두 제대로 소멸되었는지 확인해야 합니다.

## <a name="see-also"></a>참고자료

[CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
