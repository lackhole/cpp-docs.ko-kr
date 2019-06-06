---
title: 리플렉트된 메시지의 메시지 처리기 정의
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.defining.msg.msghandler
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
ms.openlocfilehash: 970dd7072cb8391d76d39536e442d5aab8e0f61d
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741594"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>리플렉트된 메시지의 메시지 처리기 정의

새 MFC 컨트롤 클래스를 만든 후에 대 한 메시지 처리기를 정의할 수 있습니다. 리플 렉 트 된 메시지 처리기는 컨트롤 클래스에서 부모에 의해 메시지가 수신 되기 전에 자체 메시지 처리를 허용 합니다. MFC를 사용할 수 있습니다 [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) 부모 창에 컨트롤에서 메시지를 보내는 함수입니다.

부모 창 (소유자 그린)에 의존 하는 것이 아니라 할 수 있습니다, 예를 들어,이 기능을 사용 하 여 자체는 다시 그리기 목록 상자를 만듭니다. 리플 렉 트 된 메시지에 대 한 자세한 내용은 참조 하세요. [리플렉션된 메시지 처리](../../mfc/handling-reflected-messages.md)합니다.

만들려는 프로그램 [ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md) 동일한 기능을 사용 하 여 ActiveX 컨트롤에 대 한 프로젝트를 만들어야 합니다.

> [!NOTE]
>  리플 렉 트 된 메시지를 추가할 수 없습니다 (OCM_*메시지*) ActiveX 제어 속성 창을 사용 하 여 아래와 같이 합니다. 이러한 메시지를 수동으로 추가 해야 합니다.

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>속성 창에서 리플 렉 트 된 메시지에 대 한 메시지 처리기를 정의 하려면

1. 목록 등의 컨트롤을, rebar 컨트롤, 도구 모음 또는 트리 컨트롤을 MFC 프로젝트에 추가 합니다.

1. 클래스 뷰에서 컨트롤 클래스의 이름을 클릭 합니다.

1. 에 [속성 창](/visualstudio/ide/reference/properties-window), 컨트롤 클래스 이름에 표시를 **클래스 이름** 목록입니다.

1. 클릭 합니다 **메시지** 단추 컨트롤을 추가할 수 있도록 Windows 메시지를 표시 합니다.

1. 메시지 속성 창의 제목에 표시 될 때까지 목록 아래로 스크롤하여 **리플렉션**합니다. 또는 클릭을 **범주** 단추를 확인 하려면 뷰를 축소 합니다 **리플렉션** 제목.

1. 리플 렉 트 된 메시지 처리기를 정의 하려면 선택 합니다. 리플 렉 트 된 메시지는 등호 (=)로 표시 됩니다.

1. 같이 처리기의 제안 된 이름을 표시 하려면 속성 창의 오른쪽 열에서 셀을 클릭 \<추가 >*HandlerName*합니다. (예를 들어 합니다 **WM_CTLCOLOR =** 메시지 처리기 제안 \<추가 >**CtlColor**).

1. 제안된 된 이름을 수락 하도록 클릭 합니다. 처리기는 프로젝트에 추가 됩니다.

   추가 된 메시지 처리기 이름은 리플 렉 트 된 메시지 창의 오른쪽 열에 나타납니다.

9. 을 편집 하거나 메시지 처리기를 삭제 하려면 4 ~ 7 단계를 반복 합니다. 편집 하거나 삭제 하 고 적절 한 작업을 클릭 처리기 이름이 포함 된 셀을 클릭 합니다.

## <a name="see-also"></a>참고자료

[함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[코드 마법사로 기능 추가](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[멤버 함수 추가](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[멤버 변수 추가](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[가상 함수 재정의](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 메시지 처리기](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[클래스 구조 탐색](../../ide/navigate-code-cpp.md)
