---
title: Rich Edit 컨트롤의 단락 서식 지정
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: f2ac69838bf39afb636c3d41c97adc1378463d1b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507986"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Rich Edit 컨트롤의 단락 서식 지정

Rich edit 컨트롤 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))의 멤버 함수를 사용 하 여 단락의 서식을 지정 하 고 서식 지정 정보를 검색할 수 있습니다. 단락 형식 지정 특성에는 맞춤, 탭, 들여쓰기 및 번호 매김이 포함됩니다.

[SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) 멤버 함수를 사용 하 여 단락 서식을 적용할 수 있습니다. 선택한 텍스트의 현재 단락 서식을 확인 하려면 [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) 멤버 함수를 사용 합니다. [PARAFORMAT](/windows/win32/api/richedit/ns-richedit-paraformat) 구조체는 이러한 멤버 함수에서 단락 특성을 지정 하는 데 사용 됩니다. **PARAFORMAT** 의 중요 한 멤버 중 하나는 *dwmask*입니다. 에서 `SetParaFormat` *dwmask* 는이 함수 호출에 의해 설정 되는 단락 특성을 지정 합니다. `GetParaFormat`선택 영역에 있는 첫 번째 단락의 특성을 보고 합니다. *Dwmask* 는 선택 영역 전체에서 일치 하는 특성을 지정 합니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
