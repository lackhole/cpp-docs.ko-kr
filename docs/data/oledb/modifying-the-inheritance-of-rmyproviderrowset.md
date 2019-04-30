---
title: RCustomRowset의 상속 수정
ms.date: 10/26/2018
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
ms.openlocfilehash: d22c6902667ec84abe7bd85ffbffd1f5c5c57f2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395575"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset의 상속 수정

추가 하는 `IRowsetLocate` 단순한 읽기 전용 공급자 예제 인터페이스의 상속 수정, `CCustomRowset`합니다. 처음에 `CCustomRowset` 에서 상속 `CRowsetImpl`합니다. 상속 하도록 수정 해야 `CRowsetBaseImpl`합니다.

이렇게 하려면 새 클래스를 만듭니다 `CCustomRowsetImpl`의 *사용자 지정*RS.h:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

이제에서 COM 인터페이스 맵을 편집 *사용자 지정*RS.h 다음과 같이 되도록 합니다.

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

이 코드에 알려주는 COM 인터페이스 맵을 만듭니다 `CMyRowsetImpl` 호출할 `QueryInterface` 둘 다에 대 한 합니다 `IRowset` 및 `IRowsetLocate` 인터페이스. 다른 행 집합에 대 한 구현의 모든 클래스, 맵 링크는 `CMyRowsetImpl` 클래스를는 `CRowsetBaseImpl` map의 COM 맵에 검색 하려면 OLE DB 템플릿 알려 주는 COM_INTERFACE_ENTRY_CHAIN 매크로 사용 하 여; OLE DB 템플릿에 정의 된 클래스 `CRowsetBaseImpl` 에 대 한 응답을 `QueryInterface` 호출 합니다.

마지막으로 연결 `CCustomRowset` 하 `CMyRowsetBaseImpl` 수정 하 여 `CCustomRowset` 상속할 `CMyRowsetImpl`같이:

```cpp
class CCustomRowset : public CMyRowsetImpl<CCustomRowset, CCustomWindowsFile, CCustomCommand>
```

`CCustomRowset` 이제 사용할 수는 `IRowsetLocate` 행 집합 클래스 구현의 나머지 부분을 활용 하는 인터페이스입니다.

이 작업을 수행할 수 있습니다 [소비자에 게 반환 되는 열을 동적으로 결정](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)합니다.

## <a name="see-also"></a>참고자료

[단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
