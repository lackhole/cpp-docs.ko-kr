---
title: 'MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱'
ms.date: 09/12/2018
f1_keywords:
- precreatewindow
- IsSubclassed
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- subclassing
- DoSuperclassPaint method [MFC]
- subclassing Windows controls
- subclassing, Windows controls
- reflected messages, in ActiveX controls
- PreCreateWindow method, overriding
- MFC ActiveX controls [MFC], subclassed controls
- MFC ActiveX controls [MFC], creating
- IsSubclassed method [MFC]
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
ms.openlocfilehash: 7042df6e7b7dc2c9a608470ba7cfc5a9e9f6127a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773257"
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱

이 문서는 ActiveX 컨트롤을 만드는 일반적인 Windows 컨트롤 서브클래싱 프로세스를 설명 합니다. 컨트롤에 ActiveX 컨트롤을 개발 하는 빠른 방법은는 기존 Windows 서브클래싱 합니다. 새 컨트롤 Windows 서브클래싱된 컨트롤 그리기 마우스 클릭에 응답 등의 기능을 갖게 됩니다. MFC ActiveX 컨트롤 샘플 [단추](../overview/visual-cpp-samples.md) Windows 컨트롤 서브클래싱 예가 됩니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

Windows 컨트롤의 하위 클래스를 만들려면 다음 작업을 완료 합니다.

