---
title: 창 개체 작업
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: c696d880ffa69b0a0399c5282621546c5783ebe4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399488"
---
# <a name="working-with-window-objects"></a>창 개체 작업

두 종류의 작업에 대 한 windows 호출 작업:

- Windows 메시지 처리

- 창에 그리기

고유한 자식 창을 포함 하 여 모든 창에서 Windows 메시지 처리를 참조 하세요 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md) 메시지를 매핑할 사용자 C++ 창 클래스입니다. 다음 클래스의 메시지 처리기 멤버 함수를 작성 합니다.

뷰에서 발생 framework 응용 프로그램에서 대부분의 그리기입니다 [OnDraw](../mfc/reference/cview-class.md#ondraw) 윈도우의 콘텐츠가 그려야 때마다 멤버 함수를 호출 합니다. 창에 자식 뷰의 경우 있습니다 수 일부 위임할 뷰의 그리기 자식 창에 함으로써 `OnDraw` 창의 멤버 함수 중 하나를 호출 합니다.

어떤 경우 든, 그리기 장치 컨텍스트를 해야 합니다. 주식 펜, 브러시 및 창과 연결 된 장치 컨텍스트에 포함 된 기타 그래픽 개체를 사용할 수 있습니다. 또는 필요한 그리기 효과 가져오려면 이러한 개체를 수정할 수 있습니다. 원하는 만큼 설정 하면 장치 컨텍스트를 사용 하 여 멤버 함수를 호출할 클래스의 [CDC](../mfc/reference/cdc-class.md) (디바이스 컨텍스트 클래스) 선, 도형 및 텍스트를 그릴; 색;을 사용 하는 데는 좌표계를 사용 하 여 작업 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)

- [뷰에 그리기](../mfc/drawing-in-a-view.md)

- [장치 컨텍스트](../mfc/device-contexts.md)

- [그래픽 개체](../mfc/graphic-objects.md)

## <a name="see-also"></a>참고자료

[창 개체](../mfc/window-objects.md)
