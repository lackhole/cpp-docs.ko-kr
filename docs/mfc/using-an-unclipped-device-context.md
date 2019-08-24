---
title: 잘리지 않는 디바이스 컨텍스트 사용
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
ms.openlocfilehash: 0f129c0bfa5bd76df4ba34b117e7ed8aa08c2ecb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411814"
---
# <a name="using-an-unclipped-device-context"></a>잘리지 않는 디바이스 컨텍스트 사용

인 경우 반드시 특정 컨트롤의 클라이언트 사각형 외부 그리지 않는 호출을 사용 하지 않도록 설정 하 여 작지만 감지 속도 향상을 실현할 수 있습니다 `IntersectClipRect` 하 여 만들어진 `COleControl`합니다. 이 작업을 수행 하려면 제거 합니다 *clipPaintDC* 반환한 플래그 집합과에서 플래그 [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)합니다. 예를 들어:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

선택 하는 경우이 플래그를 제거 하려면 코드를 자동으로 생성 됩니다는 **잘리지 않는 장치 컨텍스트** 옵션을 합니다 [제어 설정을](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX 컨트롤 마법사를 사용 하 여 컨트롤을 만들 때 페이지입니다.

창 없는 활성화를 사용 하는 경우이 최적화에 영향을 주지 않습니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)
