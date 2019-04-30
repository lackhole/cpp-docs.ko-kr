---
title: CStatusBarCtrl 개체에서 도구 설명 사용
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: 3f9a1fec7eb951fa76c542e09df751b4c58ddb16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411437"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl 개체에서 도구 설명 사용

상태 표시줄 컨트롤에 대 한 도구 설명에 사용 하려면 만들기를 `CStatusBarCtrl` SBT_TOOLTIPS 스타일을 사용 하 여 개체입니다.

> [!NOTE]
>  사용 중인 경우는 `CStatusBar` 개체에 상태 표시줄 구현를 사용 하 여는 `CStatusBar::CreateEx` 함수입니다. 포함 된 항목에 대 한 추가 스타일을 지정할 수 있도록 `CStatusBarCtrl` 개체입니다.

한 번를 `CStatusBarCtrl` 사용 하 여, 개체가 성공적으로 만들어진 [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) 및 [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) 설정 하 고 특정 창에 대 한 설명 텍스트를 검색 합니다.

도구 설명에 설정 되 면 파트 내에서 모든 텍스트를 표시할 수 없는 경우 또는 부분에는 아이콘과 텍스트가 없는 경우에 표시 됩니다. 단순 모드에서 도구 설명은 지원 되지 않습니다.

## <a name="see-also"></a>참고자료

[CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
