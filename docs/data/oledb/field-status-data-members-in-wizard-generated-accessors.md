---
title: 마법사 생성 접근자의 필드 상태 데이터 멤버
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
ms.openlocfilehash: dd650b7cafef78e23c23ddfef791c88b6b93727f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025074"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>마법사 생성 접근자의 필드 상태 데이터 멤버

사용 하는 경우는 **ATL OLE DB 소비자 마법사** 소비자를 만들려면 마법사를 열 지도에서 지정 하는 각 필드에 대 한 사용자 레코드 클래스의 데이터 멤버를 생성 합니다. 각 데이터 멤버는 형식의 `DWORD` 해당 필드에 해당 하는 상태 값을 포함 합니다.

데이터 멤버에 대 한 예를 들어 *m_OwnerID*, 필드의 상태에 대 한 추가 데이터 멤버를 생성 하는 마법사 (*dwOwnerIDStatus*) 및 필드 길이 대 한 다른 (*dwOwnerIDLength*). 또한 COLUMN_ENTRY_LENGTH_STATUS 엔터티와 함께 열 맵을 생성합니다.

이 다음 코드에 표시 됩니다.

```cpp
class CAuthorsAccessor
{
public:
   LONG m_AuID;
   TCHAR m_Author[53];
   LONG m_YearBorn;

   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;

   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;

    DEFINE_COMMAND_EX(CAuthorsAccessor, L" \
    SELECT \
        AuID, \
        Author, \
        YearBorn \
        FROM dbo.Authors")

    BEGIN_COLUMN_MAP(CAuthorsAccessor)
       COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)
       COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)
    END_COLUMN_MAP()
...
```

> [!NOTE]
> 사용자 레코드 클래스를 수정하거나 사용자 고유의 소비자를 작성하는 경우 데이터 변수가 상태 및 길이 변수 앞에 와야 합니다.

디버깅 목적으로 상태 값을 사용할 수 있습니다. 코드에서 생성 하는 경우는 **ATL OLE DB 소비자 마법사** 컴파일 오류를 생성 DB_S_ERRORSOCCURRED 또는 DB_E_ERRORSOCCURRED 등을 고려해 야 필드 상태 데이터 멤버의 현재 값입니다. 0이 아닌 값이 있는 잘못 된 열에 해당 합니다.

또한 특정 필드에 NULL 값을 설정 하는 상태 값을 사용할 수 있습니다. 이렇게 하면 0이 아닌 NULL로 필드 값을 구분 하고자 하는 경우에 도움이 됩니다. 유효한 값 또는 특수 한 값을 NULL 인지 여부를 결정 하 고 응용 프로그램 처리 해야 하는 방법을 결정 하는 것입니다. OLE DB 일반 NULL 값을 지정 하는 올바른 수단으로 DBSTATUS_S_ISNULL을 정의 합니다. 소비자 데이터를 읽고, 값이 null, status 필드 DBSTATUS_S_ISNULL에 설정 됩니다. 소비자를 NULL 값을 설정 하려는 소비자는 공급자를 호출 하기 전에 상태 값을 DBSTATUS_S_ISNULL을 설정 합니다.

다음으로 열고 Oledb.h DBSTATUSENUM 검색 합니다. DBSTATUSENUM 열거형 값에 대해 0이 아닌 상태를 나타내는 숫자 값을 일치 시킬 수 있습니다. 열거형 이름 무엇이 잘못 인지 여부를 알려줍니다. 즉, 충분 하지 않으면를 **상태** 항목에는 **바인딩 데이터 값** 부분을 [OLE DB Programmer's Guide](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). 이 항목의 상태 값을 가져오거나 데이터를 설정할 때 사용 되는 테이블을 포함 합니다. 길이 값에 대 한 자세한 내용은 합니다 **길이** 동일한 섹션에서 항목입니다.

## <a name="retrieving-the-length-or-status-of-a-column"></a>길이 또는 열의 상태를 검색합니다.

가변 길이 열의 길이 또는 열의 (DBSTATUS_S_ISNULL, 예를 들어 확인) 상태를 검색할 수 있습니다.

- 길이 가져오려면 COLUMN_ENTRY_LENGTH 매크로 사용 합니다.

- 상태를 가져오려면 COLUMN_ENTRY_STATUS 매크로 사용 합니다.

- 둘 다를 가져오려면 COLUMN_ENTRY_LENGTH_STATUS를 같이 사용 합니다.

    ```cpp
    class CProducts
    {
    public:
       char      szName[40];
       long      nNameLength;
       DBSTATUS   nNameStatus;

    BEGIN_COLUMN_MAP(CProducts)
    // Bind the column to CProducts.m_ProductName.
    // nOrdinal is zero-based, so the column number of m_ProductName is 1.
       COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)
    END_COLUMN_MAP()
    };
    ```

- 그런 다음에 액세스할 길이 및/또는 상태를 표시 된 것 처럼.

    ```cpp
    CTable<CAccessor<CProducts >> product;
    CSession session;

    product.Open(session, "Product");

    while (product.MoveNext() == S_OK)
    {
       // Check the product name isn't NULL before tracing it
       if (product.nNameStatus == DBSTATUS_S_OK)
          ATLTRACE("%s is %d characters\n", product.szName, product.nNameLength);
    }
    ```

사용 하는 경우 `CDynamicAccessor`, 길이 및 상태를 자동으로 바인딩된 됩니다. 길이 및 상태 값을 검색 하려면 사용 합니다 `GetLength` 및 `GetStatus` 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)