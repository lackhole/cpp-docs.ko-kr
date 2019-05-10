---
title: 데이터 소스 개체 인터페이스
ms.date: 10/24/2018
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
ms.openlocfilehash: fc8d2f5edf854766dcb5dcc8ed6d57a849b8f2a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176020"
---
# <a name="data-source-object-interfaces"></a>데이터 소스 개체 인터페이스

다음 표는 OLE DB가 데이터 원본 개체에 대해 정의한 필수 인터페이스와 선택적 인터페이스를 보여줍니다.

|인터페이스|필수 여부|OLE DB 템플릿에서 구현 되었습니까?|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|필수|예|
|`IDBInitialize`|필수|예|
|`IDBProperties`|필수|예|
|[IPersist](/windows/desktop/api/objidl/nn-objidl-ipersist)|필수|예|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|아니요|
|`IDBDataSourceAdmin`|Optional|아니요|
|`IDBInfo`|Optional|아니요|
|[IPersistFile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|Optional|아니요|
|`ISupportErrorInfo`|Optional|아니요|

데이터 소스 개체는 상속을 통해 `IDBProperties`, `IDBInitialize` 및 `IDBCreateSession` 인터페이스를 구현합니다. 이러한 구현 클래스 중 하나에서 상속하거나 상속하지 않도록 하여 추가 기능을 지원하도록 선택할 수 있습니다. `IDBDataSourceAdmin` 인터페이스를 지원하려는 경우 `IDBDataSourceAdminImpl` 클래스에서 상속해야 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
