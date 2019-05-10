---
title: ATL 데이터베이스 클래스(OLE DB 템플릿)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: dc016a5e1e1d9652f6a69f73b5760f42dec5e889
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222561"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL 데이터베이스 클래스(OLE DB 템플릿)

Microsoft OLE DB 데이터를 다양 한 소스 및 형식에 대 한 균일 한 액세스를 제공 하는 COM 인터페이스 집합의 몇 가지 구현을 제공 합니다.

OLE DB 템플릿은 C++ OLE DB 데이터베이스 기술을 쉽게 여러 가지 자주 사용 되는 OLE DB 인터페이스를 구현 하는 클래스를 제공 하 여 사용할 수 있도록 ATL에서 템플릿.

이 템플릿 라이브러리 포함 두 부분으로 구성이 되어 있습니다.

- [OLE DB 소비자 템플릿](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB (소비자) 클라이언트 응용 프로그램을 구현 하는 데 사용 합니다.

- [OLE DB 공급자 템플릿](../data/oledb/ole-db-provider-templates-cpp.md) OLE DB 서버 (공급자) 응용 프로그램을 구현 하는 데 사용 합니다.

또한 합니다 [OLE DB 소비자 특성](../windows/ole-db-consumer-attributes.md) OLE DB 소비자를 만드는 편리한 방법을 제공 합니다. OLE DB 작업 OLE DB 소비자를 만드는 OLE DB 소비자 템플릿을 기반으로 하는 코드를 삽입 합니다.

MFC 라이브러리 클래스를 포함 하는 참고 [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), 컨트롤의 데이터베이스 레코드를 표시 하는 합니다. 뷰는에 직접 연결 하는 폼 보기를 `CRowset` 개체 및 필드가 표시 됩니다는 `CRowset` 대화 상자 템플릿의 컨트롤에는 개체입니다.

자세한 내용은 [OLE DB 프로그래밍](../data/oledb/ole-db-programming.md) 하 고 [OLE DB Programmer's Guide](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 만들기](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[OLE DB 공급자 만들기](../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB 소비자 템플릿 참조](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB 공급자 템플릿 참조](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB 템플릿 샘플](https://github.com/Microsoft/VCSamples)
