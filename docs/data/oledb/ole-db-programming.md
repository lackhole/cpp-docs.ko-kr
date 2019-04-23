---
title: OLE DB 프로그래밍
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
ms.openlocfilehash: ac74f94b4cdc738237c2994646f7602f7f5118ca
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031649"
---
# <a name="ole-db-programming"></a>OLE DB 프로그래밍

Microsoft OLE DB는 레거시 기술입니다. 새 응용 프로그램 연결 된 SQL 서버에 필요한 데이터 액세스 API입니다. 새 응용 프로그램을 모두 ODBC 사용 해야 합니다. SQL Server에 대 한 현재 OLE DB 공급자가 SQLNCLI11입니다. DLL입니다. 공급자는 SQL Server 2016에서 여전히 배송 됩니다. 이 문서는 이미 OLE DB를 사용 하는 기존 응용 프로그램을 유지 하는 개발자를 위한 것입니다.

OLE DB 템플릿은 일반적으로 사용되는 많은 OLE DB 인터페이스를 구현하는 클래스를 제공하여 고성능 OLE DB 데이터베이스 기술을 보다 쉽게 구현하도록 하는 C++ 템플릿입니다. 이 템플릿 라이브러리는 소비자 템플릿과 공급자 템플릿으로 구분됩니다.

또한 Visual C++에는 OLE DB 시작 응용 프로그램을 만드는 마법사도 제공됩니다.

또한 OLE DB 소비자 템플릿 구현에 특성을 사용할 수 있습니다.

|자세한 정보를 확인할 항목|참조|
|-------------------------|---------|
|OLE DB 소비자 템플릿 사용(개념 항목)|[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)|
|OLE DB 공급자 템플릿 사용(개념 항목)|[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)|
|OLE DB 템플릿 클래스 및 매크로|[OLE DB 템플릿 참조](../../data/oledb/ole-db-templates.md) (Visual C++)|
|OLE DB 소비자 특성|[OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)|
|OLE DB 인터페이스|[OLE DB 프로그래머 참조](/sql/connect/oledb/oledb-driver-for-sql-server) (에 Windows SDK)|
|OLE DB 템플릿 샘플|[OLE DB 템플릿 샘플](https://github.com/Microsoft/VCSamples)|
|데이터 액세스 프로그래밍 개요(Visual C++)|[데이터 액세스 프로그래밍](../../data/data-access-programming-mfc-atl.md)|
|ODBC 개념 항목|[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)|

## <a name="see-also"></a>참고자료

[데이터 액세스](../data-access-in-cpp.md)