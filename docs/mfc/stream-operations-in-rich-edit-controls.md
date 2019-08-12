---
title: Rich Edit 컨트롤의 스트림 작업
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
ms.openlocfilehash: 04bf49371b3ab5eaaad2775b532d8d35bf990ce3
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915282"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Rich Edit 컨트롤의 스트림 작업

스트림을 사용 하 여 rich edit 컨트롤 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))에 데이터를 전송할 수 있습니다. 스트림은 버퍼 및 응용 프로그램 정의 콜백 함수를 지정 하는 [editstream](/windows/desktop/api/richedit/ns-richedit-editstream) 구조에 의해 정의 됩니다.

데이터를 rich edit 컨트롤로 읽으려면 (즉,에서 데이터 스트림), [streamin](../mfc/reference/cricheditctrl-class.md#streamin) 멤버 함수를 사용 합니다. 컨트롤이 응용 프로그램에서 정의된 콜백 함수를 반복적으로 호출하여 매번 데이터의 일부를 버퍼로 전송합니다.

Rich edit 컨트롤의 콘텐츠를 저장 하려면 (즉, 데이터를 스트리밍하는 경우), [Streamout](../mfc/reference/cricheditctrl-class.md#streamout) 멤버 함수를 사용할 수 있습니다. 컨트롤이 버퍼에 쓰기를 반복한 후 응용 프로그램에서 정의된 콜백 함수를 호출합니다. 각 호출마다 콜백 함수는 버퍼 내용을 저장합니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
