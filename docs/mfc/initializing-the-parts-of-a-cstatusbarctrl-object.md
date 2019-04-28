---
title: CStatusBarCtrl 개체의 일부 초기화
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
ms.openlocfilehash: 0f00aee03a74799bf14563653b50c487ff001d02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182321"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl 개체의 일부 초기화

기본적으로 상태 표시줄에는 별도 창을 사용 하는 상태 정보가 표시 됩니다. (파트 라고도 함) 이러한 창의 텍스트 문자열, 아이콘 또는 둘 다 포함할 수 있습니다.

사용 하 여 [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) 얼마나 많은 파트와 길이 정의 하려면 상태 표시줄을 갖습니다. 상태 표시줄의 파트를 만든 후에 호출을 수행 [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) 하 고 [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) 된 텍스트 또는 상태 표시줄의 특정 부분에 대 한 아이콘입니다. 파트를 성공적으로 설정 되 면 컨트롤이 자동으로 그려집니다.

다음 예제에서는 기존 초기화 `CStatusBarCtrl` 개체 (`m_StatusBarCtrl`) 4 개의 창을 사용 하 여 다음 두 번째 부분에서 (IDI_ICON1) 아이콘 및 텍스트를 설정 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

모드를 설정 하는 방법은 `CStatusBarCtrl` 간단한 참조 개체 [CStatusBarCtrl 개체의 모드 설정](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)합니다.

## <a name="see-also"></a>참고자료

[CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
