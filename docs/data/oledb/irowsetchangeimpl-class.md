---
title: IRowsetChangeImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
- SetData
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
ms.openlocfilehash: 8b2a92fdefd965d4b87e0a9ed411cc1b5c89b8f9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036801"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl 클래스

OLE DB 템플릿 구현의 합니다 [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) OLE DB 사양에 대 한 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <
   class T,
   class Storage,
   class BaseInterface = IRowsetChange,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface
```

### <a name="parameters"></a>매개 변수

*T*<br/>
파생 된 클래스 `IRowsetChangeImpl`합니다.

*저장소*<br/>
사용자 레코드입니다.

*BaseInterface*<br/>
와 같은 인터페이스에 대 한 기본 클래스 `IRowsetChange`합니다.

*RowClass*<br/>
행 핸들에 대 한 저장소 단위입니다.

*MapClass*<br/>
공급자가 보유 하는 모든 행 핸들에 대 한 저장소 단위입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods-used-with-irowsetchange"></a>인터페이스 메서드 (IRowsetChange와 함께 사용)

|||
|-|-|
|[DeleteRows](#deleterows)|행 집합에서 행을 삭제합니다.|
|[InsertRow](#insertrow)|행 집합에 행을 삽입 합니다.|
|[SetData](#setdata)|하나 이상의 열에 데이터 값을 설정 합니다.|

### <a name="implementation-method-callback"></a>구현 메서드 (콜백)

|||
|-|-|
|[FlushData](#flushdata)|데이터 저장소에 커밋하는 공급자가 재정의 합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 데이터 저장소에 즉시 쓰기 작업을 담당 합니다. "즉시"을 의미 하며 최종 사용자 (소비자를 사용 하 여 person) 변경 하면 해당 변경 내용을 즉시 전송 데이터 저장과 실행 취소할 수 없습니다.

`IRowsetChangeImpl` OLE DB 구현 `IRowsetChange` 행을 삭제 하 고 새 행을 삽입의 기존 행의 열 값으로 업데이트할 수 있도록 하는 인터페이스입니다.

OLE DB 템플릿 구현에서는 모든 기본 메서드를 지원 (`SetData`하십시오 `InsertRow`, 및 `DeleteRows`).

> [!IMPORTANT]
>  공급자를 구현 하기 전에 다음 설명서를 참조 하는 것이 좋습니다.

- [업데이트 가능 공급자 만들기](../../data/oledb/creating-an-updatable-provider.md)

- 6 장은 *OLE DB 프로그래머 참조*

- 참조 하는 방법을 `RUpdateRowset` 클래스에서 사용 됩니다 합니다 [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) 샘플.

## <a name="deleterows"></a> IRowsetChangeImpl::DeleteRows

행 집합에서 행을 삭제합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>매개 변수

참조 [irowsetchange:: Deleterows](/previous-versions/windows/desktop/ms724362(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="insertrow"></a> IRowsetChangeImpl::InsertRow

만들고 행 집합에 새 행을 초기화 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>매개 변수

참조 [irowsetchange:: Insertrow](/previous-versions/windows/desktop/ms716921(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="setdata"></a> IRowsetChangeImpl::SetData

하나 이상의 열에 데이터 값을 설정 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>매개 변수

참조 [irowsetchange:: Setdata](/previous-versions/windows/desktop/ms721232(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="flushdata"></a> IRowsetChangeImpl::FlushData

데이터 저장소에 커밋하는 공급자가 재정의 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>매개 변수

*hRowToFlush*<br/>
[in] 데이터에 대 한 행에 대 한 핸들입니다. 이 행의 형식에서 결정 됩니다 합니다 *RowClass* 템플릿 인수는 `IRowsetImpl` 클래스 (`CSimpleRow` 기본적으로).

*hAccessorToFlush*<br/>
[in] 바인딩 정보 및 형식 정보를 포함 하는 접근자에 대 한 핸들 해당 `PROVIDER_MAP` (참조 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)