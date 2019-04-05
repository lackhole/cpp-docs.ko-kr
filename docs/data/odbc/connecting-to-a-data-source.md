---
title: 데이터 소스에 연결
ms.date: 11/04/2016
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
ms.openlocfilehash: 1740a34036798dac69ffc8b486e03bf6439845a5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024563"
---
# <a name="connecting-to-a-data-source"></a>데이터 소스에 연결

ODBC 데이터 소스 특정 집합이 데이터를 해당 데이터와 데이터 원본 이름을 사용 하 여 표현할 수 있는 데이터 원본의 위치에 액세스 하는 데 필요한 정보입니다. 프로그램의 관점에서 데이터 원본 데이터, DBMS, 네트워크 (있는 경우) 및 ODBC를 포함 합니다.

데이터 원본에서 제공 하는 데이터에 액세스 하려면 프로그램 데이터 원본에 대 한 연결을 먼저 설정 해야 합니다. 데이터에 대 한 모든 액세스는 해당 연결을 통해 관리 됩니다.

데이터 원본 연결 클래스에 의해 캡슐화 됩니다 [CDatabase](../../mfc/reference/cdatabase-class.md)합니다. 경우는 `CDatabase` 개체가 데이터 원본에 연결 되어, 할 수 있습니다.

- 생성할 [레코드 집합](../../mfc/reference/crecordset-class.md), 어떤 쿼리나 테이블에서 레코드를 선택 합니다.

- 관리할 [트랜잭션을](../../data/odbc/transaction-odbc.md), 모든 일괄 처리 업데이트는 한 번에 데이터 소스에 커밋할 (또는 데이터 원본이 변경 되므로 다시 전체 트랜잭션이 롤백됩니다.)-데이터 원본에 필요한 수준의 트랜잭션 지 원하는 경우.

- 직접 실행 [SQL](../../data/odbc/sql.md) 문입니다.

데이터 원본 연결을 사용 하 여 작업을 마친 후 닫으면는 `CDatabase` 개체와 삭제 또는 새 연결에 다시 사용 합니다. 데이터 원본 연결에 대 한 자세한 내용은 참조 하세요. [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md)합니다.

## <a name="see-also"></a>참고자료

[ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)