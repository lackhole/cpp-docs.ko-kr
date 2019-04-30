---
title: Rich Edit 컨트롤의 문자 서식 지정
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: a7467f9cd6a14dc6dfc2c03b6eb35f71802454fb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344292"
---
# <a name="character-formatting-in-rich-edit-controls"></a>Rich Edit 컨트롤의 문자 서식 지정

Rich edit 컨트롤의 멤버 함수를 사용할 수 있습니다 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 문자 서식을 지정 하는 데 서식 지정 정보를 검색 합니다. 문자, 서체, 크기, 색 및 굵게, 기울임꼴, 같은 효과 지정할 수 있습니다 하 고 보호 합니다.

문자를 사용 하 여 서식을 적용할 수 있습니다 합니다 [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) 하 고 [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) 멤버 함수입니다. 선택한 텍스트의 서식을 현재 문자를 확인 하려면 사용 합니다 [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) 멤버 함수입니다. 합니다 [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) 구조는 이러한 멤버 함수를 사용 하 여 문자 특성을 지정 하는 데 사용 됩니다. 중요 한 멤버 중 하나 **CHARFORMAT** 됩니다 **dwMask**합니다. `SetSelectionCharFormat` 하 고 `SetWordCharFormat`, **dwMask** 문자 특성에는이 함수 호출에 의해 설정 됩니다 지정 합니다. `GetSelectionCharFormat` 선택 영역에서 첫 번째 문자의 특성을 보고 **dwMask** 선택 영역에서 일관성 있는 특성을 지정 합니다.

또한 가져오기 하 고 설정할 수는 기본 문자 서식 지정"," 이후에 삽입 된 문자에 적용 되는 합니다. 예를 들어, 응용 프로그램의 기본 문자를 굵게 서식를 설정 하는 경우 사용자가 다음 문자는 문자 굵게 표시 됩니다. Get을 설정 하려면 기본 문자 형식을 사용 합니다 [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) 및 [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) 멤버 함수입니다.

"보호" 문자 특성에는 텍스트 모양에 변경 되지 않습니다. Rich edit 컨트롤의 부모 창 보내는 사용자가 보호 된 텍스트를 수정 하려고 하는 경우는 **EN_PROTECTED** 알림 메시지를 부모 창에 허용 또는 금지를 변경 합니다. 이 알림 메시지를 받으려면 해야이 사용 하 여 사용 합니다 [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) 멤버 함수입니다. 이벤트 마스크에 대 한 자세한 내용은 참조 하세요. [서식 있는 편집 컨트롤에서 알림](../mfc/notifications-from-a-rich-edit-control.md)이 항목의 뒷부분에 나오는.

전경색 문자 특성을 이지만 배경색 rich edit 컨트롤의 속성입니다. 배경색을 설정 하려면 사용 합니다 [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
