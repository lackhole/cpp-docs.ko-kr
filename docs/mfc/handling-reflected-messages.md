---
title: 리플렉션된 메시지 처리
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 973e8cff24eca37b1806207d081636f0d1b38365
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240563"
---
# <a name="handling-reflected-messages"></a>리플렉션된 메시지 처리

메시지 리플렉션 등의 컨트롤에 대 한 메시지를 처리 하면 **WM_CTLCOLOR**를 **WM_COMMAND**, 및 **WM_NOTIFY**, 자체 컨트롤 내에서. 그러면 컨트롤의 독립성 및 이식성이 향상됩니다. 이 메커니즘은 Windows 공용 컨트롤 및 ActiveX 컨트롤(이전의 OLE 컨트롤)에서 작동합니다.

메시지 리플렉션을 사용하면 `CWnd` 파생 클래스를 보다 쉽게 재사용할 수 있습니다. 메시지 리플렉션 작동 [cwnd:: Onchildnotify](../mfc/reference/cwnd-class.md#onchildnotify)를 통해 특수 한 **ON_XXX_REFLECT** 메시지 맵 항목: 예를 들어 **ON_CTLCOLOR_REFLECT** 및 **ON_CONTROL_REFLECT**합니다. [Technical Note 62](../mfc/tn062-message-reflection-for-windows-controls.md) 메시지 리플렉션 좀 더 자세히 설명 합니다.

## <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요

- [메시지 리플렉션에 대 한 자세한 정보](../mfc/tn062-message-reflection-for-windows-controls.md)

- [공용 컨트롤에 대 한 메시지 리플렉션 구현](../mfc/tn062-message-reflection-for-windows-controls.md)

- [ActiveX 컨트롤에 대 한 메시지 리플렉션 구현](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>참고자료

[메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
