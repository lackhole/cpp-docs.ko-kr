---
title: 알림 수신
ms.date: 10/24/2018
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
ms.openlocfilehash: b35c1d3d6ff7d5d74493e843575f7448c4df8d8f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283829"
---
# <a name="receiving-notifications"></a>알림 수신

OLE DB는 이벤트가 발생할 경우 알림을 수신하기 위한 인터페이스를 제공합니다. 자세한 내용은 **OLE DB Programmer's Reference**에서 [OLE DB Object Notifications](/previous-versions/windows/desktop/ms725406(v=vs.85))을 참조하십시오. 이러한 이벤트의 설정은 표준 COM 연결 포인트 메커니즘을 사용합니다. 예를 들어, `IRowsetNotify`를 통해 이벤트를 검색하는 ATL 개체는 클래스 파생 목록에 `IRowsetNotify`를 추가하고 `COM_INTERFACE_ENTRY` 매크로를 통해 이를 노출하여 `IRowsetNotify` 인터페이스를 구현합니다.

`IRowsetNotify`에는 세 가지 메서드가 있으며, 이들은 다양한 경우에 호출될 수 있습니다. 이들 메서드 중 하나에만 응답하려는 경우, 응답하지 않을 메서드에 대해 `E_NOTIMPL`을 반환하는 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 클래스를 사용할 수 있습니다.

행 집합을 만들 경우, 알림 설정에 필요한 `IConnectionPointContainer`를 지원하는 반환된 행 집합 개체가 필요하다는 점을 공급자에게 알려야 합니다.

다음 코드에서는 ATL 개체에서 행 집합을 열고 `AtlAdvise` 함수를 사용하여 알림 싱크를 설정하는 방법을 보여 줍니다. `AtlAdvise`는 `AtlUnadvise`를 호출할 때 사용되는 쿠키를 반환합니다.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

그런 후 다음 코드에서 사용됩니다.

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)