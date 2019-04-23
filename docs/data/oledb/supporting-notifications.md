---
title: 알림 지원
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
ms.openlocfilehash: 52c4313de5017b97a193be1afebc020c9896fe6a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035652"
---
# <a name="supporting-notifications"></a>알림 지원

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>공급자 및 소비자 연결 지점 인터페이스를 구현합니다.

알림을 구현 하는 공급자 클래스에서 상속 해야 합니다 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) 하 고 [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md)합니다.

`IRowsetNotifyCP` 연결 지점 인터페이스에 대 한 공급자 사이트 구현 [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))합니다. `IRowsetNotifyCP` 구현 브로드캐스트 수신기 연결 지점에 advise 할 함수 `IID_IRowsetNotify` 행 집합의 내용 변경 합니다.

또한 구현 하 고 등록 해야 합니다 `IRowsetNotify` 를 사용 하 여 소비자 (싱크 라고도 함)에 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 소비자 알림을 처리할 수 있도록 합니다. 소비자의 연결 지점 인터페이스를 구현 하는 방법에 대 한 내용은 [알림 수신](../../data/oledb/receiving-notifications.md)합니다.

또한 클래스에 다음과 같은 연결 지점 항목을 정의 하는 맵이 있어야 합니다.

```cpp
BEGIN_CONNECTION_POINT_MAP
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)
END_CONNECTION_POINT_MAP
```

## <a name="adding-irowsetnotify"></a>IRowsetNotify 추가

추가할 `IRowsetNotify`를 추가 해야 `IConnectionPointContainerImpl<rowset-name>` 및 `IRowsetNotifyCP<rowset-name>` 상속 체인에 하 합니다.

예를 들어의 상속 체인을 같습니다 `RUpdateRowset` 에 [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV):

> [!NOTE]
> 샘플 코드입니다; 여기에 표시 된 것과 다를 수 있습니다. 샘플 코드를 좀 더 최신 버전으로 간주 해야 합니다.

```cpp
///////////////////////////////////////////////////////////////////////////
// class RUpdateRowset (in rowset.h)

class RUpdateRowset :
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,
         CAtlArray< CAgentMan, CAtlArray<CAgentMan>>, CSimpleRow,
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll >>,
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,
      public IConnectionPointContainerImpl<RUpdateRowset>,
      public IRowsetNotifyCP<RUpdateRowset>
```

### <a name="setting-com-map-entries"></a>COM 맵 엔트리를 설정합니다.

다음 행의 COM 맵에 추가 해야 합니다.

```cpp
COM_INTERFACE_ENTRY(IConnectionPointContainer)
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)
```

이러한 매크로 호출 하는 모든 허용 `QueryInterface` 연결 지점 컨테이너에 대 한 (의 기본 `IRowsetNotify`) 공급자에 요청된 된 인터페이스를 찾으려고 합니다. 연결점을 사용 하는 방법의 예로, ATL 다각형 샘플 및 자습서를 참조 하세요.

### <a name="setting-connection-point-map-entries"></a>연결 지점 맵 엔트리를 설정합니다.

연결 지점 지도 추가 해야 합니다. 와 같이 표시 됩니다.

```cpp
BEGIN_CONNECTION_POINT_MAP(rowset-name)
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))
END_CONNECTION_POINT_MAP()
```

이 연결 지점 맵은 허용에 대 한 원하는 구성 요소는 `IRowsetNotify` 공급자에 대 한 인터페이스입니다.

### <a name="setting-properties"></a>속성 설정

공급자에 다음 속성을 추가 해야 합니다. 사용자가 지 원하는 인터페이스를 기반으로 하는 속성을 추가 해야 합니다.

|속성|지원할 경우 추가|
|--------------|------------------------|
|DBPROP_IConnectionPointContainer|항상|
|DBPROP_NOTIFICATIONGRANULARITY|항상|
|DBPROP_NOTIFICATIONPHASES|항상|
|DBPROP_NOTIFYCOLUMNSET|`IRowsetChange`|
|DBPROP_NOTIFYROWDELETE|`IRowsetChange`|
|DBPROP_NOTIFYROWINSERT|`IRowsetChange`|
|DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE|항상|
|DBPROP_NOTIFYROWFIRSTCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWSETRELEASE|항상|
|DBPROP_NOTIFYROWUNDOCHANGE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDODELETE|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUNDOINSERT|`IRowsetUpdate`|
|DBPROP_NOTIFYROWUPDATE|`IRowsetUpdate`|

OLE DB 공급자 템플릿 알림 구현의 대부분 포함 되어 있습니다. 추가 하지 않으면 `IRowsetNotifyCP` 상속 체인에에 컴파일러 하므로 코드 크기의 작은 하 여 컴파일 스트림에서 모든 코드를 제거 합니다.

## <a name="see-also"></a>참고자료

[고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)