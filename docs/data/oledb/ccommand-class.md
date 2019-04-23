---
title: CCommand 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::CCommand
- CCommand
- ATL.CCommand
- CCommand.Close
- CCommand::Close
- CCommand.Create
- CCommand::Create
- CCommand.CreateCommand
- CreateCommand
- CCommand::CreateCommand
- ATL::CCommand::GetNextResult
- CCommand::GetNextResult
- GetNextResult
- CCommand.GetNextResult
- ATL.CCommand.GetNextResult
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
- ATL.CCommand.Open
- ATL::CCommand::Open
- CCommand.Open
- CCommand::Open
- CCommand.Prepare
- CCommand::Prepare
- Prepare
- CCommand.ReleaseCommand
- ReleaseCommand
- CCommand::ReleaseCommand
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
helpviewer_keywords:
- CCommand class
- Close method
- Create method [C++]
- CreateCommand method
- GetNextResult method
- GetParameterInfo method
- Open method
- Prepare method
- ReleaseCommand method
- SetParameterInfo method
- Unprepare method
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
ms.openlocfilehash: 406a78ff1958d565fcc74781f6a63d4784f48bfc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039730"
---
# <a name="ccommand-class"></a>CCommand 클래스

설정 하 고 명령을 실행 하는 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CNoAccessor,
   template <typename T> class TRowset = CRowset,
   class TMultiple = CNoMultipleResults>
class CCommand :
   public CAccessorRowset <TAccessor, TRowset>,
   public CCommandBase,
   public TMultiple
```

### <a name="parameters"></a>매개 변수

*TAccessor*<br/>
접근자 클래스의 형식 (같은 `CDynamicParameterAccessor`, `CDynamicStringAccessor`, 또는 `CEnumeratorAccessor`) 명령에서 사용 되도록 합니다. 기본값은 `CNoAccessor`, 또는 지정 하는 클래스 없습니다 매개 변수를 지원 열을 출력 합니다.

*TRowset*<br/>
행 집합 클래스의 형식 (같은 `CArrayRowset` 또는 `CNoRowset`) 명령에서 사용 되도록 합니다. 기본값은 `CRowset`입니다.

*TMultiple*<br/>
여러 결과 반환할 수 있는 OLE DB 명령을 사용 하 여, 지정 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)합니다. 사용이 고, 그렇지 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)합니다. 자세한 내용은 참조 하세요 [IMultipleResults](/previous-versions/windows/desktop/ms721289(v=vs.85))합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[닫기](#close)|현재 명령을 닫습니다.|
|[GetNextResult](#getnextresult)|여러 결과 사용 하 여 설정 하는 경우에 다음 결과 인출 합니다.|
|[열기](#open)|실행 하 고 필요에 따라 명령에 바인딩합니다.|

### <a name="inherited-methods"></a>상속 된 메서드

|||
|-|-|
|[만들기](#create)|지정된 된 세션에 대 한 새 명령을 만들고 명령 텍스트를 설정 합니다.|
|[CreateCommand](#createcommand)|새 명령을 만듭니다.|
|[GetParameterInfo](#getparameterinfo)|명령의 매개 변수, 이름 및 개체 유형의 목록을 가져옵니다.|
|[준비](#prepare)|유효성을 검사 하 고 현재 명령을 최적화 합니다.|
|[ReleaseCommand](#releasecommand)|필요한 경우 매개 변수 접근자를 해제 한 다음 명령을 해제 합니다.|
|[SetParameterInfo](#setparameterinfo)|네이티브 형식의 각 명령 매개 변수를 지정합니다.|
|[Unprepare](#unprepare)|현재 명령 실행 계획을 삭제 합니다.|

## <a name="remarks"></a>설명

매개 변수 기반 작업을 수행 하거나 명령을 실행 해야 할 때이 클래스를 사용 합니다. 단순 행 집합을 단순히 필요한 경우 사용 하 여 [CTable](../../data/oledb/ctable-class.md) 대신 합니다.

사용 중인 접근자 클래스에는 매개 변수 및 데이터를 바인딩하는 방법을 결정 합니다.

사용 하는 수 없습니다. 저장된 프로시저 OLE DB provider for Jet 해당 공급자를 지원 하지 않으므로 저장 프로시저 (상수만 쿼리 문자열에 허용 됨).

## <a name="close"></a> Ccommand:: Close

명령과 연결 된 행 집합 접근자를 해제 합니다.

### <a name="syntax"></a>구문

```cpp
void Close();
```

### <a name="remarks"></a>설명

명령에는 행 집합, 결과 집합 접근자 및 (선택 사항) (테이블과 달리, 매개 변수를 지원 하지 않는 매개 변수 접근자를 하지 않아도 되며) 매개 변수 접근자를 사용 합니다.

둘 다 호출 해야 명령을 실행할 때 `Close` 하 고 [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) 명령 뒤 합니다.

반복적으로 동일한 명령을 실행 하려는 경우 각 결과 집합 접근자를 호출 하 여 릴리스해야 `Close` 호출 하기 전에 `Execute`입니다. 계열의 끝에서 호출 하 여 매개 변수 접근자를 해제 해야 `ReleaseCommand`합니다. 출력 매개 변수가 있는 저장된 프로시저를 호출 하는 또 다른 일반적인 시나리오입니다. 여러 공급자 (예: SQL Server 용 OLE DB 공급자)에서 출력 매개 변수 값은 액세스할 수 없습니다 결과 set 접근자를 닫을 때까지. 호출 `Close` 반환된 된 행 집합 및 결과 집합 접근자는 포함 하지만 하지 매개 변수 접근자를 닫으려면 있으므로 출력 매개 변수 값을 검색할 수 있습니다.

### <a name="example"></a>예제

다음 예제에서는 호출 하는 방법을 보여 줍니다 `Close` 및 `ReleaseCommand` 실행 하면 동일한 명령을 반복 합니다.

[!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]

## <a name="getnextresult"></a> CCommand::GetNextResult

다음 결과 집합 사용 가능한 경우 인출 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetNextResult(DBROWCOUNT* pulRowsAffected,
   bool bBind = true) throw();
```

