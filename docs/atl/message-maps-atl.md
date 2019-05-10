---
title: 메시지 맵 (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
ms.openlocfilehash: 1b8b3fcb2f10f975ebdf68a285c7d5e364b9e1b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250134"
---
# <a name="message-maps-atl"></a>메시지 맵 (ATL)

메시지 맵에서 특정 메시지, 명령 또는 알림 처리기 함수를 연결합니다. ATL의를 사용 하 여 [메시지 맵 매크로](../atl/reference/message-map-macros-atl.md), 창에 대 한 메시지 맵을 지정할 수 있습니다. 창 절차 `CWindowImpl`, `CDialogImpl`, 및 `CContainedWindowT` 창의 메시지를 메시지 맵에 직접.

합니다 [메시지 처리기 함수](../atl/message-handler-functions.md) 형식의 추가 인수를 수락 `BOOL&`합니다. 이 인수는 처리 된 메시지 및 기본적으로 TRUE로 설정 되어 있는지 여부를 나타냅니다. 처리기 함수를 FALSE로 메시지를 처리 하지 않았음을 나타내는 인수를 설정할 수 있습니다. 이 경우 ATL 계속 메시지 맵에 추가 처리기 함수를 찾습니다. 이 인수를 FALSE로 설정 하면 먼저 메시지에 대 한 응답으로 일부 작업을 수행할 수 있으며 끼운 기본 처리 또는 다른 처리기 함수는 메시지의 처리를 완료할 수 있습니다.

## <a name="chained-message-maps"></a>연결 된 메시지 맵

ATL도 할 수 있습니다 체인 메시지 맵은 다른 클래스에 정의 된 메시지 맵을 처리 메시지를 보냅니다. 예를 들어, 해당 클래스에 연결 하는 모든 windows에 대 한 균일 한 동작을 제공 하도록 일반 메시지를 별도 클래스 처리를 구현할 수 있습니다. 기본 클래스 또는 클래스의 데이터 멤버에 연결할 수 있습니다.

ATL 지원 동적 체인는 연결할 수 있도록 다른 개체의 메시지 맵에 런타임에 합니다. 동적 연결을 구현 하려면 클래스에서 파생 시켜야 [CDynamicChain](../atl/reference/cdynamicchain-class.md)합니다. 다음을 선언 합니다 [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) 메시지 맵에서 매크로입니다. CHAIN_MSG_MAP_DYNAMIC 개체와 연결 된 메시지 맵이 식별 하는 고유 번호를 필요 합니다. 호출을 통해이 고유한 값을 정의 해야 `CDynamicChain::SetChainEntry`합니다.

클래스에서 파생 제공 메시지 맵이 선언 하는 모든 클래스에 연결할 수 있습니다 [CMessageMap](../atl/reference/cmessagemap-class.md)합니다. `CMessageMap` 개체가 다른 개체에는 메시지 맵을 노출할 수 있습니다. 사실은 `CWindowImpl` 에서 이미 파생 `CMessageMap`합니다.

## <a name="alternate-message-maps"></a>대체 메시지 맵

마지막으로, ATL 지원 대체 메시지 maps를 사용 하 여 선언 된 [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) 매크로입니다. 각 대체 메시지 맵에 ALT_MSG_MAP에 전달 하는 고유 번호로 식별 됩니다. 대체 메시지를 사용 하 여 맵, 맵 하나에서 여러 windows 메시지를 처리할 수 있습니다. 기본적으로 사실은 `CWindowImpl` 대체 메시지 맵을 사용 하지 않습니다. 재정의이 지원을 추가 하려면 합니다 `WindowProc` 에서 메서드 하 `CWindowImpl`-파생 클래스 및 호출 `ProcessWindowMessage` 메시지 맵 식별자를 사용 하 여 합니다.

## <a name="see-also"></a>참고자료

[창 구현](../atl/implementing-a-window.md)
