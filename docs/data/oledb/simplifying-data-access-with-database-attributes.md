---
title: 데이터베이스 특성을 사용하여 데이터 액세스 단순화
ms.date: 10/19/2018
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc-attr.db_source
helpviewer_keywords:
- attributes [C++], database
- attributes [C++], data access
- databases [C++], attributes
- data [C++], simplifying access
- data access [C++], database attributes
- database attributes [C++]
- OLE DB consumers [C++], database attributes
- attributes [C++], OLE DB consumer
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
ms.openlocfilehash: 83519ffff7dd1f1b5f8a635f094932a1f9728193
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031052"
---
# <a name="simplifying-data-access-with-database-attributes"></a>데이터베이스 특성을 사용하여 데이터 액세스 단순화

이 항목에서는 데이터베이스 작업을 간소화 하기 위해 데이터베이스 특성을 사용 하는 방법을 보여 줍니다.

데이터베이스에서 정보에 액세스 하는 기본 방법은 데이터베이스에서 명령 (또는 테이블) 클래스 및 특정 테이블에 대 한 사용자 레코드 클래스를 만드는 경우 데이터베이스 특성을 이전에 수행 해야 하 고 템플릿 선언의 일부를 간소화 합니다.

데이터베이스 특성의 사용을 보여 주기 위해 다음 섹션에서는 두 개의 동일한 테이블 및 사용자 레코드 클래스 선언이 표시 합니다: 첫 번째 특성을 사용 하 고 두 번째 OLE DB 템플릿을 사용 합니다. 이러한 선언 코드는 일반적으로 authors.h 예를 들어, 테이블 또는 명령 개체에 대 한 헤더 파일에 들어 있습니다.

두 파일을 비교 하 여 특성을 사용 하는 훨씬 간단 하다 볼 수 있습니다. 차이점 중:

- 특성을 사용 하기만 하면 하나의 클래스를 선언 합니다. `CAuthors`템플릿을 사용 하 여 두 선언 해야 하는 동안,: `CAuthorsNoAttrAccessor` 및 `CAuthorsNoAttr`.

- 합니다 `db_source` 특성이 지정 된 버전에서 호출 하는 것은 `OpenDataSource()` 템플릿 선언에서 호출 합니다.

- `db_table` 호출 특성이 지정 된 버전에서 다음 템플릿 선언 하는 것:

    ```cpp
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
    ```

- 합니다 `db_column` 특성이 지정 된 버전에서의 호출은 열 지도에 해당 하는 (참조 `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) 템플릿 선언의 합니다.

사용자 레코드 클래스 선언을 삽입 합니다. 사용자 레코드 클래스는 같음 `CAuthorsNoAttrAccessor` 템플릿 선언의 합니다. 테이블 클래스 이면 `CAuthors`에 삽입된 사용자 레코드 클래스 라고 `CAuthorsAccessor`, 삽입 된 코드에서 선언 에서만 볼 수 있습니다. 자세한 내용은 "특성 삽입 사용자 레코드 클래스"를 참조 하세요 [사용자 레코드](../../data/oledb/user-records.md)합니다.

특성 사용 및 템플릿 기반 코드에서 사용 하 여 행 집합 속성을 설정 해야 `CDBPropSet::AddProperty`합니다.

이 항목에서 설명 하는 특성에 대 한 정보를 참조 하세요 [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)합니다.

> [!NOTE]
> 다음 `include` 문 아래 예제를 컴파일하는 데 필요 합니다.
> ```cpp
> #include <atlbase.h>
> #include <atlplus.h>
> #include <atldbcli.h>
> ```

## <a name="table-and-accessor-declaration-using-attributes"></a>테이블 및 특성을 사용 하 여 접근자 선언

다음 코드 호출 `db_source` 및 `db_table` 의 테이블 클래스입니다. `db_source` 데이터 원본 및 사용 하는 연결을 지정 합니다. `db_table` 테이블 클래스 선언에 적절 한 템플릿 코드를 삽입 합니다. `db_column` 열 지도 지정 하 고 접근자 선언의 삽입 합니다. Atl이 지원 하는 프로젝트에서 OLE DB 소비자 특성을 사용할 수 있습니다.

테이블 및 접근자 선언 특성을 사용 하는 다음과 같습니다.

```cpp
//////////////////////////////////////////////////////////////////////
// Table and accessor declaration using attributes
// authors.h
//////////////////////////////////////////////////////////////////////

// Table class declaration
// (Note that you must provide your own connection string for db_source.)
[
   db_source(L"your connection string"),
   db_table("Authors")
]
class CAuthors
{
public:
   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;
   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;
   [db_column("1", status = "m_dwAuIDStatus", length = "m_dwAuIDLength")] LONG m_AuID;
   [db_column("2", status = "m_dwAuthorStatus", length = "m_dwAuthorLength")] TCHAR m_Author[51];
   [db_column("3", status = "m_dwYearBornStatus", length = "m_dwYearBornLength")] SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
};
```

## <a name="table-and-accessor-declaration-using-templates"></a>테이블 및 템플릿을 사용 하 여 접근자 선언

템플릿을 사용 하 여 테이블 및 접근자 선언을 다음과 같습니다.

```cpp
//////////////////////////////////////////////////////////////////////
// Table and user record class declaration using templates
// authors.h
//////////////////////////////////////////////////////////////////////

// User record class declaration
class CAuthorsNoAttrAccessor
{
public:
   DWORD m_dwAuIDStatus;
   DWORD m_dwAuthorStatus;
   DWORD m_dwYearBornStatus;
   DWORD m_dwAuIDLength;
   DWORD m_dwAuthorLength;
   DWORD m_dwYearBornLength;
   LONG m_AuID;
   TCHAR m_Author[51];
   SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
   HRESULT OpenDataSource()
   {
      CDataSource _db;

HRESULT hr;
      hr = _db.OpenFromInitializationString(L"your connection string");
      if (FAILED(hr))
      {
#ifdef _DEBUG
         AtlTraceErrorRecords(hr);
#endif
         return hr;
      }
      return m_session.Open(_db);
   }
   void CloseDataSource()
   {
      m_session.Close();
   }
   operator const CSession&()
   {
      return m_session;
   }
   CSession m_session;
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)
   END_COLUMN_MAP()
};
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
{
public:
   HRESULT OpenAll()
   {
HRESULT hr;
      hr = OpenDataSource();
      if (FAILED(hr))
         return hr;
      __if_exists(GetRowsetProperties)
      {
         CDBPropSet propset(DBPROPSET_ROWSET);
         __if_exists(HasBookmark)
         {
            propset.AddProperty(DBPROP_IRowsetLocate, true);
         }
         GetRowsetProperties(&propset);
         return OpenRowset(&propset);
      }
      __if_not_exists(GetRowsetProperties)
      {
         __if_exists(HasBookmark)
         {
            CDBPropSet propset(DBPROPSET_ROWSET);
            propset.AddProperty(DBPROP_IRowsetLocate, true);
            return OpenRowset(&propset);
         }
      }
      return OpenRowset();
   }
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)
   {
HRESULT hr = Open(m_session, "Authors", pPropSet);
#ifdef _DEBUG
      if(FAILED(hr))
         AtlTraceErrorRecords(hr);
#endif
      return hr;
   }
   void CloseAll()
   {
      Close();
      CloseDataSource();
   }
};
```

## <a name="see-also"></a>참고자료

[OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)
