---
title: 콜백 항목 및 콜백 마스크
ms.date: 11/04/2016
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
ms.openlocfilehash: 35967f128c6cc59bc9cea90da559b32c51fb38d1
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344276"
---
# <a name="callback-items-and-the-callback-mask"></a>콜백 항목 및 콜백 마스크

각 해당 항목에 대해 목록 뷰 컨트롤에는 일반적으로 항목 아이콘의 이미지 목록 인덱스 레이블 텍스트를 저장 하 고 비트 집합을 해당 항목의 상태에 대 한 플래그입니다. 응용 프로그램이 이미 일부 항목에 대 한 정보를 저장 하는 경우에 유용할 수 있는 콜백 항목으로 개별 항목을 정의할 수 있습니다.

적절 한 값을 지정 하 여 콜백 항목으로 항목을 정의 합니다 `pszText` 및 `iImage` 의 멤버는 **LV_ITEM** 구조 (참조 [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)). 항목이 나 하위 항목의 텍스트를 관리 하는 응용 프로그램의 경우 지정 합니다 **LPSTR_TEXTCALLBACK** 값을 `pszText` 멤버입니다. 응용 프로그램 항목에 대 한 아이콘의 추적을 지정 합니다 **I_IMAGECALLBACK** 값을 `iImage` 멤버입니다.

콜백 항목을 정의 하는 것 외에도 컨트롤의 콜백 마스크를 수정할 수도 있습니다. 이 마스크는 컨트롤 보다는 응용 프로그램을 현재 데이터를 저장 하는 항목 상태를 지정 하는 비트 플래그 집합입니다. 콜백 마스크 특정 항목에 적용 되는 콜백 항목 지정 달리 컨트롤의 항목을 모두에 적용 됩니다. 콜백 마스크는 기본적으로 컨트롤 모든 항목 상태를 추적 하는 0입니다. 이 기본 동작을 변경 하려면 다음 값의 조합 마스크를 초기화 합니다.

- **LVIS_CUT** 잘라내기 및 붙여넣기 작업에 대 한 항목이 표시 됩니다.

- **LVIS_DROPHILITED** 항목 끌어서 놓기 대상 강조 표시 됩니다.

- **LVIS_FOCUSED** 항목에 중점을 둡니다.

- **LVIS_SELECTED** 항목을 선택 합니다.

- **LVIS_OVERLAYMASK** 응용 프로그램에는 각 항목에 대 한 현재 오버레이 이미지의 이미지 목록 인덱스를 저장 합니다.

- **LVIS_STATEIMAGEMASK** 응용 프로그램에는 각 항목에 대 한 현재 상태 이미지의 이미지 목록 인덱스를 저장 합니다.

이 마스크를 설정 및 검색에 자세한 내용은 참조 [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) 하 고 [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask)합니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
