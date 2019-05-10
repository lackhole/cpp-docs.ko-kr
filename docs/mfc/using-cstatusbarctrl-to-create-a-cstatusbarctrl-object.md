---
title: CStatusBarCtrl을 사용하여 CStatusBarCtrl 개체 만들기
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
ms.openlocfilehash: 3242986d66de7d423b8ab744a691ca1904328de8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411710"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>CStatusBarCtrl을 사용하여 CStatusBarCtrl 개체 만들기

일반적인 사용 예로 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):

### <a name="to-use-a-status-bar-control-with-parts"></a>파트를 사용 하 여 상태 표시줄 컨트롤을 사용 하려면

1. `CStatusBarCtrl` 개체를 생성합니다.

1. 호출 [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) 의 그리기 영역 상태 표시줄 컨트롤의 최소 높이 설정 하려는 경우.

1. 호출 [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) 상태 표시줄 컨트롤의 배경색을 설정 합니다.

1. 호출 [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) 상태 표시줄 컨트롤 및 각 파트의 오른쪽 가장자리의 좌표에에서 파트 수를 설정 합니다.

1. 호출 [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) 상태 표시줄 컨트롤의 특정된 부분에서 텍스트를 설정 합니다. 컨트롤은 다음 WM_PAINT 메시지를 받을 경우 새 텍스트를 표시 하도록 변경 된 컨트롤의 부분을 무효화 하는 메시지입니다.

일부 경우 상태 표시줄 텍스트의 줄에 표시할만 해야 합니다. 이 경우에 호출할 [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)합니다. 이 상태 표시줄 컨트롤을 한 줄 텍스트를 표시 하는 "단순" 모드를 넣습니다.

## <a name="see-also"></a>참고자료

[CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
