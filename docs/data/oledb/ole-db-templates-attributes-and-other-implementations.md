---
title: OLE DB 템플릿, 특성 및 기타 구현
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
ms.openlocfilehash: 0e6b5dbc97f6a7bea1df342d6a792ea43907ca33
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039587"
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>OLE DB 템플릿, 특성 및 기타 구현

## <a name="atl-ole-db-templates"></a>ATL OLE DB 템플릿

OLE DB 템플릿, ATL (액티브 템플릿 라이브러리)의 일부인 고성능 OLE DB 데이터베이스 기술을 여러 가지 자주 사용 되는 OLE DB 인터페이스를 구현 하는 클래스를 제공 하 여 쉽게 합니다. 이 템플릿은 함께 라이브러리에는 OLE DB 시작 응용 프로그램을 만드는 마법사도 제공 됩니다.

이 템플릿 라이브러리 포함 두 부분으로 구성이 되어 있습니다.

- **OLE DB 소비자 템플릿** OLE DB (소비자) 클라이언트 응용 프로그램을 구현 하는 데 사용 합니다.

- **OLE DB 공급자 템플릿** OLE DB 서버 (공급자) 응용 프로그램을 구현 하는 데 사용 합니다.

OLE DB 템플릿을 사용하려면 C++ 템플릿, COM 및 OLE DB 인터페이스에 대해 잘 알고 있어야 합니다. OLE DB에 익숙하지 참조 [OLE DB Programmer's Reference](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)합니다.

자세한 내용은 다음을 수행할 수 있습니다.

- 에 대 한 항목을 참조 합니다 [OLE DB 소비자 템플릿은](../../data/oledb/ole-db-consumer-templates-cpp.md) 또는 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)합니다.

- 만들기는 [OLE DB 소비자](../../data/oledb/creating-an-ole-db-consumer.md) 하거나 [OLE DB 공급자](../../data/oledb/creating-an-ole-db-provider.md)합니다.

- 목록은 [OLE DB 소비자 클래스](../../data/oledb/ole-db-consumer-templates-reference.md) 하거나 [OLE DB 공급자 클래스](../../data/oledb/ole-db-provider-templates-reference.md)합니다.

- 목록은 [OLE DB 템플릿 샘플](https://github.com/Microsoft/VCSamples)합니다.

- 참조 [OLE DB Programmer's Reference](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) (Windows SDK)에 있습니다.

## <a name="ole-db-attributes"></a>OLE DB 특성

합니다 [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md) OLE DB 소비자를 만드는 편리한 방법을 제공 합니다. OLE DB 특성을 기반으로 하는 코드를 삽입 합니다 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-reference.md) 작업 OLE DB 소비자 및 공급자를 만들려면. 특성을 지원 하지 않는 기능이 지정 해야 할 경우 코드에서 OLE DB 템플릿 특성과 함께에서 사용할 수 있습니다.

## <a name="mfc-ole-db-classes"></a>MFC OLE DB 클래스

MFC 라이브러리에는 하나의 클래스 [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), 컨트롤의 데이터베이스 레코드를 표시 하는 합니다. 뷰는에 직접 연결 하는 폼 보기를 `CRowset` 개체 및 필드가 표시 됩니다는 `CRowset` 대화 상자 템플릿의 컨트롤에는 개체입니다. 또한 이동에 대 한 기본 구현을 제공 하면 첫 번째 다음, 이전 또는 마지막 레코드 및 view에 현재 레코드를 업데이트 하기 위한 인터페이스입니다. 자세한 내용은 `COleDBRecordView`을 참조하세요.

## <a name="ole-db-sdk-interfaces"></a>OLE DB SDK 인터페이스

OLE DB 템플릿은 OLE DB 기능을 지원 하지는 경우에는 OLE DB 인터페이스를 직접 사용 해야 합니다. 자세한 내용은 [OLE DB Programmer's Reference](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)