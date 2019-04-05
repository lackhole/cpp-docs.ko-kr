---
title: 업데이트 가능 공급자 만들기
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: d3f8314e7cd57617e35e50a67a4562d4055cb93a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024741"
---
# <a name="creating-an-updatable-provider"></a>업데이트 가능 공급자 만들기

업데이트할 수 있는 공급자 또는 공급자를 업데이트할 수 있는 visual c + + 지원 (쓸) 데이터 저장소입니다. 이 항목에서는 OLE DB 템플릿을 사용 하 여 업데이트할 수 있는 공급자를 만드는 방법을 설명 합니다.

이 항목에서는 작업 공급자를 사용 하 여 시작 한다고 가정 합니다. 업데이트 가능 공급자 만들기에 다음과 같은 두 단계가 있습니다. 어떻게 공급자는 변경 하는 데이터 저장소를 먼저 결정 해야 합니다. 특히, 변경 내용을 즉시 수행 해야 하는 여부를 update 명령이 실행 될 때까지 지연 합니다. 섹션 "[공급자 업데이트할 수 있도록](#vchowmakingprovidersupdatable)" 변경 내용과 공급자 코드에서 작업을 수행 하는 데 필요한 설정을 설명 합니다.

그런 다음 공급자 소비자가 요청 하는 아무 것도 지원 하기 위한 모든 기능이 포함 되어 있는지 확인 해야 합니다. 소비자를 데이터 저장소를 업데이트 하려는 경우 공급자는 데이터 저장소의 데이터를 유지 하는 코드를 포함 해야 합니다. 예를 들어, 데이터 원본에 따라 이러한 작업을 수행 하는 C 런타임 라이브러리 또는 MFC를 사용할 수 있습니다. 섹션 "[데이터 원본에 작성](#vchowwritingtothedatasource)" 데이터 원본에 작성, NULL이 고 기본 값을 처리 및 열 플래그를 설정 하는 방법을 설명 합니다.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) 은 업데이트할 수 있는 공급자의 예입니다. UpdatePV는 MyProv로 업데이트할 수 있는 지원과 동일합니다.

##  <a name="vchowmakingprovidersupdatable"></a> 메서드를 업데이트 가능 공급자 만들기

핵심 공급자를 업데이트할 수 있는 공급자를 데이터 저장소 및 해당 작업을 수행 하는 공급자를 원하는 방식에 대해 수행 하려는 작업 파악 합니다. 특히 중요 한 문제는 즉시 또는 지연 된 데이터 저장소에 대 한 업데이트 되는지 (일괄 처리) update 명령이 실행 될 때까지 합니다.

상속 여부를 먼저 결정 해야 합니다 `IRowsetChangeImpl` 또는 `IRowsetUpdateImpl` 행 집합 클래스에서. 이 중에서 어떤에 따라 구현에 세 가지 방법의 기능을 영향을 받게 됩니다. `SetData`, `InsertRows`, 및 `DeleteRows`합니다.

- 상속 하는 경우 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), 데이터 저장소 변경 즉시 이러한 세 가지 메서드를 호출 합니다.

- 상속 하는 경우 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), 메서드를 호출 하기 전에 데이터 저장소에 변경 내용을 연기 `Update`합니다 `GetOriginalData`, 또는 `Undo`합니다. 몇 가지 변경 사항을 포함 하는 업데이트를 일괄 처리 모드 (변경 내용 일괄 처리 상당한 메모리 오버 헤드를 추가할 수 있음을 참고)에서 수행 됩니다.

사실은 `IRowsetUpdateImpl` 에서 파생 `IRowsetChangeImpl`합니다. 따라서 `IRowsetUpdateImpl` 제공 기능 뿐만 아니라 일괄 처리 기능을 변경 합니다.

### <a name="to-support-updatability-in-your-provider"></a>업데이트를 지원 하려면 공급자에서

