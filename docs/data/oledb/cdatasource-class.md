---
title: CDataSource 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
- ATL::CDataSource::Close
- ATL.CDataSource.Close
- CDataSource::Close
- CDataSource.Close
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- GetProperties
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
helpviewer_keywords:
- CDataSource class
- Close method
- GetInitializationString method
- GetProperties method
- GetProperty method
- Open method
- OpenFromFileName method
- OpenFromInitializationString method
- OpenWithPromptFileName method
- OpenWithServiceComponents method
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
ms.openlocfilehash: 2564d4d9b0a2e5df1f575d6f2627ce80f48533c1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59021919"
---
# <a name="cdatasource-class"></a>CDataSource 클래스

데이터 원본에 공급자를 통해 연결을 나타내는 OLE DB 데이터 원본 개체에 해당 합니다.

## <a name="syntax"></a>구문

```cpp
class CDataSource
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[닫기](#close)|연결을 닫습니다.|
|[GetInitializationString](#getinitializationstring)|현재 열려 있는 데이터 원본 초기화 문자열을 검색 합니다.|
|[GetProperties](#getproperties)|연결된 된 데이터 원본에 대 한 현재 설정 된 속성의 값을 가져옵니다.|
|[GetProperty](#getproperty)|현재 연결된 된 데이터 원본에 대해 설정 하는 단일 속성의 값을 가져옵니다.|
|[열기](#open)|중 하나를 사용 하 여 공급자 (데이터 원본)에 대 한 연결을 만듭니다는 `CLSID`, `ProgID`, 또는 `CEnumerator` 호출자가 제공 하는 모니커입니다.|
|[OpenFromFileName](#openfromfilename)|사용자가 제공한 파일 이름으로 지정된 파일에서 데이터 소스를 엽니다.|
|[OpenFromInitializationString](#openfrominitializationstring)|초기화 문자열에서 지정한 데이터 원본이 열립니다.|
|[OpenWithPromptFileName](#openwithpromptfilename)|사용 하 여 해당 데이터 원본에 이전에 만든된 데이터 연결 파일을 선택할 수 있습니다.|
|[OpenWithServiceComponents](#openwithservicecomponents)|데이터 연결 대화 상자를 사용 하 여 데이터 원본 개체를 엽니다.|

## <a name="remarks"></a>설명

단일 연결에 대 한 하나 이상의 데이터베이스 세션을 만들 수 있습니다. 이러한 세션으로 표시 됩니다 `CSession`합니다. 호출 해야 합니다 [cdatasource:: Open](../../data/oledb/cdatasource-open.md) 사용 하 여 세션을 만들기 전에 연결을 열지 `CSession::Open`합니다.

사용 하는 방법의 예 `CDataSource`를 참조 합니다 [CatDB](../../overview/visual-cpp-samples.md) 샘플입니다.

## <a name="close"></a> CDataSource::Close

해제 하 여 연결을 닫습니다는 `m_spInit` 포인터입니다.

### <a name="syntax"></a>구문

```cpp
void Close() throw();
```

## <a name="getinitializationstring"></a> CDataSource::GetInitializationString

현재 열려 있는 데이터 원본 초기화 문자열을 검색 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,
   bool bIncludePassword = false) throw();
```

#### <a name="parameters"></a>매개 변수

*pInitializationString*<br/>
[out] 초기화 문자열에 대 한 포인터입니다.

*bIncludePassword*<br/>
[in] **true** 문자열에 암호를 포함 하는 경우이 고, 그렇지 **false**합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

나중에이 데이터 원본 연결을 다시 초기화 문자열 결과 사용할 수 있습니다.

## <a name="getproperties"></a> CDataSource::GetProperties

연결 된 데이터 원본 개체에 대해 요청 된 속성 정보를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetProperties(ULONG ulPropIDSets,
   constDBPROPIDSET* pPropIDSet,
   ULONG* pulPropertySets,
   DBPROPSET** ppPropsets) const throw();
```

#### <a name="parameters"></a>매개 변수

참조 [idbproperties:: Getproperties](/previous-versions/windows/desktop/ms714344(v=vs.85)) 에 *OLE DB Programmer's Reference* Windows SDK에에서 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

단일 속성을 사용 [GetProperty](../../data/oledb/cdatasource-getproperty.md)합니다.

## <a name="getproperty"></a> CDataSource::GetProperty

연결 된 데이터 원본 개체에 대해 지정된 된 속성의 값을 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetProperty(const GUID& guid,
   DBPROPID propid,
   VARIANT* pVariant) const throw();
```

#### <a name="parameters"></a>매개 변수

