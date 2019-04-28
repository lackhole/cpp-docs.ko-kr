---
title: 행 집합 개체 인터페이스
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
ms.openlocfilehash: 1f3e6066af4b6870c5fa90f7bde373bb7be476ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243980"
---
# <a name="rowset-object-interfaces"></a>행 집합 개체 인터페이스

다음 표는 OLE DB가 행 집합 개체에 대해 정의한 필수 인터페이스와 선택적 인터페이스를 보여 줍니다.

|인터페이스|필수 여부|OLE DB 템플릿에서 구현 되었습니까?|
|---------------|---------------|--------------------------------------|
|[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))|필수|예|
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|필수|예|
|[IConvertType](/previous-versions/windows/desktop/ms715926(v=vs.85))|필수|예|
|[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85))|필수|예|
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|필수|예|
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180(v=vs.85))|Optional|아니요|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953(v=vs.85))|Optional|아니요|
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657(v=vs.85))|Optional|아니요|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|예 (ATL)|
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832(v=vs.85))|Optional|아니요|
|[IGetRow](/previous-versions/windows/desktop/ms718047(v=vs.85))|Optional|아니요|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))|Optional|예|
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430(v=vs.85))|Optional|아니요|
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700(v=vs.85))|Optional|아니요|
|[IRowsetFind](/previous-versions/windows/desktop/ms724221(v=vs.85))|Optional|아니요|
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85))|선택적 (수준 0 공급자에 대 한 필수)|예|
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604(v=vs.85))|Optional|아니요|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))|Optional|예|
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892(v=vs.85))|Optional|아니요|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984(v=vs.85))|Optional|아니요|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))|Optional|예|
|[IRowsetView](/previous-versions/windows/desktop/ms709755(v=vs.85))|Optional|아니요|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|예|
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246(v=vs.85))|Optional|아니요|

마법사가 생성한 행 집합 개체는 상속을 통해 `IAccessor`, `IRowset` 및 `IRowsetInfo`를 구현합니다. `IAccessorImpl` 인터페이스는 출력 열을 바인딩합니다. `IRowset` 인터페이스는 행과 데이터 페치를 처리합니다. `IRowsetInfo` 인터페이스는 행 집합 속성을 처리합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
