---
title: CStatusBarCtrl 개체의 모드 설정
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: a6d1a0edb356f9737aa287809dd8bca4146c1854
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307722"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl 개체의 모드 설정

에 대 한 두 가지 모드를 가지는 `CStatusBarCtrl` 개체: 단순 및 비 단순 합니다. 대부분의 경우 상태 표시줄 컨트롤에 텍스트와 아이콘이 나 아이콘 함께 하나 이상의 파트를 해야 합니다. 이 비 단순 모드를 라고 합니다. 이 모드에 대 한 자세한 내용은 참조 하세요. [CStatusBarCtrl 개체의 일부 초기화](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)합니다.

그러나만 해야 하는 텍스트 한 줄을 표시 하는 경우가 있습니다. 이 경우 간단한 모드 요구 사항에 맞게 충분 한입니다. 모드를 변경 합니다 `CStatusBarCtrl` simple로 개체를 호출 하는 [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) 멤버 함수입니다. 상태 표시줄 컨트롤은 단순 모드에서 되 면 호출 하 여 텍스트를 설정 합니다 `SetText` 255에 대 한 값으로 전달 되는 멤버 함수는 *nPane* 매개 변수입니다.

사용할 수는 [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) 모드를 결정 하는 함수는 `CStatusBarCtrl` 개체가 있습니다.

> [!NOTE]
>  경우 상태 표시줄 개체가 인스턴스이므로에서 간단 하 고로 변경 됩니다 또는 창을 즉시 다시 그릴 그 반대의 경우와 해당 하는 경우, 정의 된 모든 부분이 자동으로 복원 됩니다.

## <a name="see-also"></a>참고자료

[CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
