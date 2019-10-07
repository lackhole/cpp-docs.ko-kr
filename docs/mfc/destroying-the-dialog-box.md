---
title: 대화 상자 소멸시키기
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
ms.openlocfilehash: 8b407c6e832dde7a5865146e7cc12d1840d3234a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685848"
---
# <a name="destroying-the-dialog-box"></a>대화 상자 소멸시키기

모달 대화 상자는 일반적으로 스택 프레임에서 만들어지고 해당 대화 상자를 만든 함수가 종료 될 때 소멸 됩니다. 대화 상자 개체의 소멸자는 개체가 범위를 벗어날 때 호출 됩니다.

모덜리스 대화 상자는 일반적으로 부모 뷰나 프레임 창 (응용 프로그램의 주 프레임 창 또는 문서 프레임 창)에서 만들고 소유 합니다. 기본 [OnClose](../mfc/reference/cwnd-class.md#onclose) 처리기는 대화 상자 창을 소멸 시키는 [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)를 호출 합니다. 대화 상자가 단독으로 사용 되는 경우이 대화 상자에 대 한 포인터 또는 다른 특별 한 소유권 의미 체계가 없으면 [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) 를 C++ 재정의 하 여 대화 상자 개체를 제거 해야 합니다. 또한 [OnCancel](../mfc/reference/cdialog-class.md#oncancel) 를 재정의 하 고 내부에서 `DestroyWindow`을 호출 해야 합니다. 그렇지 않으면 대화 상자의 소유자가 개체가 더 이상 필요 하지 않을 C++ 때 해당 개체를 삭제 해야 합니다.

## <a name="see-also"></a>참조

[MFC에서 대화 상자 작업](../mfc/life-cycle-of-a-dialog-box.md)
