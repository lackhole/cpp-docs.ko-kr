---
title: 깜빡임 없는 활성화 제공
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
ms.openlocfilehash: fad24d6201260e87ff32436752a9fbf035e822ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297049"
---
# <a name="providing-flicker-free-activation"></a>깜빡임 없는 활성화 제공

그리기 작업 및 깜빡임을 비활성 사이 전환할 때는 일반적으로 발생 하는 컨트롤의 비활성 및 활성 상태에서 동일 하 게 자신을 그릴과 창 없는 활성화를 사용 하지 않는 경우 제거할 수 있습니다. 및 활성 상태입니다. 이 위해 포함 된 **noFlickerActivate** 반환한 플래그 집합이 플래그 [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)합니다. 예를 들어:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

이 플래그를 포함 하는 코드는 선택 하는 경우에 자동으로 생성 됩니다는 **깜빡임 없는 활성화** 옵션을 합니다 [제어 설정을](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX 컨트롤 마법사를 사용 하 여 컨트롤을 만들 때 페이지입니다.

창 없는 활성화를 사용 하는 경우이 최적화에 영향을 주지 않습니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)