#### <a name="parameters"></a>매개 변수

*pulRowsAffected*<br/>
[에서/out] 명령에 의해 영향을 받는 행 수가 반환 되는 메모리에 대 한 포인터입니다.

*bBind*<br/>
[in] 실행 중인 후 명령을 자동으로 바인딩할 지 여부를 지정 합니다. 기본값은 **true**, 그러면 명령이 자동으로 바인딩할 수 있습니다. 설정 *bBind* 하 **false** 수동으로 바인딩할 수 있도록 명령의 자동 바인딩 방지 합니다. (수동 바인딩으로 OLAP 사용자에 게 특히 관심입니다.)

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

결과 집합을 이전에 가져온 경우이 함수는 이전 결과 집합을 해제 하 고 열을 바인딩 해제 합니다. 하는 경우 *bBind* 됩니다 **true**, 새 열을 바인딩합니다.

설정 하 여 여러 결과 지정한 경우에이 함수를 호출 해야 합니다 `CCommand` 템플릿 매개 변수 *TMultiple*=`CMultipleResults`합니다.

## <a name="open"></a> Ccommand:: Open

실행 하 고 필요에 따라 명령에 바인딩합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   LPCSTR szCommand,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(const CSession& session,
   INT szCommand = NULL,
   DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   REFGUID guidCommand = DBGUID_DEFAULT,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();

HRESULT Open(DBPROPSET *pPropSet = NULL,
   DBROWCOUNT* pRowsAffected = NULL,
   bool bBind = true,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>매개 변수

*session*<br/>
[in] 세션에서 명령을 실행 합니다.

*wszCommand*<br/>
[in] 를 실행 하려면 명령에 유니코드 문자열로 전달 합니다. 사용 하는 경우 NULL 일 수 있습니다 `CAccessor`, 명령에 전달 된 값에서 검색할 경우 합니다 [DEFINE_COMMAND](../../data/oledb/define-command.md) 매크로입니다. 참조 [icommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) 에 *OLE DB Programmer's Reference* 세부 정보에 대 한 합니다.

*szCommand*<br/>
[in] 동일 *wszCommand* 제외 하 고이 매개 변수는 ANSI 명령 문자열을 사용 합니다. 이 메서드의 네 번째 폼에는 NULL 값을 걸릴 수 있습니다. 자세한 내용은이 항목의 뒷부분에 나오는 "주의"를 참조 하세요.

*pPropSet*<br/>
[in] 배열에 대 한 포인터 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 속성 및 값을 설정할 수를 포함 하는 구조체. 참조 [속성 집합 및 속성 그룹](/previous-versions/windows/desktop/ms713696(v=vs.85)) 에 *OLE DB Programmer's Reference* Windows SDK에에서 있습니다.

*pRowsAffected*<br/>
[에서/out] 명령에 의해 영향을 받는 행 수가 반환 되는 메모리에 대 한 포인터입니다. 하는 경우  *\*pRowsAffected* 가 null 인 경우 없는 행 수가 반환 됩니다. 그렇지 않으면 `Open` 설정  *\*pRowsAffected* 다음 조건에 따라:

|조건|결과|
|--------|----------|
|합니다 `cParamSets` 요소의 `pParams` 1 보다 큰 경우|*\*pRowsAffected* 모든 실행에 지정 된 매개 변수 집합에 영향을 받는 행의 총 수를 나타냅니다.|
|영향을 받는 행 수를 사용할 수 없는 경우|*\*pRowsAffected* -1로 설정 됩니다.|
|명령을 업데이트 하지 않습니다, 삭제 또는 행을 삽입|*\*pRowsAffected* 정의 되지 않습니다.|

*guidCommand*<br/>
[in] 명령 텍스트를 구문 분석 중 구문 및 사용 하도록 공급자에 대 한 일반 규칙을 지정 하는 GUID입니다. 참조 [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) 및 [icommandtext:: Setcommandtext](/previous-versions/windows/desktop/ms709757(v=vs.85)) 에 *OLE DB Programmer's Reference* 세부 정보에 대 한 합니다.

*bBind*<br/>
[in] 실행 중인 후 명령을 자동으로 바인딩할 지 여부를 지정 합니다. 기본값은 **true**, 그러면 명령이 자동으로 바인딩할 수 있습니다. 설정 *bBind* 하 **false** 수동으로 바인딩할 수 있도록 명령의 자동 바인딩 방지 합니다. (수동 바인딩으로 OLAP 사용자에 게 특히 관심입니다.)

*ulPropSets*<br/>
[in] 수가 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 구조에 전달 합니다 *pPropSet* 인수입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

처음 세 가지 형태의 `Open` 세션 수행할 명령을 만들고 필요에 따라 매개 변수 바인딩 명령을 실행 합니다.

첫 번째 폼은 `Open` 유니코드 명령 문자열을 사용 하며 기본값은 없습니다.

두 번째 형식의 `Open` ANSI 명령 문자열을 취하고 (기존 ANSI 응용 프로그램을 사용 하 여 이전 버전과 호환성을 위해 제공) 기본값은 없습니다.

세 번째 형태의 `Open` 명령 문자열을 형식으로 인해 NULL 일 수 있습니다 **int** 이며 기본값은 NULL입니다. 호출에 대 한 제공 됩니다 `Open(session, NULL);` 나 `Open(session);` 형식의 NULL 이므로 **int**합니다. 이 버전 필요 하며 임을 어설션 합니다 **int** 매개 변수가 NULL 이어야 합니다.

네 번째 양식을 사용 하 여 `Open` 이미 만든 명령을 단일 수행 하려는 시점과 [준비](../../data/oledb/ccommand-prepare.md) 및 여러 실행 합니다.

> [!NOTE]
>  `Open` 호출 `Execute`, 호출 `GetNextResult`합니다.

## <a name="create"></a> Ccommand:: Create

호출 [ccommand:: Createcommand](../../data/oledb/ccommand-createcommand.md) 지정된 된 세션에 대 한 명령을 만드는 데 호출 [icommandtext:: Setcommandtext](/previous-versions/windows/desktop/ms709825(v=vs.85)) 명령 텍스트를 지정 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::Create(const CSession& session,
   LPCWSTR wszCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();

HRESULT CCommandBase::Create(const CSession& session,
   LPCSTR szCommand,
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();
```

#### <a name="parameters"></a>매개 변수

*session*<br/>
[in] 명령을 만드는 데는 세션입니다.

*wszCommand*<br/>
[in] 명령 문자열의 유니코드 텍스트에 대 한 포인터입니다.

*szCommand*<br/>
[in] 명령 문자열을 ANSI 텍스트에 대 한 포인터입니다.

*guidCommand*<br/>
[in] 명령 텍스트를 구문 분석 중 구문 및 사용 하도록 공급자에 대 한 일반 규칙을 지정 하는 GUID입니다. 언어에 대 한 참조 [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

첫 번째 폼은 `Create` 유니코드 명령 문자열을 사용 합니다. 두 번째 형식의 `Create` (기존 ANSI 응용 프로그램을 사용 하 여 이전 버전과 호환성을 위해 제공 됨)는 ANSI 명령 문자열을 사용 합니다.

## <a name="createcommand"></a> CCommand::CreateCommand

새 명령을 만듭니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::CreateCommand(const CSession& session) throw ();
```

#### <a name="parameters"></a>매개 변수

*session*<br/>
[in] `CSession` 새 명령과 사용 하 여 연결할 개체입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드는 지정 된 세션 개체를 사용 하 여 명령을 만듭니다.

## <a name="getparameterinfo"></a> Ccommand:: Getparameterinfo

명령의 매개 변수, 이름 및 개체 유형의 목록을 가져옵니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,
   DBPARAMINFO** ppParamInfo,
   OLECHAR** ppNamesBuffer) throw ();
```

#### <a name="parameters"></a>매개 변수

참조 [icommandwithparameters:: Getparameterinfo](/previous-versions/windows/desktop/ms714917(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="prepare"></a> Ccommand:: Prepare

유효성을 검사 하 고 현재 명령을 최적화 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();
```

#### <a name="parameters"></a>매개 변수

*cExpectedRuns*<br/>
[in] 명령을 실행 하 여 원하는 횟수입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드는 OLE DB 메서드를 래핑합니다 [icommandprepare:: Prepare](/previous-versions/windows/desktop/ms718370(v=vs.85))합니다.

## <a name="releasecommand"></a> CCommand::ReleaseCommand

매개 변수 접근자를 해제 한 다음 명령 자체를 해제 합니다.

### <a name="syntax"></a>구문

```cpp
void CCommandBase::ReleaseCommand() throw();
```

### <a name="remarks"></a>설명

`ReleaseCommand` 와 함께 사용 되어 `Close`입니다. 참조 [닫기](../../data/oledb/ccommand-close.md) 사용법에 대 한 합니다.

## <a name="setparameterinfo"></a> Ccommand:: Setparameterinfo

네이티브 형식의 각 명령 매개 변수를 지정합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,
   const DBORDINAL* pOrdinals,
   const DBPARAMBINDINFO* pParamInfo) throw();
```

#### <a name="parameters"></a>매개 변수

참조 [icommandwithparameters:: Setparameterinfo](/previous-versions/windows/desktop/ms725393(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="unprepare"></a> Ccommand:: Unprepare

현재 명령 실행 계획을 삭제 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CCommandBase::Unprepare() throw();
```

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드는 OLE DB 메서드를 래핑합니다 [icommandprepare:: Unprepare](/previous-versions/windows/desktop/ms719635(v=vs.85))합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)