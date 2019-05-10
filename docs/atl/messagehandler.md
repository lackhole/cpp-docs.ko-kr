---
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: 1acd56357f9ce234e3c479fd8fa88c1ed8407878
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261698"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler` 메시지 맵에서 MESSAGE_HANDLER 매크로의 두 번째 매개 변수로 식별 된 함수의 이름이입니다.

## <a name="syntax"></a>구문

```
LRESULT MessageHandler(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>매개 변수

*uMsg*<br/>
메시지를 지정합니다.

*wParam*<br/>
추가 메시지 관련 정보입니다.

*lParam*<br/>
추가 메시지 관련 정보입니다.

*bHandled*<br/>
메시지 맵 집합 *bHandled* 하기 전에 true `MessageHandler` 라고 합니다. 경우 `MessageHandler` 메시지를 완전히 처리 하지 않는 설정 해야 *bHandled* 에 FALSE를 메시지에 추가 처리가 필요 합니다.

## <a name="return-value"></a>반환 값

메시지 처리의 결과입니다. 성공한 경우 0입니다.

## <a name="remarks"></a>설명

메시지 맵에서이 메시지 처리기를 사용 하 여 예제를 참조 하세요 [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler)합니다.

## <a name="see-also"></a>참고자료

[창 구현](../atl/implementing-a-window.md)<br/>
[메시지 맵](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
