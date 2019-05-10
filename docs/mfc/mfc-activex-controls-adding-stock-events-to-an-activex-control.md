---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤에 스톡 이벤트 추가'
ms.date: 11/04/2016
f1_keywords:
- EVENT__STOCK_ERROR
- EVENT__STOCK_READYSTATECHANGE
- ReadyStateChange
- EVENT__STOCK_MOUSEMOVE
- EVENT__STOCK_MOUSEUP
- EVENT__STOCK_DBLCLICK
- KeyPress
- EVENT__STOCK_KEYDOWN
- EVENT__STOCK
- EVENT__STOCK_MOUSEDOWN
- EVENT__STOCK_KEYPRESS
- EVENT__STOCK_CLICK
- EVENT__STOCK_KEYUP
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- KeyPress event
- FireDblClick event
- FireMouseDown event
- events [MFC], stock
- FireKeyPress event
- EVENT_STOCK_MOUSEMOVE event
- EVENT_STOCK_CLICK event
- FireClick event
- FireKeyUp event
- FireMouseUp event
- EVENT_STOCK_ERROREVENT event
- EVENT_STOCK_KEYDOWN event
- EVENT_STOCK_MOUSEDOWN event
- EVENT_STOCK_KEYPRESS macro [MFC]
- EVENT_STOCK_KEYUP event
- EVENT_STOCK_DBLCLICK event
- FireError event
- FireKeyDown event
- ReadyStateChange event
- EVENT_STOCK_MOUSEUP event
- FireMouseMove event
- EVENT_STOCK prefix
- EVENT_STOCK_READYSTATECHANGE event
- EVENT_STOCK_KEYPRESS event
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
ms.openlocfilehash: 9f6f3c63f0436296791df428c704bce96eca3ec0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392728"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤에 스톡 이벤트 추가

스톡 이벤트는 클래스에 의해 자동으로 발생 하는 사용자 지정 이벤트에서 다릅니다 [COleControl](../mfc/reference/colecontrol-class.md)합니다. `COleControl` 일반적인 작업에서 이벤트를 실행 하는 미리 정의 된 멤버 함수를 포함 합니다. 구현한 몇 가지 일반적인 동작 `COleControl` 단일-한 번 또는 두-clicks 컨트롤, 키보드 이벤트 및 변경 내용에에서 포함 된 마우스 단추의 상태입니다. 이벤트는 이벤트 앞에 항상 EVENT_STOCK 접두사 재고에 대 한 항목을 매핑합니다.

##  <a name="_core_stock_events_supported_by_classwizard"></a> 지 원하는 스톡 이벤트는 이벤트 추가 마법사

`COleControl` 클래스는 다음 표에 나열 된 10 스톡 이벤트를 제공 합니다. 사용 하 여 컨트롤에서 원하는 이벤트를 지정할 수는 [이벤트 추가 마법사](../ide/add-event-wizard.md)합니다.

### <a name="stock-events"></a>스톡 이벤트

