---
title: 행 집합에서 여러 접근자 사용
ms.date: 10/24/2018
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
ms.openlocfilehash: d1ab314edeebedef4cff14cd5364a7ca16c74769
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216384"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>행 집합에서 여러 접근자 사용

세 가지 기본 시나리오 여러 접근자를 사용 해야 합니다.

- **여러 읽기/쓰기 행 집합입니다.** 이 시나리오에서 기본 키를 사용 하 여 테이블을 수 있습니다. 기본 키를 포함 하 여 행의 모든 열을 읽을 수 있도록 하려고 합니다. (기본 키 열에 쓸 수 없습니다) 때문에 기본 키를 제외한 모든 열에 데이터를 쓸 수 있으려면 수도 있습니다. 이 경우 두 접근자를 설정할 수도 있습니다.

  - 모든 열을 포함 하는 접근자 0입니다.

  - 접근자 1 기본 키를 제외한 모든 열을 포함 합니다.

- **성능.** 이 시나리오에서는 하나 이상의 열에는 많은 양의 데이터를 예를 들어, 그래픽, 사운드 또는 비디오 파일입니다. 행으로 이동할 때마다 있습니다 하려는 큰 데이터 파일을 사용 하 여 열을 검색할 수행 하므로 응용 프로그램의 성능을 저하 때문에 있습니다.

  대규모 데이터를 제외한 모든 열을 포함 하는 첫 번째 접근자에 자동으로 해당이 열에서 데이터를 검색 하는 별도 접근자를 설정할 수 있습니다. 첫 번째 접근자가 자동 접근자입니다. 두 번째 접근자 큰 데이터를 포함 하는 열만 검색 하지만 자동으로이 열에서 데이터를 검색 하지 것입니다. 다른 메서드를 업데이트 하거나 요청 시 큰 데이터를 가져올 수도 있습니다.

  - 접근자 0은 자동 접근자; 대규모 데이터를 제외한 모든 열을 검색 합니다.

  - 접근자 1 되지 자동 접근자; 큰 데이터를 사용 하 여 열을 검색합니다.

  자동 인수를 사용 하 여 접근자 자동 접근자가 있는지 여부를 지정 합니다.

- **여러 ISequentialStream 열입니다.** 이 시나리오에서는 둘 이상의 열 보유 하면 `ISequentialStream` 데이터입니다. 그러나 각 접근자 하나로 제한 됩니다 `ISequentialStream` 데이터 스트림 합니다. 이 문제를 해결 하기 위해 설정 여러 접근자를 각각 하나 `ISequentialStream` 포인터입니다.

일반적으로 사용 하 여 접근자를 만든 합니다 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 하 고 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다. 사용할 수도 있습니다는 [db_accessor](../../windows/db-accessor.md) 특성입니다. (접근자에 자세히 설명 되어 [사용자 레코드](../../data/oledb/user-records.md).) 매크로 또는 특성 접근자 자동 인지, 자동이 아닌 접근자를 지정 합니다.

- 자동 접근자 메서드를 같은 이동할 `MoveFirst`, `MoveLast`를 `MoveNext`, 및 `MovePrev` 모든 열을 자동으로 지정에 대 한 데이터를 검색 합니다. 접근자 0은 자동 접근자 여야 합니다.

- 명시적으로 메서드를 호출 하면 같은 될 때까지 자동이 아닌 접근자를 검색이 발생 하지 않습니다 `Update`, `Insert`를 `Fetch`, 또는 `Delete`합니다. 위에서 설명한 시나리오에서 모든 전환에 모든 열을 검색 하려는 없습니다. 개별 접근자에 하나 이상의 열을 배치할 수 있으며 아래와 같이 자동이 아닌 접근자를 확인 합니다.

다음 예에서는 읽기 및 쓰기 여러 접근자를 사용 하 여 SQL Server pubs 데이터베이스의 작업 테이블에 여러 접근자를 사용 합니다. 이 예제는 여러 접근자;의 가장 일반적인 사용 위의 "여러 읽기/쓰기 행 집합" 시나리오를 참조 하세요.

