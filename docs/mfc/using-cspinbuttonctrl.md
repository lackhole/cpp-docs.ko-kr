---
title: CSpinButtonCtrl 사용
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
ms.openlocfilehash: 6bb663b6ff9b9b039bd774f6e607c7acdb1c4b11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411723"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl 사용

합니다 *스핀 단추* 컨트롤 (라고도 *위쪽 / 아래쪽* 컨트롤)는 사용자가 클릭 하 여 값을 조정할 수 있는 화살표 쌍 제공 합니다. 이 값 이라고 합니다 *현재 위치*합니다. 위치 스핀 단추의 범위 내에 유지 합니다. 사용자가 위쪽 화살표를 클릭 하면 위치로 이동할 때 최대; 및 아래쪽 화살표를 클릭 위치 최소 쪽으로 이동 합니다.

스핀 단추 컨트롤에서 MFC에 표시 됩니다는 [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) 클래스입니다.

> [!NOTE]
>  기본적으로 스핀 단추에 대 한 범위에 영 (0)로 최대 및 최소 100으로 설정 합니다. 최 댓 값이 최소값 보다 작은 이기 때문에 위쪽 화살표를 클릭 하면 위치 줄어들고 늘립니다 아래쪽 화살표를 클릭 합니다. 사용 하 여 [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) 이러한 값을 조정 합니다.

일반적으로 현재 위치 관련 컨트롤에 표시 됩니다. 도우미 컨트롤 이라고 합니다 *버디 창*합니다. 스핀 단추 컨트롤의 그림을 참조 하세요 [Up-down 컨트롤에 대 한](/windows/desktop/Controls/up-down-controls) Windows SDK에 있습니다.

스핀 컨트롤 및 편집 컨트롤 버디 창, Visual Studio에서를 만들려면 먼저 대화 상자 또는 창에 편집 컨트롤을 끌어 놓은 스핀 컨트롤에 놓습니다. Spin 컨트롤을 선택 하 고 설정 해당 **Auto Buddy** 하 고 **Buddy Integer 설정** 속성을 **True**합니다. 설정 된 **맞춤** 속성 **오른쪽 맞춤** 가장 일반적입니다. 이러한 설정을 사용 하 여 바로 편집 컨트롤 탭 순서에서 앞에 오는 때문에 편집 컨트롤은 버디 창으로 설정 됩니다. 편집 컨트롤은 정수를 표시 하 고 spin 컨트롤은 편집 컨트롤의 오른쪽에 포함 됩니다. 필요에 따라 사용 하 여 spin 컨트롤의 유효한 범위를 설정할 수 있습니다 합니다 [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) 메서드. 이벤트 처리기가 없는 데이터를 직접 교환 하기 때문에 버디 창 고 spin 컨트롤 사이 통신 해야 합니다. 다른 용도로 스핀 컨트롤을 사용 하는 경우 예를 들어 일련의 창이 나 대화 상자를 통해 페이지 UDN_DELTAPOS 메시지에 대 한 처리기를 추가 하십시오을 사용자 지정 작업을 수행 합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [스핀 단추 스타일](../mfc/spin-button-styles.md)

- [스핀 단추 멤버 함수](../mfc/spin-button-member-functions.md)

## <a name="see-also"></a>참고자료

[컨트롤](../mfc/controls-mfc.md)
