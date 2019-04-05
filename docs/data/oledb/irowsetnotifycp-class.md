---
title: IRowsetNotifyCP 클래스
ms.date: 11/04/2016
f1_keywords:
- IRowsetNotifyCP
- Fire_OnFieldChange
- ATL::IRowsetNotifyCP::Fire_OnFieldChange
- ATL.IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP::Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
ms.openlocfilehash: a3ab63206ce7ac53ff996ecf1bb64bdaa0b79fcb
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031688"
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP 클래스

연결 지점 인터페이스에 대 한 공급자 사이트 구현 [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))합니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>
class IRowsetNotifyCP :
   public IConnectionPointImpl<
      T,
      piid = &__uuidof(IRowsetNotify),
      CComDynamicUnkArray DynamicUnkArray>,
   public ReentrantEventSync
```

### <a name="parameters"></a>매개 변수

*T*<br/>
파생 된 클래스 `IRowsetNotifyCP`합니다.

*ReentrantEventSync*<br/>
재입력을 지 원하는 mutex 클래스 (기본값은 `CComSharedMutex`). 뮤텍스는 리소스에 한 스레드가 상호 배타적 액세스를 허용 하는 동기화 개체입니다.

*piid*<br/>
인터페이스 ID 포인터 (`IID*`)에 대 한는 `IRowsetNotify` 연결 지점 인터페이스입니다. 기본값은 `&__uuidof(IRowsetNotify)`입니다.

*DynamicUnkArray*<br/>
형식의 배열을 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), 동적으로 할당 된 배열을 `IUnknown` 클라이언트에 대 한 포인터 싱크 인터페이스.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[Fire_OnFieldChange](#onfieldchange)|열의 값이 변경의 소비자를 게 알립니다.|
|[Fire_OnRowChange](#onrowchange)|행에 영향을 미치는 변경의 소비자를 게 알립니다.|
|[Fire_OnRowsetChange](#onrowsetchange)|전체 행 집합에 영향을 미치는 변경의 소비자를 게 알립니다.|

## <a name="remarks"></a>설명

`IRowsetNotifyCP` 구현 브로드캐스트 수신기 연결 지점에 advise 할 함수 `IID_IRowsetNotify` 행 집합의 내용 변경 합니다.

또한 구현 및 등록 해야 하는 참고 `IRowsetNotify` 를 사용 하 여 소비자 (라고도 "sink")에 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) 소비자 알림을 처리할 수 있도록 합니다. 참조 [알림 수신](../../data/oledb/receiving-notifications.md) 에서 소비자 연결 지점 인터페이스를 구현 하는 방법에 대 한 합니다.

알림을 구현에 대 한 자세한 내용은 "지원 알림"를 참조 하세요 [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)합니다.

## <a name="onfieldchange"></a> IRowsetNotifyCP::Fire_OnFieldChange

브로드캐스트는 [OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 열의 값이 변경의 소비자에 게 알리는 이벤트를 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Fire_OnFieldChange(IRowset* pRowset,
   HROW hRow,
   DBORDINAL cColumns,
   DBORDINAL* rgColumns,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>매개 변수

참조 [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="onrowchange"></a> IRowsetNotifyCP::Fire_OnRowChange

브로드캐스트는 [OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 연결 지점에 대해 모든 수신기에 이벤트 `IID_IRowsetNotify` 행에 영향을 미치는 변경의 소비자에 게 알립니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>매개 변수

참조 [irowsetnotify:: Onrowchange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="onrowsetchange"></a> IRowsetNotifyCP::Fire_OnRowsetChange

브로드캐스트는 [OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 연결 지점에 대해 모든 수신기에 이벤트 `IID_IRowsetNotify` 전체 행 집합에 영향을 미치는 변경의 소비자에 게 알립니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,
   DBREASON eReason,
   DBEVENTPHASE ePhase,
   BOOL fCantDeny);
```

#### <a name="parameters"></a>매개 변수

참조 [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[알림 (COM)](/windows/desktop/com/notifications)<br/>
[BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)<br/>
[END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)<br/>
[CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)<br/>
[업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)