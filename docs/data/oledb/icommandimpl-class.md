---
title: ICommandImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ICommandImpl
- ICommandImpl::Cancel
- Cancel
- ICommandImpl.Cancel
- ICommandImpl::CancelExecution
- ATL::ICommandImpl::CancelExecution
- ATL.ICommandImpl.CancelExecution
- CancelExecution
- ICommandImpl.CancelExecution
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
- ICommandImpl::Execute
- ICommandImpl.Execute
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
- ATL.ICommandImpl.ICommandImpl
- ATL::ICommandImpl::ICommandImpl
- ICommandImpl
- ICommandImpl::ICommandImpl
- ICommandImpl.ICommandImpl
- ICommandImpl::m_bCancel
- ICommandImpl.m_bCancel
- m_bCancel
- ATL::ICommandImpl::m_bCancel
- ATL.ICommandImpl.m_bCancel
- ICommandImpl::m_bCancelWhenExecuting
- ICommandImpl.m_bCancelWhenExecuting
- ATL::ICommandImpl::m_bCancelWhenExecuting
- m_bCancelWhenExecuting
- ATL.ICommandImpl.m_bCancelWhenExecuting
- ICommandImpl.m_bIsExecuting
- ATL::ICommandImpl::m_bIsExecuting
- m_bIsExecuting
- ATL.ICommandImpl.m_bIsExecuting
- ICommandImpl::m_bIsExecuting
helpviewer_keywords:
- ICommandImpl class
- Cancel method
- CancelExecution method
- CreateRowset method
- Execute method
- GetDBSession method
- ICommandImpl constructor
- ICommandImpl class, constructor
- m_bCancel
- m_bCancelWhenExecuting
- m_bIsExecuting
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
ms.openlocfilehash: d890b62e4e4aabb9f8ca7ebb9d3051c53febd91f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026794"
---
# <a name="icommandimpl-class"></a>ICommandImpl 클래스

