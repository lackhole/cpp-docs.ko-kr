---
title: Rich Edit 컨트롤의 인쇄
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
ms.openlocfilehash: 2ddc52e43da2e409117ccc5169442002ac27a315
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238397"
---
# <a name="printing-in-rich-edit-controls"></a>Rich Edit 컨트롤의 인쇄

Rich edit 컨트롤을 확인할 수 있습니다 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 프린터와 같은 지정 된 장치에 대해 해당 출력을 렌더링 합니다. 출력 장치는 rich edit 컨트롤의 텍스트 서식을 지정할 수 있습니다.

특정 장치에 대 한 서식 있는 편집 컨트롤의 내용 중에 서식을 지정 하려면 사용할 수 있습니다 합니다 [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) 멤버 함수입니다. 합니다 [FORMATRANGE](/windows/desktop/api/richedit/ns-richedit-_formatrange) 대상 장치에 대 한 장치 컨텍스트 (DC) 뿐만 아니라 형식을 지정 하는 텍스트 범위를 지정 하는이 함수를 사용 하 여 사용 되는 구조입니다.

출력 장치에 대 한 텍스트를 포맷 한 후 보낼 수 있습니다 출력 장치에 사용 하 여 합니다 [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) 멤버 함수입니다. 반복적으로 사용 하 여 `FormatRange` 고 `DisplayBand`, rich edit 컨트롤의 내용을 인쇄 하는 응용 프로그램에서 밴드를 구현할 수 있습니다. (밴드는 출력의 작은 부분으로 나누기 인쇄용.)

사용할 수는 [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) rich edit 컨트롤 대상 장치를 지정 하는 멤버 함수는 텍스트의 서식을 지정 합니다. (표시 된 내용이 얻게)이이 함수는 WYSIWYG에 대 한 유용한 서식 있는 응용 프로그램 화면의 대신 기본 프린터의 글꼴 메트릭을 사용 하 여 텍스트를 배치 합니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
