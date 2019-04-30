---
title: 스핀 단추 스타일
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
ms.openlocfilehash: d955ba1d76ee4d5648613ddaf6c5f6a652f3d3af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307174"
---
# <a name="spin-button-styles"></a>스핀 단추 스타일

스핀 단추에 대 한 설정의 많은 ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) 스타일에 의해 제어 됩니다. 사용 하 여 다음과 같은 스타일을 설정할 수 있습니다 합니다 **속성** 대화 상자 편집기의 창.

- **방향** 세로 또는 가로입니다. 화살표 단추의 방향을 제어합니다. UDS_HORZ 스타일을 사용 하 여 연결 합니다.

- **맞춤** 연결 되지 않은, 왼쪽 또는 오른쪽 중 하나입니다. 스핀 단추 위치를 제어합니다. 왼쪽 및 오른쪽 스핀 단추 버디 창 옆에 배치합니다. 스핀 단추에 맞게 버디 창의 너비를 줄입니다. UDS_ALIGNLEFT 및 UDS_ALIGNRIGHT 스타일을 사용 하 여 연결 합니다.

- **Auto Buddy** Z 순서로 스핀 단추에 버디 창으로 이전 윈도우를 자동으로 선택 합니다. 대화 상자 템플릿에서 스핀 단추 탭 순서에서 앞에 있는 컨트롤입니다. UDS_AUTOBUDDY 스타일을 사용 하 여 연결 합니다.

- **Buddy Integer 설정** 를 현재 위치 변경 될 때 버디 창의 캡션을 증감 스핀 컨트롤입니다. UDS_SETBUDDYINT 스타일을 사용 하 여 연결 합니다.

- **No Thousands** 1000 단위를 넣지 않습니다 버디 창의 캡션 값에서 구분 기호입니다. UDS_NOTHOUSANDS 스타일을 사용 하 여 연결 합니다.

    > [!NOTE]
    >  Buddy 컨트롤에서 정수 값을 검색할 대화 상자 데이터 교환 (DDX)를 사용 하려는 경우에이 스타일을 설정 합니다. `DDX_Text` 포함 된 천 구분 기호를 허용 하지 않습니다.

- **줄 바꿈** 면 위치가 증가 하거나 감소 컨트롤의 범위를 벗어나는 값은 "래핑" 합니다. UDS_WRAP 스타일을 사용 하 여 연결 합니다.

- **화살표 키** 스핀 단추가 위쪽 화살표 및 아래쪽 화살표 키를 누를 때 위치를 늘이거나 합니다. UDS_ARROWKEYS 스타일을 사용 하 여 연결 합니다.

## <a name="see-also"></a>참고자료

[CSpinButtonCtrl 사용](../mfc/using-cspinbuttonctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
