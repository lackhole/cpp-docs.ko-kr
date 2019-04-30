---
title: 스핀 단추 멤버 함수
ms.date: 11/04/2016
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
ms.openlocfilehash: 5ad6f529762e77e1cf1c00f41eea0add5d196fbb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307265"
---
# <a name="spin-button-member-functions"></a>스핀 단추 멤버 함수

Spin 컨트롤에 사용할 수 있는 몇 가지 멤버 함수는 ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). 스핀 단추 다음 특성을 변경 하려면 이러한 함수를 사용 합니다.

- **가속** 화살표 단추를 누르고 있는 경우 위치 변경 하는 속도 조정할 수 있습니다. 가속을 사용 하려면 사용 합니다 [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) 하 고 [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) 멤버 함수입니다.

- **기본** 버디 창 캡션에 있는 위치를 표시 하는 데 기본 (10 또는 16)을 변경할 수 있습니다. 기본 작업을 하려면 사용 합니다 [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) 및 [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) 멤버 함수입니다.

- **버디 창** 버디 창을 동적으로 설정할 수 있습니다. 쿼리하거나 버디 창 컨트롤 변경 하려면 사용 합니다 [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) 하 고 [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) 멤버 함수입니다.

- **위치** 쿼리하고 위치를 변경할 수 있습니다. 위치와 직접 작업 하려면 사용 합니다 [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) 하 고 [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) 멤버 함수입니다. Buddy 컨트롤의 캡션 (예를 들어에서는 버디가 편집 컨트롤) 변경 있는 수도 있으므로 `GetPos` 현재 캡션을 검색 및 위치를 적절 하 게 조정 합니다.

- **범위** 스핀 단추에 대 한 최대 및 최소 위치를 변경할 수 있습니다. 기본적으로 최대 0으로 설정 되어 및 최소 100으로 설정 됩니다. 기본 최대 기본 최소값 보다 작기 때문에 화살표 단추의 작업은 직관적이 지 합니다. 일반적으로 설정한 사용 하 여 범위를 [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) 멤버 함수입니다. 쿼리 범위를 사용 하려면 [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange)합니다.

## <a name="see-also"></a>참고자료

[CSpinButtonCtrl 사용](../mfc/using-cspinbuttonctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
