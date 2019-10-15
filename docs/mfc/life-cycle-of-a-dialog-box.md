---
title: MFC에서 대화 상자 작업
ms.date: 09/27/2019
helpviewer_keywords:
- dialog boxes [MFC], life cycle
- modal dialog boxes [MFC], life cycle
- modeless dialog boxes [MFC], life cycle
- MFC dialog boxes [MFC], life cycle
- life cycle of dialog boxes [MFC]
ms.assetid: e16fd78e-238d-4f31-8c9d-8564f3953bd9
ms.openlocfilehash: ad15250cf9a8dd663072cf9423263260bbb40a0e
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685725"
---
# <a name="working-with-dialog-boxes-in-mfc"></a>MFC에서 대화 상자 작업

대화 상자의 수명 주기 동안 사용자가 대화 상자를 호출 합니다 .이 대화 상자는 일반적으로 대화 상자 개체를 만들고 초기화 하는 명령 처리기 내에서 사용자가 대화 상자와 상호 작용 한 다음 대화 상자를 닫습니다.

모달 대화 상자의 경우 처리기는 대화 상자를 닫을 때 사용자가 입력 한 데이터를 수집 합니다. Dialog 개체는 대화 상자 창이 닫힌 후에도 존재 하므로 대화 상자 클래스의 멤버 변수를 사용 하 여 데이터를 추출할 수 있습니다.

모덜리스 대화 상자의 경우 대화 상자를 계속 표시 하는 동안 대화 상자 개체에서 데이터를 추출 하는 경우가 종종 있습니다. 특정 시점에 대화 상자 개체가 제거 됩니다. 이러한 상황이 발생 하는 경우에는 코드에 따라 달라 집니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [대화 상자 만들기 및 표시](../mfc/creating-and-displaying-dialog-boxes.md)

- [모달 대화 상자 만들기](../mfc/creating-modal-dialog-boxes.md)

- [모덜리스 대화 상자 만들기](../mfc/creating-modeless-dialog-boxes.md)

- [메모리에서 대화 상자 템플릿 사용](../mfc/using-a-dialog-template-in-memory.md)

- [대화 상자의 배경색 설정](../mfc/setting-the-dialog-boxs-background-color.md)

- [대화 상자 초기화](../mfc/initializing-the-dialog-box.md)

- [대화 상자에서 Windows 메시지 처리](../mfc/handling-windows-messages-in-your-dialog-box.md)

- [대화 상자 개체에서 데이터 검색](../mfc/retrieving-data-from-the-dialog-object.md)

- [대화 상자 닫기](../mfc/closing-the-dialog-box.md)

- [대화 상자 삭제](../mfc/destroying-the-dialog-box.md)

- [DDX (대화 상자 데이터 교환) 및 유효성 검사 (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [속성 시트 대화 상자](../mfc/property-sheets-and-property-pages-mfc.md)

## <a name="see-also"></a>참조

[대화 상자](../mfc/dialog-boxes.md)
