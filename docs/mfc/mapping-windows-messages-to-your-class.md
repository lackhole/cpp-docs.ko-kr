---
title: 클래스에 Windows 메시지 매핑
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 7e15f52e41d4ac91a839629342258128db86e2d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363858"
---
# <a name="mapping-windows-messages-to-your-class"></a>클래스에 Windows 메시지 매핑

Windows 메시지를 처리 하 여 대화 상자에 필요한 경우 적절 한 처리기 함수를 재정의 합니다. 이렇게 하려면 속성 창을 사용 하 여 [메시지 매핑](../mfc/reference/mapping-messages-to-functions.md) 대화 상자 클래스에 있습니다. 각 메시지에 대 한 메시지 맵 항목을 쓰고 메시지 처리기 멤버 함수는 클래스에 추가 합니다. 시각적 개체를 사용 하 여 C++ 소스 코드 편집기의 메시지 처리기에 코드를 작성 합니다.

멤버 함수를 재정의할 수도 있습니다 [CDialog](../mfc/reference/cdialog-class.md) 와 해당 기본 클래스, 특히 [CWnd](../mfc/reference/cwnd-class.md)합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)

- [일반적으로 재정의 된 멤버 함수](../mfc/commonly-overridden-member-functions.md)

- [일반적으로 추가 되는 멤버 함수](../mfc/commonly-added-member-functions.md)

## <a name="see-also"></a>참고자료

[대화 상자](../mfc/dialog-boxes.md)<br/>
[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)
