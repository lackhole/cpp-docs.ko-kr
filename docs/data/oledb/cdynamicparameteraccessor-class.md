---
title: CDynamicParameterAccessor 클래스
ms.date: 02/14/2018
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
- ATL::CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor::GetParamCount
- CDynamicParameterAccessor.GetParamCount
- GetParamCount
- ATL.CDynamicParameterAccessor.GetParamCount
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
- ATL::CDynamicParameterAccessor::GetParamLength
- ATL.CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor.GetParamLength
- CDynamicParameterAccessor::GetParamLength
- GetParamLength
- CDynamicParameterAccessor::GetParamName
- ATL.CDynamicParameterAccessor.GetParamName
- GetParamName
- CDynamicParameterAccessor.GetParamName
- ATL::CDynamicParameterAccessor::GetParamName
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
- CDynamicParameterAccessor.GetParamType
- CDynamicParameterAccessor:GetParamType
- CDynamicParameterAccessor::GetParamType
- ATL.CDynamicParameterAccessor.GetParamType
- GetParamType
- ATL::CDynamicParameterAccessor::GetParamType
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParamLength
- CDynamicParameterAccessor.SetParamLength
- ATL.CDynamicParameterAccessor.SetParamLength
- CDynamicParameterAccessor::SetParamLength
- SetParamLength
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamString
- ATL::CDynamicParameterAccessor::SetParamString
- SetParamString
- CDynamicParameterAccessor::SetParamString
- CDynamicParameterAccessor.SetParamString
helpviewer_keywords:
- CDynamicParameterAccessor class
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
- GetParam method
- GetParamCount method
- GetParamIO method
- GetParamLength method
- GetParamName method
- GetParamStatus method
- GetParamString method
- GetParamType method
- SetParam method
- SetParamLength method
- SetParamStatus method
- SetParamString method
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
ms.openlocfilehash: a655d95cf165ab2c5cba3a391b81d6f420f8322f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230868"
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor 클래스

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 와 유사하지만 [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) 인터페이스를 호출하여 설정한 매개 변수 정보를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="requirements"></a>요구 사항

