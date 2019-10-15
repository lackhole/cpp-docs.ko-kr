---
title: 코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: fefa722209d37e2612201c4471e5764f9d71f27a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685034"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>코드 마법사를 사용하여 컨트롤에 대한 형식이 안전한 액세스 수행

DDX 기능에 대해 잘 알고 있는 경우 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) 에서 컨트롤 속성을 사용 하 여 형식이 안전한 액세스를 만들 수 있습니다. 이 방법은 코드 마법사 없이 컨트롤을 만드는 것 보다 쉽습니다.

컨트롤의 값에 액세스 하려는 경우 DDX는이를 제공 합니다. 컨트롤의 값에 액세스 하는 것 보다 더 많은 작업을 수행 하려는 경우 멤버 변수 추가 마법사를 사용 하 여 해당 클래스의 멤버 변수를 대화 상자 클래스에 추가 합니다. 이 멤버 변수를 컨트롤 속성에 연결 합니다.

멤버 변수는 Value 속성 대신 컨트롤 속성을 가질 수 있습니다. Value 속성은 `CString` 또는 **int**와 같이 컨트롤에서 반환 되는 데이터의 형식을 참조 합니다. 컨트롤 속성을 사용 하면 `CButton` 또는 `CEdit`과 같은 MFC의 컨트롤 클래스 중 하나인 데이터 멤버를 통해 컨트롤에 직접 액세스할 수 있습니다.

> [!NOTE]
>  지정 된 컨트롤의 경우 Value 속성을 사용 하는 여러 멤버 변수와 컨트롤 속성을 가진 멤버 변수가 최대 하나만 있을 수 있습니다. 컨트롤에 연결 된 여러 개체 또는 다른 창에는 메시지 맵의 모호성이 발생 하므로 하나의 MFC 개체만 컨트롤에 매핑할 수 있습니다.

이 개체를 사용 하 여 컨트롤 개체에 대 한 멤버 함수를 호출할 수 있습니다. 이러한 호출은 대화 상자의 컨트롤에 영향을 줍니다. 예를 들어 `CButton` 형식의 변수 *m_Checkbox*으로 표시 된 확인란 컨트롤의 경우 다음을 호출할 수 있습니다.

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

여기서 *m_Checkbox* 멤버 변수는 [코드 마법사를 사용 하지 않고 컨트롤에 대 한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-without-code-wizards.md)에 표시 되는 멤버 함수 `GetMyCheckbox`과 동일한 용도를 제공 합니다. 확인란이 자동 확인란이 아니면 단추를 클릭할 때 BN_CLICKED 컨트롤 알림 메시지에 대 한 대화 상자 클래스에 처리기가 계속 필요 합니다.

컨트롤에 대 한 자세한 내용은 [컨트롤](../mfc/controls-mfc.md)을 참조 하세요.

## <a name="see-also"></a>참조

[대화 상자의 컨트롤에 대한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[MFC에서 대화 상자 작업](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[코드 마법사를 사용하지 않고 컨트롤에 대한 형식이 안전한 액세스 수행](../mfc/type-safe-access-to-controls-without-code-wizards.md)
