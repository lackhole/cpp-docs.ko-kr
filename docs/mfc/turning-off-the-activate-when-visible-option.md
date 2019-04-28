---
title: 표시되었을 때 활성화 옵션 해제
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
ms.openlocfilehash: a7afe9617aa356916fe184828d7684f228293e39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181499"
---
# <a name="turning-off-the-activate-when-visible-option"></a>표시되었을 때 활성화 옵션 해제

컨트롤은 활성 및 비활성의 두 가지 기본 상태를 가집니다. 일반적으로 이러한 상태는 컨트롤에 창이 있는지 여부에 따라 구분됩니다. 활성 컨트롤에는 창이 있지만 비활성 컨트롤에는 창이 없습니다. 창 없는 활성화의 도입으로 이러한 구분은 더 이상 일반적이지 않지만 여전히 많은 컨트롤에 적용됩니다.

일반적으로 ActiveX 컨트롤에서 수행 된 초기화의 나머지 부분에 비해 창 만들기는 매우 비용이 많이 드는 작업입니다. 이상적으로 컨트롤을 반드시 필요한 때까지 창을 만들지 않는 것입니다.

많은 컨트롤 컨테이너에서 볼 수 있도록 전체에 활성화 될 필요가 없습니다. 종종, 컨트롤 사용자 (예: 마우스로 클릭 하거나 TAB 키를 눌러) 활성화 해야 하는 작업을 수행할 때까지 비활성 상태에 남아 있습니다. 활성화 하려면 컨테이너를 만들어야 하는 때까지 비활성 상태로 유지 하기 위한 컨트롤을 제거 합니다 **OLEMISC_ACTIVATEWHENVISIBLE** 컨트롤의 기타 플래그의 플래그:

[!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]

**OLEMISC_ACTIVATEWHENVISIBLE** 플래그를 해제 하면 자동으로 생략 하면는 **활성화할 때 표시** 옵션을 [제어 설정을](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX 페이지 컨트롤을 만들 때 마법사를 제어 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)