1. 행 집합 클래스에서 상속 `IRowsetChangeImpl` 또는 `IRowsetUpdateImpl`합니다. 이러한 클래스는 데이터 저장소 변경에 대 한 적절 한 인터페이스를 제공 합니다.

   **IRowsetChange 추가**

   추가 `IRowsetChangeImpl` 이 형식을 사용 하 여 사용자가 상속 체인을 합니다.

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   추가할 수도 `COM_INTERFACE_ENTRY(IRowsetChange)` 에 `BEGIN_COM_MAP` 행 집합 클래스에서 섹션입니다.

   **IRowsetUpdate 추가**

   추가 `IRowsetUpdate` 이 형식을 사용 하 여 사용자가 상속 체인을 합니다.

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > 제거 해야 합니다 `IRowsetChangeImpl` 상속 체인에 줄. 앞에서 언급 한 지시문이 한 가지 예외에 대 한 코드를 포함 해야 `IRowsetChangeImpl`합니다.

1. 다음을 고 COM 맵에 추가 합니다 (`BEGIN_COM_MAP ... END_COM_MAP`):

   |  구현 하는 경우   |           COM 맵에 추가             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | 구현 하는 경우 | 속성 집합 구조에 추가 |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. 명령에 다음 속성 집합 맵에 추가 합니다 (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`):

   |  구현 하는 경우   |                                             속성 집합 구조에 추가                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. 사용자 속성 집합 구조의 포함 해야 다음 설정 중 모든 아래 나타나는:

    ```cpp
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)

    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)
    ```

   속성 Id 및 값을 Atldb.h에 검색 하 여 이러한 매크로 호출에 사용 되는 값을 찾을 수 있습니다 (Atldb.h 온라인 설명서와 다른 경우 Atldb.h 대체 설명서).

   > [!NOTE]
   > 많은 합니다 `VARIANT_FALSE` 및 `VARIANT_TRUE` 설정은 OLE DB 템플릿에서 필요; OLE DB 사양은 읽기/쓰기 수 하지만 OLE DB 템플릿 하나의 값을 하나만 지원할 수 있습니다.

   **IRowsetChangeImpl를 구현 하는 경우**

   구현 하는 경우 `IRowsetChangeImpl`를 공급자에는 다음 속성을 설정 해야 합니다. 이러한 속성을 통해 인터페이스를 요청 사용 주로 `ICommandProperties::SetProperties`합니다.

   - `DBPROP_IRowsetChange`: 자동으로 설정은 `DBPROP_IRowsetChange`합니다.

   - `DBPROP_UPDATABILITY`: 지원 되는 메서드를 지정 하는 비트 마스크 `IRowsetChange`: `SetData`하십시오 `DeleteRows`, 또는 `InsertRow`.

   - `DBPROP_CHANGEINSERTEDROWS`: 소비자를 호출할 수 있습니다 `IRowsetChange::DeleteRows` 또는 `SetData` 새로 삽입된 된 행에 대 한 합니다.

   - `DBPROP_IMMOBILEROWS`: 행 집합 삽입 되거나 업데이트 된 행 순서를 바꾸지 않습니다.

   **IRowsetUpdateImpl를 구현 하는 경우**

   구현 하는 경우 `IRowsetUpdateImpl`를 설정 해야 다음 속성을 공급자 뿐만 아니라 모든 속성을 설정 하 `IRowsetChangeImpl` 위에 나열 된:

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.

   - `DBPROP_OWNUPDATEDELETE`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.

   - `DBPROP_OTHERINSERT`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.

   - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.

   - `DBPROP_REMOVEDELETED`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > 알림을 지 원하는 경우 해야 할 수 있습니다 다른 속성 에서도; 섹션을 참조 `IRowsetNotifyCP` 이 목록에 대 한 합니다.

##  <a name="vchowwritingtothedatasource"></a> 데이터 원본에 쓰기

데이터 원본에서 읽기 호출을 `Execute` 함수입니다. 데이터 원본에 쓸 호출을 `FlushData` 함수입니다. (일반적인 의미에서 플러시 테이블 또는 인덱스를 디스크에 수정 내용을 저장 하는 수단입니다.)

```cpp
FlushData(HROW, HACCESSOR);
```

행 핸들 (HROW) 및 접근자 핸들 (HACCESSOR) 인수를 사용 하면 쓸 지역을 지정할 수 있습니다. 일반적으로 한 번에 단일 데이터 필드를 작성합니다.

`FlushData` 메서드는 원래 저장 된 형식으로 데이터를 씁니다. 이 함수를 재정의 하지 않는 경우에 공급자는 제대로 작동 하지만 변경 내용을 데이터 저장소로 플러시되지 않습니다.

### <a name="when-to-flush"></a>플러시 하는 경우

공급자 템플릿 데이터를 데이터 저장소에 쓸 때마다 FlushData 호출 이 일반적으로 (항상 그렇지는 않지만) 결과로 발생 하는 다음 함수 호출:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (새 데이터 행에 삽입할 경우)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>작동 방법

소비자 (예: 업데이트) 플러시를 필요로 하는 호출을 만들고이 호출은 항상 다음을 수행 하는 공급자에 게 전달 됩니다.

- 호출 `SetDBStatus` 바인딩된 상태 값이 있을 때마다 합니다.

- 열의 플래그를 확인합니다.

- `IsUpdateAllowed`.

다음 세 단계를 보안을 제공 합니다. 공급자 호출 `FlushData`합니다.

### <a name="how-to-implement-flushdata"></a>FlushData를 구현 하는 방법

구현 `FlushData`, 몇 가지 문제를 고려해 야 할 필요 합니다.

데이터 저장소에 변경 내용을 처리할 수 있도록 되었는지 확인 하십시오.

NULL 값을 처리 합니다.

### <a name="handling-default-values"></a>기본 값을 처리 합니다.

자체적으로 구현 하려면 `FlushData` 메서드를 해야 합니다.

- 행 집합 클래스를 이동 합니다.

- 행 집합 클래스 선언의 넣습니다.

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- 구현을 제공 `FlushData`합니다.

제대로 구현 하면 `FlushData` 행과 실제로 업데이트 된 열만을 저장 합니다. 현재 행 및 최적화에 대 한 저장 되는 열을 결정 하는 HROW 및 HACCESSOR 매개 변수를 사용할 수 있습니다.

일반적으로 가장 큰 문제는 사용자의 기본 데이터 저장소를 사용 하 여 작동지 않습니다. 가능한 경우 하려고 합니다.

- 가능한 간단 하 게 데이터 저장소에 쓰는 메서드를 유지 합니다.

- (선택 사항 이지만 권장) NULL 값을 처리 합니다.

- 기본값 (선택 사항 이지만 권장)를 처리 합니다.

가장 좋은 점은 실제 값을 지정 NULL 값과 기본값에 대 한 데이터 저장소에서 하는 것입니다. 이 데이터를 추정할 수 있습니다 하는 것이 좋습니다. 그렇지 않은 경우 NULL 값과 기본값을 사용할 수 없도록는 것이 좋습니다.

다음 예제와 어떻게 `FlushData` 에서 구현 되는 `RUpdateRowset` 클래스는 `UpdatePV` 샘플 (샘플 코드에서 Rowset.h 참조):

```cpp
///////////////////////////////////////////////////////////////////////////
// class RUpdateRowset (in rowset.h)
...
HRESULT FlushData(HROW, HACCESSOR)
{
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");

    USES_CONVERSION;
    enum {
        sizeOfString = 256,
        sizeOfFileName = MAX_PATH
    };
    FILE*    pFile = NULL;
    TCHAR    szString[sizeOfString];
    TCHAR    szFile[sizeOfFileName];
    errcode  err = 0;

    ObjectLock lock(this);

    // From a filename, passed in as a command text,
    // scan the file placing data in the data array.
    if (m_strCommandText == (BSTR)NULL)
    {
        ATLTRACE( "RRowsetUpdate::FlushData -- "
                  "No filename specified\n");
        return E_FAIL;
    }

    // Open the file
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));
    if ((szFile[0] == _T('\0')) ||
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))
    {
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");
        return DB_E_NOTABLE;
    }

    // Iterate through the row data and store it.
    for (long l=0; l<m_rgRowData.GetSize(); l++)
    {
        CAgentMan am = m_rgRowData[l];

        _putw((int)am.dwFixed, pFile);

        if (_tcscmp(&am.szCommand[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);
    }

    if (fflush(pFile) == EOF || fclose(pFile) == EOF)
    {
        ATLTRACE("RRowsetUpdate::FlushData -- "
                 "Couldn't flush or close file\n");
    }

    return S_OK;
}
```

### <a name="handling-changes"></a>변경 내용 처리

변경 내용을 처리 하 여 공급자에 대 한 먼저 데이터 저장소 (예: 텍스트 파일 또는 비디오 파일)을 변경할 수 있도록 하는 시설에 있는지 확인 해야 합니다. 표시 되지 않는 경우 공급자 프로젝트에서 개별적으로 해당 코드를 만들 해야 있습니다.

### <a name="handling-null-data"></a>NULL 데이터를 처리합니다.

최종 사용자가 NULL 데이터를 보내는 것 같습니다. 데이터 소스의 필드에 NULL 값을 작성 하는 경우 문제가 있을 수 있습니다. 도시 및 우편 번호;에 대 한 값을 허용 하는 주문 처리 응용 프로그램 이런 배달 불가능 하기 때문에 값 중 하나 또는 둘 다 있지만 둘 다 하지 수락할 수 있습니다. 따라서 특정 조합의 응용 프로그램에 의미 있는 필드에 NULL 값을 제한 해야 합니다.

공급자 개발자는 데이터를 저장 하는 방법, 데이터 저장소에서 데이터를 읽는 방법 및 방법을 지정 하는 사용자에 게 고려해 야 합니다. 데이터 원본에서 데이터 행 집합의 데이터 상태를 변경 하는 방법을 고려해 야 하는 구체적으로 (예: DataStatus = NULL). 소비자가 NULL 값을 포함 하는 필드에 액세스할 때 반환할 값을 결정 해야 합니다.

UpdatePV 예제의 코드를 확인 공급자를 NULL 데이터를 처리할 수 있는 방법을 보여 줍니다. UpdatePV, 공급자 문자열 "NULL"을 작성 하 여 NULL 데이터를 데이터 저장소에 저장 합니다. 데이터 저장소에서 NULL 데이터를 읽을 때 해당 문자열을 확인 한 다음 NULL 문자열을 만들어 버퍼를 비웁니다. 역시 재정의 `IRowsetImpl::GetDBStatus` 데이터 값이 비어 있는 경우에 DBSTATUS_S_ISNULL을 반환 합니다.

### <a name="marking-nullable-columns"></a>Null 허용 열 표시

또한 스키마 행 집합을 구현 하는 경우 (참조 `IDBSchemaRowsetImpl`), 열이 null을 허용함 구현 (일반적으로 공급자에서으로 표시 CxxxSchemaColSchemaRowset) DBSCHEMA_COLUMNS 행 집합에서 지정 해야 합니다.

모든 null 허용 열 포함 버전 DBCOLUMNFLAGS_ISNULLABLE 값을 지정 해야 합니다 `GetColumnInfo`합니다.

OLE DB 템플릿 구현에서 null 허용으로 열을 표시 하지 않으면 공급자 가정는 값을 포함 해야 하며 null 값을 전송 하기 위해 소비자를 허용 하지 것입니다.

다음 예제와 방법을 `CommonGetColInfo` CUpdateCommand 함수 구현 됩니다 (UpProvRS.cpp 참조) UpdatePV에서. 어떻게 열에 null 허용 열에 대 한이 DBCOLUMNFLAGS_ISNULLABLE note 합니다.

```cpp
/////////////////////////////////////////////////////////////////////////////
// CUpdateCommand (in UpProvRS.cpp)

ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)
{
    static ATLCOLUMNINFO _rgColumns[6];
    ULONG ulCols = 0;

    if (bBookmark)
    {
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                            sizeof(DWORD), DBTYPE_BYTES,
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                            DBCOLUMNFLAGS_ISBOOKMARK)
        ulCols++;
    }

    // Next set the other columns up.
    // Add a fixed length entry for OLE DB conformance testing purposes
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,
                        10, 255, GUID_NULL, CAgentMan, dwFixed,
                        DBCOLUMNFLAGS_WRITE |
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    if (pcCols != NULL)
    {
        *pcCols = ulCols;
    }

    return _rgColumns;
}
```

### <a name="default-values"></a>기본값

NULL 데이터와 마찬가지로 기본값을 변경 하 여 처리할을 해야 합니다.

기본값인 `FlushData` 고 `Execute` S_OK를 반환 하는 것입니다. 따라서이 함수를 재정의 하지 않으면 하는 경우 변경 내용이 표시 되려면 (S_OK가 반환 되어), 데이터 저장소에 전송 되지 않게 됩니다.

에 `UpdatePV` 샘플 (Rowset.h)는 `SetDBStatus` 메서드 기본 값을 다음과 같이 처리:

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,
                            ATLCOLUMNINFO* pColInfo)
{
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);

    void* pData = NULL;
    char* pDefaultData = NULL;
    DWORD* pFixedData = NULL;

    switch (*pdbStatus)
    {
        case DBSTATUS_S_DEFAULT:
            pData = (void*)&m_rgRowData[pRow->m_iRowset];
            if (pColInfo->wType == DBTYPE_STR)
            {
                pDefaultData = (char*)pData + pColInfo->cbOffset;
                strcpy_s(pDefaultData, "Default");
            }
            else
            {
                pFixedData = (DWORD*)((BYTE*)pData +
                                          pColInfo->cbOffset);
                *pFixedData = 0;
                return S_OK;
            }
            break;
        case DBSTATUS_S_ISNULL:
        default:
            break;
    }
    return S_OK;
}
```

