---
title: 다이너셋에 대한 ODBC 드라이버 요구 사항
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, dynasets
- drivers, for dynasets
- drivers, ODBC
- recordsets, dynasets
- dynasets
- ODBC drivers, dynasets
ms.assetid: 585cc67b-4d92-404b-9903-d769cd17badc
ms.openlocfilehash: c44e34023ecdeb994ea3a60ea3b699cd5b1488a3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023830"
---
# <a name="odbc-driver-requirements-for-dynasets"></a>다이너셋에 대한 ODBC 드라이버 요구 사항

MFC ODBC 데이터베이스 클래스 다이너셋에 동적 속성을 사용 하 여 레코드 집합 다양 한 방식으로 데이터 소스와 동기화 상태로 남아 있습니다. MFC 다이너셋 (그러나 정방향 전용 레코드 집합)에 수준 2 API 규칙을 사용 하 여 ODBC 드라이버가 필요합니다. 경우에 대 한 드라이버에 [데이터 원본](../../data/odbc/data-source-odbc.md) 수준 1 API를 준수 설정 계속 사용 하 여 모두 업데이트 가능 하 고 읽기 전용 스냅숏 및 정방향 전용 레코드 집합 있지만 다이너셋 없습니다. 그러나 확장된 페치 및 키 집합 커서를 지 원하는 경우 수준 1 드라이버 다이너셋을 지원할 수 있습니다.

ODBC 용어에서 다이너셋 및 스냅숏을 라고 커서입니다. 커서에는 레코드 집합에서 해당 위치는 추적에 사용 되는 메커니즘입니다. 다이너셋에 대 한 드라이버 요구 사항에 대 한 자세한 내용은 참조 하세요. [다이너셋](../../data/odbc/dynaset.md)합니다. 커서에 대 한 자세한 내용은 참조는 [개방형 데이터베이스 연결 (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) MSDN 설명서에서 SDK.

> [!NOTE]
>  ODBC 드라이버를 업데이트할 수 있는 레코드 집합 위치 지정된 update 문 중 하나를 지원 해야 합니다 또는 `::SQLSetPos` ODBC API 함수입니다. MFC를 사용 하는 둘 다 지 원하는 경우 `::SQLSetPos` 효율성에 대 한 합니다. 또는 스냅숏을 업데이트할 수 있는 스냅숏 (정적 커서 및 위치 지정된 update 문)에 대 한 지원 요구 사항에 제공 하는 커서 라이브러리를 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

[ODBC 기초](../../data/odbc/odbc-basics.md)