---
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 99a95228f6036e5f391395be367cdef39ca3dc3b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492463"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler`는 메시지 맵에 있는 COMMAND_HANDLER 매크로의 세 번째 매개 변수로 식별 되는 함수입니다.

## <a name="syntax"></a>구문

```cpp
LRESULT CommandHandler(
    WORD wNotifyCode,
    WORD wID,
    HWND hWndCtl,
    BOOL& bHandled);
```

#### <a name="parameters"></a>매개 변수

*wNotifyCode*<br/>
알림 코드입니다.

*wID*<br/>
메뉴 항목, 컨트롤 또는 액셀러레이터 키의 식별자입니다.

*hWndCtl*<br/>
창 컨트롤에 대 한 핸들입니다.

*bHandled*<br/>
메시지 맵은가 호출 되기 전에 `CommandHandler` *bhandled* 를 TRUE로 설정 합니다. 에서 `CommandHandler` 메시지를 완전히 처리 하지 않는 경우에는 메시지에 추가 처리가 필요 함을 나타내려면 *bhandled* 를 FALSE로 설정 해야 합니다.

## <a name="return-value"></a>반환 값

메시지 처리의 결과입니다. 성공 하는 경우 0입니다.

## <a name="remarks"></a>설명

메시지 맵에서이 메시지 처리기를 사용 하는 방법에 대 한 예제는 [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler)를 참조 하세요.

## <a name="see-also"></a>참고자료

[창 구현](../atl/implementing-a-window.md)<br/>
[메시지 맵](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