### <a name="column-flags"></a>열 플래그

메타 데이터를 사용 하 여 설정 해야 하는 열에 기본값을 지원 합니다 \<공급자 클래스\>SchemaRowset 클래스입니다. `m_bColumnHasDefault = VARIANT_TRUE`를 설정합니다.

열거 형식의 DBCOLUMNFLAGS를 사용 하 여 지정 된 열의 플래그를 설정을 해야 합니다. 열 플래그 열 특성을 설명 합니다.

예를 들어 합니다 `CUpdateSessionColSchemaRowset` 클래스의 `UpdatePV` (Session.h)에서 첫 번째 열은 이런 방식이으로 설정:

```cpp
// Set up column 1
trData[0].m_ulOrdinalPosition = 1;
trData[0].m_bIsNullable = VARIANT_FALSE;
trData[0].m_bColumnHasDefault = VARIANT_TRUE;
trData[0].m_nDataType = DBTYPE_UI4;
trData[0].m_nNumericPrecision = 10;
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));
m_rgRowData.Add(trData[0]);
```

이 코드 지정 무엇 보다도 열 지원 하 고 기본값은 0으로 쓰기를 가능 하 고 열의 모든 데이터가 동일한 길이 갖도록 하 합니다. 가변 길이 열에 데이터를 원하는 경우이 플래그를 설정 하지 것입니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 만들기](creating-an-ole-db-provider.md)