*guid*<br/>
[in] 집합의 속성을 반환 하는 속성을 식별 하는 GUID입니다.

*propid*<br/>
[in] ID 속성에 대해 반환할 속성입니다.

*pVariant*<br/>
[out] 변형에 대 한 포인터는 `GetProperty` 속성의 값을 반환 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

여러 속성을 사용 [GetProperties](../../data/oledb/cdatasource-getproperties.md)합니다.

## <a name="open"></a> CDataSource::Open

사용 하 여 데이터 원본에 연결을 엽니다는 `CLSID`, `ProgID`, 또는 `CEnumerator` 모니커 또는 로케이터 대화 상자를 사용 하 여 사용자 프롬프트입니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Open(const CLSID& clsid,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CLSID& clsid,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,
   LPCTSTR pName,  LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(const CEnumerator& enumerator,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(const CEnumerator& enumerator,
   LPCTSTR pName,
   LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();

HRESULT Open(HWND hWnd = GetActiveWindow(),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID,
   DBPROPSET* pPropSet = NULL,
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID,
   LPCTSTR pName,LPCTSTR pUserName = NULL,
   LPCTSTR pPassword = NULL,
   long nInitMode = 0) throw();
```

#### <a name="parameters"></a>매개 변수

*clsid*<br/>
[in] `CLSID` 데이터 공급자입니다.

*pPropSet*<br/>
[in] 배열에 대 한 포인터 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 속성 및 값을 설정할 수를 포함 하는 구조체. 참조 [속성 집합 및 속성 그룹](/previous-versions/windows/desktop/ms713696(v=vs.85)) 에 *OLE DB Programmer's Reference* Windows SDK에에서 있습니다.

*nPropertySets*<br/>
[in] 수가 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 구조에 전달 합니다 *pPropSet* 인수입니다.

*pName*<br/>
[in] 연결할 데이터베이스의 이름입니다.

*pUserName*<br/>
[in] 사용자의 이름입니다.

*pPassword*<br/>
[in] 사용자의 암호입니다.

*nInitMode*<br/>
[in] 데이터베이스 초기화 모드입니다. 참조 [초기화 속성](/previous-versions/windows/desktop/ms723127(v=vs.85))에 *OLE DB Programmer's Reference* 올바른 초기화 모드 목록을 Windows sdk입니다. 하는 경우 *nInitMode* 0, 아니요 초기화가 모드는 연결을 여는데 사용 되는 속성 집합에 포함 됩니다.

*szProgID*<br/>
[in] 프로그램 식별자입니다.

*enumerator*<br/>
[in] A [CEnumerator](../../data/oledb/cenumerator-class.md) 호출자에 게 지정 하지 않는 경우 연결을 열기 위해 모니커를 가져오는 데 사용 되는 개체는 `CLSID`합니다.

*hWnd*<br/>
[in] 대화 상자의 부모가 될 창의 핸들입니다. 사용 하는 함수 오버 로드를 사용 하 여 *hWnd* 매개 변수는 서비스 구성 요소를 자동으로 호출 세부 정보에 대 한 주의 참조 하십시오.

*dwPromptOptions*<br/>
[in] 표시할 로케이터 대화 상자의 스타일을 결정합니다. 가능한 값은 Msdasc.h를 참조하세요.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

사용 하 여 메서드 오버 로드 된 *hWnd* 매개 변수는 oledb32.dll에서 서비스 구성 요소를 사용 하 여 데이터 원본 개체를 엽니다;이 DLL에는 리소스 풀링, 자동 같은 서비스 구성 요소 기능의 구현이 포함 되어 있습니다. 트랜잭션 참여 등과 합니다. 자세한 내용은 "OLE DB 서비스"의 OLE DB 프로그래머 참조에서 참조 하세요 [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)합니다.

사용 하지 않는 메서드 오버 로드 된 *hWnd* 매개 변수는 oledb32.dll에서 서비스 구성 요소를 사용 하지 않고 데이터 원본 개체를 엽니다. A [CDataSource](../../data/oledb/cdatasource-class.md) 이러한 함수 오버 로드를 사용 하 여 열린 개체 구성 요소 서비스의 기능 중 하나를 사용할 수 있게 됩니다.

### <a name="example"></a>예제

다음 코드에서는 OLE DB 템플릿을 사용하여 Jet 4.0 데이터 소스를 여는 방법을 보여 줍니다. Jet 데이터 소스를 OLE DB 데이터 소스로 처리합니다. 그러나를 호출 하 여 `Open` 두 속성 집합을 필요: DBPROPSET_DBINIT 및 DBPROPSET_JETOLEDB_DBINIT, 다른 하나 DBPROP_JETOLEDB_DATABASEPASSWORD 설정할 수 있도록 합니다.

[!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]

## <a name="openfromfilename"></a> CDataSource::OpenFromFileName

사용자가 제공한 파일 이름으로 지정된 파일에서 데이터 소스를 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();
```

#### <a name="parameters"></a>매개 변수

*szFileName*<br/>
[in] 일반적으로 데이터 소스 연결(.UDL) 파일의 이름입니다.

데이터 연결 파일 (.udl 파일)에 대 한 자세한 내용은 참조 하세요. [데이터 링크 API 개요](/previous-versions/windows/desktop/ms718102(v=vs.85)) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다. 자세한 내용은 "OLE DB 서비스"의 OLE DB 프로그래머 참조에서 참조 하세요 [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)합니다.

## <a name="openfrominitializationstring"></a> CDataSource::OpenFromInitializationString

사용자가 제공한 초기화 문자열에 지정 된 데이터 소스를 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,
   bool fPromptForInfo= false) throw();
```

#### <a name="parameters"></a>매개 변수

*szInitializationString*<br/>
[in] 초기화 문자열입니다.

*fPromptForInfo*<br/>
[in] 이 인수 설정 된 경우 **true**, 다음 `OpenFromInitializationString` DBPROP_INIT_PROMPT 속성이 있는지 묻는 자세한 정보가 필요한 경우에 지정 하는 DBPROMPT_COMPLETEREQUIRED로 설정 됩니다. 초기화 문자열 암호에 필요한 데이터베이스를 지정 하는 경우에 유용 하지만 문자열 암호를 포함 하지 않습니다. 사용자 암호 (또는 누락 된 기타 정보)에 대 한 메시지가 표시 되는 데이터베이스에 연결할 때 발생 합니다.

기본값은 **false**, 사용자 안 메시지 표시 (DBPROMPT_NOPROMPT DBPROP_INIT_PROMPT 집합)를 지정 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다.

## <a name="openwithpromptfilename"></a> CDataSource::OpenWithPromptFileName

이 메서드는 사용자에게 대화 상자를 표시한 다음 사용자가 지정한 파일을 사용하여 데이터 원본을 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,
   LPCOLESTR szInitialDirectory = NULL) throw();
```

#### <a name="parameters"></a>매개 변수

*hWnd*<br/>
[in] 대화 상자의 부모가 될 창의 핸들입니다.

*dwPromptOptions*<br/>
[in] 표시할 로케이터 대화 상자의 스타일을 결정합니다. 가능한 값은 Msdasc.h를 참조하세요.

*szInitialDirectory*<br/>
[in] 로케이터 대화 상자에 표시할 초기 디렉터리입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다. 자세한 내용은 "OLE DB 서비스"의 OLE DB 프로그래머 참조에서 참조 하세요 [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)합니다.

## <a name="openwithservicecomponents"></a> CDataSource::OpenWithServiceComponents

oledb32.dll에서 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);

HRESULT OpenWithServiceComponents (LPCSTR szProgID,
   DBPROPSET* pPropset = NULL,
   ULONG ulPropSets = 1);
```

#### <a name="parameters"></a>매개 변수

*clsid*<br/>
[in] `CLSID` 데이터 공급자입니다.

*szProgID*<br/>
[in] 데이터 공급자의 프로그램 ID입니다.

*pPropset*<br/>
[in] 배열에 대 한 포인터 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 속성 및 값을 설정할 수를 포함 하는 구조체. 참조 [속성 집합 및 속성 그룹](/previous-versions/windows/desktop/ms713696(v=vs.85)) 에 *OLE DB Programmer's Reference* Windows SDK에에서 있습니다. 데이터 원본 개체가 초기화되면 속성은 데이터 원본 속성 그룹에 속해야 합니다. 동일한 속성에 두 번 이상 지정 된 경우 *pPropset*, 다음 사용 되는 값은 공급자별으로 다릅니다. 하는 경우 *ulPropSets* 가 0 이면이 매개 변수가 무시 됩니다.

*ulPropSets*<br/>
[in] 수가 [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 구조에 전달 합니다 *pPropSet* 인수입니다. 이 값이 0 이면 공급자 무시 *pPropset*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드는 oledb32.dll에 있는 서비스 구성 요소를 사용하여 데이터 원본 개체를 엽니다. 이 DLL에는 리소스 풀링, 자동 트랜잭션 참여 등과 같은 서비스 구성 요소 기능의 구현이 들어 있습니다. 자세한 내용은 "OLE DB 서비스"의 OLE DB 프로그래머 참조에서 참조 하세요 [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)