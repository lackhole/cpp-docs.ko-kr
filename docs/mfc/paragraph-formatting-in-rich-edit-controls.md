---
title: Rich Edit 컨트롤의 단락 서식 지정
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: baee4863bee9b96e7a850e70b8f13388f69b41cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218834"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Rich Edit 컨트롤의 단락 서식 지정

Rich edit 컨트롤의 멤버 함수를 사용할 수 있습니다 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 단락 형식을 지정 하는 서식 지정 정보를 검색 합니다. 단락 형식 지정 특성에는 맞춤, 탭, 들여쓰기 및 번호 매김이 포함됩니다.

단락을 사용 하 여 서식 지정을 적용할 수 있습니다 합니다 [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) 멤버 함수입니다. 선택한 텍스트의 서식을 현재 단락을 확인 하려면 사용 합니다 [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) 멤버 함수입니다. 합니다 [PARAFORMAT](/windows/desktop/api/richedit/ns-richedit-_paraformat) 구조는 이러한 멤버 함수를 사용 하 여 단락 특성을 지정 하는 데 사용 됩니다. 중요 한 멤버 중 하나 **PARAFORMAT** 됩니다 *dwMask*합니다. `SetParaFormat`하십시오 *dwMask* 이 함수 호출으로 설정할 단락 특성을 지정 합니다. `GetParaFormat` 보고서 선택 영역에서 첫 번째 단락의 특성 *dwMask* 선택 영역에서 일관성 있는 특성을 지정 합니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
