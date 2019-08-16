---
title: 애니메이션 컨트롤이 보내는 알림
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 68ede3bc55669a29eef192d38b29b8c1ab433e4b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508020"
---
# <a name="notifications-sent-by-animation-controls"></a>애니메이션 컨트롤이 보내는 알림

애니메이션 컨트롤 ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md))은 두 가지 유형의 알림 메시지를 보냅니다. 알림은 [WM_COMMAND](/windows/win32/menurc/wm-command) 메시지 형식으로 전송 됩니다.

[ACN_START](/windows/win32/Controls/acn-start) 메시지는 애니메이션 컨트롤이 클립 재생을 시작할 때 전송 됩니다. [ACN_STOP](/windows/win32/Controls/acn-stop) 메시지는 애니메이션 컨트롤이 완료 되거나 클립 재생이 중지 될 때 전송 됩니다.

## <a name="see-also"></a>참고자료

[CAnimateCtrl 사용](../mfc/using-canimatectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