- [COleControl의 IsSubclassedControl 및 PreCreateWindow 멤버 함수를 재정의 합니다.](#_core_overriding_issubclassedcontrol_and_precreatewindow)

- [OnDraw 멤버 함수를 수정 합니다.](#_core_modifying_the_ondraw_member_function)

- [컨트롤에 반영 ActiveX 제어 메시지 (OCM)를 처리 합니다.](#_core_handling_reflected_window_messages)

   > [!NOTE]
   > 이 작업의 대부분은가 수행 ActiveX 컨트롤 마법사를 사용 하 여 서브클래싱 할 컨트롤을 선택 합니다 **부모 창 클래스 선택** 드롭 다운 목록에서를 **제어 설정을** 페이지.

##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> IsSubclassedControl 및 PreCreateWindow 재정의

재정의할 `PreCreateWindow` 및 `IsSubclassedControl`, 다음 줄의 코드를 추가 합니다 **보호** 컨트롤 클래스 선언의 섹션:

[!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]

컨트롤 구현 파일에서 (합니다. CPP), 두 가지 재정의 함수를 구현 하는 코드의 다음 줄을 추가 합니다.

[!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]

공지는이 예제는 Windows 단추 컨트롤에 지정 된 `PreCreateWindow`합니다. 그러나 모든 표준 Windows 컨트롤 서브클래싱 할 수 있습니다. 표준 Windows 컨트롤에 대 한 자세한 내용은 참조 하세요. [컨트롤](../mfc/controls-mfc.md)합니다.

Windows 컨트롤 서브클래싱, 경우에 특정 창 스타일 (WS_) 또는 컨트롤의 창을 만드는 데 사용할 확장된 창 스타일 (WS_EX_) 플래그를 지정 하는 것이 좋습니다. 이 매개 변수에 대해 값을 설정할 수는 `PreCreateWindow` 수정 하 여 멤버 함수는 `cs.style` 및 `cs.dwExStyle` 구조체 필드. 이 필드를 수정할 수 있어야를 사용 하는 **또는** 클래스에 의해 설정 된 기본 플래그를 유지 하기 위해 작업 `COleControl`합니다. 예를 들어, 컨트롤 단추 컨트롤의 하위 클래스 지정을 컨트롤을 확인란으로 표시 하는 경우 다음 코드 줄에 삽입 구현의 `CSampleCtrl::PreCreateWindow`, return 문:

[!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]

이 작업은 클래스의 기본 스타일 플래그 (WS_CHILD)를 그대로 유지 하면서 BS_CHECKBOX 스타일 플래그를 추가 `COleControl` 그대로 유지 됩니다.

##  <a name="_core_modifying_the_ondraw_member_function"></a> OnDraw 멤버 함수를 수정합니다.

서브클래싱된 컨트롤을 해당 Windows 컨트롤과 동일한 모양을 유지 하려는 경우는 `OnDraw` 컨트롤에 대 한 멤버 함수를 호출 하기만 하면 있어야 합니다.는 `DoSuperclassPaint` 다음 예제와 같이 멤버 함수:

[!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]

합니다 `DoSuperclassPaint` 멤버 함수를 구현한 `COleControl`를 Windows 컨트롤의 창 프로시저를 사용 하 여 경계 사각형 내에서 지정 된 장치 컨텍스트에 컨트롤을 그립니다. 이렇게 하면 컨트롤 표시 활성화 되어 있지 않은 경우에 있습니다.

> [!NOTE]
>  합니다 `DoSuperclassPaint` 멤버 함수는 장치 컨텍스트에 변수로 전달할 수 있도록 해당 컨트롤 형식 에서만 작동 합니다 *wParam* WM_PAINT 메시지입니다. 이 스크롤 막대 및 단추와 같은 표준 Windows 컨트롤 중 일부와 일반적인 모든 컨트롤을 포함합니다. 이 동작을 지원 하지 않는 컨트롤에 대 한 제대로 비활성 컨트롤을 표시 하는 사용자 고유의 코드를 제공 해야 합니다.

##  <a name="_core_handling_reflected_window_messages"></a> 리플렉션된 창 메시지 처리

일반적으로 Windows 컨트롤의 부모 창에 특정 창 메시지를 보냅니다. WM_COMMAND와 같은 이러한 메시지 중 일부에 사용자가 작업에 대 한 알림을 제공합니다. 다른 WM_CTLCOLOR 같은 하는 데 부모 창에서 정보를 가져옵니다. ActiveX 컨트롤을 다른 방법으로 부모 창을 사용 하 여 일반적으로 통신합니다. 이벤트 (이벤트 알림 보내기)를 실행 하 여 알림을 전달 하는 및 컨테이너의 앰비언트 속성에 액세스 하 여 컨트롤 컨테이너에 대 한 정보를 가져옵니다. 이러한 통신 기술 때문에 ActiveX 컨트롤 컨테이너는 컨트롤에 의해 전송 된 모든 창 메시지를 처리 하는 데 필요 하지 않습니다.

컨테이너 서브클래싱된 Windows 컨트롤을 통해 전송 창 메시지를 받지 못하도록 `COleControl` 컨트롤의 부모 역할을 추가 창을 만듭니다. 이 추가 창에서는 "reflector" 라는 하위 클래스는 Windows 컨트롤과 같은 크기 및 위치에 컨트롤 창 ActiveX 컨트롤에 대해서만 생성 됩니다. Reflector 창의 특정 창 메시지를 가로채 고 컨트롤에 다시 보냅니다. 다음 컨트롤의 창 프로시저 (예: 이벤트를 발생 시키기) ActiveX 컨트롤에 대 한 적절 한 조치를 취 함으로써 이러한 리플 렉 트 된 메시지를 처리할 수 있습니다. 참조 [리플렉션된 창 메시지 Id](../mfc/reflected-window-message-ids.md) 가로챈 창의 목록에 대 한 메시지 및 해당 메시지 반영 됩니다. 합니다.

ActiveX 컨트롤 컨테이너의 필요성 해소 자체 메시지 리플렉션을 수행 되도록 디자인 됩니다 `COleControl` 만들려면 reflector 창과 런타임 서브클래싱된 Windows 컨트롤에 대 한 오버 헤드를 줄일 합니다. `COleControl` 컨테이너 MessageReflect 앰비언트 속성의 값을 확인 하 여이 기능을 지원 하는지 여부를 감지 **TRUE**합니다.

리플렉션된 창 메시지를 처리 하려면 컨트롤 메시지 맵에 항목을 추가 하 고 처리기 함수를 구현 합니다. 리플 렉 트 된 메시지는 표준 Windows에서 정의한 메시지 집합의 일부가 아닌, 때문에 클래스 뷰 이러한 메시지 처리기 추가 지원 하지 않습니다. 그러나 처리기를 수동으로 추가 하기는 어렵지 않습니다.

추가할 리플렉션된 창 메시지에 대 한 메시지 처리기를 수동으로 다음을 수행 합니다.

- 컨트롤 클래스에 해당 합니다. H 파일 처리기 함수를 선언 합니다. 함수 반환 형식이 있어야 합니다. **LRESULT** 형식과 두 개의 매개 변수를 **WPARAM** 하 고 **LPARAM**, 각각. 예를 들어:

   [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]

- 컨트롤 클래스에 해당 합니다. CPP 파일을 메시지 맵에 ON_MESSAGE 항목을 추가 합니다. 이 항목의 매개 변수는 메시지 식별자 및 처리기 함수의 이름 이어야 합니다. 예를 들어:

   [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]

- 또한 합니다. CPP 파일에 구현 된 `OnOcmCommand` 리플 렉 트 된 메시지를 처리할 멤버 함수입니다. 합니다 *wParam* 하 고 *lParam* 매개 변수는 원래 창 메시지의 것과 동일 합니다.

메시지 처리 반영 하는 방법의 예제에 대 한 MFC ActiveX 컨트롤 샘플을 참조 하세요 [단추](../overview/visual-cpp-samples.md)합니다. 보여 줍니다는 `OnOcmCommand` BN_CLICKED 알림 코드를 감지 하 고 (송신) 하 여 대응 하는 처리기는 `Click` 이벤트입니다.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
