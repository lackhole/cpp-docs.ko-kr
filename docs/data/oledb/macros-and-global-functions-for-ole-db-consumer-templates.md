---
title: OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수
ms.date: 02/11/2019
f1_keywords:
- vc.templates.ole
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
- BEGIN_ACCESSOR
- BEGIN_ACCESSOR_MAP
- END_ACCESSOR
- END_ACCESSOR_MAP
- BEGIN_COLUMN_MAP
- BLOB_ENTRY
- BLOB_ENTRY_LENGTH
- BLOB_ENTRY_LENGTH_STATUS
- BLOB_ENTRY_STATUS
- BLOB_NAME
- BLOB_NAME_LENGTH
- BLOB_NAME_LENGTH_STATUS
- BLOB_NAME_STATUS
- BOOKMARK_ENTRY
- COLUMN_ENTRY
- COLUMN_ENTRY_EX
- COLUMN_ENTRY_LENGTH
- COLUMN_ENTRY_LENGTH_STATUS
- COLUMN_ENTRY_PS
- COLUMN_ENTRY_PS_LENGTH
- COLUMN_ENTRY_PS_LENGTH_STATUS
- COLUMN_ENTRY_PS_STATUS
- COLUMN_ENTRY_STATUS
- COLUMN_ENTRY_TYPE
- COLUMN_ENTRY_TYPE_SIZE
- COLUMN_NAME
- COLUMN_NAME_EX
- COLUMN_NAME_LENGTH
- COLUMN_NAME_LENGTH_STATUS
- COLUMN_NAME_PS
- COLUMN_NAME_PS_LENGTH
- COLUMN_NAME_PS_LENGTH_STATUS
- COLUMN_NAME_PS_STATUS
- COLUMN_NAME_STATUS
- COLUMN_NAME_TYPE
- COLUMN_NAME_TYPE_PS
- COLUMN_NAME_TYPE_SIZE
- COLUMN_NAME_TYPE_STATUS
- END_COLUMN_MAP
- DEFINE_COMMAND
- DEFINE_COMMAND_EX
- BEGIN_PARAM_MAP
- END_PARAM_MAP
- SET_PARAM_TYPE
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
- AtlTraceErrorRecords function
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR_MAP macro
- END_ACCESSOR macro
- END_ACCESSOR_MAP macro
- BEGIN_COLUMN_MAP macro
- BLOB_ENTRY macro
- BLOB_ENTRY_LENGTH macro
- BLOB_ENTRY_LENGTH_STATUS macro
- BLOB_ENTRY_STATUS macro
- BLOB_NAME macro
- BLOB_NAME_LENGTH macro
- BLOB_NAME_LENGTH_STATUS macro
- BLOB_NAME_STATUS macro
- BOOKMARK_ENTRY macro
- COLUMN_ENTRY macro
- COLUMN_ENTRY_EX macro
- COLUMN_ENTRY_LENGTH macro
- COLUMN_ENTRY_LENGTH_STATUS macro
- COLUMN_ENTRY_PS macro
- COLUMN_ENTRY_PS_LENGTH macro
- COLUMN_ENTRY_PS_LENGTH_STATUS macro
- COLUMN_ENTRY_PS_STATUS macro
- COLUMN_ENTRY_STATUS macro
- COLUMN_ENTRY_TYPE macro
- COLUMN_ENTRY_TYPE_SIZE macro
- COLUMN_NAME macro
- COLUMN_NAME_EX macro
- COLUMN_NAME_LENGTH macro
- COLUMN_NAME_LENGTH_STATUS macro
- COLUMN_NAME_PS macro
- COLUMN_NAME_PS_LENGTH macro
- COLUMN_NAME_PS_LENGTH_STATUS macro
- COLUMN_NAME_PS_STATUS macro
- COLUMN_NAME_STATUS macro
- COLUMN_NAME_TYPE macro
- COLUMN_NAME_TYPE_PS macro
- COLUMN_NAME_TYPE_SIZE macro
- COLUMN_NAME_TYPE_STATUS macro
- END_COLUMN_MAP macro
- DEFINE_COMMAND macro
- DEFINE_COMMAND_EX macro
- BEGIN_PARAM_MAP macro
- END_PARAM_MAP macro
- SET_PARAM_TYPE macro
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
ms.openlocfilehash: d4ed6b86d99cdfc272b5df10ede6af6bd05ed366
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361349"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수

OLE DB 소비자 템플릿은 다음과 같습니다. 다음 매크로 및 전역 함수

## <a name="global-functions"></a>전역 함수