|이벤트(event)|함수 실행|설명|
|-----------|---------------------|--------------|
|클릭 대상|**void FireClick( )**|마우스를 캡처하면 컨트롤에서 모든 발생 **BUTTONUP** (왼쪽, 가운데 또는 오른쪽) 메시지를 수신 하 고 단추를 컨트롤 위에 놓을 합니다. MouseDown 재고 및 MouseUp 이벤트를이 이벤트 전에 발생합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_CLICK( )**|
|DblClick|**void FireDblClick( )**|클릭과 유사 하지만 때 발생 하는 **BUTTONDBLCLK** 메시지를 수신 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_DBLCLICK( )**|
|Error|**void FireError( SCODE**  *scode* **, LPCSTR**  `lpszDescription` **, UINT**  `nHelpID`  **= 0 )**|메서드 호출 또는 속성 액세스의 범위 외부에서 ActiveX 컨트롤 내에 오류가 있을 때 발생 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_ERROREVENT( )**|
|KeyDown|**void FireKeyDown( short**  `nChar` **, short**  `nShiftState`  **)**|때 발생 하는 `WM_SYSKEYDOWN` 또는 `WM_KEYDOWN` 메시지를 수신 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYDOWN( )**|
|키 누름|**void FireKeyPress( short** <strong>\*</strong>  `pnChar`  **)**|때 발생 하는 `WM_CHAR` 메시지를 수신 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYPRESS( )**|
|KeyUp|**void FireKeyUp( short**  `nChar` **, short**  `nShiftState`  **)**|때 발생 하는 `WM_SYSKEYUP` 또는 `WM_KEYUP` 메시지를 수신 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYUP( )**|
|MouseDown|**void FireMouseDown( short**  `nButton` **, short**  `nShiftState` **, float**  *x* **, float**  *y*  **)**|있는 경우 발생 **BUTTONDOWN** (왼쪽, 가운데 또는 오른쪽) 수신 합니다. 마우스는이 이벤트가 발생 하기 직전에 캡처됩니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEDOWN( )**|
|MouseMove|**void FireMouseMove( short**  `nButton` **, short**  `nShiftState` **, float**  *x* **, float**  *y*  **)**|WM_MOUSEMOVE 메시지를 받을 때 발생 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEMOVE( )**|
|MouseUp|**void FireMouseUp( short**  `nButton` **, short**  `nShiftState` **, float**  *x* **, float**  *y*  **)**|있는 경우 발생 **BUTTONUP** (왼쪽, 가운데 또는 오른쪽) 수신 합니다. 이 이벤트가 발생 하기 전에 마우스 캡처가 해제 됩니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEUP( )**|
|ReadyStateChange|**void FireReadyStateChange( )**|컨트롤이 받은 데이터의 양으로 인해 다음 준비 상태로 전환 하는 경우 발생 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_READYSTATECHANGE( )**|

##  <a name="_core_adding_a_stock_event_using_classwizard"></a> 사용 하 여 스톡 이벤트 추가 이벤트 추가 마법사

실제 이벤트의 발생이 기본 클래스에 의해 자동으로 처리 되므로 사용자 지정 이벤트를 추가 하는 보다 더 적은 작업을 필요 스톡 이벤트 추가 `COleControl`합니다. 다음 절차를 사용 하 여 개발 된 컨트롤에 스톡 이벤트 추가 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)합니다. KeyPress, 호출 이벤트 키를 누르면 컨트롤이 활성화 된 경우 발생 합니다. 이 절차는 다른 스톡 이벤트 추가 하려면 데도 사용할 수 있습니다. 키 누름에 대 한 선택한 스톡 이벤트 이름을 대체 합니다.

#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>이벤트 추가 마법사를 사용 하 여 KeyPress 스톡 이벤트 추가

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 바로 가기 메뉴를 열려면 ActiveX 컨트롤 클래스를 마우스 오른쪽 단추로 클릭 합니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **이벤트 추가**합니다.

   이 이벤트 추가 마법사를 엽니다.

1. 에 **이벤트 이름** 드롭 다운 목록에서 `KeyPress`합니다.

1. **마침**을 클릭합니다.

##  <a name="_core_classwizard_changes_for_stock_events"></a> 스톡 이벤트 추가 이벤트 마법사 변경

스톡 이벤트는 컨트롤의 기본 클래스에 의해 처리 되므로, 이벤트 추가 마법사에는 클래스 선언에 어떤 방식으로든에서 변경 되지 않습니다. 컨트롤의 이벤트 구조에 이벤트를 추가 하 고 항목을 사용 하면 해당 합니다. IDL 파일입니다. 다음 줄 컨트롤 클래스 구현 되는 컨트롤의 이벤트 맵에 추가 됩니다 (합니다. Cpp) 됩니다.

[!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]

이 코드를 추가 WM_CHAR 메시지를 수신 하 고 컨트롤이 활성화 된 KeyPress 이벤트를 발생 시킵니다. KeyPress 이벤트의 발생 함수를 호출 하 여 다른 시간에 발생할 수 있습니다 (예를 들어 `FireKeyPress`)에서 컨트롤 코드 내에서.

이벤트 추가 마법사를 컨트롤의 다음 코드 줄을 추가합니다. IDL 파일:

[!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]

이 줄은 표준 디스패치 ID를 사용 하 여 KeyPress 이벤트를 연결 하 고 KeyPress 이벤트를 예상할 컨테이너를 허용 합니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl 클래스](../mfc/reference/colecontrol-class.md)
