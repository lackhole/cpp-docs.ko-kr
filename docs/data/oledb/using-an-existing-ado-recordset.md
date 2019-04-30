---
title: 기존 ADO 레코드 집합 사용
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: eb558bb319bb5ddb61d0383846099d708f99c627
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389010"
---
# <a name="using-an-existing-ado-recordset"></a>기존 ADO 레코드 집합 사용

OLE DB 소비자 템플릿과 ADO(Active Data Objects)를 혼합하려면, ADO를 사용하여 OLE DB 소비자 템플릿의 행 집합에 해당하는 레코드 집합을 여십시오. 레코드 집합이 있으면 다음을 수행하여 OLE DB 행 집합에 연결하십시오.

1. `IRowset` 및 `IAccessor` 포인터에 대해 `QueryInterface`를 호출합니다.

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *lpUnk*는 ADO 레코드 집합의 `IUnknown` 개체를 가리킵니다.

1. 접근자와 행 집합을 알맞은 OLE DB 소비자 템플릿 클래스에 첨부합니다.

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>참고자료

[접근자 사용](../../data/oledb/using-accessors.md)
