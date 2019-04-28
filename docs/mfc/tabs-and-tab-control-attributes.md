---
title: 탭 및 탭 컨트롤 특성
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
ms.openlocfilehash: ca9f89565770e60a59007d609d132fae15eacae6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306459"
---
# <a name="tabs-and-tab-control-attributes"></a>탭 및 탭 컨트롤 특성

탭 컨트롤을 구성 하는 탭의 동작과 모양을 세부적으로 제어할 해야 ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). 각 탭에는 레이블, 아이콘, 항목 상태 및 응용 프로그램 정의 32 비트 값을 연결 되어 있을 수 있습니다. 각 탭에 대 한 아이콘, 레이블 또는 둘 다 표시할 수 있습니다.

또한 각 탭 항목 상태를 가질 수 있습니다: 누름, 누르지 않은 상태 또는 강조 표시 합니다. 이 상태는 기존 탭 항목을 수정 하 여 설정할 수만 있습니다. 기존 탭 항목을 수정 하려면에 대 한 호출을 사용 하 여 검색할 [GetItem](../mfc/reference/ctabctrl-class.md#getitem)를 수정 합니다 `TCITEM` 구조 (특히 합니다 *dwState* 및 *dwStateMask* 데이터 멤버 )를 다음 수정 된 반환 `TCITEM` 구조에 대 한 호출을 사용 하 여 [SetItem](../mfc/reference/ctabctrl-class.md#setitem)합니다. 항목 상태에 있는 모든 탭 항목의 선택을 취소 해야 하는 경우는 `CTabCtrl` 개체를 호출할 [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall)합니다. 이 함수에는 모든 탭 항목 또는 현재 선택 된 것을 제외한 모든 항목의 상태 다시 설정 합니다.

다음 코드를 모든 탭 항목의 상태를 지우고 세 번째 항목의 상태를 수정 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]

탭 특성에 대 한 자세한 내용은 참조 하세요. [탭 및 탭 특성](/windows/desktop/Controls/tab-controls) Windows SDK에 있습니다. 탭 컨트롤에 탭을 추가 하는 방법에 대 한 자세한 내용은 참조 하세요. [탭 컨트롤에 탭 추가](../mfc/adding-tabs-to-a-tab-control.md) 이 항목의에서 뒷부분에 있습니다.

## <a name="see-also"></a>참고자료

[CTabCtrl 사용](../mfc/using-ctabctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
