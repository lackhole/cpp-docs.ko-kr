---
title: CCustomRowset (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
- ccustomrowset
- customrs.h
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
ms.openlocfilehash: 9f9dcb97ecd6b5f37f1af2187abf8b5612eedce3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230665"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

마법사는 행 집합 개체에 대 한 진입점을 생성합니다. 이 경우에 호출 됩니다 `CCustomRowset`합니다. 합니다 `CCustomRowset` 클래스 라고 하는 OLE DB 공급자 클래스에서 상속 `CRowsetImpl`, 행 집합 개체에 필요한 모든 인터페이스를 구현 하는 합니다. 다음 코드에 대 한 상속 체인을 보여 주는 `CRowsetImpl`:

```cpp
template <class T, class Storage, class CreatorClass, 
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, 
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` 또한 사용 하 여는 `IAccessor` 고 `IColumnsInfo` 인터페이스입니다. 출력 필드를 테이블에 대 한 이러한 인터페이스를 사용합니다. 또한이 클래스에 대 한 구현을 제공 `IRowsetIdentity`, 소비자가 두 행이 동일한 경우를 확인할 수 있습니다. `IRowsetInfo` 인터페이스 행 집합 개체에 대 한 속성을 구현 합니다. `IConvertType` 인터페이스는 소비자가 요청한 데이터 형식 및 공급자가 사용 되는 차이점을 해결 하기 위해 공급자를 사용 합니다.

`IRowset` 검색 데이터를 실제로 처리 하는 인터페이스입니다. 메서드를 먼저 호출 하는 소비자 `GetNextRows` 으로 알려진 행에 핸들을 반환 하는 `HROW`합니다. 호출 `IRowset::GetData` 된 `HROW` 요청한 데이터를 검색 합니다.

`CRowsetImpl` 또한 여러 템플릿 매개 변수를 사용합니다. 이러한 매개 변수를 확인할 수 있습니다를 사용 하는 방법을 `CRowsetImpl` 클래스가 데이터를 처리 합니다. `ArrayType` 인수를 사용 하면 저장소 메커니즘은 행 데이터를 저장 하는 데 사용 됩니다 확인할 수 있습니다. *RowClass* 매개 변수 지정 어떤 클래스를 포함 한 `HROW`합니다.

합니다 *RowsetInterface* 매개 변수를 사용할 수도 있습니다는 `IRowsetLocate` 또는 `IRowsetScroll` 인터페이스입니다. 합니다 `IRowsetLocate` 하 고 `IRowsetScroll` 인터페이스에서 상속 하는 둘 다 `IRowset`합니다. 따라서 OLE DB 공급자 템플릿 이러한 인터페이스에 대 한 특수 처리를 제공 해야 합니다. 이러한 인터페이스 중 하나를 사용 하려는 경우이 매개 변수를 사용 해야 합니다.

## <a name="see-also"></a>참고자료

[공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)<br/>