사용자 레코드 클래스는 다음과 같습니다. 두 접근자에 설정: 접근자 0만 기본 키 열 (ID)를 포함 하 고 접근자 1 다른 열을 포함 합니다.

```cpp
class CJobs
{
public:
    enum {
        sizeOfDescription = 51
    };

    short nID;
    char szDescription[ sizeOfDescription ];
    short nMinLvl;
    short nMaxLvl;

    DWORD dwID;
    DWORD dwDescription;
    DWORD dwMinLvl;
    DWORD dwMaxLvl;

BEGIN_ACCESSOR_MAP(CJobs, 2)
    // Accessor 0 is the automatic accessor
    BEGIN_ACCESSOR(0, true)
        COLUMN_ENTRY_STATUS(1, nID, dwID)
    END_ACCESSOR()
    // Accessor 1 is the non-automatic accessor
    BEGIN_ACCESSOR(1, true)
        COLUMN_ENTRY_STATUS(2, szDescription, dwDescription)
        COLUMN_ENTRY_STATUS(3, nMinLvl, dwMinLvl)
        COLUMN_ENTRY_STATUS(4, nMaxLvl, dwMaxLvl)
    END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

기본 코드는 다음과 같습니다. 호출 `MoveNext` 접근자 0을 사용 하 여 기본 키 열 ID에서 데이터를 자동으로 검색 합니다. 참고 하는 방법을 `Insert` 기본 키 열에 쓰지 않기 위해 사용 하 여 최종 접근자 1 부분의 메서드.

```cpp
int main(int argc, char* argv[])
{
    // Initialize COM
    ::CoInitialize(NULL);

    // Create instances of the data source and session
    CDataSource source;
    CSession session;
    HRESULT hr = S_OK;

    // Set initialization properties
    CDBPropSet dbinit(DBPROPSET_DBINIT);
    dbinit.AddProperty(DBPROP_AUTH_USERID, OLESTR("my_user_id"));
    dbinit.AddProperty(DBPROP_INIT_CATALOG, OLESTR("pubs"));
    dbinit.AddProperty(DBPROP_INIT_DATASOURCE, OLESTR("(local)"));

    hr = source.Open("SQLOLEDB.1", &dbinit);
    if (hr == S_OK)
    {
        hr = session.Open(source);
        if (hr == S_OK)
        {
            // Ready to fetch/access data
            CTable<CAccessor<CJobs>> jobs;

            // Set properties for making the rowset a read/write cursor
            CDBPropSet dbRowset(DBPROPSET_ROWSET);
            dbRowset.AddProperty(DBPROP_CANFETCHBACKWARDS, true);
            dbRowset.AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
            dbRowset.AddProperty(DBPROP_IRowsetChange, true);
            dbRowset.AddProperty(DBPROP_UPDATABILITY,
                DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE |
                DBPROPVAL_UP_DELETE);

            hr = jobs.Open(session, "jobs", &dbRowset);
            if (hr == S_OK)
            {
                // Calling MoveNext automatically retrieves ID
                // (using accessor 0)
                while(jobs.MoveNext() == S_OK)
                   printf_s("Description = %s\n", jobs.szDescription);

                hr = jobs.MoveFirst();
                if (hr == S_OK)
                {
                    jobs.nID = 25;
                    strcpy_s(&jobs.szDescription[0],
                             jobs.sizeOfDescription,
                             "Developer");
                    jobs.nMinLvl = 10;
                    jobs.nMaxLvl = 20;

                    jobs.dwDescription = DBSTATUS_S_OK;
                    jobs.dwID = DBSTATUS_S_OK;
                    jobs.dwMaxLvl = DBSTATUS_S_OK;
                    jobs.dwMinLvl = DBSTATUS_S_OK;

                    // Insert method uses accessor 1
                    // (to avoid writing to the primary key column)
                    hr = jobs.Insert(1);
                }
                jobs.Close();
            }
            session.Close();
        }
        source.Close();
    }

    // Uninitialize COM
    ::CoUninitialize();
    return 0;
}
```

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)<br/>
[사용자 레코드](../../data/oledb/user-records.md)
