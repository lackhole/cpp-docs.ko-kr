---
title: 매개 변수가 있는 쿼리 실행
ms.date: 10/19/2018
helpviewer_keywords:
- parameter queries, running using CCommand class
ms.assetid: aedb0fce-52a4-4c97-a5c9-b2114be6c3b0
ms.openlocfilehash: 1ac029d954fc6cefaae6349e01af7728ca0886fd
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025700"
---
# <a name="issuing-a-parameterized-query"></a>매개 변수가 있는 쿼리 실행

다음 예제는 Microsoft Access 데이터베이스의 테이블에서 나이 필드 값이 (30 이상인) 레코드를 검색하는 단순 매개 변수가 있는 쿼리를 실행합니다. 매개 변수를 지원하려면 사용자 레코드에 추가 맵이 있어야 합니다. 다음 ATL 프로젝트의 코드에서는 이전 예제 [단순 행 집합 검색](../../data/oledb/traversing-a-simple-rowset.md)에서 사용된 `CTable` 클래스 대신 `CCommand` 클래스를 사용합니다.

```cpp
#include <atldbcli.h>
#include <iostream>

using namespace std;

int main()
{
    CDataSource connection;
    CSession session;
    CCommand<CAccessor<CArtists>> artists;
    LPCSTR clsid; // Initialize CLSID_MSDASQL here
    LPCTSTR pName = L"NWind";

    // Open the connection, session, and table, specifying authentication
    // using Windows NT integrated security. Hard-coding a password is a major
    // security weakness.
    connection.Open(clsid, pName, NULL, NULL, DBPROP_AUTH_INTEGRATED);

    session.Open(connection);

    // Set the parameter for the query
    artists.m_nAge = 30;
    artists.Open(session, "select * from artists where age > ?");

    // Get data from the rowset
    while (artists.MoveNext() == S_OK)
    {
        cout << artists.m_szFirstName;
        cout << artists.m_szLastName;
    }

    return 0;
}
```

사용자 레코드 `CArtists`는 다음과 같습니다.

```cpp
class CArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_COLUMN_MAP(CArtists)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
   COLUMN_ENTRY(3, m_nAge)
END_COLUMN_MAP()

// Parameter binding map
BEGIN_PARAM_MAP(CArtists)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_nAge)
END_PARAM_MAP()
};
```

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)