---
title: 슬라이더 컨트롤 멤버 함수
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
ms.openlocfilehash: a88dd1a49eb928261393a4473ee7eb53628c607a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307433"
---
# <a name="slider-control-member-functions"></a>슬라이더 컨트롤 멤버 함수

응용 프로그램 슬라이더 슬라이더 컨트롤에 대 한 정보를 검색할 컨트롤의 멤버 함수를 호출할 수 있습니다 ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) 및 해당 특성을 변경 합니다.

사용 합니다 (즉, 사용자가 선택한 값) 슬라이더의 위치를 검색 합니다 [GetPos](../mfc/reference/csliderctrl-class.md#getpos) 멤버 함수입니다. 슬라이더의 위치를 설정 하려면 사용 합니다 [SetPos](../mfc/reference/csliderctrl-class.md#setpos) 멤버 함수입니다. 언제 든 지 사용할 수는 `VerifyPos` 멤버 함수를 슬라이더 최소값과 최대값 사이 인지 확인 합니다.

슬라이더 컨트롤의 범위는 슬라이더 컨트롤을 나타낼 수 있는 연속 값의 집합. 대부분의 응용 프로그램을 사용 합니다 [SetRange](../mfc/reference/csliderctrl-class.md#setrange) 멤버 함수를 처음 만들 때 슬라이더 컨트롤의 범위를 설정 하려면. 슬라이더 컨트롤을 사용 하 여 만들어진 후 응용 프로그램 범위를 동적으로 변경할 수는 [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) 하 고 [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) 멤버 함수입니다. 일반적으로 동적으로 변경할 수 범위를 허용 하는 응용 프로그램 사용자 슬라이더 컨트롤을 사용 하 여 작업을 마치면 최종 범위 설정을 검색 합니다. 이러한 설정을 검색 하려면 사용 합니다 [GetRange](../mfc/reference/csliderctrl-class.md#getrange)를 [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax), 및 [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) 멤버 함수입니다.

응용 프로그램 TBS_AUTOTICKS 스타일을 사용 하 여 자동으로 표시 하는 슬라이더 컨트롤의 눈금 표시를 할 수 있습니다. 그러나 응용 프로그램을 눈금 표시의 빈도 제어 하는 경우 많은 멤버 함수도 사용할 수 있습니다.

눈금 표시의 위치를 설정 하려면 응용 프로그램 사용 합니다 [SetTic](../mfc/reference/csliderctrl-class.md#settic) 멤버 함수입니다. 합니다 [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) 멤버 함수 눈금 슬라이더 컨트롤의 범위에 정기적으로 표시 된 표시를 설정 하는 응용 프로그램을 허용 합니다. 예를 들어, 응용 프로그램 1과 100 사이 범위의 10 눈금을 표시 하려면이 멤버 함수를 사용할 수 있습니다.

눈금 표시에 해당 하는 범위에서 인덱스를 검색 하려면 사용 합니다 [GetTic](../mfc/reference/csliderctrl-class.md#gettic) 멤버 함수입니다. 합니다 [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) 멤버 함수에는 이러한 인덱스의 배열을 검색 합니다. 클라이언트 좌표에서 눈금 표시의 위치를 검색 하려면 사용 합니다 [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) 멤버 함수입니다. 응용 프로그램 사용 하 여 눈금의 수를 검색할 수는 [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) 멤버 함수입니다.

합니다 [ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) 멤버 함수는 슬라이더 컨트롤의 눈금 표시를 모두 제거 합니다.

슬라이더 컨트롤의 줄 크기는 응용 프로그램 TB_LINEDOWN 또는 TB_LINEUP 알림 메시지를 받으면 슬라이더를 이동 하는 정도 결정 합니다. 마찬가지로, 페이지 크기 TB_PAGEDOWN 및 TB_PAGEUP 알림 메시지에 대 한 응답을 결정합니다. 응용 프로그램에서 검색 하 고 사용 하 여 행 및 페이지 크기 값을 설정할 수 있습니다 합니다 [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize)합니다 [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize), 및 [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) 멤버 함수입니다.

응용 프로그램 멤버 함수를 사용 하 여 슬라이더 컨트롤의 크기를 검색할 수 있습니다. 합니다 [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) 슬라이더에 대 한 경계 사각형을 검색 하는 멤버 함수입니다. 합니다 [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) 멤버 함수는 슬라이더 컨트롤의 채널에 대 한 경계 사각형을 검색 합니다. (채널 영역에 따른은 슬라이더를 이동 하 고 강조를 포함 하는 범위를 선택 합니다.)

슬라이더 컨트롤을 TBS_ENABLESELRANGE 스타일에 사용자를 연속 값의 범위를 선택할 수 있습니다. 동적으로 조정 되도록 선택 범위를 허용 하는 다양 한 멤버 함수입니다. 합니다 [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) 시작 및 끝 위치 선택 된 멤버 함수를 설정 합니다. 응용 프로그램 설정을 사용 하 여 검색할 수 있습니다 사용자 선택 범위 설정 완료 되 면 합니다 [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) 멤버 함수입니다. 사용자의 선택을 취소를 사용 합니다 [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[CSliderCtrl 사용](../mfc/using-csliderctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
