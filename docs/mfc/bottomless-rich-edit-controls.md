---
title: 바닥 없는 Rich Edit 컨트롤
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: 6f078680777dcf80a4349ea34e4520cb56031f44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400749"
---
# <a name="bottomless-rich-edit-controls"></a>바닥 없는 Rich Edit 컨트롤

응용 프로그램에 rich edit 컨트롤 크기 조정 수 있습니다 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 해당 콘텐츠와 동일한 크기가 항상 있도록 필요에 따라 합니다. Rich edit 컨트롤의 부모 창에 전송 하 여이 소위 "바닥 없음" 기능을 지원 합니다는 [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize) 해당 내용의 크기를 변경할 때마다 알림 메시지입니다.

처리 하는 경우는 **EN_REQUESTRESIZE** 알림 메시지를 응용 프로그램에는 지정 된 차원으로 컨트롤 크기 조정 해야 [REQRESIZE](/windows/desktop/api/richedit/ns-richedit-_reqresize) 구조입니다. 응용 프로그램은 높이에서의 컨트롤 변경 사항을 수용하기 위해 컨트롤 근처의 모든 정보를 이동할 수 있습니다. 컨트롤의 크기를 조정 하려면 사용 합니다 `CWnd` 함수 [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)합니다.

바닥 없는 rich edit 컨트롤 보내도록 할 수 있습니다는 **EN_REQUESTRESIZE** 사용 하 여 알림 메시지를 [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) 멤버 함수입니다. 이 메시지에 유용 합니다 [OnSize](../mfc/reference/cwnd-class.md#onsize) 처리기입니다.

받을 **EN_REQUESTRESIZE** 알림 메시지를 사용 하 여 알림을 활성화 해야 합니다는 `SetEventMask` 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
