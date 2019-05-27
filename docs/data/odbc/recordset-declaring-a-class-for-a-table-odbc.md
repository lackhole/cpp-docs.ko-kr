---
title: '레코드 집합: 테이블에 대한 클래스 선언(ODBC)'
ms.date: 05/09/2019
helpviewer_keywords:
- ODBC recordsets, declaring class for tables
- recordsets, declaring classes for tables
ms.assetid: 3fe286c2-3f3d-493d-9d8c-762310939d08
ms.openlocfilehash: ea17f131552fe7f71d9106a8979bb661955fe850
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707943"
---
# <a name="recordset-declaring-a-class-for-a-table-odbc"></a>레코드 집합: 테이블에 대한 클래스 선언(ODBC)

> [!NOTE] 
> Visual Studio 2019 이상에서는 MFC ODBC 소비자 마법사를 사용할 수 없습니다. 여전히 수동으로 소비자를 만들 수 있습니다.

이 항목은 MFC ODBC 클래스에 적용됩니다.

가장 일반적인 레코드 집합 클래스는 단일 테이블을 엽니다. 단일 테이블에 대한 레코드 집합 클래스를 선언하려면 **클래스 추가**에서 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md)를 사용하고 해당 레코드 집합 필드 데이터 멤버 이름을 지정하여 원하는 각 열을 선택합니다.

레코드 집합의 다른 용도는 다음과 같습니다.

- 두 개 이상의 테이블에 조인합니다.

- 미리 정의된 쿼리의 결과를 포함합니다.

## <a name="see-also"></a>참고 항목

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합 레코드 집합 만들기 및 닫기(ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)<br/>
[레코드 집합 미리 정의된 쿼리에 대한 클래스 선언(ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[레코드 집합 조인 수행(ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)