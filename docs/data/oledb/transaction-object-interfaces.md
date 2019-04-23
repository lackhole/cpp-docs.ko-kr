---
title: 트랜잭션 개체 인터페이스
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
ms.openlocfilehash: 0caecc797a3175d5769f98e181e1d99ef6b1ad16
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034036"
---
# <a name="transaction-object-interfaces"></a>트랜잭션 개체 인터페이스

트랜잭션 개체는 데이터 소스에 대한 작업의 원자 단위를 정의하고 이러한 작업 단위가 서로 연관되는 방법을 결정합니다. 이 개체는 OLE DB 공급자가 직접 지원하지 않습니다(즉,  사용자가 직접 만들어야 합니다).

다음 표는 OLE DB가 트랜잭션 개체에 대해 정의한 필수 인터페이스와 선택적 인터페이스를 보여 줍니다.

|인터페이스|필수 여부|OLE DB 템플릿에서 구현 되었습니까?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|필수|아니요|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|필수|아니요|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|아니요|

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
