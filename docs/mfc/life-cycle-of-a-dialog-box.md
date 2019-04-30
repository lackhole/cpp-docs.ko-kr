---
title: 대화 상자의 수명 주기
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: a3772a180e35a57c997446fcf2268d84bec2daa5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365343"
---
# <a name="life-cycle-of-a-dialog-box"></a>대화 상자의 수명 주기

대화 상자의 수명 주기 동안 사용자 대화 상자를 호출 하 고 일반적으로 만들고 대화 상자 개체를 초기화 하는 명령 처리기 내에서 사용자 상호 작용 하는 대화 상자를 사용 하 여 대화 상자를 닫습니다.

모달 대화 상자에 대 한 처리기는 사용자가 대화 상자를 닫히고를 입력 한 모든 데이터를 수집 합니다. 대화 상자 개체 대화 상자 창을 닫으면 있으므로 데이터를 추출 하 대화 상자 클래스의 멤버 변수를 간단히 사용할 수 있습니다.

모덜리스 대화 상자에 대 한 하면 데이터를 추출할 수도 대화 상자 개체에서 대화 상자는 계속 표시 합니다. 어느 시점에서 대화 개체는 소멸 됩니다. 이 경우 코드에 따라 달라 집니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [만들기 및 대화 상자를 표시 합니다.](../mfc/creating-and-displaying-dialog-boxes.md)

- [모달 대화 상자 만들기](../mfc/creating-modal-dialog-boxes.md)

- [모덜리스 대화 상자 만들기](../mfc/creating-modeless-dialog-boxes.md)

- [메모리의 대화 상자 템플릿 사용](../mfc/using-a-dialog-template-in-memory.md)

- [대화 상자의 배경색 설정](../mfc/setting-the-dialog-boxs-background-color.md)

- [대화 상자 초기화](../mfc/initializing-the-dialog-box.md)

- [대화 상자에서 Windows 메시지 처리](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [대화 상자 개체에서 데이터 검색](../mfc/retrieving-data-from-the-dialog-object.md)

- [대화 상자 닫기](../mfc/closing-the-dialog-box.md)

- [대화 상자 제거](../mfc/destroying-the-dialog-box.md)

- [(DDX) 대화 상자 데이터 교환 및 유효성 검사 (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [속성 시트 대화 상자](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>참고자료

[대화 상자](../mfc/dialog-boxes.md)
