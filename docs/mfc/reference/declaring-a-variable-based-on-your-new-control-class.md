---
title: 새 컨트롤 클래스 기반의 변수 선언
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.control.variable
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
ms.openlocfilehash: d550b80beb124f3d8ec36ba81dad1a9ca7e9fa15
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741612"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>새 컨트롤 클래스 기반의 변수 선언

MFC 컨트롤 클래스를 만든 경우에 따라 변수를 선언할 수 있습니다. 컨텍스트를 새 변수를 제공 하려면 대화 상자 편집기를 열고는 재사용 가능한 컨트롤을 사용 하려면 대화 상자를 편집 합니다. 또한 대화 상자에 관련 된 클래스가 이미 있어야 합니다. 대화 상자 편집기를 사용 하 여 정보를 참조 하세요 [대화 상자 편집기](../../windows/dialog-editor.md)합니다.

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>다시 사용할 수 있는 클래스 기반의 변수 선언

1. 대화 상자를 편집 하는 경우, 대화 상자 컨트롤 도구 모음에서 새 컨트롤의 기본 클래스와 동일한 형식의 컨트롤을 끕니다.

1. 삭제 컨트롤 위에 마우스 포인터를 놓습니다.

1. CTRL 키를 누른 컨트롤을 두 번 클릭 합니다.

   합니다 [멤버 변수 추가](../../ide/add-member-variable-wizard.md) 대화 상자가 나타납니다.

1. 에 **액세스** 상자 컨트롤에 대 한 올바른 액세스를 선택 합니다.

1. 클릭 합니다 **제어 변수** 확인란 합니다.

1. 에 **변수 이름** 상자에 이름을 입력 합니다.

1. 아래 **범주**, 클릭 **제어**입니다.

1. 에 **컨트롤 ID** 목록에서 추가한 컨트롤을 선택 합니다. **변수 형식** 목록에 올바른 변수 유형, 표시 및 **컨트롤 형식과** 상자 정확한 컨트롤 유형을 표시 되어야 합니다.

9. 에 **주석** 상자를 표시 하려면 코드에 주석을 추가 합니다.

10. **확인**을 클릭합니다.

## <a name="see-also"></a>참고자료

[함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[클래스 구조 탐색](../../ide/navigate-code-cpp.md)
