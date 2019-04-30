---
title: 진행률 컨트롤 조작
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
ms.openlocfilehash: c9da6f8048adf1c7da184570ff7f94deee7441e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279192"
---
# <a name="manipulating-the-progress-control"></a>진행률 컨트롤 조작

진행률 컨트롤의 현재 위치를 변경 하는 방법은 세 가지가 있습니다 ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)).

- 미리 설정 된 증분 양만큼 위치를 변경할 수 있습니다.

- 임의의 값에 따라 위치를 변경할 수 있습니다.

- 특정 값으로 위치를 변경할 수 있습니다.

### <a name="to-change-the-position-by-a-preset-amount"></a>미리 설정 된 양만큼 위치를 변경 하려면

1. 사용 된 [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) 증분을 설정 하려면 멤버 함수입니다. 기본적으로이 값은 10입니다. 이 값은 일반적으로 컨트롤의 초기 설정 중 하나로 설정 됩니다. 단계 값은 음수일 수 있습니다.

1. 사용 된 [StepIt](../mfc/reference/cprogressctrl-class.md#stepit) 위치를 증가 시키는 멤버 함수입니다. 이렇게 하면 컨트롤을 다시 그리도록 합니다.

    > [!NOTE]
    >  `StepIt` 래핑할 위치를 발생 합니다. 예를 들어, 20, 단계 및 90의 위치 1-100의 범위를 지정 `StepIt` 위치를 10으로 설정 됩니다.

### <a name="to-change-the-position-by-an-arbitrary-amount"></a>임의의 값에 따라 위치를 변경 하려면

1. 사용 된 [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos) 멤버 함수는 위치를 변경 합니다. `OffsetPos` 음수 값을 허용 합니다.

    > [!NOTE]
    >  `OffsetPos`을 달리 `StepIt`, 위치를 줄 바꿈할 수 있습니다. 새 위치는 범위 내에 유지 하도록 조정 됩니다.

### <a name="to-change-the-position-to-a-specific-value"></a>특정 값으로 위치를 변경 하려면

1. 사용 된 [SetPos](../mfc/reference/cprogressctrl-class.md#setpos) 멤버 함수를 위치에 특정 값으로 설정 합니다. 필요한 경우 새 위치는 범위 내에 조정 됩니다.

일반적으로 진행률 컨트롤 출력에만 사용 됩니다. 새 값을 지정 하지 않고 현재 위치를 가져오려면 [GetPos](../mfc/reference/cprogressctrl-class.md#getpos)합니다.

## <a name="see-also"></a>참고자료

[CProgressCtrl 사용](../mfc/using-cprogressctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
