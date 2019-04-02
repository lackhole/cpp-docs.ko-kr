---
title: CSession 클래스
ms.date: 11/04/2016
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
- CSession::StartTransaction
- StartTransaction
- ATL.CSession.StartTransaction
- CSession.StartTransaction
- ATL::CSession::StartTransaction
helpviewer_keywords:
- CSession class
- Abort method
- Close method
- Commit method
- GetTransactionInfo method
- Open method
- StartTransaction method
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
ms.openlocfilehash: c4f6cc19897b66bfe26c6d53ccb87c35dbed82c9
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777651"
---
# <a name="csession-class"></a>CSession 클래스

단일 데이터베이스 액세스 세션을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class CSession
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[Abort](#abort)|취소 (종료) 트랜잭션.|
|[닫기](#close)|세션을 닫습니다.|
|[커밋](#commit)|트랜잭션을 커밋합니다.|
|[GetTransactionInfo](#gettransactioninfo)|트랜잭션에 대 한 정보를 반환합니다.|
|[열기](#open)|데이터 원본 개체에 대 한 새 세션을 엽니다.|
|[StartTransaction](#starttransaction)|이 세션에 대 한 새 트랜잭션을 시작합니다.|

## <a name="remarks"></a>설명

하나 이상의 세션으로 표현 되는 각 공급자 연결 (데이터 원본)를 사용 하 여 연결할 수는 [CDataSource](../../data/oledb/cdatasource-class.md) 개체입니다. 새로 만들 `CSession` 에 대 한는 `CDataSource`를 호출 [csession:: Open](../../data/oledb/csession-open.md)합니다. 데이터베이스 트랜잭션을 시작 하기 `CSession` 제공 된 `StartTransaction` 메서드. 트랜잭션이 시작 되 면 사용 하 여 커밋할 수 있습니다 합니다 `Commit` 메서드를 사용 하 여 취소 또는 `Abort` 메서드.

## <a name="abort"></a> CSession::Abort

트랜잭션을 종료합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Abort(BOID* pboidReason = NULL,
   BOOL bRetaining = FALSE,
   BOOL bAsync = FALSE) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [itransaction:: Abort](/previous-versions/windows/desktop/ms709833(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="close"></a> CSession::Close

열려 있는 세션을 닫습니다 [csession:: Open](../../data/oledb/csession-open.md)합니다.

### <a name="syntax"></a>구문

```cpp
void Close() throw();
```

### <a name="remarks"></a>설명

릴리스는 `m_spOpenRowset` 포인터입니다.

## <a name="commit"></a> CSession::Commit

트랜잭션을 커밋합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Commit(BOOL bRetaining = FALSE,
   DWORD grfTC = XACTTC_SYNC,
   DWORD grfRM = 0) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [itransaction:: Commit](/previous-versions/windows/desktop/ms713008(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

자세한 내용은 [itransaction:: Commit](/previous-versions/windows/desktop/ms713008(v=vs.85))합니다.

## <a name="gettransactioninfo"></a> CSession::GetTransactionInfo

트랜잭션에 대 한 정보를 반환합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [ITransaction::GetTransactionInfo](/previous-versions/windows/desktop/ms714975(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

자세한 내용은 [ITransaction::GetTransactionInfo](/previous-versions/windows/desktop/ms714975(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="open"></a> CSession::Open

데이터 원본 개체에 대 한 새 세션을 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Open(const CDataSource& ds,
   DBPROPSET *pPropSet = NULL,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>매개 변수

*ds*<br/>
[in] 데이터 소스 세션을 열 수입니다.

*pPropSet*<br/>
[in] 배열에 대 한 포인터 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 속성 및 값을 설정할 수를 포함 하는 구조체. 참조 [속성 집합 및 속성 그룹](/previous-versions/windows/desktop/ms713696(v=vs.85)) 에 *OLE DB Programmer's Reference* Windows SDK에에서 있습니다.

*ulPropSets*<br/>
[in] 수가 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 구조에 전달 합니다 *pPropSet* 인수입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

사용 하 여 데이터 원본 개체를 열어야 [cdatasource:: Open](../../data/oledb/cdatasource-open.md) 전달 하기 전에 `CSession::Open`입니다.

## <a name="starttransaction"></a> CSession::StartTransaction

이 세션에 대 한 새 트랜잭션을 시작합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT StartTransaction(ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,
   ULONG isoFlags = 0,
   ITransactionOptions* pOtherOptions = NULL,
   ULONG* pulTransactionLevel = NULL) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [itransactionlocal:: Starttransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

자세한 내용은 [itransactionlocal:: Starttransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="see-also"></a>참고 항목

[CatDB](../../overview/visual-cpp-samples.md)<br/>
[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)