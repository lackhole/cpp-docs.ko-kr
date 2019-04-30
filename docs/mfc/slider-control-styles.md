---
title: 슬라이더 컨트롤 스타일
ms.date: 11/04/2016
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
ms.openlocfilehash: c6765445552826b71cca278c1fbbc66e500cb75a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307403"
---
# <a name="slider-control-styles"></a>슬라이더 컨트롤 스타일

슬라이더 컨트롤 ([CSliderCtrl](../mfc/reference/csliderctrl-class.md))을 세로 또는 가로 방향 중 하나를 가질 수 있습니다. 어느 쪽에 눈금 표시가 있을 수 있습니다 또는 둘 다 양쪽 모두 합니다. 또한 연속 값의 범위를 지정 하려면 사용 수 있습니다. 이러한 속성은 슬라이더 컨트롤을 만들 때 지정 하는 슬라이더 컨트롤 스타일을 사용 하 여 제어 됩니다.

TBS_HORZ 및 TBS_VERT 스타일 슬라이더 컨트롤의 방향을 결정합니다. 방향을 지정 하지 않으면 경우 슬라이더 컨트롤이 가로 방향입니다.

TBS_AUTOTICKS 스타일 늘어날 때마다 눈금 값의 범위에 있는 슬라이더 컨트롤을 만듭니다. 호출 하는 경우 이러한 눈금 자동으로 추가 되는 [SetRange](../mfc/reference/csliderctrl-class.md#setrange) 멤버 함수입니다. 와 같은 멤버 함수를 들 TBS_AUTOTICKS를 지정 하지 않으면 하는 경우 사용할 수 있습니다 [SetTic](../mfc/reference/csliderctrl-class.md#settic) 하 고 [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)눈금 표시의 위치를 지정 합니다. 눈금 표시를 표시 하지 않습니다 하는 슬라이더 컨트롤을 만들려면 TBS_NOTICKS 스타일을 사용할 수 있습니다.

슬라이더 컨트롤 중 하나 또는 양쪽에 눈금을 표시할 수 있습니다. 가로 슬라이더 컨트롤에 대 한 TBS_BOTTOM 또는 TBS_TOP 스타일을 지정할 수 있습니다. 세로 슬라이더 컨트롤에 대 한 TBS_RIGHT 또는 TBS_LEFT 스타일을 지정할 수 있습니다. (TBS_BOTTOM TBS_RIGHT와 기본 설정입니다.) 양쪽 방향에서 슬라이더 컨트롤의 눈금 표시에 대 한 TBS_BOTH 스타일을 지정 합니다.

슬라이더 컨트롤을 만들 때 TBS_ENABLESELRANGE 스타일을 지정 하는 경우에 선택 범위를 표시할 수 있습니다. 슬라이더 컨트롤에이 스타일을 선택 범위의 시작 및 끝 위치에서 눈금 표시 (대신 세로 파선)는 삼각형으로 표시 되 고 선택 범위를 강조 표시 됩니다. 예를 들어, 선택 범위 간단한 예약 응용 프로그램에 유용할 수 있습니다. 사용자 시간 예약 된 회의 시간을 식별 하는 일에 해당 하는 눈금 표시의 범위를 선택할 수 있습니다.

기본적으로 슬라이더 컨트롤을 슬라이더의 길이 선택 범위 변경에 따라 달라 집니다. 슬라이더 컨트롤 TBS_FIXEDLENGTH 스타일 있으면 슬라이더의 길이 동일 선택 범위를 변경 하는 경우에 합니다. TBS_NOTHUMB 스타일에 있는 슬라이더 컨트롤에서 슬라이더를 포함 하지 않습니다.

## <a name="see-also"></a>참고자료

[CSliderCtrl 사용](../mfc/using-csliderctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
