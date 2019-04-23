---
title: 메시지 맵 범위에 대한 처리기
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- handlers [MFC], message-map ranges
- message maps [MFC], message handler functions
- message maps [MFC], ranges
- control-notification messages [MFC]
- command IDs [MFC], message mapping
- message-map ranges [MFC]
- handlers [MFC]
- message handling [MFC], message handler functions
- mappings [MFC], message ranges
- command handling [MFC], command update handlers
- controls [MFC], notifications
- handler functions [MFC], message-map ranges
- handler functions [MFC]
- command update handlers [MFC]
- command routing [MFC], command update handlers
- message ranges [MFC]
- handler functions [MFC], declaring
- message ranges [MFC], mapping
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
ms.openlocfilehash: d2bc961486d9bc686e1ca0d5feb0fe01d65f9512
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773998"
---
# <a name="handlers-for-message-map-ranges"></a>메시지 맵 범위에 대한 처리기

이 문서 (하나의 함수에 하나의 메시지를 매핑) 대신 단일 메시지 처리기 함수에 다양 한 메시지를 매핑하는 방법을 설명 합니다.

동일한 방식으로 둘 이상의 메시지 또는 컨트롤 알림 처리 해야 하는 경우가 있습니다. 이러한 시간에 메시지를 모두 단일 처리기 함수에 매핑할 하고자 할 수 있습니다. 메시지 맵 범위를 사용 하면 메시지의 연속 된 범위에 대 한이 작업을 수행할 수 있습니다.

- 명령 Id의 범위를 매핑할 수 있습니다.

  - 명령 처리기 함수입니다.

  - 명령 업데이트 처리기 함수입니다.

- 컨트롤 Id의 범위에 대 한 컨트롤 알림 메시지는 메시지 처리기 함수에 매핑할 수 있습니다.

이 문서에서 다루는 항목은 다음과 같습니다.

