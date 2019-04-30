---
title: 'MFC ActiveX 컨트롤: 이벤트'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
ms.openlocfilehash: 0d8a881d07a3e48673c6dc3298816d165273be0d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392676"
---
# <a name="mfc-activex-controls-events"></a>MFC ActiveX 컨트롤: 이벤트

Activex는 컨트롤에 발생 하는 컨테이너에 알리기 위해 이벤트를 사용 합니다. 이벤트의 일반적인 예로 컨트롤, 컨트롤의 상태 변경 내용을 확인 하 고 키보드를 사용 하 여 입력 데이터에 대 한 클릭을 포함 합니다. 이러한 동작이 발생 하면 컨트롤에 이벤트 컨테이너 경고를 발생 시킵니다.

이벤트 메시지 라고도 합니다.

MFC에서는 두 가지 유형의 이벤트: 스톡 및 사용자 지정 합니다. 스톡 이벤트는 클래스는 해당 이벤트 [COleControl](../mfc/reference/colecontrol-class.md) 자동으로 처리 합니다. 스톡 이벤트의 전체 목록은, 문서를 참조 하세요. [MFC ActiveX 컨트롤: 스톡 이벤트 추가](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)합니다. 사용자 지정 이벤트를 제어 하는 특정 작업 발생 하는 경우 컨테이너를 알리는 기능을 제어를 허용 합니다. 몇 가지 예제를 변경 하는 컨트롤의 내부 상태 또는 특정 창 메시지를 받을 것입니다.

이벤트를 올바르게 실행 하려면 컨트롤에 대 한 사용자 컨트롤 클래스 관련된 이벤트가 발생할 때 호출 해야 하는 멤버 함수에 컨트롤의 각 이벤트를 매핑해야 합니다. 이 매핑 메커니즘 (맵이라고 이벤트) 이벤트에 대 한 정보를 중앙 집중화 하 고 쉽게 액세스 하 고 컨트롤의 이벤트를 조작 하는 Visual Studio를 허용 합니다. 이 이벤트 맵 헤더에 있는 다음 매크로 사용 하 여 선언 (합니다. H) 컨트롤 클래스 선언의 파일:

[!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/cpp/mfc-activex-controls-events_1.h)]

이벤트 맵을 선언한 후 컨트롤의 구현에서 정의 되어야 합니다 (합니다. Cpp) 합니다. 다음 코드 줄은 컨트롤을 특정 이벤트를 발생 시킬 수 있도록 이벤트 맵을 정의 합니다.

[!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/cpp/mfc-activex-controls-events_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/cpp/mfc-activex-controls-events_3.cpp)]

MFC ActiveX 컨트롤 마법사를 사용 하 여 프로젝트를 만드는 경우 자동으로 다음이 줄을 추가 합니다. MFC ActiveX 컨트롤 마법사를 사용 하지 않는 경우이 코드를 수동으로 추가 해야 있습니다.

클래스 뷰를 사용 하 여 클래스에 의해 지원 되는 스톡 이벤트를 추가할 수 있습니다 `COleControl` 또는 사용자가 정의한 사용자 지정 이벤트입니다. 각 새 이벤트에 대 한 클래스 뷰 컨트롤의 이벤트 맵 및 컨트롤에 적절 한 항목을 자동으로 추가합니다. IDL 파일입니다.

두 문서에서 이벤트를 자세히 설명 합니다.

- [MFC ActiveX 컨트롤: 스톡 이벤트 추가](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [MFC ActiveX 컨트롤: 사용자 지정 이벤트 추가](../mfc/mfc-activex-controls-adding-custom-events.md)

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl 클래스](../mfc/reference/colecontrol-class.md)
