---
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 292a1c6606585dc0694ee678ba8bc9b5fbc42681
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261448"
---
# <a name="notifyhandler"></a>NotifyHandler

메시지 맵에서 NOTIFY_HANDLER 매크로의 세 번째 매개 변수로 식별 된 함수의 이름입니다.

## <a name="syntax"></a>구문

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>매개 변수

*idCtrl*<br/>
메시지를 전송 하는 컨트롤의 식별자입니다.

*pnmh*<br/>
주소는 [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) 알림 코드 및 추가 정보를 포함 하는 구조입니다. 일부 알림 메시지의 경우이 매개 변수가 가리키는 있는 더 큰 구조체는 `NMHDR` 첫 번째 멤버로 구조체입니다.

*bHandled*<br/>
메시지 맵 집합 *bHandled* 하기 전에 true *NotifyHandler* 라고 합니다. 경우 *NotifyHandler* 메시지를 완전히 처리 하지 않는 설정 해야 *bHandled* 에 **FALSE** 를 나타내는 메시지에 추가 처리가 필요 합니다.

## <a name="return-value"></a>반환 값

메시지 처리의 결과입니다. 성공한 경우 0입니다.

## <a name="remarks"></a>설명

메시지 맵에서이 메시지 처리기를 사용 하 여 예제를 참조 하세요 [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>참고자료

[창 구현](../atl/implementing-a-window.md)<br/>
[메시지 맵](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
