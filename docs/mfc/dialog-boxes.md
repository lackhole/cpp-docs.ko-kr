---
title: 대화 상자
ms.date: 11/04/2016
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
ms.openlocfilehash: 32a8f8784459338131d4893f25d8798f8031b68b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778496"
---
# <a name="dialog-boxes"></a>대화 상자

Windows 용 응용 프로그램은 자주 대화 상자를 통해 사용자와 통신합니다. 클래스 [CDialog](../mfc/reference/cdialog-class.md) 코드 마법사를 초기화 하는 프로세스를 간소화 하 고 대화 상자를 관리, Visual c + + 대화 상자 편집기 쉽게 대화 상자를 디자인 하 고 해당 대화 상자 템플릿 리소스를 만드는 인터페이스를 제공 하 고 사용자가 입력 한 값을 수집 하 고 대화 상자에서 컨트롤의 유효성을 검사 합니다.

대화 상자에 컨트롤을 포함 하 여 포함 합니다.

- 와 같은 Windows 공용 컨트롤 상자, 누름 단추, 목록 상자, 콤보 상자, 트리 컨트롤, 목록 컨트롤 및 진행률 표시기를 편집 합니다.

- ActiveX 컨트롤입니다.

- 소유자가 그린 컨트롤: 사용자는 대화 상자에서 그리기를 담당 하는 컨트롤입니다.

대부분의 대화 상자는 모달 사용자 프로그램의 다른 부분을 사용 하기 전에 대화 상자를 닫아야 합니다. 그러나 사용자 대화 상자가 열려 있는 동안 다른 windows를 사용 하 여 작업할 수 있는 모덜리스 대화 상자를 만들 수 있습니다. MFC는 두 가지 유형의 클래스를 사용 하 여 대화 상자를 모두 지원 `CDialog`합니다. 컨트롤 정렬 되 고 생성 된 대화 상자 템플릿 리소스를 사용 하 여 관리 합니다 [대화 상자 편집기](../windows/dialog-editor.md)합니다.

[속성 시트](../mfc/property-sheets-mfc.md)탭 대화 상자 라고도 하며,은 고유한 대화 상자 컨트롤의 "페이지"를 포함 하는 대화 상자. 각 페이지 맨 위에 있는 "탭" 파일 폴더를 있습니다. 탭을 클릭 하면 대화 상자의 맨 앞으로 해당 페이지를 제공 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [예제: 메뉴 명령을 통해 대화 상자를 표시합니다.](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)

- [프레임 워크의 대화 상자 구성 요소](../mfc/dialog-box-components-in-the-framework.md)

- [모달 및 모덜리스 대화 상자](../mfc/modal-and-modeless-dialog-boxes.md)

- [속성 시트 및 속성 페이지](../mfc/property-sheets-and-property-pages-mfc.md) 대화 상자에서

- [대화 상자 리소스 만들기](../mfc/creating-the-dialog-resource.md)

- [코드 마법사로 대화 상자 클래스 만들기](../mfc/creating-a-dialog-class-with-code-wizards.md)

- [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)

- [(DDX) 대화 상자 데이터 교환 및 유효성 검사 (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [대화 상자에서 컨트롤에 대 한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [클래스에 Windows 메시지 매핑](../mfc/mapping-windows-messages-to-your-class.md)

- [일반적으로 재정의되는 멤버 함수](../mfc/commonly-overridden-member-functions.md)

- [일반적으로 추가되는 멤버 함수](../mfc/commonly-added-member-functions.md)

- [일반 대화 상자 클래스](../mfc/common-dialog-classes.md)

- [OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)

- 해당 사용자 인터페이스 대화 상자는 응용 프로그램 만들기: 참조를 [CMNCTRL1](../overview/visual-cpp-samples.md) 또는 [CMNCTRL2](../overview/visual-cpp-samples.md) 샘플 프로그램입니다. 응용 프로그램 마법사는이 옵션을 제공합니다.

- [샘플](../mfc/dialog-sample-list.md)

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