**헤더**: atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CDynamicParameterAccessor](#cdynamicparameteraccessor)|생성자입니다.|
|[GetParam](#getparam)|버퍼에서 매개 변수 데이터를 검색합니다.|
|[GetParamCount](#getparamcount)|접근자에서 매개 변수 개수를 검색합니다.|
|[GetParamIO](#getparamio)|지정된 매개 변수가 입력 매개 변수인지 출력 매개 변수인지를 결정합니다.|
|[GetParamLength](#getparamlength)|버퍼에 저장된 지정된 매개 변수의 길이를 검색합니다.|
|[GetParamName](#getparamname)|지정된 매개 변수의 이름을 검색합니다.|
|[GetParamStatus](#getparamstatus)|버퍼에 저장된 지정된 매개 변수의 상태를 검색합니다.|
|[GetParamString](#getparamstring)|버퍼에 저장된 지정된 매개 변수의 문자열 데이터를 검색합니다.|
|[GetParamType](#getparamtype)|지정된 매개 변수의 데이터 형식을 검색합니다.|
|[SetParam](#setparam)|매개 변수 데이터를 사용하여 버퍼를 설정합니다.|
|[SetParamLength](#setparamlength)|버퍼에 저장된 지정된 매개 변수의 길이를 설정합니다.|
|[SetParamStatus](#setparamstatus)|버퍼에 저장된 지정된 매개 변수의 상태를 설정합니다.|
|[SetParamString](#setparamstring)|버퍼에 저장된 지정된 매개 변수의 문자열 데이터를 설정합니다.|

## <a name="remarks"></a>설명

공급자는 이 클래스를 사용할 소비자에 대해 `ICommandWithParameters` 를 지원해야 합니다.

매개 변수 정보는 이 클래스로 만들고 관리하는 버퍼에 저장됩니다. [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) 및 [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)을 사용하여 버퍼에서 매개 변수 데이터를 가져옵니다.

SQL Server 저장 프로시저를 실행 하 고 출력 매개 변수 값을 가져옵니다이 클래스를 사용 하는 방법을 보여주는 예제를 참조 하세요. 합니다 [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) 샘플에서 코드를 [Microsoft 사용자를 위해](https://github.com/Microsoft/VCSamples) GitHub의 리포지토리를 제공 합니다.

## <a name="cdynamicparameteraccessor"></a> CDynamicParameterAccessor::CDynamicParameterAccessor

생성자입니다.

### <a name="syntax"></a>구문

```cpp
typedef CDynamicParameterAccessor _ParamClass;
CDynamicParameterAccessor(
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000 )
   : CDynamicAccessor(eBlobHandling, nBlobSize )
```

#### <a name="parameters"></a>매개 변수

*eBlobHandling*<br/>
BLOB 데이터를 처리할 방법을 지정 합니다. 기본값은 DBBLOBHANDLING_DEFAULT 합니다. 참조 [cdynamicaccessor:: Setblobhandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) DBBLOBHANDLINGENUM 값에 대 한 합니다.

*nBlobSize*<br/>
최대 BLOB 크기 (바이트) 이 값에 대해 열 데이터를 BLOB로 처리 됩니다. 기본값은 8000입니다. 참조 [cdynamicaccessor:: Setblobsizelimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) 세부 정보에 대 한 합니다.

### <a name="remarks"></a>설명

참조 된 [cdynamicaccessor:: Cdynamicaccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) BLOB 처리에 대 한 자세한 정보에 대 한 생성자입니다.

## <a name="getparam"></a> CDynamicParameterAccessor::GetParam

매개 변수 버퍼에서 지정된 된 매개 변수에 대 한 문자열이 아닌 데이터를 검색합니다.

### <a name="syntax"></a>구문

```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,
   ctype* pData) const throw();

template <class ctype> bool GetParam(TCHAR* pParamName,
   ctype* pData) const throw();

void* GetParam(DBORDINAL nParam) const throw();

void* GetParam(TCHAR* pParamName) const throw();
```

#### <a name="parameters"></a>매개 변수

*ctype*<br/>
데이터 형식이 템플릿 매개 변수입니다.

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*pParamName*<br/>
[in] 매개 변수 이름입니다.

*pData*<br/>
[out] 버퍼에서 검색 되는 데이터를 포함 하는 메모리에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

템플릿이 아닌 버전에 대 한 데이터를 포함 하는 메모리를 가리킵니다 버퍼에서 검색 됩니다. 템플릿 버전에 대 한 반환 **true** 성공 시 또는 **false** 실패 합니다.

사용 하 여 `GetParam` 버퍼에서 문자열이 아닌 매개 변수 데이터를 검색 합니다. 사용 하 여 [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) 버퍼에서 문자열 매개 변수 데이터를 검색 합니다.

## <a name="getparamcount"></a> CDynamicParameterAccessor::GetParamCount

버퍼에 저장된 매개 변수의 수를 검색합니다.

### <a name="syntax"></a>구문

```cpp
DB_UPARAMS GetParamCount() const throw();
```

### <a name="return-value"></a>반환 값

매개 변수 수입니다.

## <a name="getparamio"></a> CDynamicParameterAccessor::GetParamIO

지정된 매개 변수가 입력 매개 변수인지 출력 매개 변수인지를 결정합니다.

### <a name="syntax"></a>구문

```cpp
bool GetParamIO(DBORDINAL nParam,
   DBPARAMIO* pParamIO) const throw();
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*pParamIO*<br/>
포함 하는 변수와에 대 한 포인터를 `DBPARAMIO` 지정된 된 매개 변수의 형식 (입력 또는 출력). 다음과 같이 정의 됩니다.

```cpp
typedef DWORD DBPARAMIO;

enum DBPARAMIOENUM {
    DBPARAMIO_NOTPARAM   = 0,
    DBPARAMIO_INPUT      = 0x1,
    DBPARAMIO_OUTPUT     = 0x2
};
```

### <a name="return-value"></a>반환 값

반환 **true** 성공 하거나 **false** 실패 합니다.

## <a name="getparamlength"></a> CDynamicParameterAccessor::GetParamLength

버퍼에 저장된 지정된 매개 변수의 길이를 검색합니다.

### <a name="syntax"></a>구문

```cpp
bool GetParamLength(DBORDINAL nParam,
   DBLENGTH* pLength);

DBLENGTH* GetParamLength(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*pLength*<br/>
[out] 지정된 매개 변수의 길이(바이트)를 포함하는 변수에 대한 포인터입니다.

### <a name="remarks"></a>설명

첫 번째 재정의 반환 **true** 성공 시 또는 **false** 실패 합니다. 두 번째 재정의는 매개 변수 길이를 포함하는 메모리를 가리킵니다.

## <a name="getparamname"></a> CDynamicParameterAccessor::GetParamName

지정된 된 매개 변수의 이름을 검색합니다.

### <a name="syntax"></a>구문

```cpp
LPOLESTR GetParamName(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

### <a name="return-value"></a>반환 값

지정된 된 매개 변수의 이름입니다.

## <a name="getparamstatus"></a> CDynamicParameterAccessor::GetParamStatus

버퍼에 저장된 지정된 매개 변수의 상태를 검색합니다.

### <a name="syntax"></a>구문

```cpp
bool GetParamStatus(DBORDINAL nParam,
   DBSTATUS* pStatus);

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*pStatus*<br/>
[out] 지정된 된 매개 변수의 DBSTATUS 상태가 들어 있는 변수에 대 한 포인터입니다. DBSTATUS 값에 대 한 자세한 내용은 [상태](/previous-versions/windows/desktop/ms722617(v=vs.85)) 에 *OLE DB Programmer's Reference*, 또는 DBSTATUS oledb.h에서 검색 합니다.

### <a name="remarks"></a>설명

첫 번째 재정의 반환 **true** 성공 시 또는 **false** 실패 합니다. 두 번째 재정의 지정된 된 매개 변수의 상태를 포함 하는 메모리를 가리킵니다.

## <a name="getparamstring"></a> CDynamicParameterAccessor::GetParamString

버퍼에 저장된 지정된 매개 변수의 문자열 데이터를 검색합니다.

### <a name="syntax"></a>구문

```cpp
bool GetParamString(DBORDINAL nParam,
   CSimpleStringA& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CSimpleStringW& strOutput) throw();

bool GetParamString(DBORDINAL nParam,
   CHAR* pBuffer,
   size_t* pMaxLen) throw();

bool GetParamString(DBORDINAL nParam,
   WCHAR* pBuffer,
   size_t* pMaxLen) throw();
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*strOutput*<br/>
[out] ANSI (`CSimpleStringA`) 또는 유니코드 (`CSimpleStringW`) 문자열 데이터의 지정된 된 매개 변수입니다. 형식의 매개 변수를 전달 해야 `CString`예를 들어:

[!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]

*pBuffer*<br/>
[out] ANSI에 대 한 포인터 (**CHAR**) 또는 유니코드 (**WCHAR**) 문자열 데이터의 지정된 된 매개 변수입니다.

*pMaxLen*<br/>
[out] 버퍼의 크기에 대 한 포인터에서 가리키는 *pBuffer* (문자에서 종결 NULL을 포함).

### <a name="remarks"></a>설명

반환 **true** 성공 하거나 **false** 실패 합니다.

경우 *pBuffer* 가 null 인 경우이 메서드는 필요한 버퍼 크기를 가리키는 메모리에 설정 *pMaxLen* 돌아와 **true** 데이터를 복사 하지 않고 있습니다.

이 메서드가 실패 하는 경우 버퍼 *pBuffer* 전체 문자열을 포함할 만큼 크지 않습니다.

사용 하 여 `GetParamString` 버퍼에서 문자열 매개 변수 데이터를 검색 합니다. 사용 하 여 [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) 버퍼에서 문자열이 아닌 매개 변수 데이터를 검색 합니다.

## <a name="getparamtype"></a> CDynamicParameterAccessor::GetParamType

지정된 매개 변수의 데이터 형식을 검색합니다.

### <a name="syntax"></a>구문

```cpp
bool GetParamType(DBORDINAL nParam,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*pType*<br/>
[out] 지정된 된 매개 변수의 데이터 형식이 포함 된 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 **true** 성공 하거나 **false** 실패 합니다.

## <a name="setparam"></a> CDynamicParameterAccessor::SetParam

지정된 된 (비문자열) 데이터를 사용 하 여 매개 변수 버퍼를 설정 합니다.

### <a name="syntax"></a>구문

```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,
   constctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();

template <class ctype>
bool SetParam(TCHAR* pParamName,
   const ctype* pData,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>매개 변수

*ctype*<br/>
데이터 형식이 템플릿 매개 변수입니다.

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 예를 들어:

[!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]

*pParamName*<br/>
[in] 매개 변수 이름입니다.

*pData*<br/>
[in] 버퍼에 쓸 데이터를 포함 하는 메모리에 대 한 포인터입니다.

*status*<br/>
[in] DBSTATUS 열 상태입니다. DBSTATUS 값에 대 한 자세한 내용은 [상태](/previous-versions/windows/desktop/ms722617(v=vs.85)) 에 *OLE DB Programmer's Reference*, 또는 DBSTATUS oledb.h에서 검색 합니다.

### <a name="return-value"></a>반환 값

반환 **true** 성공 하거나 **false** 실패 합니다.

사용 하 여 `SetParam` 문자열이 아닌 매개 변수 데이터 버퍼에 설정 합니다. 사용 하 여 [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) 버퍼에서 문자열 매개 변수 데이터를 설정 합니다.

## <a name="setparamlength"></a> CDynamicParameterAccessor::SetParamLength

버퍼에 저장된 지정된 매개 변수의 길이를 설정합니다.

### <a name="syntax"></a>구문

```cpp
bool SetParamLength(DBORDINAL nParam,
   DBLENGTH length);
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*length*<br/>
[in] 지정된 된 매개 변수의 길이 (바이트)에서입니다.

### <a name="remarks"></a>설명

반환 **true** 성공 하거나 **false** 실패 합니다.

## <a name="setparamstatus"></a> CDynamicParameterAccessor::SetParamStatus

버퍼에 저장된 지정된 매개 변수의 상태를 설정합니다.

### <a name="syntax"></a>구문

```cpp
bool SetParamStatus(DBORDINAL nParam,
   DBSTATUS status);
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*status*<br/>
[in] 지정된 된 매개 변수의 DBSTATUS 상태입니다. DBSTATUS 값에 대 한 자세한 내용은 [상태](/previous-versions/windows/desktop/ms722617(v=vs.85)) 에 *OLE DB Programmer's Reference*, 또는 DBSTATUS oledb.h에서 검색 합니다.

### <a name="remarks"></a>설명

반환 **true** 성공 하거나 **false** 실패 합니다.

## <a name="setparamstring"></a> CDynamicParameterAccessor::SetParamString

버퍼에 저장된 지정된 매개 변수의 문자열 데이터를 설정합니다.

### <a name="syntax"></a>구문

```cpp
bool SetParamString(DBORDINAL nParam,
   constCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();bool SetParamString(DBORDINAL nParam,
   constWCHAR* pString,
   DBSTATUS status = DBSTATUS_S_OK) throw();
```

#### <a name="parameters"></a>매개 변수

*nParam*<br/>
[in] 매개 변수 번호입니다(1에서 오프셋). 매개 변수 0은 반환 값으로 예약됩니다. 매개 변수 번호는 SQL 또는 저장 프로시저 호출에서 해당 순서를 기준으로 하는 매개 변수의 인덱스입니다. 참조 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 예입니다.

*pString*<br/>
[in] ANSI에 대 한 포인터 (**CHAR**) 또는 유니코드 (**WCHAR**) 문자열 데이터의 지정된 된 매개 변수입니다. Oledb.h에서 DBSTATUS를 참조 하세요.

*status*<br/>
[in] 지정된 된 매개 변수의 DBSTATUS 상태입니다. DBSTATUS 값에 대 한 자세한 내용은 [상태](/previous-versions/windows/desktop/ms722617(v=vs.85)) 에 *OLE DB Programmer's Reference*, 또는 DBSTATUS oledb.h에서 검색 합니다.

### <a name="remarks"></a>설명

반환 **true** 성공 하거나 **false** 실패 합니다.

`SetParamString` 지정 된 최대 크기 보다 큰 문자열을 설정 하려고 하면 실패 *pstring이*합니다.

사용 하 여 `SetParamString` 버퍼에서 문자열 매개 변수 데이터를 설정 합니다. 사용 하 여 [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) 문자열이 아닌 매개 변수 데이터 버퍼에 설정 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor 클래스](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)