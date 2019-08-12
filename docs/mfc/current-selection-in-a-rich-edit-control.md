---
title: Rich Edit 컨트롤의 현재 선택
ms.date: 11/04/2016
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
ms.openlocfilehash: e493f46e2a2b5bec695177e8c8da9c09de13376d
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916447"
---
# <a name="current-selection-in-a-rich-edit-control"></a>Rich Edit 컨트롤의 현재 선택

사용자는 마우스나 키보드를 사용 하 여 rich edit 컨트롤 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))에서 텍스트를 선택할 수 있습니다. 현재 선택 항목은 선택 된 문자의 범위 또는 문자를 선택 하지 않은 경우 삽입 지점의 위치입니다. 응용 프로그램은 현재 선택 항목에 대 한 정보를 가져오고, 현재 선택 영역을 설정 하 고, 현재 선택 항목의 변경 내용을 확인 하 고, 선택 영역 강조 표시를 표시 하거나 숨길 수 있습니다

Rich edit 컨트롤에서 현재 선택 항목을 확인 하려면 [Getsel](../mfc/reference/cricheditctrl-class.md#getsel) 멤버 함수를 사용 합니다. 현재 선택 영역을 설정 하려면 [Setsel](../mfc/reference/cricheditctrl-class.md#setsel) 멤버 함수를 사용 합니다. [Charrange](/windows/desktop/api/richedit/ns-richedit-charrange) 구조체는 이러한 함수와 함께 문자 범위를 지정 하는 데 사용 됩니다. 현재 선택 항목의 내용에 대 한 정보를 검색 하기 위해 [Getselectiontype](../mfc/reference/cricheditctrl-class.md#getselectiontype) 멤버 함수를 사용할 수 있습니다.

기본적으로 rich edit 컨트롤은 포커스를 얻거나 잃을 때 선택 강조 표시를 표시 하 고 숨깁니다. [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) 멤버 함수를 사용 하 여 언제 든 지 선택 영역을 표시 하거나 숨길 수 있습니다. 예를 들어 응용 프로그램에서 검색 대화 상자를 제공 하 여 rich edit 컨트롤에서 텍스트를 찾을 수 있습니다. 응용 프로그램은 대화 상자를 닫지 않고 일치 하는 텍스트를 선택할 수 있습니다 .이 `HideSelection` 경우에는를 사용 하 여 선택 영역을 강조 표시 해야 합니다.

Rich edit 컨트롤에서 선택한 텍스트를 가져오려면 [Getseltext](../mfc/reference/cricheditctrl-class.md#getseltext) 멤버 함수를 사용 합니다. 지정 된 문자 배열로 텍스트가 복사 됩니다. 배열이 선택 된 텍스트와 종료 null 문자를 포함할 만큼 충분히 큰지 확인 해야 합니다.

[FindText](../mfc/reference/cricheditctrl-class.md#findtext) 멤버 함수를 사용 하 여 rich edit 컨트롤에서 문자열을 검색할 수 있습니다 .이 함수에 사용 되는 [Findtextex](/windows/desktop/api/richedit/ns-richedit-findtextexa) 구조체는 검색할 텍스트 범위와 검색할 문자열을 지정 합니다. 검색에서 대/소문자를 구분 하는지 여부와 같은 옵션을 지정할 수도 있습니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
