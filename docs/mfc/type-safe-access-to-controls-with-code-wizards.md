---
title: 코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: bf3ecf3016fcc15bd4ada7a15208acd9a04ca0a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180865"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행

DDX 기능에 익숙한 경우에 컨트롤 속성을 사용할 수 있습니다 합니다 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) 형식이 안전한 액세스를 만들려고 합니다. 이 방법은 코드 마법사 하지 않고 컨트롤을 만드는 것 보다 쉽습니다.

컨트롤의 값에 대 한 액세스를 간단히 하려는 경우 DDX는 것을 제공 합니다. 컨트롤의 값에 액세스 둘 수행 하려는 경우 해당 클래스의 멤버 변수 대화 상자 클래스에 추가할 멤버 변수 추가 마법사를 사용 합니다. 컨트롤 속성에이 멤버 변수를 연결 합니다.

멤버 변수 값 속성 대신 컨트롤 속성이 있을 수 있습니다. Value 속성 참조와 같은 컨트롤에서 반환 되는 데이터 형식의 `CString` 나 **int**합니다. 컨트롤 속성에 형식이 같은 MFC 컨트롤 클래스 중 하나는 데이터 멤버를 통해 컨트롤에 직접 액세스할 수 있도록 `CButton` 또는 `CEdit`합니다.

> [!NOTE]
>  지정된 된 컨트롤에 사용할 수 있습니다, 원한다 면 값 속성을 최대 컨트롤 속성을 가진 하나의 멤버 변수를 사용 하 여 여러 멤버 변수. 컨트롤 또는 다른 창에 연결 하는 여러 개체 메시지 맵에 모호성을 초래 하기 때문에 컨트롤에 매핑되어 MFC 개체를 하나만 사용할 수 있습니다.

컨트롤 개체에 대 한 모든 멤버 함수를 호출 하려면이 개체를 사용할 수 있습니다. 이러한 호출 대화 상자에서 컨트롤을 영향을 줍니다. 예를 들어, 확인란 컨트롤을 나타내는 변수 *m_Checkbox*, 형식의 `CButton`를 호출할 수 있습니다.

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

여기 멤버 변수 *m_Checkbox* 멤버 함수와 동일한 용도로 사용 됩니다 `GetMyCheckbox` 에서처럼 [컨트롤 없이 코드 마법사에 대 한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-without-code-wizards.md)합니다. 확인란을 자동 확인란 없는 경우 계속 해야 처리기 BN_CLICKED 컨트롤 알림 메시지에 대 한 대화 상자 클래스에 단추를 클릭할 때 합니다.

컨트롤에 대 한 자세한 내용은 참조 하세요. [컨트롤](../mfc/controls-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[대화 상자의 컨트롤에 대한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[코드 마법사를 사용하지 않고 컨트롤에 대한 형식이 안전한 액세스 수행](../mfc/type-safe-access-to-controls-without-code-wizards.md)
