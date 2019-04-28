---
title: 이중 인터페이스 및 이벤트
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 01233edb63145d69d335349bb9dff91e6a4aca5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198267"
---
# <a name="dual-interfaces-and-events"></a>이중 인터페이스 및 이벤트

이중 이벤트 인터페이스를 디자인할 수 있지만, 여러 가지 좋은 디자인 이유로 이렇게 필요가 있습니다. 기본 원인은 이벤트의 원본 또는 vtable을 통해 이벤트를 발생만 됩니다 `Invoke`하나만 있습니다. 이벤트 소스를 직접 vtable 메서드 호출으로 이벤트를 실행 하는 경우는 `IDispatch` 메서드를 사용 하지 않을 인터페이스 해야 셨 기를 순수 vtable 인터페이스를 명확 합니다. 이벤트 소스에 대 한 호출으로 이벤트를 발생 하는 경우 `Invoke`, vtable 메서드를 사용 하지 않을 이며 인터페이스 해야 되었는지는 dispinterface의 선택을 취소 합니다. 이중 이벤트 인터페이스를 정의 하는 경우 일부 기본값이 사용 되지 것입니다 하는 인터페이스를 구현 하는 클라이언트 요구 됩니다.

> [!NOTE]
>  이 인수에서 일반적으로 이중 인터페이스에 적용 되지 않습니다. 구현 측면에서 볼 때 이중 빠르고 편리 하 고 잘 지원 되는 다양 한 범위의 클라이언트에 액세스할 수 있는 인터페이스를 구현할 수는 있습니다.

이중 이벤트 인터페이스를 방지 하는 이유 추가 됩니다. Visual Basic 아니고 Internet Explorer 지원 합니다.

## <a name="see-also"></a>참고자료

[이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)
