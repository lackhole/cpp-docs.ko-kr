---
title: 비활성 상태 중 마우스 상호 작용 제공
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
ms.openlocfilehash: d37deeec06551ae8bf340c99a9759327ce2ec2b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297127"
---
# <a name="providing-mouse-interaction-while-inactive"></a>비활성 상태 중 마우스 상호 작용 제공

컨트롤은 즉시 활성화 되지 않으면 할 수 있습니다 프로세스 WM_SETCURSOR 고 WM_MOUSEMOVE 메시지를 컨트롤에는 고유의 창이 없는 경우에 합니다. 사용 하 여이 작업을 수행할 수 있습니다 `COleControl`의 구현을 `IPointerInactive` 인터페이스를 기본적으로 비활성화 됩니다. (참조를 *ActiveX SDK* 이 인터페이스에 대 한 합니다.) 사용 하려면 pointerInactive 플래그에서 반환 하는 플래그 집합에 포함할지 [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]

이 플래그를 포함 하는 코드는 선택 하는 경우에 자동으로 생성 됩니다는 **마우스 포인터 알림 경우 비활성** 옵션을 합니다 [제어 설정을](../mfc/reference/control-settings-mfc-activex-control-wizard.md) 를사용하여컨트롤을만들때페이지**MFC ActiveX 컨트롤 마법사**합니다.

경우는 `IPointerInactive` 인터페이스를 사용 하면 컨테이너 WM_SETCURSOR 및 WM_MOUSEMOVE 메시지를 위임 합니다. `COleControl`구현 `IPointerInactive` 조정 마우스 좌표를 적절히 후 컨트롤의 메시지 맵을 통해 메시지를 디스패치합니다. 해당 항목을 메시지 맵에 추가 하 여 일반적인 창 메시지와 마찬가지로 메시지를 처리할 수 있습니다. 이러한 메시지에 대 한 처리기를 사용 하지 않도록 합니다 *m_hWnd* 멤버 변수 (또는 사용 하는 멤버 함수)의 값이 있는지를 먼저 확인 하지 않고 **NULL**합니다.

비활성 컨트롤을 OLE 끌어서 놓기 작업의 대상이 될 수도 있습니다. 이 컨트롤의 창을 놓기 대상으로 등록 될 수 있도록 사용자가이 통해 개체를 끌 시점 컨트롤을 활성화 해야 합니다. 끌기 중에 발생 하는 활성화 시킬 재정의 [COleControl::GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy), POINTERINACTIVE_ACTIVATEONDRAG 플래그를 반환 합니다.

[!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]

사용 하도록 설정 된 `IPointerInactive` 인터페이스 일반적으로 컨트롤을 항상 마우스 메시지를 처리할 수 있는 것을 의미 합니다. 지원 하지 않는 컨테이너에서이 결과를 얻으려면는 `IPointerInactive` 컨트롤이 표시 될 때 항상 활성화 해야 하는 인터페이스, 즉, 컨트롤의 기타 플래그 간에 OLEMISC_ACTIVATEWHENVISIBLE 플래그를 포함 해야 합니다. 그러나이 플래그를 방지 하기 위해 적용 된 컨테이너에는 지원 하지 않습니다 `IPointerInactive`, OLEMISC_IGNOREACTIVATEWHENVISIBLE 플래그를 지정할 수도 있습니다.

[!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)
