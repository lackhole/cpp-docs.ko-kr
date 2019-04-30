---
title: 진행률 컨트롤에 대한 설정
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
ms.openlocfilehash: 1960b15c2f76d7cbfc9f249a77481b795e6a27ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307681"
---
# <a name="settings-for-the-progress-control"></a>진행률 컨트롤에 대한 설정

진행률 컨트롤에 대 한 기본 설정 ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md))은 범위 및 현재 위치입니다. 범위는 전체 작업 기간을 나타냅니다. 현재 위치는 작업 완료에 대 한 응용 프로그램에 대 한 진행률을 나타냅니다. 범위 또는 위치를 변경 하면 진행률 컨트롤을 다시 그리도록 합니다.

기본적으로 설정 되어 범위 0-100 및 초기 위치는 0으로 설정 합니다. 진행률 컨트롤에 대 한 현재 범위 설정을 검색 하려면 사용 합니다 [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) 멤버 함수입니다. 범위를 변경 하려면 사용 합니다 [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) 멤버 함수입니다.

위치를 설정 하려면 [SetPos](../mfc/reference/cprogressctrl-class.md#setpos)합니다. 사용 하 여 새 값을 지정 하지 않고 현재 위치를 검색할 [GetPos](../mfc/reference/cprogressctrl-class.md#getpos)합니다. 예를 들어, 다음 단순히 현재 작업의 상태를 쿼리 하는 것이 좋습니다.

진행률 컨트롤의 현재 위치 단계를 사용 하 여 [StepIt](../mfc/reference/cprogressctrl-class.md#stepit)합니다. 각 단계의 크기를 설정 하려면 사용 하 여 [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)

## <a name="see-also"></a>참고자료

[CProgressCtrl 사용](../mfc/using-cprogressctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
