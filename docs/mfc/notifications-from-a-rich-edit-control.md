---
title: Rich Edit 컨트롤에서 보내는 알림
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: fcb1dda1d915dc13e01effed9ba99070b825a15e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238212"
---
# <a name="notifications-from-a-rich-edit-control"></a>Rich Edit 컨트롤에서 보내는 알림

알림 메시지 보고서는 다양 한 영향을 주는 이벤트 편집 컨트롤 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). 해당 부모 창에서 처리할 수 있습니다 또는 메시지 리플렉션을 사용 하는 rich edit 컨트롤 자체. Rich edit 컨트롤 몇 가지 추가 항목 뿐만 아니라 편집 컨트롤을 사용 하 여 사용 하는 알림 메시지 중 일부를 지원 합니다. 알림 메시지를 rich edit 컨트롤의 부모 창 해당 "이벤트 마스크입니다."를 설정 하 여 보내는 것을 확인할 수 있습니다.

Rich edit 컨트롤에 대 한 이벤트 마스크를 설정 하려면 사용 합니다 [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) 멤버 함수입니다. 사용 하 여 서식 있는 편집 컨트롤에 대 한 현재 이벤트 마스크를 검색할 수 있습니다 합니다 [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) 멤버 함수입니다.

다음 단락에서는 몇 가지 특정 알림 및 해당 용도 나열합니다.

- EN_MSGFILTER EN_MSGFILTER 알림 처리 있습니다 클래스 하거나 rich edit 컨트롤 또는 부모 창의 모든 키보드 및 마우스 입력 컨트롤을 필터링 합니다. 처리기에서 처리 중인 키보드 또는 마우스 메시지를 방지할 수 있습니다 또는 지정 된 수정 하 여 메시지를 변경할 수 있습니다 [메시지 필터](/windows/desktop/api/richedit/ns-richedit-_msgfilter) 구조입니다.

- EN_PROTECTED는 EN_PROTECTED 알림 메시지는 사용자가 보호 된 텍스트를 수정 하려고 할 때 검색을 처리 합니다. 텍스트 범위를 protected로 표시 하려면 보호 된 문자 효과 설정할 수 있습니다. 자세한 내용은 [Rich Edit 컨트롤의 문자 서식을](../mfc/character-formatting-in-rich-edit-controls.md)합니다.

- EN_DROPFILES 있습니다 EN_DROPFILES 알림 메시지를 처리 하 여 rich edit 컨트롤에서 파일을 삭제 하려면 사용자를 설정할 수 있습니다. 지정 된 [ENDROPFILES](/windows/desktop/api/richedit/ns-richedit-_endropfiles) 구조 삭제할 파일에 대 한 정보가 들어 있습니다.

- 응용 프로그램 EN_SELCHANGE EN_SELCHANGE 알림 메시지를 처리 하 여 현재 선택 영역이 변경 될 때 감지할 수 있습니다. 알림 메시지를 지정 된 [SELCHANGE](/windows/desktop/api/richedit/ns-richedit-_selchange) 새 선택 영역에 대 한 정보를 포함 하는 구조체.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
