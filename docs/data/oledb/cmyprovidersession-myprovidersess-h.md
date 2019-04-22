---
title: CCustomSession (CustomSess.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidersession
- myprovidersess.h
- ccustomsession
- customsess.h
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
- CCustomSession class in CustomSess.H
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
ms.openlocfilehash: 5cb462aba671e79450e9ee7b8447410252f8edc9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023466"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*사용자 지정*Sess.H 선언 및 OLE DB 세션 개체에 대 한 구현을 포함 합니다. 데이터 원본 개체 세션 개체를 만들고이 소비자와 공급자 간의 대화를 나타냅니다. 여러 개의 세션을 하나의 데이터 원본에 대 한 열 수 있습니다. 상속 목록 `CCustomSession` 따릅니다.

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSession
class ATL_NO_VTABLE CCustomSession : 
   public CComObjectRootEx<CComSingleThreadModel>,
   public IGetDataSourceImpl<CCustomSession>,
   public IOpenRowsetImpl<CCustomSession>,
   public ISessionPropertiesImpl<CCustomSession>,
   public IObjectWithSiteSessionImpl<CCustomSession>,
   public IDBSchemaRowsetImpl<CCustomSession>,
   public IDBCreateCommandImpl<CCustomSession, CCustomCommand>
```

세션 개체에서 상속 `IGetDataSource`, `IOpenRowset`를 `ISessionProperties`, 및 `IDBCreateCommand`합니다. `IGetDataSource` 인터페이스를 사용 하면 세션을 만든 데이터 원본을 검색 합니다. 사용자가 만든 데이터 원본 또는 데이터 소스를 제공할 수 있는 기타 정보에서 속성을 가져올 해야 할 경우에 유용 합니다. `ISessionProperties` 세션에 대 한 모든 속성을 처리 하는 인터페이스입니다. 합니다 `IOpenRowset` 고 `IDBCreateCommand` 인터페이스는 데이터베이스 작업을 수행 하는 데 사용 됩니다. 공급자 명령을 지 원하는 경우 구현 된 `IDBCreateCommand` 인터페이스입니다. 명령을 실행 하는 명령 개체를 만드는 사용 됩니다. 공급자가 항상 구현 하는 `IOpenRowset` 개체입니다. 행 집합 공급자에서 생성 하는 것이 됩니다. 기본 행 집합 (예를 들어 `"select * from mytable"`) 공급자에서입니다.

마법사는 세 가지 세션 클래스를 생성 합니다. `CCustomSessionColSchema`, `CCustomSessionPTSchema`, 및 `CCustomSessionTRSchema`합니다. 이러한 세션은 스키마 행 집합에 사용 됩니다. 스키마 행 집합 공급자는 소비자가 실행 된 쿼리 또는 fetch 데이터 소비자에 게 메타 데이터를 반환할 수 있습니다. 메타 데이터를 인출 하는 것은 공급자의 기능을 찾는 것 보다 훨씬 빠를 수 있습니다.

OLE DB 사양에는 구현 하는 공급자는 `IDBSchemaRowset` 인터페이스 스키마 행 집합 형식을 지 원하는 3: DBSCHEMA_COLUMNS DBSCHEMA_PROVIDER_TYPES, 고 DBSCHEMA_TABLES입니다. 마법사는 각 스키마 행 집합에 대 한 구현을 생성합니다. 마법사에서 생성 된 각 클래스를 포함 한 `Execute` 메서드. 이 `Execute` 메서드를 지 원하는 테이블, 열 및 데이터 형식에 대 한 공급자에 게 데이터를 반환할 수 있습니다. 이 데이터는 컴파일 타임에 알려집니다.

## <a name="see-also"></a>참고자료

[공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)<br/>
