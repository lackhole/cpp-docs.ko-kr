---
title: IRowsetNotifyImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
ms.openlocfilehash: 552fcdcee99f1bfe78a28c6ea41a89557f1682f4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026070"
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl 클래스

구현 및 등록 [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85)) 소비자 (라고도 "sink")에 알림을 처리할 수 있도록 합니다.

## <a name="syntax"></a>구문

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[OnFieldChange](#onfieldchange)|열의 값을 변경한의 소비자를 게 알립니다.|
|[OnRowChange](#onrowchange)|첫 번째 행을 변경 또는 전체 행에 영향을 주는 변경 소비자를 게 알립니다.|
|[OnRowsetChange](#onrowsetchange)|전체 행 집합에 영향을 미치는 변경의 소비자를 게 알립니다.|

## <a name="remarks"></a>설명

참조 [알림 수신](../../data/oledb/receiving-notifications.md) 에서 소비자 연결 지점 인터페이스를 구현 하는 방법에 대 한 합니다.

`IRowsetNotifyImpl` 더미 구현을 제공 `IRowsetNotify`에 대 한 빈 함수를 사용 하 여 합니다 `IRowsetNotify` 메서드 [OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85))에 [OnRowChange](/previous-versions/windows/desktop/ms722694(v=vs.85)), 및 [OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)). 구현 하는 경우이 클래스에서 상속 하는 경우는 `IRowsetNotify` 인터페이스를 해야 하는 방법만 구현할 수 있습니다. 다른 방법에 대 한 빈 구현을 직접 제공 해야 합니다.

## <a name="onfieldchange"></a> IRowsetNotifyImpl::OnFieldChange

열의 값을 변경한의 소비자를 게 알립니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(OnFieldChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ HROW /* hRow */,
/* [in] */ DBORDINAL /* cColumns */,
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>매개 변수

참조 [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 매개 변수 설명에 대 한 합니다.

### <a name="return-value"></a>반환 값

참조 [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 에 대 한 설명 값을 반환 합니다.

### <a name="remarks"></a>설명

이 메서드를 래핑하는 [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961(v=vs.85)) 메서드. 자세한 내용은 OLE DB 프로그래머 참조에서 해당 메서드의 설명을 참조하십시오.

## <a name="onrowchange"></a> IRowsetNotifyImpl::OnRowChange

첫 번째 행을 변경 또는 전체 행에 영향을 주는 변경 소비자를 게 알립니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(OnRowChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBCOUNTITEM /* cRows */,
/* [size_is][in] */ const HROW /* rghRows*/ [] ,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>매개 변수

참조 [irowsetnotify:: Onrowchange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 매개 변수 설명에 대 한 합니다.

### <a name="return-value"></a>반환 값

참조 [irowsetnotify:: Onrowchange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 에 대 한 설명 값을 반환 합니다.

### <a name="remarks"></a>설명

이 메서드를 래핑하는 [irowsetnotify:: Onrowchange](/previous-versions/windows/desktop/ms722694(v=vs.85)) 메서드. 자세한 내용은 OLE DB 프로그래머 참조에서 해당 메서드의 설명을 참조하십시오.

## <a name="onrowsetchange"></a> IRowsetNotifyImpl::OnRowsetChange

전체 행 집합에 영향을 미치는 변경의 소비자를 게 알립니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(OnRowsetChange)(
/* [in] */ IRowset* /* pRowset */,
/* [in] */ DBREASON /* eReason */,
/* [in] */ DBEVENTPHASE /* ePhase */,
/* [in] */ BOOL /* fCantDeny */)
```

#### <a name="parameters"></a>매개 변수

참조 [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 매개 변수 설명에 대 한 합니다.

### <a name="return-value"></a>반환 값

참조 [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 에 대 한 설명 값을 반환 합니다.

### <a name="remarks"></a>설명

이 메서드를 래핑하는 [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669(v=vs.85)) 메서드. 자세한 내용은 OLE DB 프로그래머 참조에서 해당 메서드의 설명을 참조하십시오.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))
[IRowsetNotifyCP 클래스](../../data/oledb/irowsetnotifycp-class.md)