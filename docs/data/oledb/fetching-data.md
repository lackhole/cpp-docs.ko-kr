---
title: 데이터 페치
ms.date: 10/19/2018
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
ms.openlocfilehash: 441f036d1677806e81bc419ec6a45e810e63a34f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409061"
---
# <a name="fetching-data"></a>데이터 페치

데이터 원본, 세션 및 행 집합 개체를 연 후에 데이터를 가져올 수 있습니다. 사용 중인 접근자의 형식에 따라 열을 바인딩하는 것이 해야 합니다.

## <a name="to-fetch-data"></a>데이터를 인출 하려면

1. 적절 한 사용 하 여 행 집합을 엽니다 **열고** 명령입니다.

1. 사용 중인 경우 `CManualAccessor`을 아직 수행 하지 않은 경우 출력 열을 바인딩합니다. 다음 예제에서 가져온 것은 [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) 샘플입니다. 열을 바인딩하려면 호출 `GetColumnInfo`를 만든 다음 접근자는 바인딩을 사용 하 여 다음 예와에서 같이 및:

    ```cpp
    // From the DBViewer Sample CDBTreeView::OnQueryEdit
    // Get the column information
    ULONG ulColumns       = 0;
    DBCOLUMNINFO* pColumnInfo  = NULL;
    LPOLESTR pStrings      = NULL;
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);
    struct MYBIND* pBind = new MYBIND[ulColumns];
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);
    for (ULONG l=0; l<ulColumns; l++)
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);
    rs.Bind();
    ```

1. 쓰기를 **동안** 루프 데이터를 검색 합니다. 루프에서 호출 `MoveNext` 커서를 이동 하 고 다음 예와에서 같이 S_OK 반환 값을 검사 하려면:

    ```cpp
    while (rs.MoveNext() == S_OK)
    {
        // Add code to fetch data here
        // If you are not using an auto accessor, call rs.GetData()
    }
    ```

1. 내 합니다 **동안** 루프 접근자 유형에 따라 데이터를 가져올 수 있습니다.

   - 사용 하는 경우는 [CAccessor](../../data/oledb/caccessor-class.md) 클래스 데이터 멤버를 포함 하는 사용자 레코드가 있어야 합니다. 다음 예제에서와 같이 해당 데이터 멤버를 사용 하 여 데이터를 액세스할 수 있습니다.

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members directly. In this case, m_nFooID
            // is declared in a user record that derives from
            // CAccessor
            wsprintf_s("%d", rs.m_nFooID);
        }
        ```

   - 사용 하는 경우는 `CDynamicAccessor` 또는 `CDynamicParameterAccessor` 클래스에 액세스 하는 함수를 사용 하 여 데이터를 가져올 수 있습니다 `GetValue` 및 `GetColumn`다음 예제에서와 같이 합니다. 사용 중인 데이터의 형식을 확인 하려는 경우, 사용 하 여 `GetType`입니다.

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the dynamic accessor functions to retrieve your data.

            ULONG ulColumns = rs.GetColumnCount();
            for (ULONG i=0; i<ulColumns; i++)
            {
                rs.GetValue(i);
            }
        }
        ```

   - 사용 하는 경우 `CManualAccessor`, 사용자 고유의 데이터 멤버를 지정, 사용자가 직접 바인딩 및 다음 예와에서 같이, 직접 액세스 해야 합니다.

        ```cpp
        while (rs.MoveNext() == S_OK)
        {
            // Use the data members you specified in the calls to
            // AddBindEntry.

            wsprintf_s("%s", szFoo);
        }
        ```

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)
