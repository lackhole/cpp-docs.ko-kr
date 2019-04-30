---
title: Rich Edit 컨트롤의 단어 분리
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
ms.openlocfilehash: e71643350ced5b8ecff7c8ac7829741cc3e8493b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399540"
---
# <a name="word-breaks-in-rich-edit-controls"></a>Rich Edit 컨트롤의 단어 분리

Rich edit 컨트롤 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) "단어 분리 프로시저"를 호출 하는 함수 호출 단어 사이의 구분선을 찾을 하 고 줄을 중단할 수 있습니다 위치를 확인할 수 있습니다. 자동 줄 바꿈 작업을 수행할 때 및 CTRL + 왼쪽 화살표 및 CTRL + 오른쪽 화살표 키 조합을 처리할 때이 정보를 사용 하는 컨트롤입니다. 응용 프로그램에 해당 단어 분리 정보를 검색 하 고 지정 된 문자 줄을 확인할 기본 단어 분리 절차를 바꾸려면 rich edit 컨트롤에 메시지를 보낼 수 있습니다.

## <a name="see-also"></a>참고자료

[CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
