---
title: 모달 및 모덜리스 대화 상자
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
ms.openlocfilehash: c3a5263736324d7fe25066e8879d13b3a41768de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238418"
---
# <a name="modal-and-modeless-dialog-boxes"></a>모달 및 모덜리스 대화 상자

클래스를 사용할 수 있습니다 [CDialog](../mfc/reference/cdialog-class.md) 두 종류의 대화 상자를 관리 하려면:

- *모달 대화 상자*, 사용자가 프로그램을 계속 하려면 응답 필요

- *모덜리스 대화 상자*, 다른 사용자 작업을 허용 하지만 화면에는 언제 든 지 사용할 수 있는

리소스 편집 및 만들기 대화 상자 템플릿을 절차 모달 및 모덜리스 대화 상자에 대 한 동일 합니다.

프로그램에 대 한 대화 상자를 만드는 다음 단계를 수행 합니다.

1. 사용 된 [대화 상자 편집기](../windows/dialog-editor.md) 대화 상자를 디자인 하 고 해당 대화 상자 템플릿 리소스를 만들어야 합니다.

1. 대화 상자 클래스를 만듭니다.

1. 연결 된 [메시지 처리기에 대화 상자 리소스의 컨트롤](../windows/adding-event-handlers-for-dialog-box-controls.md) 대화 상자 클래스에서.

1. 연결 대화 상자의 컨트롤을 사용 하 여 지정 하는 데이터 멤버를 추가 [대화 상자 데이터 교환](../mfc/dialog-data-exchange.md) 하 고 [대화 상자 데이터 유효성 검사](../mfc/dialog-data-validation.md) 컨트롤에 대 한 합니다.

## <a name="see-also"></a>참고자료

[대화 상자](../mfc/dialog-boxes.md)<br/>
[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)
