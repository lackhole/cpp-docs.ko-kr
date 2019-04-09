---
title: 스키마 행 집합을 사용하여 메타데이터 구하기
ms.date: 10/24/2018
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
ms.openlocfilehash: 12c3de79626411b76a402a7f5407f40a7b054318
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026031"
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>스키마 행 집합을 사용하여 메타데이터 구하기

행 집합을 열지 않고 공급자, 행 집합, 테이블, 열에 대한 정보나 다른 데이터베이스 정보를 구해야 하는 경우가 있습니다. 데이터베이스 구조에 대한 데이터는 메타데이터라고 하며 다양한 방법으로 검색할 수 있습니다. 한 가지 방법은 스키마 행 집합을 사용하는 것입니다.

OLE DB 템플릿은 스키마 정보를 검색 하는 클래스 집합을 제공 이러한 클래스 미리 정의 된 스키마 행 집합을 만들고에 나와 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)합니다.

> [!NOTE]
> OLAP를 사용 중이며 일부 행 집합이 스키마 행 집합 클래스에서 지원되지 않는 경우(예: 다양한 수의 열이 있는 경우) `CManualAccessor` 또는 `CDynamicAccessor`를 사용하는 것이 좋습니다. 열을 스크롤하고 case 문을 사용하여 각 열에 대한 가능한 데이터 형식을 처리할 수 있습니다.

## <a name="catalogschema-model"></a>카탈로그/스키마 모델

ANSI SQL은 데이터 저장소에 대한 카탈로그/스키마 모델을 정의합니다. OLE DB는 이 모델을 사용합니다. 이 모델에서는 카탈로그 (데이터베이스) 있는 스키마 및 스키마 테이블을 보유 합니다.

- **카탈로그** 카탈로그는 데이터베이스에 대 한 다른 이름입니다. 관련 된 스키마의 컬렉션입니다. 지정된 된 데이터 원본에 속한 카탈로그 (데이터베이스)를 나열 하려면 사용 하 여 [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md)합니다. 여러 데이터베이스에 카탈로그가 하나만 있으므로 메타 데이터 스키마 정보를 라고 합니다.

- **스키마** 스키마가 소유 하거나 특정 사용자가 만든 데이터베이스 개체의 컬렉션입니다. 지정된 된 사용자가 소유한 스키마를 나열 하려면 사용 하 여 [CSchemata](../../data/oledb/cschemata-cschematainfo.md)합니다.

   Microsoft SQL Server 및 ODBC 2.x 측면에서 스키마의 소유자 (예를 들어 dbo는 일반적인 스키마 이름임). SQL Server 테이블 집합에서 메타 데이터를 저장 하는 또한: 한 테이블에 있는 모든 테이블의 목록을 포함 하 고 다른 테이블에 있는 모든 열의 목록을 포함 합니다. Microsoft Access 데이터베이스에서 스키마에 해당 요소가 있습니다.

- **테이블** 테이블은 특정 순서로 정렬 하는 열의 컬렉션입니다. 해당 테이블에 대 한 정보를 지정 된 카탈로그 (데이터베이스)에 정의 된 테이블을 나열 하려면 사용 하 여 [CTables](../../data/oledb/ctables-ctableinfo.md)).

## <a name="restrictions"></a>제한

스키마 정보를 쿼리할 때 관심 있는 정보 유형을 지정할 수 제한을 사용할 수 있습니다. 제한을 쿼리의 필터나 한정자로 생각할 수 있습니다. 예를 들어 다음 쿼리에서

```sql
SELECT * FROM authors WHERE l_name = 'pivo'
```

`l_name` 제한이 됩니다. 이것은 하나의 제한 사용 합니다;를 사용 하 여 간단한 예 스키마 행 집합 클래스에는 몇 가지 제한을 지원 합니다.

합니다 [스키마 행 집합 typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) 인스턴스화하고 열어 하 여 다른 행 집합 처럼 스키마 행 집합을 액세스할 수 있도록 모든 OLE DB 스키마 행 집합을 캡슐화 합니다. 예를 들어 typedef 클래스 [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) 으로 정의 됩니다.

```cpp
CRestrictions<CAccessor<CColumnsInfo>
```

합니다 [CRestrictions](../../data/oledb/crestrictions-class.md) 클래스는 제한을 지원 제공 합니다. 스키마 행 집합의 인스턴스를 만든 후 호출 [crestrictions:: Open](../../data/oledb/crestrictions-open.md)합니다. 이 메서드는 지정하는 제한을 기반으로 결과 집합을 반환합니다.

제한 지정, 참조 [부록 b: 스키마 행 집합](/previous-versions/windows/desktop/ms712921(v=vs.85)) 및 사용 하는 행 집합을 조회 합니다. 예를 들어 `CColumns` 에 해당 하는 [COLUMNS 행 집합](/previous-versions/windows/desktop/ms723052(v=vs.85));에서는 COLUMNS 행 집합에서 제한 열이 나열: TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME. 제한을 지정할 때 이 순서를 따라야 합니다.

따라서 예를 들어 테이블 이름으로 제한 하려는 경우 TABLE_NAME는 세 번째 제한 열 및 호출 `Open`, 다음 예제에서와 같이 원하는 테이블 이름을 세 번째 제한 매개 변수로 지정 합니다.

### <a name="to-use-schema-rowsets"></a>스키마 행 집합을 사용하려면

1. 헤더 파일 포함 `Atldbsch.h` (해야 `Atldbcli.h` 물론 소비자 지원을 위해).

1. 소비자의 헤더 파일이나 문서의 헤더 파일에서 스키마 행 집합 개체를 인스턴스화합니다. 테이블 정보를 원하는 경우에 선언 된 `CTables` 개체; 열 정보를 원하는 경우에 선언를 `CColumns` 개체. 이 예제에서는 authors 테이블의 열을 검색하는 방법을 보여 줍니다.

    ```cpp
    CDataSource ds;
    ds.Open();
    CSession ss;
    ss.Open(ds);
    CColumns columnSchemaRowset;
    // TABLE_NAME is the third restriction column, so
    // specify "authors" as the third restriction parameter:
    HRESULT hr = columnSchemaRowset.Open(ss, NULL, NULL, L"authors");
    hr = columnSchemaRowset.MoveFirst();
    while (hr == S_OK)
    {
       hr = columnSchemaRowset.MoveNext();
    }
    ```

1. 정보를 가져오려면 스키마 행 집합 개체의 적절한 데이터 멤버에 액세스합니다(예: `ColumnSchemaRowset.m_szColumnName`). 이 데이터 멤버는 COLUMN_NAME에 해당 합니다. 각 데이터 멤버에 해당 하는 OLE DB 열을 보려면 [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)합니다.

스키마 행 집합의 참조를 OLE DB 템플릿에서 typedef 클래스가 제공 (참조 [스키마 행 집합 클래스 및 Typedef 클래스](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)).

제한 열을 포함 하 여 OLE DB 스키마 행 집합에 대 한 자세한 내용은 참조 하세요. [부록 b: 스키마 행 집합](/previous-versions/windows/desktop/ms712921(v=vs.85)) 에 **OLE DB Programmer's Reference**합니다.

스키마 행 집합 클래스를 사용 하는 방법의 더 복잡 한 예제를 참조 하세요. 합니다 [CatDB](https://github.com/Microsoft/VCSamples) 하 고 [DBViewer](https://github.com/Microsoft/VCSamples) 샘플입니다.

스키마 행 집합에 대 한 공급자 지원에 대 한 자세한 내용은 [스키마 행 집합 지원](../../data/oledb/supporting-schema-rowsets.md)합니다.

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)