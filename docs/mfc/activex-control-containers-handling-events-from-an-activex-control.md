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
ms.openlocfilehash: 7487792fbc9fe6775640f40755a7f725543fb9f3
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907768"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤의 이벤트 처리

이 문서에서는 **클래스 뷰**의 **속성** 창을 사용 하 여 ActiveX 컨트롤 컨테이너의 activex 컨트롤에 대 한 이벤트 처리기를 설치 하는 방법을 설명 합니다. 이벤트 처리기는 특정 이벤트의 알림 (컨트롤에서)을 수신 하 고 응답으로 일부 동작을 수행 하는 데 사용 됩니다. 이 알림을 이벤트를 "실행" 이라고 합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 하지 않아야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 [Activex Controls](activex-controls.md)을 참조 하세요.

> [!NOTE]
>  이 문서에서는 프로시저 및 코드에서 예제로 이름이 Container 이라는 대화 상자 기반 ActiveX 컨트롤 컨테이너 프로젝트와 Circ 라는 포함 된 컨트롤을 사용 합니다.

**클래스 뷰**의 **속성** 창에서 이벤트 단추를 사용 하 여 ActiveX 컨트롤 컨테이너 응용 프로그램에서 발생할 수 있는 이벤트 맵을 만들 수 있습니다. 컨트롤 컨테이너 클래스에 이벤트 처리기를 추가할 때 "이벤트 싱크 맵 ' ' 이라는이 맵을 C++ 시각적으로 만들고 유지 관리 합니다. 이벤트 맵 항목으로 구현 된 각 이벤트 처리기는 특정 이벤트를 컨테이너 이벤트 처리기 멤버 함수에 매핑합니다. 이 이벤트 처리기 함수는 ActiveX 컨트롤 개체에서 지정 된 이벤트를 발생 시킬 때 호출 됩니다.

이벤트 싱크 맵에 대 한 자세한 내용은 *클래스 라이브러리 참조*에서 [이벤트 싱크 맵](../mfc/reference/event-sink-maps.md) 을 참조 하세요.

##  <a name="_core_event_handler_modifications_to_the_project"></a>프로젝트에 대 한 이벤트 처리기 수정

**속성** 창을 사용 하 여 이벤트 처리기를 추가 하면 프로젝트에 이벤트 싱크 맵이 선언 되 고 정의 됩니다. 다음 문이 컨트롤에 추가 됩니다. 이벤트 처리기가 처음 추가 될 때의 CPP 파일입니다. 이 코드는 대화 상자 클래스 (이 경우 `CContainerDlg`)에 대 한 이벤트 싱크 맵을 선언 합니다.

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

**속성** 창을 사용 하 여 이벤트를 추가 하면 이벤트 맵 항목 (`ON_EVENT`)이 이벤트 싱크 맵에 추가 되 고 이벤트 처리기 함수가 컨테이너의 구현 (에 추가 됩니다. CPP) 파일입니다.

다음 예제에서는 Circ 컨트롤의 `OnClickInCircCtrl` `ClickIn` 이벤트에 대해 이라는 이벤트 처리기를 선언 합니다.

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

또한 `CContainerDlg` 클래스 구현 ()에 다음 템플릿이 추가 됩니다. CPP) 이벤트 처리기 멤버 함수에 대 한 파일입니다.

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

이벤트 싱크 매크로에 대 한 자세한 내용은 *클래스 라이브러리 참조*에서 [이벤트 싱크 맵](../mfc/reference/event-sink-maps.md) 을 참조 하세요.

#### <a name="to-create-an-event-handler-function"></a>이벤트 처리기 함수를 만들려면

1. 클래스 뷰에서 ActiveX 컨트롤을 포함 하는 대화 상자 클래스를 선택 합니다. 이 예에서는를 사용 `CContainerDlg`합니다.

1. **속성** 창에서 **이벤트** 단추를 클릭합니다.

1. **속성** 창에서 포함 ActiveX 컨트롤의 컨트롤 ID를 선택 합니다. 이 예에서는를 사용 `IDC_CIRCCTRL1`합니다.

   **속성** 창에는 포함 ActiveX 컨트롤에서 발생 시킬 수 있는 이벤트 목록이 표시 됩니다. 굵게 표시 된 멤버 함수에는 이미 처리기 함수가 할당 되어 있습니다.

1. 대화 상자 클래스에서 처리할 이벤트를 선택 합니다. 이 예에서는 **클릭**을 선택 합니다.

1. 오른쪽의 드롭다운 목록 상자에서  **\<추가 > ClickCircctrl1**를 선택 합니다.

1. 클래스 뷰에서 새 처리기 함수를 두 번 클릭 하 여 구현 (에 있는 이벤트 처리기 코드로 이동 합니다. .CPP)의 `CContainerDlg`파일입니다.

## <a name="see-also"></a>참고자료

[ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)
