---
title: Rebar 컨트롤 및 밴드
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
ms.openlocfilehash: 4bb7b4aeab1478138aa2b52649f41ca943b5daa4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378168"
---
# <a name="rebar-controls-and-bands"></a>Rebar 컨트롤 및 밴드

Rebar 컨트롤의 주 목적은 자식 창, 공용 대화 상자 컨트롤, 메뉴, 도구 모음, 등에 대 한 컨테이너 역할을 합니다. 이 포함 된 "밴드"의 개념으로 사용할 수 각 rebar 밴드의 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창을의 조합을 포함할 수 있습니다.

클래스 `CReBarCtrl` 를 검색 하는 데 하 고 특정 rebar 밴드에 대 한 정보를 조작할 수 있는 많은 멤버 함수는:

- [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) rebar 컨트롤에서 현재 밴드의 수를 검색 합니다.

- [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) 초기화를 **REBARBANDINFO** 지정된 대역 외에서 정보를 사용 하 여 구조입니다. 해당 [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) 멤버 함수입니다.

- [GetRect](../mfc/reference/crebarctrl-class.md#getrect) 지정된 밴드의 경계 사각형을 검색 합니다.

- [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) rebar 컨트롤에서 밴드 행의 수를 검색 합니다.

- [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) 지정된 밴드의 인덱스를 검색 합니다.

- [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) 밴드의 테두리를 검색 합니다.

여러 멤버 함수에는 조작 하는 것 외에도 특정 rebar 밴드에 적용할 수 있는 제공 됩니다.

[InsertBand](../mfc/reference/crebarctrl-class.md#insertband) 하 고 [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) 추가 및 rebar 밴드를 제거 합니다. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) 하 고 [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) 특정 rebar 밴드의 현재 크기에 영향을 줍니다. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) 특정 rebar 밴드의 인덱스를 변경 합니다. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) 하거나 사용자 로부터 rebar 밴드를 숨깁니다.

다음 예제에서는 도구 모음 밴드를 추가 하는 방법을 보여 줍니다 (*m_wndToolBar*)를 기존 rebar 컨트롤 (*m_wndReBar*). 밴드를 초기화 하 여 설명 합니다 `rbi` 구조 및 호출 된 `InsertBand` 멤버 함수:

[!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]

## <a name="see-also"></a>참고자료

[CReBarCtrl 사용](../mfc/using-crebarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
