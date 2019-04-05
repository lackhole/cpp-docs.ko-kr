---
title: 단순 소비자 구현
ms.date: 10/12/2018
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
ms.openlocfilehash: 9067e8645fac9a06bd85ca5ef18fbaff45d16aae
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033536"
---
# <a name="implementing-a-simple-consumer"></a>단순 소비자 구현

다음 항목에서 만든 파일을 편집 하는 방법을 보여 줍니다 합니다 **MFC 응용 프로그램 마법사** 및 **ATL OLE DB 소비자 마법사** 간단한 소비자를 만듭니다. 이 예제에는 다음과 같은 부분에 있습니다.

- [소비자를 사용 하 여 데이터를 검색](#retrieve) 데이터베이스 테이블에서 모든 데이터를 행 단위로 읽는 소비자 코드를 구현 하는 방법을 보여 줍니다.

- [소비자에 게 책갈피 지원을 추가](#bookmark) 소비자에 책갈피 지원을 추가 하는 방법을 보여 줍니다.

> [!NOTE]
> 이 섹션에 설명 된 소비자 응용 프로그램을 사용 하 여 테스트 합니다 `MyProv` 및 `Provider` 공급자 샘플입니다.

> [!NOTE]
> 테스트할 소비자 응용 프로그램을 빌드하 `MyProv` (동일한 공급자에서 설명한 [간단한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md))에 설명 된 대로 책갈피 지원을 포함 해야 [에 책갈피 지원을 추가 합니다 소비자](#bookmark)합니다.

## <a name="retrieve" ></a> 소비자를 사용 하 여 데이터를 검색합니다.

### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>OLE DB 소비자를 사용 하 여 콘솔 응용 프로그램을 수정 하려면

1. `MyCons.cpp`, 다음과 같은 굵은 텍스트를 삽입 하 여 기본 코드를 변경 합니다.

    ```cpp
    // MyCons.cpp : Defines the entry point for the console application.
    //
    #include "stdafx.h"
    #include "Products.h"
    ...
    int main(int argc, char* argv[])
    {
       HRESULT hr = CoInitialize(NULL);   // Instantiate rowset
       CProducts rs;
       hr = rs.OpenAll();
       ATLASSERT(SUCCEEDED(hr ) );
       hr = rs.MoveFirst();   // Iterate through the rowset
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row
         printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",
           rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );
         hr = rs.MoveNext();   }
       rs.Close();
       rs.ReleaseCommand();
       CoUninitialize();

       return 0;
    }
    ```

## <a name="bookmark" ></a> 소비자에 게 추가 책갈피 지원

책갈피에는 테이블의 행을 고유 하 게 식별 하는 열입니다. 일반적으로 것이 키 열이 있지만 항상 그렇지는 않습니다. 이 공급자별으로 다릅니다. 이 섹션에서는 책갈피 지원을 추가 하는 방법을 보여 줍니다. 이렇게 하려면 사용자 레코드 클래스에서 다음 단계를 수행 해야 합니다.

- 책갈피를 인스턴스화하십시오. 형식의 개체를 이들은 [CBookmark](../../data/oledb/cbookmark-class.md)합니다.

- 책갈피 열을 설정 하 여 공급자 로부터 요청을 `DBPROP_IRowsetLocate` 속성입니다.

- 책갈피 항목을 사용 하 여 열 지도에 추가 합니다 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md) 매크로입니다.

이전 단계를 작업 하는 책갈피 개체 및 지원을 제공 합니다. 이 코드 예제에서는 책갈피를 다음과 같이 보여 줍니다.

- 파일을 쓰기용으로 엽니다.

- 출력 행 집합 파일의 데이터를 행 단위로 합니다.

- 호출 하 여 행 집합 커서는 책갈피로 이동할 [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)합니다.

- 파일의 끝에 추가 하 여 책갈피가 표시 된 행을 출력 합니다.

> [!NOTE]
> 이 소비자 응용 프로그램 테스트를 사용 하는 경우는 `Provider` 샘플 공급자 응용 프로그램, 책갈피 지원은이 섹션에 설명 된 상태로 둡니다.

### <a name="to-instantiate-the-bookmark"></a>책갈피를 인스턴스화

1. 형식의 개체를 포함 해야 하는 접근자 [CBookmark](../../data/oledb/cbookmark-class.md)합니다. 합니다 *nSize* 매개 변수 (일반적으로 32 비트 플랫폼에 대 한 4) 및 64 비트 플랫폼에 대 한 8 바이트에서 책갈피 버퍼의 크기를 지정 합니다. 사용자 레코드 클래스의 열 데이터 멤버에 다음 선언을 추가 합니다.

    ```cpp
    //////////////////////////////////////////////////////////////////////
    // Products.h
    class CProductsAccessor
    {
    public:
       CBookmark<4> m_bookmark;   // Add bookmark declaration
       LONG m_ProductID;
       ...
    ```

### <a name="to-request-a-bookmark-column-from-the-provider"></a>책갈피 열 공급자를 요청 하려면

1. 다음 코드를 추가 합니다 `GetRowsetProperties` 사용자 레코드 클래스의 메서드:

    ```cpp
    // Set the DBPROP_IRowsetLocate property.
    void GetRowsetProperties(CDBPropSet* pPropSet)
    {
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);
    }
    ```

### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>책갈피 항목 열 지도를 추가 하려면

1. 사용자 레코드 클래스의 열 지도에 다음 항목을 추가 합니다.

    ```cpp
    // Set a bookmark entry in the column map.
    BEGIN_COLUMN_MAP(CProductsAccessor)
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
    ...
    END_COLUMN_MAP()
    ```

### <a name="to-use-a-bookmark-in-your-main-code"></a>기본 코드에 책갈피를 사용 하려면

1. 에 `MyCons.cpp` 콘솔 응용 프로그램의 이전에 만든 코드를 변경 하면 주요를 다음과 같이 파일입니다. 책갈피를 사용 하려면 주 코드 자체 책갈피 개체를 인스턴스화하려면 요구 (`myBookmark`);는이 접근자에서 다른 책갈피 (`m_bookmark`).

    ```cpp
    ///////////////////////////////////////////////////////////////////////
    // MyCons.cpp : Defines the entry point for the console application.
    //

    #include "stdafx.h"
    #include "Products.h"
    #include <iostream>
    #include <fstream>
    using namespace std;

    int _tmain(int argc, _TCHAR* argv[])
    {
       HRESULT hr = CoInitialize(NULL);

       // Instantiate rowset
       CProducts rs;

       hr = rs.OpenAll();
       hr = rs.MoveFirst();

       // Cast CURRENCY m_UnitPrice to a long value
       LONGLONG lPrice = rs.m_UnitPrice.int64;

       // Open file output.txt for writing in overwrite mode
       ofstream outfile( "C:\\output.txt", ios::out );

       if (!outfile)      // Test for invalid file
          return -1;

       // Instantiate a bookmark object myBookmark for the main code
       CBookmark<4> myBookmark;
       int nCounter = 0;

       // Iterate through the rowset and output column data to output.txt row by row
       // In the file, mark the beginning of this set of data:
       outfile << "initial row dump" << endl;
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
       {
          nCounter++;
          if(nCounter == 5 )
             myBookmark = rs.m_bookmark;
          // Output the column information for each row:
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;
          hr = rs.MoveNext();
       }

       // Move cursor to bookmark
       hr = rs.MoveToBookmark(myBookmark);

       // Iterate through the rowset and output column data to output.txt row by row
       // In the file, mark the beginning of this set of data:
       outfile << "row dump starting from bookmarked row" << endl;
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
       {
          // Output the column information for each row
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;
          hr = rs.MoveNext();
       }

       rs.CloseAll();
       CoUninitialize();

       return 0;
    }
    ```

책갈피에 대 한 자세한 내용은 참조 하세요. [책갈피를 사용 하 여](../../data/oledb/using-bookmarks.md)입니다. 책갈피의 예에도 표시 됩니다 [행 집합 업데이트](../../data/oledb/updating-rowsets.md)합니다.

## <a name="see-also"></a>참고자료

[마법사를 사용하여 OLE DB 소비자 만들기](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
