---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤의 이벤트 처리'
ms.date: 09/12/2018
helpviewer_keywords:
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
ms.openlocfilehash: 8087d84d2203e4f910200acdd1b00e58d14f920e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394899"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤의 이벤트 처리

이 문서에서는 ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤에 대 한 이벤트 처리기를 설치 하려면 속성 창을 사용 하 여 설명 합니다. 이벤트 처리기는 특정 이벤트 (컨트롤)에서 알림을 수신 및 응답의 일부 작업을 수행 하려면 사용 됩니다. 이 알림 이벤트를 "시작" 이라고 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

> [!NOTE]
>  이 문서는 대화 상자 기반 ActiveX 컨트롤 컨테이너 프로젝트 라는 컨테이너와 절차 및 코드의 예로 Circ 라는 포함 된 컨트롤을 사용 합니다.

이벤트 단추를 사용 하 여 속성 창에서 ActiveX 컨트롤 컨테이너 응용 프로그램에서 발생할 수 있는 이벤트의 지도 만들 수 있습니다. 라는 단어는 "이벤트 싱크 맵' 이라는이 맵에서 생성 되어 시각적 개체에서 유지 관리 C++ 컨트롤 컨테이너 클래스에 이벤트 처리기를 추가 합니다. 이벤트 맵 항목을 사용 하 여 구현 되는 각 이벤트 처리기에 이벤트 처리기 컨테이너 멤버 함수에는 특정 이벤트를 매핑합니다. 이 이벤트 처리기 함수에는 ActiveX 컨트롤 개체에 의해 지정 된 이벤트를 발생 시 호출 됩니다.

이벤트 싱크 맵에 대 한 자세한 내용은 참조 하세요. [이벤트 싱크 맵](../mfc/reference/event-sink-maps.md) 에 *클래스 라이브러리 참조*합니다.

##  <a name="_core_event_handler_modifications_to_the_project"></a> 프로젝트에 이벤트 처리기 수정

속성 창을 사용 하 여 이벤트 처리기를 추가 하는 이벤트 싱크 맵 선언 되 고 프로젝트에 정의 합니다. 다음 문은 컨트롤에 추가 됩니다. Cpp 처음은 이벤트 처리기를 추가 합니다. 이 코드는 대화 상자 클래스에 대 한 이벤트 싱크 맵과 선언 (이 예제의 경우 `CContainerDlg`):

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

이벤트 맵 항목 속성 창에 이벤트 추가를 사용 하 여 (`ON_EVENT`) 추가 하는 이벤트 싱크 맵 및 이벤트 처리기 함수에 추가 된 컨테이너의 구현 (합니다. Cpp) 합니다.

다음 예제에서는 라는 이벤트 처리기를 선언 `OnClickInCircCtrl`, Circ 컨트롤 `ClickIn` 이벤트:

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

다음 템플릿을 추가할 뿐만 아니라는 `CContainerDlg` 클래스 구현 (합니다. 이벤트 처리기 멤버 함수에 대 한 CPP) 파일:

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

이벤트 싱크 매크로에 대 한 자세한 내용은 참조 하세요. [이벤트 싱크 맵](../mfc/reference/event-sink-maps.md) 에 *클래스 라이브러리 참조*합니다.

#### <a name="to-create-an-event-handler-function"></a>이벤트 처리기 함수를 만들려면

1. 클래스 뷰에서 ActiveX 컨트롤이 포함 된 대화 상자 클래스를 선택 합니다. 예를 들어 사용 하 여 `CContainerDlg`입니다.

1. 속성 창에서 클릭 합니다 **이벤트** 단추입니다.

1. 속성 창에서 포함 된 ActiveX 컨트롤의 컨트롤 ID를 선택 합니다. 예를 들어 사용 하 여 `IDC_CIRCCTRL1`입니다.

   속성 창에는 포함 된 ActiveX 컨트롤에서 실행 될 수 있는 이벤트의 목록을 표시 합니다. 이미 굵게 표시 된 멤버 함수에 할당 하는 처리기 함수가 있습니다.

1. 원하는 이벤트를 처리 하는 대화 상자 클래스를 선택 합니다. 예를 들어 선택 **클릭**합니다.

1. 오른쪽의 드롭다운 목록 상자에서 선택  **\<추가 > ClickCircctrl1**합니다.

1. 구현에서 이벤트 처리기 코드를 이동할 클래스 뷰에서 새 처리기 함수를 두 번 클릭 (합니다. Cpp)에 `CContainerDlg`입니다.

## <a name="see-also"></a>참고자료

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