에 대 한 구현을 제공 합니다 [ICommand](/previous-versions/windows/desktop/ms709737(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class CommandBase = ICommand>
class ATL_NO_VTABLE ICommandImpl : public CommandBase
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `ICommandImpl`합니다.

*CommandBase*<br/>
명령 인터페이스입니다. 기본값은 `ICommand`입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[취소](#cancel)|현재 명령 실행을 취소합니다.|
|[CancelExecution](#cancelexecution)|현재 명령 실행을 취소합니다.|
|[CreateRowset](#createrowset)|행 집합 개체를 만듭니다.|
|[Execute](#execute)|명령을 실행합니다.|
|[GetDBSession](#getdbsession)|명령을 만든 세션에 대 한 인터페이스 포인터를 반환 합니다.|
|[ICommandImpl](#icommandimpl)|생성자입니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_bCancel](#bcancel)|명령을 취소할지 여부를 나타냅니다.|
|[m_bCancelWhenExecuting](#bcancelwhenexecuting)|명령을 실행 하는 경우 취소 여부를 나타냅니다.|
|[m_bIsExecuting](#bisexecuting)|명령은 현재 실행 되 고 있는지 여부를 나타냅니다.|

## <a name="remarks"></a>설명

명령 개체에는 필수 인터페이스입니다.

## <a name="cancel"></a> Icommandimpl:: Cancel

현재 명령 실행을 취소합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(Cancel)();
```

### <a name="remarks"></a>설명

참조 [ICommand::Cancel](/previous-versions/windows/desktop/ms714402(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="cancelexecution"></a> Icommandimpl:: Cancelexecution

현재 명령 실행을 취소합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CancelExecution();
```

## <a name="createrowset"></a> ICommandImpl::CreateRowset

호출한 [Execute](../../data/oledb/icommandimpl-execute.md) 단일 행 집합을 만들려고 합니다.

### <a name="syntax"></a>구문

```cpp
template template <class RowsetClass>
HRESULT CreateRowset(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset,
   RowsetClass*& pRowsetObj);
```

#### <a name="parameters"></a>매개 변수

*RowsetClass*<br/>
사용자의 행 집합 클래스를 나타내는 템플릿 클래스 멤버입니다. 일반적으로 마법사에서 생성 됩니다.

*pUnkOuter*<br/>
[in] 제어에 대 한 포인터 `IUnknown` 이 null이 고, 그렇지 않으면 행 집합을 집계의 일부로 만들어지는 경우 인터페이스.

*riid*<br/>
[in] 에 해당 *riid* 에서 `ICommand::Execute`합니다.

*pParams*<br/>
[에서/out] 에 해당 *pParams* 에서 `ICommand::Execute`합니다.

*pcRowsAffected*<br/>
에 해당 *pcRowsAffected* 에서 `ICommand::Execute`합니다.

*ppRowset*<br/>
[에서/out] 에 해당 *ppRowset* 에서 `ICommand::Execute`합니다.

*pRowsetObj*<br/>
[out] 행 집합 개체에 대 한 포인터입니다. 일반적으로이 매개 변수는 사용 되지 않지만 COM 개체를 전달 하기 전에 행 집합에서 더 많은 작업을 수행 해야 하는 경우 사용할 수 있습니다. 수명을 *pRowsetObj* 바인딩된 *ppRowset*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다. 참조 `ICommand::Execute` 일반적인 값의 목록에 대 한 합니다.

### <a name="remarks"></a>설명

둘 이상의 행 집합을 만들고, 다른 행 집합 만들기에 대 한 사용자 고유의 조건을 제공 하는 다양 한 호출을 배치 `CreateRowset` 내에서 `Execute`합니다.

참조 [icommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) 에 *OLE DB 프로그래머 참조입니다.*

## <a name="execute"></a> Icommandimpl:: Execute

명령을 실행합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Execute(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset);
```

#### <a name="parameters"></a>매개 변수

참조 [icommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

요청 하는 송신 인터페이스에는이 함수에서 만들어지는 행 집합 개체에서 가져온 인터페이스가 됩니다.

`Execute` 호출 [CreateRowset](../../data/oledb/icommandimpl-createrowset.md)합니다. 서로 다른 행 집합을 만들기 위한 사용자 고유의 조건을 제공 하거나 둘 이상의 행 집합을 만들려면 기본 구현을 재정의 합니다.

## <a name="getdbsession"></a> ICommandImpl::GetDBSession

명령을 만든 세션에 대 한 인터페이스 포인터를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetDBSession) (REFIID riid,
   IUnknown** ppSession);
```

#### <a name="parameters"></a>매개 변수

참조 [ICommand::GetDBSession](/previous-versions/windows/desktop/ms719622(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

세션에서 속성을 검색 하는 데 유용 합니다.

## <a name="icommandimpl"></a> Icommandimpl:: Icommandimpl

생성자입니다.

### <a name="syntax"></a>구문

```cpp
ICommandImpl();
```

## <a name="bcancel"></a> Icommandimpl:: M_bcancel

명령이 취소 되 고 있는지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
unsigned m_bCancel:1;
```

### <a name="remarks"></a>설명

이 변수를 검색할 수 있습니다는 `Execute` 명령 클래스 및 적절 하 게 취소 메서드.

## <a name="bcancelwhenexecuting"></a> Icommandimpl:: M_bcancelwhenexecuting

실행 하는 경우 명령을 취소할 수 있는지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
unsigned m_bCancelWhenExecuting:1;
```

### <a name="remarks"></a>설명

기본값으로 **true** (취소할 수 있습니다).

## <a name="bisexecuting"></a> Icommandimpl:: M_bisexecuting

명령은 현재 실행 되 고 있는지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
unsigned m_bIsExecuting:1;
```

### <a name="remarks"></a>설명

합니다 `Execute` 명령 클래스의 메서드이 변수를 설정할 수 있습니다 **true**합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)