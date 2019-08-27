---
title: 고무 밴드 및 추적기
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
ms.openlocfilehash: a6a9c9848e21129d4e6a8ce300e8750b4a0c6126
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308851"
---
# <a name="rubber-banding-and-trackers"></a>고무 밴드 및 추적기

추적기에 제공되는 또 다른 기능은 "고무 밴드" 선택 기능입니다. 이 기능을 통해 사용자는 선택할 항목 주위의 크기 조정 직사각형을 끌어서 여러 OLE 항목을 선택할 수 있습니다. 사용자가 왼쪽 마우스 단추를 놓으면 사용자가 선택한 영역 내에 있는 항목이 선택되고 사용자가 조작할 수 있는 상태가 됩니다. 예를 들어 사용자가 선택한 항목을 다른 컨테이너 애플리케이션으로 끌어갈 수 있습니다.

이 기능을 구현 응용 프로그램의 WM_LBUTTONDOWN 처리기 함수에 일부 추가 코드가 필요 합니다.

다음 코드 샘플은 고무 밴드 선택 및 추가 기능을 구현합니다.

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

고무 밴드 추적기의 방향의 되돌릴 수 있도록 하려는 경우 호출 해야 [:: Trackrubberband](../mfc/reference/crecttracker-class.md#trackrubberband) 로 설정 하는 세 번째 매개 변수를 사용 하 여 **TRUE**합니다. 해독 가능한 방향 허용 됩니다 발생 때로는 [CRectTracker::m_rect](../mfc/reference/crecttracker-class.md#m_rect) 반전 됩니다. 이를 호출 하 여 수정할 수 있습니다 [crect:: Normalizerect](../atl-mfc-shared/reference/crect-class.md#normalizerect)합니다.

자세한 내용은 [컨테이너 클라이언트 항목](../mfc/containers-client-items.md) 하 고 [끌어서 놓기 사용자 지정](../mfc/drag-and-drop-customizing.md)합니다.

## <a name="see-also"></a>참고자료

[추적기: OLE 애플리케이션에서 추적기 구현](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[CRectTracker 클래스](../mfc/reference/crecttracker-class.md)
