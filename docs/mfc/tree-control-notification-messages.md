---
title: 트리 컨트롤 알림 메시지
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
ms.openlocfilehash: 90e2e112d7862dfed7d8af31cfb72ff45633a2c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181644"
---
# <a name="tree-control-notification-messages"></a>트리 컨트롤 알림 메시지

트리 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) WM_NOTIFY 메시지 다음 알림 메시지를 보냅니다.

|알림 메시지|설명|
|--------------------------|-----------------|
|TVN_BEGINDRAG|끌어서 놓기 작업의 시작을 알림|
|TVN_BEGINLABELEDIT|전체 레이블 편집의 시작을 알림|
|TVN_BEGINRDRAG|마우스 오른쪽 단추를 사용 하 여 끌어서 놓기 작업의 시작을 신호|
|TVN_DELETEITEM|특정 항목의 삭제를 알림|
|TVN_ENDLABELEDIT|레이블 편집의 끝을 알리기|
|TVN_GETDISPINFO|트리 컨트롤 항목을 표시 해야 하는 요청 정보|
|TVN_ITEMEXPANDED|하위 항목의 부모 항목의 목록을 확장 또는 축소 되었음을 신호|
|TVN_ITEMEXPANDING|하위 항목의 부모 항목의 목록을 확장 하거나 축소할 수에 신호|
|TVN_KEYDOWN|키보드 이벤트를 알림|
|TVN_SELCHANGED|한 항목에서 다른 선택이 변경 되었음|
|TVN_SELCHANGING|다른 항목에서 변경 될 선택 된 신호|
|TVN_SETDISPINFO|항목에 대 한 유지 관리 정보를 업데이트 하려면 알림|

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
