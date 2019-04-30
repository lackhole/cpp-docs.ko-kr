---
title: 대화 상자 닫기
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 07e4159eccde1fab89d4a5ffadee4e6d11fc20f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326848"
---
# <a name="closing-the-dialog-box"></a>대화 상자 닫기

사용자가 해당 단추, 일반적으로 단추를 확인 또는 취소 단추 중 하나를 선택 하는 경우 모달 대화 상자를 닫습니다. Windows 대화 상자 개체를 보낼 확인 또는 취소 단추를 선택 하면를 **BN_CLICKED** 단추를 사용 하 여 컨트롤 알림 메시지의 ID를 하거나 **IDOK** 하거나 **IDCANCEL**합니다. `CDialog` 이러한 메시지에 대 한 기본 처리기 함수를 제공 합니다. `OnOK` 고 `OnCancel`입니다. 기본 처리기 호출을 `EndDialog` 멤버 함수 대화 상자 창을 닫습니다. 호출할 수도 있습니다 `EndDialog` 사용자 고유의 코드에서. 자세한 내용은 참조는 [EndDialog](../mfc/reference/cdialog-class.md#enddialog) 클래스의 멤버 함수 `CDialog` 에 *MFC 참조*.

을 닫고 삭제 모덜리스 대화 상자에 대 한 정렬 하려면 재정의 `PostNcDestroy` 호출을 **삭제** 연산자를 **이** 포인터입니다. [대화 상자 제거](../mfc/destroying-the-dialog-box.md) 다음에 대해 설명 합니다.

## <a name="see-also"></a>참고자료

[대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)
