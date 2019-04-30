---
title: 리플렉션된 창 메시지 ID
ms.date: 11/04/2016
f1_keywords:
- OCM_CTLCOLORBTN
- OCM_PARENTNOTIFY
- OCM_VKEYTOITEM
- OCM_CTLCOLORSTATIC
- OCM_HSCROLL
- OCM_CHARTOITEM
- OCM_DRAWITEM
- OCM_MEASUREITEM
- OCM_COMPAREITEM
- OCM_COMMAND
- OCM_NOTIFY
- OCM_CTLCOLORMSGBOX
- OCM_DELETEITEM
- OCM_CTLCOLORLISTBOX
- OCM_CTLCOLORDLG
- OCM_CTLCOLOREDIT
- OCM_CTLCOLORSCROLLBAR
- OCM_VSCROLL
- OCM_CTLCOLOR
helpviewer_keywords:
- OCM_HSCROLL message [MFC]
- OCM_PARENTNOTIFY message [MFC]
- messages, reflected
- reflected messages, window message Ids
- OCM_CTLCOLORDLG message [MFC]
- OCM_COMMAND message [MFC]
- OCM_CTLCOLORMSGBOX message [MFC]
- OCM_COMPAREITEM message [MFC]
- OCM_DRAWITEM message [MFC]
- OCM_VSCROLL message [MFC]
- OCM_CTLCOLOREDIT message [MFC]
- OCM_VKEYTOITEM message [MFC]
- OCM_CHARTOITEM message [MFC]
- OCM_CTLCOLORBTN message [MFC]
- OCM_CTLCOLORSTATIC message [MFC]
- OCM_MEASUREITEM message [MFC]
- OCM_CTLCOLOR message [MFC]
- OCM_CTLCOLORSCROLLBAR message [MFC]
- OCM_ messages
- OCM_DELETEITEM message [MFC]
- OCM_CTLCOLORLISTBOX message [MFC]
- OCM_NOTIFY message [MFC]
- reflected messages
ms.assetid: 3417ff51-ff9f-458c-bff4-17c200f00d96
ms.openlocfilehash: 2f6aea30fbf86865b5d42ea8da364685010c95c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309059"
---
# <a name="reflected-window-message-ids"></a>리플렉션된 창 메시지 ID

ActiveX 컨트롤을 만들거나 다른 특수 한 컨트롤을 신속 하 게 창 하위입니다. 자세한 내용은 참조 하세요. [MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)합니다.

컨트롤의 컨테이너 서브클래싱된 Windows 컨트롤을 통해 전송 창 메시지를 받지 못하도록 [COleControl](../mfc/reference/colecontrol-class.md) 특정 창 메시지를 가로채 고 컨트롤에 다시 보내지 하는 "구문은 reflector" 창을 만듭니다. 그런 다음 자체 창 프로시저에서 컨트롤을 ActiveX 컨트롤에 대 한 적절 한 조치를 취 함으로써 이러한 리플 렉 트 된 메시지를 처리할 수 있습니다.

다음 표에서 차단 된 메시지 및 리플렉터 창 전송 하는 해당 메시지를 보여 줍니다.

|컨트롤에서 보낸 메시지|컨트롤에 반영 되는 메시지|
|---------------------------------|--------------------------------------|
|[WM_COMMAND](/windows/desktop/menurc/wm-command)|OCM_COMMAND|
|[WM_CTLCOLORBTN](/windows/desktop/Controls/wm-ctlcolorbtn)|OCM_CTLCOLORBTN|
|[WM_CTLCOLOREDIT](/windows/desktop/Controls/wm-ctlcoloredit)|OCM_CTLCOLOREDIT|
|[WM_CTLCOLORDLG](/windows/desktop/dlgbox/wm-ctlcolordlg)|OCM_CTLCOLORDLG|
|[WM_CTLCOLORLISTBOX](/windows/desktop/Controls/wm-ctlcolorlistbox)|OCM_CTLCOLORLISTBOX|
|[WM_CTLCOLORSCROLLBAR](/windows/desktop/Controls/wm-ctlcolorscrollbar)|OCM_CTLCOLORSCROLLBAR|
|[WM_CTLCOLORSTATIC](/windows/desktop/Controls/wm-ctlcolorstatic)|OCM_CTLCOLORSTATIC|
|[WM_DRAWITEM](/windows/desktop/Controls/wm-drawitem)|OCM_DRAWITEM|
|[WM_MEASUREITEM](/windows/desktop/Controls/wm-measureitem)|OCM_MEASUREITEM|
|[WM_DELETEITEM](/windows/desktop/Controls/wm-deleteitem)|OCM_DELETEITEM|
|[WM_VKEYTOITEM](/windows/desktop/Controls/wm-vkeytoitem)|OCM_VKEYTOITEM|
|[WM_CHARTOITEM](/windows/desktop/Controls/wm-chartoitem)|OCM_CHARTOITEM|
|[WM_COMPAREITEM](/windows/desktop/Controls/wm-compareitem)|OCM_COMPAREITEM|
|[WM_HSCROLL](/windows/desktop/Controls/wm-hscroll)|OCM_HSCROLL|
|[WM_VSCROLL](/windows/desktop/Controls/wm-vscroll)|OCM_VSCROLL|
|[WM_PARENTNOTIFY](/previous-versions/windows/desktop/inputmsg/wm-parentnotify)|OCM_PARENTNOTIFY|
|[WM_NOTIFY](/windows/desktop/controls/wm-notify)|OCM_NOTIFY|

> [!NOTE]
>  여러 유형의 WM_CTLCOLOR 가지 컨트롤 Win32 시스템에서 실행 되 면\* 메시지를 받을 수 있습니다. 자세한 내용은 WM_CTLCOLORBTN, WM_CTLCOLORDLG, WM_CTLCOLOREDIT, WM_CTLCOLORLISTBOX, WM_CTLCOLORMSGBOX, WM_CTLCOLORSCROLLBAR, WM_CTLCOLORSTATIC를 참조 하십시오.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)<br/>
[TN062: Windows 컨트롤에 대한 메시지 리플렉션](../mfc/tn062-message-reflection-for-windows-controls.md)