- [메시지 맵 항목 기록](#_core_writing_the_message.2d.map_entry)

- [처리기 함수 선언](#_core_declaring_the_handler_function)

- [명령 Id의 범위에 대 한 예제](#_core_example_for_a_range_of_command_ids)

- [컨트롤 Id의 범위에 대 한 예제](#_core_example_for_a_range_of_control_ids)

##  <a name="_core_writing_the_message.2d.map_entry"></a> 메시지 맵 항목 기록

안에. CPP 파일을 다음 예와에서 같이 메시지 맵 항목을 추가 합니다.

[!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

메시지 맵 항목의 다음 항목으로 구성 됩니다.

- 메시지 맵 범위 매크로:

  - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

  - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

  - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- 매크로에 매개 변수:

  처음 두 매크로 세 개의 매개 변수를 수행합니다.

  - 범위를 시작 하는 명령 ID

  - 범위를 끝내는 명령 ID

  - 메시지 처리기 함수의 이름

  명령 Id의 범위는 연속적 이어야 합니다.

  세 번째 매크로 `ON_CONTROL_RANGE`, 추가 첫 번째 매개 변수: 컨트롤 알림 메시지와 같은 **에서 EN_CHANGE**합니다.

##  <a name="_core_declaring_the_handler_function"></a> 처리기 함수 선언

처리기 함수 선언에 추가 합니다. H 파일입니다. 다음 코드는 아래와 같이이 모습을 보여줍니다.

[!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

단일 명령에 대 한 처리기 함수에는 일반적으로 매개 변수 없이 사용합니다. 업데이트 처리기 함수를 제외 하 고 메시지 맵 범위에 대 한 처리기 함수에는 추가 매개 변수는 필요 *nID*, 형식의 **UINT**합니다. 이 매개 변수는 첫 번째 매개 변수입니다. 추가 매개 변수는 사용자가 실제로 선택 하는 명령을 지정 하는 데 필요한 추가 명령 ID를 적용 합니다.

업데이트 처리기 함수에 대 한 매개 변수 요구 사항에 대 한 자세한 내용은 참조 하세요. [예제에 대 한 명령 Id 범위](#_core_example_for_a_range_of_command_ids)합니다.

##  <a name="_core_example_for_a_range_of_command_ids"></a> 범위의 명령 Id에 대 한 예제

한 가지 예는 MFC 샘플에서 확대/축소 명령 처럼 명령 처리 범위를 사용 하면 [HIERSVR](../overview/visual-cpp-samples.md)합니다. 이 명령은 300% 보통 크기의 25% 사이의 확장 보기를 확대 합니다. HIERSVR의 뷰 클래스 범위를 사용 하 여이 비슷한 메시지 맵 항목을 사용 하 여 확대/축소 명령 처리.

[!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

메시지 맵 엔트리를 쓸 다음 항목을 지정 합니다.

- 두 명령 Id, 시작 및 연속 된 범위를 종료 합니다.

   마련 **ID_VIEW_ZOOM25** 하 고 **ID_VIEW_ZOOM300**합니다.

- 명령에 대 한 처리기 함수의 이름입니다.

   여기에 `OnZoom`입니다.

함수 선언은 다음과 같습니다.

[!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

업데이트 처리기 함수의 경우 이와 유사 하며 보다 광범위 하 게 유용 합니다. 쓸 짓는 것 `ON_UPDATE_COMMAND_UI` 명령의 수에 대 한 처리기 작성 하거나 복사, 동일한 코드를 계속 해 서 찾습니다. 솔루션은 다양 한 명령 처리기 함수를 사용 하 여 Id 하나에 업데이트를 매핑하는 `ON_UPDATE_COMMAND_UI_RANGE` 매크로입니다. 명령 Id는 연속 된 범위를 형성 해야 합니다. 예를 들어 참조를 `OnUpdateZoom` 처리기 및 해당 `ON_UPDATE_COMMAND_UI_RANGE` HIERSVR 샘플의 뷰 클래스의 메시지 맵 항목입니다.

에 대 한 단일 명령을 일반적으로 단일 매개 변수 처리기 함수를 업데이트할 *pCmdUI*, 형식의 `CCmdUI*`합니다. 메시지 맵 범위에 대 한 업데이트 처리기 함수 처리기 함수와 달리는 추가 매개 변수를 필요 하지 않습니다 *nID*, 형식의 **UINT**합니다. 사용자가 실제로 선택 되는 명령은 지정 하는 데 필요한 명령 ID를에서 발견 되는 `CCmdUI` 개체입니다.

##  <a name="_core_example_for_a_range_of_control_ids"></a> 컨트롤의 범위 Id에 대 한 예제

또 다른 흥미로운 사례에서는 컨트롤 Id의 범위에 대 한 컨트롤 알림 메시지를 단일 처리기에 매핑할는 합니다. 사용자에 10 개의 단추를 클릭할 수 있다고 가정 합니다. 모든 10 개의 단추 처리기에 매핑하려면 메시지 맵 항목은 다음과 같습니다.

[!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

작성 하는 경우는 `ON_CONTROL_RANGE` 지정할 메시지 맵에서 매크로:

- 특정 컨트롤 알림 메시지입니다.

   여기에 **BN_CLICKED**합니다.

- 컨트롤의 연속 된 범위에 연결 된 컨트롤 ID 값입니다.

   다음은 이러한 **IDC_BUTTON1** 하 고 **IDC_BUTTON10**합니다.

- 메시지 처리기 함수의 이름입니다.

   여기에 `OnButtonClicked`입니다.

처리기 함수를 작성할 때 지정할 추가 **UINT** 매개 변수를 다음과 같이 합니다.

[!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

합니다 `OnButtonClicked` 단일 처리기 **BN_CLICKED** 메시지 매개 변수를 사용 합니다. 단추의 범위에 대 한 동일한 처리기 하나를 사용 합니다. **UINT**합니다. 생성을 담당 특정 컨트롤을 식별 하는 데 추가 매개 변수를 사용 합니다 **BN_CLICKED** 메시지입니다.

예제에 표시 된 코드는 일반적인: 전달 되는 값을 변환는 `int` 메시지 범위 및 대/소문자는 어설션 내에서. 그런 다음 몇 가지 다른 작업에 따라 단추를 클릭 했을 걸릴 수 있습니다.

## <a name="see-also"></a>참고자료

[메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
