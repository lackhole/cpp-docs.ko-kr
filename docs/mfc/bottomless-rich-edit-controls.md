---
title: 바닥 없는 Rich Edit 컨트롤
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: d5650d34ffc350444061aa6147c38af016458811
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915262"
---
# <a name="bottomless-rich-edit-controls"></a>바닥 없는 Rich Edit 컨트롤

응용 프로그램은 필요에 따라 rich edit 컨트롤 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))의 크기를 조정 하 여 항상 콘텐츠와 크기가 같도록 할 수 있습니다. Rich edit 컨트롤은 해당 콘텐츠 크기가 변경 될 때마다 부모 창에 [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize) 알림 메시지를 전송 하 여이를 "무제한" 기능 이라고 합니다.

**EN_REQUESTRESIZE** 알림 메시지를 처리할 때 응용 프로그램은 지정 된 [REQRESIZE](/windows/desktop/api/richedit/ns-richedit-reqresize) 구조체의 차원에 맞게 컨트롤의 크기를 조정 해야 합니다. 응용 프로그램은 높이에서의 컨트롤 변경 사항을 수용하기 위해 컨트롤 근처의 모든 정보를 이동할 수 있습니다. 컨트롤의 크기를 조정 하려면 `CWnd` [setwindowpos](../mfc/reference/cwnd-class.md#setwindowpos)함수를 사용 하면 됩니다.

무제한 rich edit 컨트롤에서 [Requestresize](../mfc/reference/cricheditctrl-class.md#requestresize) 멤버 함수를 사용 하 여 **EN_REQUESTRESIZE** 알림 메시지를 보내도록 강제할 수 있습니다. 이 메시지는 [Onsize](../mfc/reference/cwnd-class.md#onsize) 처리기에서 유용할 수 있습니다.

**EN_REQUESTRESIZE** 알림 메시지를 받으려면 `SetEventMask` 멤버 함수를 사용 하 여 알림을 사용 하도록 설정 해야 합니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
