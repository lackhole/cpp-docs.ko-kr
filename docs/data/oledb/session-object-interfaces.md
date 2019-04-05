---
title: 세션 개체 인터페이스
ms.date: 11/19/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: 2fb91365fec0709e1bb2a26afa519e6565862681
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031457"
---
# <a name="session-object-interfaces"></a>세션 개체 인터페이스

다음 표는 OLE DB가 세션 개체에 대해 정의한 필수 인터페이스와 선택적 인터페이스를 보여줍니다.

|인터페이스|필수 여부|OLE DB 템플릿에서 구현 되었습니까?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85))|필수|예|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))|필수|예|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85))|필수|예|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943(v=vs.85))|Optional|아니요|
|[IAlterTable](/previous-versions/windows/desktop/ms719764(v=vs.85))|Optional|아니요|
|[IBindResource](/previous-versions/windows/desktop/ms714936(v=vs.85))|Optional|아니요|
|[ICreateRow](/previous-versions/windows/desktop/ms716832(v=vs.85))|Optional|아니요|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))|Optional|예|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))|Optional|예|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593(v=vs.85))|Optional|아니요|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|예|
|[ITableCreation](/previous-versions/windows/desktop/ms713639(v=vs.85))|Optional|아니요|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277(v=vs.85))|Optional|아니요|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947(v=vs.85))|Optional|아니요|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Optional|아니요|
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071(v=vs.85))|Optional|아니요|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893(v=vs.85))|Optional|아니요|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659(v=vs.85))|Optional|아니요|

세션 개체는 행 집합 개체를 만듭니다. 또한 공급자가 명령을 지원하는 경우에는 명령 개체(OLE DB `TCommand`를 구현하는 `CCommand`)도 만듭니다. 명령 개체는 다음 그림과 같이 `ICommand` 인터페이스를 구현하고 `ICommand::Execute` 메서드를 사용하여 행 집합에 대한 명령을 실행합니다.

![공급자 개념적 다이어그램](../../data/oledb/media/vc4u551.gif "공급자 개념적 다이어그램")

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
