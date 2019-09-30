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
ms.openlocfilehash: 18b4c4d1386716a0a3282b88d6fdf5a701abce08
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685795"
---
# <a name="dialog-boxes"></a>대화 상자

Windows 용 응용 프로그램은 대화 상자를 통해 사용자와 통신 하는 경우가 많습니다. 클래스 [CDialog](../mfc/reference/cdialog-class.md) 는 대화 상자를 관리 하기 위한 인터페이스를 제공 C++ 하 고, 시각적 대화 상자 편집기를 사용 하 여 대화 상자를 쉽게 디자인 하 고, 대화 상자 템플릿 리소스를 만들고, 코드 마법사를 사용 하 여의 초기화 및 유효성 검사 프로세스를 간소화 대화 상자에서 컨트롤을 만들고 사용자가 입력 한 값을 수집 합니다.

대화 상자에는 다음을 비롯 한 컨트롤이 포함 됩니다.

- 편집 상자, 누름 단추, 목록 상자, 콤보 상자, 트리 컨트롤, 목록 컨트롤, 진행률 표시기 등의 Windows 공용 컨트롤

- ActiveX 컨트롤.

- 소유자가 그린 컨트롤: 대화 상자에서 그리기를 담당 하는 컨트롤입니다.

대부분의 대화 상자는 모달 이며, 사용자가 프로그램의 다른 부분을 사용 하기 전에 대화 상자를 닫아야 합니다. 하지만 대화 상자가 열려 있는 동안 사용자가 다른 창에서 작업할 수 있도록 하는 모덜리스 대화 상자를 만들 수 있습니다. MFC는 @no__t 클래스를 사용 하 여 두 가지 종류의 대화 상자를 모두 지원 합니다. [대화 상자 편집기](../windows/dialog-editor.md)를 사용 하 여 만든 대화 상자 템플릿 리소스를 사용 하 여 컨트롤을 정렬 하 고 관리 합니다.

[속성 시트](../mfc/property-sheets-mfc.md)(탭 대화 상자 라고도 함)는 개별 대화 상자 컨트롤의 "페이지"를 포함 하는 대화 상자입니다. 각 페이지의 맨 위에는 파일 폴더 "탭"이 있습니다. 탭을 클릭 하면 대화 상자의 맨 앞으로 페이지가 표시 됩니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [예제: 메뉴 명령을 통해 대화 상자 표시](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)

- [프레임 워크의 대화 상자 구성 요소](../mfc/dialog-box-components-in-the-framework.md)

- [모달 및 모덜리스 대화 상자](../mfc/modal-and-modeless-dialog-boxes.md)

- 대화 상자의 [속성 시트 및 속성 페이지](../mfc/property-sheets-and-property-pages-mfc.md)

- [대화 상자 리소스 만들기](../mfc/creating-the-dialog-resource.md)

- [코드 마법사로 대화 상자 클래스 만들기](../mfc/creating-a-dialog-class-with-code-wizards.md)

- [MFC에서 대화 상자 작업](../mfc/life-cycle-of-a-dialog-box.md)

- [DDX (대화 상자 데이터 교환) 및 유효성 검사 (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [대화 상자의 컨트롤에 대 한 형식이 안전한 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [클래스에 Windows 메시지 매핑](../mfc/mapping-windows-messages-to-your-class.md)

- [일반적으로 재정의되는 멤버 함수](../mfc/commonly-overridden-member-functions.md)

- [일반적으로 추가되는 멤버 함수](../mfc/commonly-added-member-functions.md)

- [일반 대화 상자 클래스](../mfc/common-dialog-classes.md)

- [OLE의 대화 상자](../mfc/dialog-boxes-in-ole.md)

- 사용자 인터페이스가 대화 상자 인 응용 프로그램 만들기: [CMNCTRL1](../overview/visual-cpp-samples.md) 또는 [CMNCTRL2](../overview/visual-cpp-samples.md) 샘플 프로그램을 참조 하세요. 응용 프로그램 마법사도이 옵션을 제공 합니다.

- [샘플](../mfc/dialog-sample-list.md)

## <a name="see-also"></a>참조

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
