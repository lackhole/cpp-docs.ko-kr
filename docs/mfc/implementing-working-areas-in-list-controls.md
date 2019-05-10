---
title: 리스트 컨트롤의 작업 영역 구현
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
ms.openlocfilehash: 01b166243c9032a113d46ff297b9f6e53429da21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297218"
---
# <a name="implementing-working-areas-in-list-controls"></a>리스트 컨트롤의 작업 영역 구현

기본적으로 목록 컨트롤을 표준 표 형태 방식으로 모든 항목을 정렬합니다. 그러나 작업 영역, 사각형 그룹으로 목록 항목을 정렬 하는 다른 메서드는 지원 합니다. 작업 영역을 구현 하는 목록 컨트롤의 이미지를 Windows sdk에서를 사용 하 여 목록 뷰 컨트롤을 참조 하세요.

> [!NOTE]
>  작업 영역 목록 컨트롤 아이콘 또는 작은 아이콘 모드에 있을 때만 표시 됩니다. 그러나 현재 작업 영역 보기 보고서 또는 목록을 모드로 전환 될 경우 유지 됩니다.

작업 영역 (왼쪽, 위쪽 이나 항목의 오른쪽)에 빈 테두리를 표시 하거나 없을 하나 때 표시할 가로 스크롤 막대를 사용할 수 있습니다. 다른 일반적인 용도는 항목 수 이동 하거나 삭제할 여러 작업 영역을 만드는 것입니다. 이 메서드를 사용 하 여 다른 의미를 갖는 단일 보기에서 영역을 만들 수 있습니다. 다음 사용자 다른 영역에 배치 하 여 항목을 분류할 수 있습니다. 이 예는 읽기/쓰기 파일에 대 한 영역 및 읽기 전용 파일에 대 한 다른 영역에 있는 파일 시스템의 보기를 것입니다. 파일 항목에는 읽기 전용 영역으로 이동한 경우 자동으로 할 읽기 전용입니다. 파일을 읽기 전용 영역에서 읽기/쓰기 영역으로 이동 읽기/쓰기 파일을 확인 됩니다.

`CListCtrl` 만들고 목록 컨트롤에서 작업 영역을 관리 하기 위한 몇 가지 멤버 함수를 제공 합니다. [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas) 하 고 [SetWorkAreas](../mfc/reference/clistctrl-class.md#setworkareas) 검색 하 고 설정의 배열을 `CRect` 개체 (또는 `RECT` 구조), 목록 컨트롤의 현재 구현 된 작업 영역을 저장 하는 합니다. 또한 [GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas) 목록 컨트롤에 대 한 작업 영역 수를 현재 검색 (기본적으로 0).

## <a name="items-and-working-areas"></a>항목 및 작업 영역

작업 영역이 만들어지면 작업 영역 내에 있는 항목의 멤버를 됩니다. 마찬가지로, 항목 작업 영역으로 이동 되 면 이동 된 작업 영역의 구성원이 됩니다. 모든 작업 영역 내에서 항목에 포함 되지 않는, 첫 번째 (인덱스 0) 작업 영역 구성원 자동으로 됩니다. 항목을 만들고 다음을 호출 하 여 원하는 작업 영역으로 이동 해야 하는 항목을 만들 고 특정 작업 영역 내에 배치 하려는 경우 [SetItemPosition](../mfc/reference/clistctrl-class.md#setitemposition)합니다. 아래 두 번째 예제에서는이 기술을 보여 줍니다.

다음 예에서는 4 개의 작업 영역 구현 (`rcWorkAreas`), 목록 컨트롤에서 각 작업 영역은 10 픽셀 너비 테두리를 사용 하 여 동일한 크기의 (`m_WorkAreaListCtrl`).

[!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]

에 대 한 호출 [ApproximateViewRect](../mfc/reference/clistctrl-class.md#approximateviewrect) 한 지역의 모든 항목을 표시 하는 데 필요한 전체 영역의 추정 했습니다. 이 견적 4 개의 영역으로 분할 되어 5 픽셀 너비 테두리 채워집니다.

다음 예제에서는 각 그룹에 기존 목록 항목을 할당 (`rcWorkAreas`) 컨트롤 뷰를 새로 고칩니다 (`m_WorkAreaListCtrl`) 효과 완료 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
