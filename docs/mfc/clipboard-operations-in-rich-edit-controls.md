---
title: Rich Edit 컨트롤의 클립보드 작업
ms.date: 11/04/2016
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
ms.openlocfilehash: 882c589d0d25b54650affa7fd41f916ecf6097d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327108"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Rich Edit 컨트롤의 클립보드 작업

응용 프로그램 서식 있는 편집 컨트롤로 클립보드의 내용을 붙여넣을 수 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 사용 가능한 최상의 클립보드 형식 또는 특정 클립보드 형식을 사용 합니다. 또한 서식 있는 편집 컨트롤에서 클립보드 형식 붙여넣기가 지원되는지 여부도 확인할 수 있습니다.

사용 하 여 현재 선택 영역의 내용을 잘라낸 하거나 복사할 수 있습니다 합니다 [복사본](../mfc/reference/cricheditctrl-class.md#copy) 또는 [잘라내기](../mfc/reference/cricheditctrl-class.md#cut) 멤버 함수입니다. 사용 하 여 서식 있는 편집 컨트롤로 클립보드의 내용을 붙여넣을 수는 마찬가지로 합니다 [붙여](../mfc/reference/cricheditctrl-class.md#paste) 멤버 함수입니다. 컨트롤은 처음으로 인식되는 첫 번째 사용 가능한 형식을 가장 설명적인 형식으로 인지하고 이를 붙여넣습니다.

특정 클립보드 형식을 붙여넣으려면를 사용할 수 있습니다 합니다 [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial) 멤버 함수입니다. 이 함수는 사용자가 클립보드 형식을 선택할 수 있게 해주는 선택하여 붙여넣기 명령이 있는 응용 프로그램에서 유용합니다. 사용할 수는 [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) 컨트롤에서 지정된 된 형식으로 인식 되는지 여부를 결정 하는 멤버 함수입니다.

또한 `CanPaste`를 사용하면 사용 가능한 클립보드 형식이 서식 있는 편집 컨트롤에서 인식되는지 여부를 확인할 수 있습니다. 이 기능은 `OnInitMenuPopup` 처리기에서 유용합니다. 응용 프로그램은 컨트롤이 모든 사용 가능한 형식을 붙여넣을 수 있는지 여부에 따라 해당 붙여넣기 명령을 활성화하거나 회색으로 표시할 수 있습니다.

서식 있는 편집 컨트롤은 복합 텍스트 형식과 RichEdit 텍스트 및 개체라고 부르는 형식의 두 가지 클립보드 형식을 등록합니다. 응용 프로그램 사용 하 여 이러한 형식을 등록할 수는 [됩니다](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) 함수를 지정 하는 **CF_RTF** 하 고 **CF_RETEXTOBJ** 값.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