|||
|-|-|
|[AtlTraceErrorRecords](#atltraceerrorrecords)|오류를 반환 하는 경우 OLE DB 오류 레코드 덤프 장치 정보를 덤프 합니다.|

## <a name="accessor-map-macros"></a>접근자 맵 매크로

|||
|-|-|
|[BEGIN_ACCESSOR](#begin_accessor)|접근자 항목의 시작을 표시 합니다.|
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|접근자 맵 항목의 시작을 표시합니다.|
|[END_ACCESSOR](#end_accessor)|접근자 항목의 끝을 표시 합니다.|
|[END_ACCESSOR_MAP](#end_accessor_map)|접근자 맵 항목의 끝을 표시 합니다.|

## <a name="column-map-macros"></a>열 맵 매크로

|||
|-|-|
|[BEGIN_COLUMN_MAP](#begin_column_map)|사용자 레코드 클래스의 열 지도 항목의 시작을 표시 합니다.|
|[BLOB_ENTRY](#blob_entry)|Binary large object (BLOB)에 바인딩하는 데 사용 합니다.|
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|BLOB 데이터 열의 길이 보고합니다.|
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|길이 및 BLOB 데이터 열의 상태를 보고합니다.|
|[BLOB_ENTRY_STATUS](#blob_entry_status)|BLOB 열 데이터의 상태를 보고합니다.|
|[BLOB_NAME](#blob_name)|열 이름별으로 binary large object를 바인딩하는 데 사용 합니다.|
|[BLOB_NAME_LENGTH](#blob_name_length)|BLOB 데이터 열의 길이 보고합니다.|
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|길이 및 BLOB 데이터 열의 상태를 보고합니다.|
|[BLOB_NAME_STATUS](#blob_name_status)|BLOB 열 데이터의 상태를 보고합니다.|
|[BOOKMARK_ENTRY](#bookmark_entry)|행 집합에 대해 책갈피 항목을 나타냅니다. 책갈피 항목은 특별 한 열 항목의 합니다.|
|[COLUMN_ENTRY](#column_entry)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다.|
|[COLUMN_ENTRY_EX](#column_entry_ex)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 *형식*, *길이*를 *정밀도*, *규모*, 및 *상태* 매개 변수입니다.|
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 합니다 *길이* 변수입니다.|
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 *상태* 하 고 *길이* 매개 변수입니다.|
|[COLUMN_ENTRY_PS](#column_entry_ps)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 *정밀도* 하 고 *확장* 매개 변수입니다.|
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 합니다 *길이* 변수인 *정밀도* 및 *확장* 매개 변수입니다.|
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 *상태* 하 고 *길이* 변수인 *정밀도* 및 *확장* 매개 변수입니다.|
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 합니다 *상태* 변수인 *정밀도* 및 *확장* 매개 변수입니다.|
|[COLUMN_ENTRY_STATUS](#column_entry_status)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 합니다 *상태* 변수입니다.|
|[COLUMN_ENTRY_TYPE](#column_entry_type)|데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 *형식* 매개 변수입니다.|
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 *형식* 하 고 *크기* 매개 변수입니다.|
|[COLUMN_NAME](#column_name)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다.|
|[COLUMN_NAME_EX](#column_name_ex)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식, 크기, 전체 자릿수, 확장성, 열 길이 및 상태 열 사양을 지원합니다.|
|[COLUMN_NAME_LENGTH](#column_name_length)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 열 길이 지정을 지원 합니다.|
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 열 길이 및 상태 사양을 지원합니다.|
|[COLUMN_NAME_PS](#column_name_ps)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 전체 자릿수 및 소수 자릿수의 사양을 지원합니다.|
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 전체 자릿수, 소수 자릿수 및 열 길이 사양을 지원합니다.|
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 전체 자릿수, 확장성, 열 길이 및 상태 열 사양을 지원합니다.|
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 전체 자릿수, 소수 자릿수 및 열 상태는 사양을 지원합니다.|
|[COLUMN_NAME_STATUS](#column_name_status)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 열 상태는 사양을 지원합니다.|
|[COLUMN_NAME_TYPE](#column_name_type)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식 사양을 지원합니다.|
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식, 자릿수 및 소수 자릿수의 사양을 지원합니다.|
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식 및 크기의 사양을 지원합니다.|
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|이름으로 데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 데이터 형식 및 열 상태는 사양을 지원합니다.|
|[END_COLUMN_MAP](#end_column_map)|열 맵 항목의 끝을 표시 합니다.|

## <a name="command-macros"></a>명령 매크로

|||
|-|-|
|[DEFINE_COMMAND](#define_command)|사용 하는 경우 행 집합을 만드는 데 사용할 명령을 지정 합니다 [CCommand](../../data/oledb/ccommand-class.md) 클래스입니다. 지정 된 응용 프로그램 형식 (ANSI 또는 유니코드)와 일치 하는 문자열 형식만 허용 합니다. 사용 하는 것이 좋습니다 [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) DEFINE_COMMAND 대신 합니다.|
|[DEFINE_COMMAND_EX](#define_command_ex)|사용 하는 경우 행 집합을 만드는 데 사용할 명령을 지정 합니다 [CCommand](../../data/oledb/ccommand-class.md) 클래스입니다. ANSI 및 유니코드 응용 프로그램을 지원합니다.|

## <a name="parameter-map-macros"></a>매개 변수 맵 매크로

|||
|-|-|
|[BEGIN_PARAM_MAP](#begin_param_map)|사용자 레코드 클래스의 매개 변수 맵 항목의 시작을 표시 합니다.|
|[END_PARAM_MAP](#end_param_map)|매개 변수가 맵 항목의 끝을 표시 합니다.|
|[SET_PARAM_TYPE](#set_param_type)|SET_PARAM_TYPE 매크로 입력, 출력 또는 입출력으로 따르는 COLUMN_ENTRY 매크로 지정 합니다.|

### <a name="atltraceerrorrecords"></a> AtlTraceErrorRecords

오류를 반환 하는 경우 OLE DB 오류 레코드 덤프 장치 정보를 덤프 합니다.

#### <a name="syntax"></a>구문

```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);
```

#### <a name="parameters"></a>매개 변수

*hErr*<br/>
[in] OLE DB 소비자 템플릿 멤버 함수로 반환 된 HRESULT입니다.

#### <a name="remarks"></a>설명

하는 경우 *hErr* S_OK 아닙니다 `AtlTraceErrorRecords` OLE DB 오류 레코드 덤프 장치 정보를 덤프 (합니다 **디버그** 출력 창 또는 파일로 탭). 공급자에서 가져온 오류 레코드 정보를 각 오류 레코드 항목에 대 한 행 번호, 원본, 설명, 도움말 파일, 컨텍스트 및 GUID를 포함 합니다. `AtlTraceErrorRecords` 디버그 빌드에서만에서이 정보를 덤프합니다. 릴리스 빌드에서 빈 스텁을 아웃 최적화 된 것입니다. 자세한 내용은 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)합니다.

### <a name="begin_accessor"></a> BEGIN_ACCESSOR

접근자 항목의 시작을 표시 합니다.

#### <a name="syntax"></a>구문

```cpp
BEGIN_ACCESSOR(num, bAuto)
```

#### <a name="parameters"></a>매개 변수

*num*<br/>
[in] 이 접근자 맵에 있는 접근자에 대 한 0 오프셋 수입니다.

*bAuto*<br/>
[in] 이 접근자 접근자를 자동 또는 수동 접근자를 지정 합니다. 하는 경우 **true**, 경우 접근자가 자동; **false**, 접근자가 수동입니다. 자동 접근자 이동 작업에서 데이터를 인출 되 의미 합니다.

#### <a name="remarks"></a>설명

행 집합에서 여러 접근자의 경우 BEGIN_ACCESSOR_MAP를 지정 하 고 각 접근자에 BEGIN_ACCESSOR 매크로 사용 해야 합니다. BEGIN_ACCESSOR 매크로 END_ACCESSOR 매크로 사용 하 여 완료 됩니다. BEGIN_ACCESSOR_MAP 매크로 END_ACCESSOR_MAP 매크로 사용 하 여 완료 됩니다.

#### <a name="example"></a>예제

참조 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)합니다.

### <a name="begin_accessor_map"></a> BEGIN_ACCESSOR_MAP

접근자 맵 항목의 시작을 표시합니다.

#### <a name="syntax"></a>구문

```cpp
BEGIN_ACCESSOR_MAP(x, num)
```

#### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 사용자 레코드 클래스의 이름입니다.

*num*<br/>
[in] 이 접근자 맵에 있는 접근자 수입니다.

#### <a name="remarks"></a>설명

행 집합에서 여러 접근자의 경우 부분 BEGIN_ACCESSOR_MAP를 지정 하 고 각 접근자에 BEGIN_ACCESSOR 매크로 사용 해야 합니다. BEGIN_ACCESSOR 매크로 END_ACCESSOR 매크로 사용 하 여 완료 됩니다. 접근자 맵은 END_ACCESSOR_MAP 매크로 사용 하 여 완료 됩니다.

사용자 레코드에 접근자가 하나만 있는 경우 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)매크로를 사용합니다.

#### <a name="example"></a>예제

```cpp
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
```

### <a name="end_accessor"></a> END_ACCESSOR

접근자 항목의 끝을 표시 합니다.

#### <a name="syntax"></a>구문

```cpp
END_ACCESSOR()
```

#### <a name="remarks"></a>설명

행 집합에서 여러 접근자에 대 한 BEGIN_ACCESSOR_MAP를 지정 하 고 각 접근자에 BEGIN_ACCESSOR 매크로 사용 해야 합니다. BEGIN_ACCESSOR 매크로 END_ACCESSOR 매크로 사용 하 여 완료 됩니다. BEGIN_ACCESSOR_MAP 매크로 END_ACCESSOR_MAP 매크로 사용 하 여 완료 됩니다.

#### <a name="example"></a>예제

참조 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)합니다.

### <a name="end_accessor_map"></a> END_ACCESSOR_MAP

접근자 맵 항목의 끝을 표시 합니다.

#### <a name="syntax"></a>구문

```cpp
END_ACCESSOR_MAP()
```

#### <a name="remarks"></a>설명

행 집합에서 여러 접근자에 대 한 BEGIN_ACCESSOR_MAP를 지정 하 고 각 접근자에 BEGIN_ACCESSOR 매크로 사용 해야 합니다. BEGIN_ACCESSOR 매크로 END_ACCESSOR 매크로 사용 하 여 완료 됩니다. BEGIN_ACCESSOR_MAP 매크로 END_ACCESSOR_MAP 매크로 사용 하 여 완료 됩니다.

#### <a name="example"></a>예제

참조 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)합니다.

### <a name="begin_column_map"></a> BEGIN_COLUMN_MAP

열 맵 항목의 시작을 표시합니다.

#### <a name="syntax"></a>구문

```cpp
BEGIN_COLUMN_MAP(x)
```

#### <a name="parameters"></a>매개 변수

*x*<br/>
[in] `CAccessor`에서 파생된 사용자 레코드 클래스의 이름입니다.

#### <a name="remarks"></a>설명

이 매크로는 행 집합에 단일 접근자가 있는 경우에 사용됩니다. 행 집합에 여러 접근자가 있는 경우 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)을 사용합니다.

BEGIN_COLUMN_MAP 매크로 END_COLUMN_MAP 매크로 사용 하 여 완료 됩니다. 이 매크로는 사용자 레코드에 하나의 접근자만 필요한 경우에 사용됩니다.

열은 바인딩하려면 행 집합의 필드에 해당합니다.

#### <a name="example"></a>예제

다음은 열 및 매개 변수 맵의 샘플입니다.

<!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a> BLOB_ENTRY

BEGIN_COLUMN_MAP END_COLUMN_MAP와 바인딩하는 데 사용할 binary large object ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))).

#### <a name="syntax"></a>구문

```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)
```

#### <a name="parameters"></a>매개 변수

*nOrdinal*<br/>
[in] 열 번호입니다.

*IID*<br/>
[in] GUID와 같은 인터페이스 `IDD_ISequentialStream`BLOB를 검색 하는 데 사용 합니다.

*flags*<br/>
[in] OLE 구조적 저장소 모델에서 정의 된 저장소 모드 플래그 (예를 들어 `STGM_READ`).

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="example"></a>예제

참조 [BLOB을 검색 하는 방법을?](../../data/oledb/retrieving-a-blob.md)합니다.

### <a name="blob_entry_length"></a> BLOB_ENTRY_LENGTH

BEGIN_COLUMN_MAP END_COLUMN_MAP와 바인딩하는 데 사용할 binary large object ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). 비슷합니다 [BLOB_ENTRY](../../data/oledb/blob-entry.md)한다는 점을 제외 하이 매크로 BLOB 열의 바이트 길이 가져옵니다.

#### <a name="syntax"></a>구문

```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)
```

#### <a name="parameters"></a>매개 변수

*nOrdinal*<br/>
[in] 열 번호입니다.

*IID*<br/>
[in] GUID와 같은 인터페이스 `IDD_ISequentialStream`BLOB를 검색 하는 데 사용 합니다.

*flags*<br/>
[in] OLE 구조적 저장소 모델에서 정의 된 저장소 모드 플래그 (예를 들어 `STGM_READ`).

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[out] BLOB 열 (실제) 길이 (바이트)에서입니다.

#### <a name="example"></a>예제

참조 [BLOB을 검색 하는 방법을?](../../data/oledb/retrieving-a-blob.md)합니다.

### <a name="blob_entry_length_status"></a> BLOB_ENTRY_LENGTH_STATUS

BEGIN_COLUMN_MAP END_COLUMN_MAP와 바인딩하는 데 사용할 binary large object ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). 비슷합니다 [BLOB_ENTRY](../../data/oledb/blob-entry.md)한다는 점을 제외 하는 길이 상태의 해당 BLOB 열에도이 매크로 가져옵니다.

#### <a name="syntax"></a>구문

```cpp
BLOB_ENTRY_LENGTH_STATUS(
    nOrdinal,
    IID,
    flags,
    data,
    length,
    status )
```

#### <a name="parameters"></a>매개 변수

*nOrdinal*<br/>
[in] 열 번호입니다.

*IID*<br/>
[in] GUID와 같은 인터페이스 `IDD_ISequentialStream`BLOB를 검색 하는 데 사용 합니다.

*flags*<br/>
[in] OLE 구조적 저장소 모델에서 정의 된 저장소 모드 플래그 (예를 들어 `STGM_READ`).

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[out] BLOB 열 (실제) 길이 (바이트)에서입니다.

*status*<br/>
[out] BLOB 열 데이터의 상태입니다.

#### <a name="example"></a>예제

참조 [BLOB을 검색 하는 방법을?](../../data/oledb/retrieving-a-blob.md)합니다.

### <a name="blob_entry_status"></a> BLOB_ENTRY_STATUS

바인딩하는 데 BEGIN_COLUMN_MAP 또는 BEGIN_ACCESSOR_MAP binary large object ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). 비슷합니다 [BLOB_ENTRY](../../data/oledb/blob-entry.md)한다는 점을 제외 하이 매크로는 또한 BLOB 열의 상태를 가져옵니다.

#### <a name="syntax"></a>구문

```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)
```

#### <a name="parameters"></a>매개 변수

*nOrdinal*<br/>
[in] 열 번호입니다.

*IID*<br/>
[in] GUID와 같은 인터페이스 `IDD_ISequentialStream`BLOB를 검색 하는 데 사용 합니다.

*flags*<br/>
[in] OLE 구조적 저장소 모델에서 정의 된 저장소 모드 플래그 (예를 들어 `STGM_READ`).

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*status*<br/>
[out] BLOB 필드의 상태입니다.

#### <a name="example"></a>예제

참조 [BLOB을 검색 하는 방법을?](../../data/oledb/retrieving-a-blob.md)합니다.

### <a name="blob_name"></a> BLOB_NAME

BEGIN_COLUMN_MAP END_COLUMN_MAP와 바인딩하는 데 사용할 binary large object ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). 비슷합니다 [BLOB_ENTRY](../../data/oledb/blob-entry.md)한다는 점을 제외 하이 매크로 열 번호 대신 열 이름을 사용 합니다.

#### <a name="syntax"></a>구문

```cpp
BLOB_NAME(pszName, IID, flags, data )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*IID*<br/>
[in] GUID와 같은 인터페이스 `IDD_ISequentialStream`BLOB를 검색 하는 데 사용 합니다.

*flags*<br/>
[in] OLE 구조적 저장소 모델에서 정의 된 저장소 모드 플래그 (예를 들어 `STGM_READ`).

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="example"></a>예제

참조 [BLOB을 검색 하는 방법을?](../../data/oledb/retrieving-a-blob.md)합니다.

### <a name="blob_name_length"></a> BLOB_NAME_LENGTH

BEGIN_COLUMN_MAP END_COLUMN_MAP와 바인딩하는 데 사용할 binary large object ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). 비슷합니다 [BLOB_NAME](../../data/oledb/blob-name.md)한다는 점을 제외 하도이 매크로의 BLOB 열 데이터의 바이트의 길이 가져옵니다.

#### <a name="syntax"></a>구문

```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*IID*<br/>
[in] GUID와 같은 인터페이스 `IDD_ISequentialStream`BLOB를 검색 하는 데 사용 합니다.

*flags*<br/>
[in] OLE 구조적 저장소 모델에서 정의 된 저장소 모드 플래그 (예를 들어 `STGM_READ`).

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[out] BLOB 열 (실제) 길이 (바이트)에서입니다.

### <a name="blob_name_length_status"></a> BLOB_NAME_LENGTH_STATUS

BEGIN_COLUMN_MAP END_COLUMN_MAP와 바인딩하는 데 사용할 binary large object ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). 비슷합니다 [BLOB_NAME](../../data/oledb/blob-name.md)한다는 점을 제외 하이 매크로 또한 길이 및 BLOB 데이터 열의 상태를 가져옵니다.

#### <a name="syntax"></a>구문

```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*IID*<br/>
[in] GUID와 같은 인터페이스 `IDD_ISequentialStream`BLOB를 검색 하는 데 사용 합니다.

*flags*<br/>
[in] OLE 구조적 저장소 모델에서 정의 된 저장소 모드 플래그 (예를 들어 `STGM_READ`).

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[out] BLOB 열 (실제) 길이 (바이트)에서입니다.

*status*<br/>
[out] BLOB 필드의 상태입니다.

### <a name="blob_name_status"></a> BLOB_NAME_STATUS

BEGIN_COLUMN_MAP END_COLUMN_MAP와 바인딩하는 데 사용할 binary large object ([BLOB](/previous-versions/windows/desktop/ms711511(v=vs.85))). 비슷합니다 [BLOB_NAME](../../data/oledb/blob-name.md)한다는 점을 제외 하이 매크로는 또한 BLOB 열 데이터의 상태를 가져옵니다.

#### <a name="syntax"></a>구문

```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*IID*<br/>
[in] GUID와 같은 인터페이스 `IDD_ISequentialStream`BLOB를 검색 하는 데 사용 합니다.

*flags*<br/>
[in] OLE 구조적 저장소 모델에서 정의 된 저장소 모드 플래그 (예를 들어 `STGM_READ`).

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*status*<br/>
[out] BLOB 필드의 상태입니다.

### <a name="bookmark_entry"></a> BOOKMARK_ENTRY

책갈피 열에 바인딩합니다.

#### <a name="syntax"></a>구문

```cpp
BOOKMARK_ENTRY(variable)
```

#### <a name="parameters"></a>매개 변수

*variable*<br/>
[in] 책갈피 열에 바인딩할 변수입니다.

#### <a name="example"></a>예제

```cpp
class CArtistsBookmark
{
public:
// Data Elements
   CBookmark<4> m_bookmark;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

// Output binding map
BEGIN_COLUMN_MAP(CArtistsBookmark)
   BOOKMARK_ENTRY(m_bookmark)
   COLUMN_ENTRY(1, m_nAge)
   COLUMN_ENTRY(2, m_szFirstName)
   COLUMN_ENTRY(3, m_szLastName)
END_COLUMN_MAP()

   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_BOOKMARKS, true);
   }

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsBookmark, L" \
   SELECT \
      Age, \
      FirstName, \
      LastName \
      FROM Artists")
};
```

자세한 내용은 [를 사용 하 여 책갈피](using-bookmarks.md) 하 고 [CBookmark 클래스](../../data/oledb/cbookmark-class.md).

### <a name="column_entry"></a> COLUMN_ENTRY

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY(nOrdinal, data)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 열 번호입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

COLUMN_ENTRY 매크로 다음 위치에서 사용 됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

#### <a name="example"></a>예제

매크로 항목의 예제를 참조 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)합니다.

### <a name="column_entry_ex"></a> COLUMN_ENTRY_EX

데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 열 번호입니다.

*wType*<br/>
[in] 데이터 형식입니다.

*nLength*<br/>
[in] 데이터 크기 (바이트)입니다.

*nPrecision*<br/>
[in] 데이터를 가져올 때 사용 하 여 최대 전체 자릿수와 *wType* 는 `DBTYPE_NUMERIC`합니다. 그렇지 않으면이 매개 변수가 무시 됩니다.

*nScale*<br/>
[in] 데이터를 가져올 때 사용 하도록 눈금 및 *wType* 됩니다 `DBTYPE_NUMERIC` 또는 `DBTYPE_DECIMAL`합니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

COLUMN_ENTRY_EX 매크로 다음 위치에서 사용 됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

#### <a name="example"></a>예제

참조 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)합니다.

### <a name="column_entry_length"></a> COLUMN_ENTRY_LENGTH

데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 하나를 사용 하 여 시작 하는 열 번호입니다. 책갈피 열 0에 해당합니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

이 매크로 지원 합니다 *길이* 변수입니다. 다음과 같은 위치에 사용됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

### <a name="column_entry_length_status"></a> COLUMN_ENTRY_LENGTH_STATUS

데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 열 번호입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

이 매크로는 길이 및 상태 변수를 지원하려는 경우에 사용합니다. 다음과 같은 위치에 사용됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

### <a name="column_entry_ps"></a> COLUMN_ENTRY_PS

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 열 번호입니다.

*nPrecision*<br/>
[in] 바인딩하려는 열의 최대 정밀도입니다.

*nScale*<br/>
[in] 바인딩할 열의 배율입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

바인딩할 열의 정밀도 및 배율을 지정할 수 있습니다. 다음과 같은 위치에 사용됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

### <a name="column_entry_ps_length"></a> COLUMN_ENTRY_PS_LENGTH

데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 하나를 사용 하 여 시작 하는 열 번호입니다. 책갈피 열 0에 해당합니다.

*nPrecision*<br/>
[in] 바인딩하려는 열의 최대 정밀도입니다.

*nScale*<br/>
[in] 바인딩할 열의 배율입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

바인딩할 열의 정밀도 및 배율을 지정할 수 있습니다. 이 매크로 지원 합니다 *길이* 변수입니다. 다음과 같은 위치에 사용됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

### <a name="column_entry_ps_length_status"></a> COLUMN_ENTRY_PS_LENGTH_STATUS

데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 열 번호입니다.

*nPrecision*<br/>
[in] 바인딩하려는 열의 최대 정밀도입니다.

*nScale*<br/>
[in] 바인딩할 열의 배율입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

바인딩할 열의 정밀도 및 배율을 지정할 수 있습니다. 이 매크로는 길이 및 상태 변수를 지원하려는 경우에 사용합니다. 다음과 같은 위치에 사용됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

### <a name="column_entry_ps_status"></a> COLUMN_ENTRY_PS_STATUS

데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 열 번호입니다.

*nPrecision*<br/>
[in] 바인딩하려는 열의 최대 정밀도입니다.

*nScale*<br/>
[in] 바인딩할 열의 배율입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

바인딩할 열의 정밀도 및 배율을 지정할 수 있습니다. 이 매크로 지원 합니다 *상태* 변수입니다. 다음과 같은 위치에 사용됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

### <a name="column_entry_status"></a> COLUMN_ENTRY_STATUS

데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)
```

#### <a name="parameters"></a>매개 변수

참조 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

*nOrdinal*<br/>
[in] 열 번호입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

이 매크로 지원 합니다 *상태* 변수입니다. 다음과 같은 위치에 사용됩니다.

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

### <a name="column_entry_type"></a> COLUMN_ENTRY_TYPE

데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 *형식* 매개 변수입니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)
```

#### <a name="parameters"></a>매개 변수

*nOrdinal*<br/>
[in] 열 번호입니다.

*wType*<br/>
[in] 데이터 형식 열 항목입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

이 매크로 특수 한 변형 합니다 [COLUMN_ENTRY](../../data/oledb/column-entry.md) 데이터 형식을 지정 하는 수단을 제공 하는 매크로입니다.

### <a name="column_entry_type_size"></a> COLUMN_ENTRY_TYPE_SIZE

데이터베이스에서 특정 열에 대 한 바인딩을 나타냅니다. 지원 *형식* 하 고 *크기* 매개 변수입니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)
```

#### <a name="parameters"></a>매개 변수

*nOrdinal*<br/>
[in] 열 번호입니다.

*wType*<br/>
[in] 데이터 형식 열 항목입니다.

*nLength*<br/>
[in] 크기 (바이트)에서 열 항목입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

이 매크로 특수 한 변형 합니다 [COLUMN_ENTRY](../../data/oledb/column-entry.md) 데이터 크기 및 유형을 지정 하는 수단을 제공 하는 매크로입니다.

### <a name="column_name"></a> COLUMN_NAME

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_ENTRY](../../data/oledb/column-entry.md)한다는 점을 제외 하이 매크로 열 번호를 하는 대신 열 이름을 사용 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME(pszName, data)
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

COLUMN_NAME_ * 매크로와 동일한 위치에서 사용 하는 [COLUMN_ENTRY](../../data/oledb/column-entry.md):

- 간의 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 하 고 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.

- 간의 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.

- 간의 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 하 고 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.

### <a name="column_name_ex"></a> COLUMN_NAME_EX

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)한다는 점을 제외 하이 매크로 데이터 형식, 크기, 정밀도, 배율, 열 길이 및 열 상태에도 사용 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*wType*<br/>
[in] 데이터 형식입니다.

*nLength*<br/>
[in] 데이터 크기 (바이트)입니다.

*nPrecision*<br/>
[in] 데이터를 가져올 때 사용 하 여 최대 전체 자릿수와 *wType* 는 `DBTYPE_NUMERIC`합니다. 그렇지 않으면이 매개 변수가 무시 됩니다.

*nScale*<br/>
[in] 데이터를 가져올 때 사용 하도록 눈금 및 *wType* 됩니다 `DBTYPE_NUMERIC` 또는 `DBTYPE_DECIMAL`합니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_length"></a> COLUMN_NAME_LENGTH

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)이 매크로 열 길이 사용 한다는 점을 제외 하면, 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_LENGTH(pszName, data, length)
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_length_status"></a> COLUMN_NAME_LENGTH_STATUS

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)열 길이 및 상태 열에도이 매크로 사용 한다는 점을 제외 하면, 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_ps"></a> COLUMN_NAME_PS

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)한다는 점을 제외 하이 매크로 전체 자릿수 및 소수에도 사용 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*nPrecision*<br/>
[in] 바인딩하려는 열의 최대 정밀도입니다.

*nScale*<br/>
[in] 바인딩할 열의 배율입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_ps_length"></a> COLUMN_NAME_PS_LENGTH

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)이 매크로 전체 자릿수, 소수 자릿수 및 열 길이 사용 한다는 점을 제외 하면, 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*nPrecision*<br/>
[in] 바인딩하려는 열의 최대 정밀도입니다.

*nScale*<br/>
[in] 바인딩할 열의 배율입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_ps_length_status"></a> COLUMN_NAME_PS_LENGTH_STATUS

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)단 정밀도, 배율, 열 길이 및 열 상태에도이 매크로, 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*nPrecision*<br/>
[in] 바인딩하려는 열의 최대 정밀도입니다.

*nScale*<br/>
[in] 바인딩할 열의 배율입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*length*<br/>
[in] 열 길이에 바인딩할 변수입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_ps_status"></a> COLUMN_NAME_PS_STATUS

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)이 매크로 전체 자릿수, 소수 자릿수 및 열 상태를 사용 한다는 점을 제외 하면, 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*nPrecision*<br/>
[in] 바인딩하려는 열의 최대 정밀도입니다.

*nScale*<br/>
[in] 바인딩할 열의 배율입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_status"></a> COLUMN_NAME_STATUS

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)이 매크로 열 상태를 사용 한다는 점을 제외 하면, 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_STATUS(pszName, data, status )
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_type"></a> COLUMN_NAME_TYPE

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)이 매크로 또한 데이터 형식을 사용 한다는 점을 제외 하면, 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_TYPE(pszName, wType, data)
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*wType*<br/>
[in] 데이터 형식입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_type_ps"></a> COLUMN_NAME_TYPE_PS

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)한다는 점을 제외 하이 매크로 데이터 형식, 전체 자릿수 및 크기 조정에도 사용 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*wType*<br/>
[in] 데이터 형식입니다.

*nPrecision*<br/>
[in] 데이터를 가져올 때 사용 하 여 최대 전체 자릿수와 *wType* 는 `DBTYPE_NUMERIC`합니다. 그렇지 않으면이 매개 변수가 무시 됩니다.

*nScale*<br/>
[in] 데이터를 가져올 때 사용 하도록 눈금 및 *wType* 됩니다 `DBTYPE_NUMERIC` 또는 `DBTYPE_DECIMAL`합니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_type_size"></a> COLUMN_NAME_TYPE_SIZE

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)한다는 점을 제외 하이 매크로 데이터 형식 및 크기에도 사용 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*wType*<br/>
[in] 데이터 형식입니다.

*nLength*<br/>
[in] 데이터 크기 (바이트)입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="column_name_type_status"></a> COLUMN_NAME_TYPE_STATUS

행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷합니다 [COLUMN_NAME](../../data/oledb/column-name.md)이 매크로 데이터 형식과 열 상태를 사용 한다는 점을 제외 하면, 합니다.

#### <a name="syntax"></a>구문

```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)
```

#### <a name="parameters"></a>매개 변수

*pszName*<br/>
[in] 열 이름에 대 한 포인터입니다. 이름에 유니코드 문자열 이어야 합니다. 예를 들어 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.

*wType*<br/>
[in] 데이터 형식입니다.

*status*<br/>
[in] 열 상태에 바인딩할 변수입니다.

*data*<br/>
[in] 사용자 레코드에서 해당 데이터 멤버입니다.

#### <a name="remarks"></a>설명

참조 [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * 매크로 사용 되는 위치에 대 한 정보에 대 한 합니다.

### <a name="end_column_map"></a> END_COLUMN_MAP

열 맵 항목의 끝을 표시 합니다.

#### <a name="syntax"></a>구문

```cpp
END_COLUMN_MAP()
```

#### <a name="remarks"></a>설명

행 집합에서 단일 접근자를 사용 하 여 사용 됩니다. BEGIN_COLUMN_MAP 매크로 END_COLUMN_MAP 매크로 사용 하 여 완료 됩니다.

#### <a name="example"></a>예제

See [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).

### <a name="define_command"></a> DEFINE_COMMAND

사용 하는 경우 행 집합을 만드는 데 사용할 명령을 지정 합니다 [CCommand](../../data/oledb/ccommand-class.md) 클래스입니다. 지정 된 응용 프로그램 형식 (ANSI 또는 유니코드)와 일치 하는 문자열 형식만 허용 합니다.

> [!NOTE]
>  사용 하는 것이 좋습니다 [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) DEFINE_COMMAND 대신 합니다.

#### <a name="syntax"></a>구문

```cpp
DEFINE_COMMAND(x, szCommand)
```

#### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 사용자 레코드 (명령) 클래스의 이름입니다.

*szCommand*<br/>
[in] 사용 하는 경우 행 집합을 만드는 데 사용할 수 있는 명령 문자열 [CCommand](../../data/oledb/ccommand-class.md)합니다.

#### <a name="remarks"></a>설명

지정 하는 명령 문자열에서 명령 텍스트를 지정 하지 않으면 기본적으로 사용 됩니다 합니다 [ccommand:: Open](../../data/oledb/ccommand-open.md) 메서드.

이 매크로를 유니코드로 응용 프로그램을 빌드할 경우 ANSI로 응용 프로그램을 빌드할 경우 ANSI 문자열 또는 유니코드 문자열을 허용 합니다. 사용 하는 것이 좋습니다 [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) DEFINE_COMMAND, 대신 전자는 ANSI 또는 유니코드 응용 프로그램 종류에 관계 없이 유니코드 문자열을 수락 하므로 합니다.

#### <a name="example"></a>예제

참조 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)합니다.

### <a name="define_command_ex"></a> DEFINE_COMMAND_EX

사용 하는 경우 행 집합을 만드는 데 사용할 명령을 지정 합니다 [CCommand](../../data/oledb/ccommand-class.md) 클래스입니다. 유니코드 및 ANSI 응용 프로그램을 지원합니다.

#### <a name="syntax"></a>구문

```cpp
DEFINE_COMMAND_EX(x, wszCommand)
```

#### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 사용자 레코드 (명령) 클래스의 이름입니다.

*wszCommand*<br/>
[in] 사용 하는 경우 행 집합을 만드는 데 사용할 수 있는 명령 문자열 [CCommand](../../data/oledb/ccommand-class.md)합니다.

#### <a name="remarks"></a>설명

지정 하는 명령 문자열에서 명령 텍스트를 지정 하지 않으면 기본적으로 사용 됩니다 합니다 [ccommand:: Open](../../data/oledb/ccommand-open.md) 메서드.

이 매크로 응용 프로그램 종류에 관계 없이 유니코드 문자열을 허용합니다. 이 매크로 보다 선호 [DEFINE_COMMAND](../../data/oledb/define-command.md) 유니코드를 지원 하기 때문에 ANSI 응용 프로그램 뿐만 아니라 합니다.

#### <a name="example"></a>예제

참조 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)합니다.

### <a name="begin_param_map"></a> BEGIN_PARAM_MAP

매개 변수가 맵 항목의 시작을 표시 합니다.

#### <a name="syntax"></a>구문

```cpp
BEGIN_PARAM_MAP(x)
```

#### <a name="parameters"></a>매개 변수

*x*<br/>
[in] 사용자 레코드 클래스의 이름입니다.

#### <a name="remarks"></a>설명

매개 변수를 사용 하 여 [명령](/previous-versions/windows/desktop/ms724608(v=vs.85))입니다.

#### <a name="example"></a>예제

예제를 참조 합니다 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 매크로입니다.

### <a name="end_param_map"></a> END_PARAM_MAP

매개 변수가 맵 항목의 끝을 표시 합니다.

#### <a name="syntax"></a>구문

```cpp
END_PARAM_MAP()
```

#### <a name="example"></a>예제

예제를 참조 합니다 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 매크로입니다.

### <a name="set_param_type"></a> SET_PARAM_TYPE

SET_PARAM_TYPE 매크로 입력, 출력 또는 입력/출력 다음에 나오는 COLUMN_ENTRY 매크로 지정 합니다.

#### <a name="syntax"></a>구문

```cpp
SET_PARAM_TYPE(type)
```

#### <a name="parameters"></a>매개 변수

*type*<br/>
[in] 매개 변수에 대해 설정할 형식입니다.

#### <a name="remarks"></a>설명

공급자는 기본 데이터 소스에서 지원되는 매개 변수 입력/출력 형식만 지원합니다. 형식은 하나 이상의 조합 `DBPARAMIO` 값 (참조 [DBBINDING 구조체](/previous-versions/windows/desktop/ms716845(v=vs.85)) 에 *OLE DB Programmer's Reference*):

- `DBPARAMIO_NOTPARAM` 접근자에 매개 변수가 없습니다. 일반적으로 설정한 `eParamIO` 이 값 행 접근자에서 사용자 매개 변수가 무시 됩니다.

- `DBPARAMIO_INPUT` 입력된 매개 변수입니다.

- `DBPARAMIO_OUTPUT` 출력 매개 변수입니다.

- `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT` 입력 및 출력 매개 변수입니다.

#### <a name="example"></a>예제

```cpp
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)