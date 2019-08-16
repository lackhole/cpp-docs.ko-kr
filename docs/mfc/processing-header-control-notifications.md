---
title: 헤더 컨트롤 알림 처리
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
ms.openlocfilehash: f60a0c918476702881984f976b220130727cf4b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507941"
---
# <a name="processing-header-control-notifications"></a>헤더 컨트롤 알림 처리

보기 또는 대화 상자 클래스에서 속성 창를 사용 하 여 처리 하려는 모든 헤더 컨트롤 ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) 알림 메시지에 대 한 switch 문을 사용 하 여 [onchildnotify](../mfc/reference/cwnd-class.md#onchildnotify) 처리기 함수를 만듭니다 ( [메시지를 함수에 매핑 참조). ](../mfc/reference/mapping-messages-to-functions.md)). 사용자가 머리글 항목을 클릭 하거나 두 번 클릭 하 고 항목 사이에 구분선을 끌어와 같이 알림이 부모 창으로 전송 됩니다.

헤더 컨트롤과 연결 된 알림 메시지는 Windows SDK의 [헤더 컨트롤 참조](/windows/win32/controls/header-control-reference) 에 나열 됩니다.

## <a name="see-also"></a>참고자료

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
