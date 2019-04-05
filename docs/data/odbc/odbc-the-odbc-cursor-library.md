---
title: 'ODBC: ODBC 커서 라이브러리'
ms.date: 11/04/2016
helpviewer_keywords:
- cursor library [ODBC]
- snapshots, support in ODBC
- timestamps, ODBC timestamp columns
- ODBC cursor library [ODBC]
- static cursors
- ODBC drivers, Level 1
- ODBC drivers, cursor support
- positioned updates
- cursors, ODBC cursor library
- Level 1 ODBC drivers
- cursor library [ODBC], snapshots
- ODBC, timestamp
- positioning cursors
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
ms.openlocfilehash: 862303a0dc66fbd49bfcba83336ab29dfc7145c0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032234"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC 커서 라이브러리

이 항목에서는 ODBC 커서 라이브러리 및 사용 하는 방법을 설명 합니다. 자세한 내용은 다음을 참조하세요.

- [커서 라이브러리와 수준 1 ODBC 드라이버](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [위치 지정된 업데이트 및 타임 스탬프 열](#_core_positioned_updates_and_timestamp_columns)

- [커서 라이브러리 사용](#_core_using_the_cursor_library)

ODBC 커서 라이브러리는 ODBC 드라이버 관리자와 드라이버 사이 위치 하는 동적 연결 라이브러리 (DLL). ODBC 용어 드라이버를 레코드 집합의 해당 위치를 추적 하는 커서를 유지 합니다. 커서가 이미 스크롤 했는지 레코드 집합 위치를 표시 합니다.-현재 레코드입니다.

##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> 커서 라이브러리와 수준 1 ODBC 드라이버

ODBC 커서 라이브러리는 다음과 같은 새로운 기능 수준 1 드라이버를 제공합니다.

- 앞으로 및 뒤로 스크롤입니다. 수준 2 드라이버 커서 라이브러리를 스크롤할 수 있는 이미 있기 때문에 필요 하지 않습니다.

- 스냅숏 지원 합니다. 커서 라이브러리는 스냅숏 레코드를 포함 하는 버퍼를 관리 합니다. 이 버퍼는 프로그램의 삭제 및 편집 레코드 하지만 하지 추가, 삭제, 또는 다른 사용자의 편집을 반영합니다. 따라서 스냅샷 커서 라이브러리의 버퍼로 최신만입니다. 버퍼 또한 반영 하지 않습니다 고유한 추가 호출할 때까지 `Requery`입니다. 다이너셋 커서 라이브러리를 사용 하지 마세요.

커서 라이브러리는 드라이버에서 지원 하지 않는 경우에 스냅숏 (정적 커서)를 제공 합니다. 드라이버에서 이미 정적 커서를 지 원하는 경우 스냅숏 지원을 받으려면 커서 라이브러리를 로드할 필요가 없습니다. 커서 라이브러리를 사용 하는 경우에 스냅숏 및 정방향 전용 레코드 집합을 사용할 수 있습니다. 드라이버가 지원 다이너셋 (KEYSET_DRIVEN 커서)를 사용 하려는 경우에 커서 라이브러리를 사용 해야 합니다. 스냅숏과 다이너셋 둘 다 사용 하려는 경우 두 가지에 기반 해야 `CDatabase` 드라이버를 모두 지원 하지 않으면 (두 개의 서로 다른 연결) 개체입니다.

##  <a name="_core_positioned_updates_and_timestamp_columns"></a> 위치 지정된 업데이트 및 타임 스탬프 열

> [!NOTE]
>  ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC Data Access Object(DAO) 클래스를 통해서도 액세스할 수 있습니다.

> [!NOTE]
>  ODBC 드라이버에서 지 원하는 경우 `SQLSetPos`는 MFC 사용 가능한 경우,이 항목에서는 적용 되지 않습니다.

대부분의 수준 1 드라이버 위치 지정된 업데이트를 지원 하지 않습니다. 이러한 드라이버는 이런 점에서 수준 2 드라이버의 기능을 에뮬레이트 하려면 커서 라이브러리에 의존 합니다. 커서 라이브러리는 변경 되지 않는 필드에 검색 결과 업데이트를 수행 하 여 위치 지정된 업데이트 지원을 에뮬레이트합니다.

일부 경우에는 레코드 집합 변경 되지 않은 이러한 필드 중 하나로 타임 스탬프 열을 포함할 수 있습니다. 타임 스탬프 열이 포함 된 테이블을 사용 하 여 MFC 레코드 집합을 사용 하 여 두 가지 문제가 발생 합니다.

첫 번째 문제는 타임 스탬프 열이 있는 테이블에서 업데이트할 수 있는 스냅숏 관련 됩니다. 호출 해야에 스냅숏이 바인딩되는 테이블에 타임 스탬프 열이 있으면 `Requery` 호출한 후 `Edit` 고 `Update`입니다. 그렇지 않은 경우 다시 같은 레코드를 편집할 수 있습니다. 호출 하는 경우 `Edit` 차례로 `Update`레코드가 데이터 원본에 기록 되 고 타임 스탬프 열이 업데이트 됩니다. 호출 하지 않으면 `Requery`, 스냅숏의 레코드에 대 한 타임 스탬프 값은 데이터 원본에 해당 타임 스탬프를 더 이상 일치 합니다. 레코드를 다시 업데이트 하려고 할 때 데이터 소스는 불일치로 인해 업데이트를 허용 하지 않을 수 있습니다.

클래스의 제한 사항과 관련 된 두 번째 문제 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 사용 하는 경우는 `RFX_Date` 하거나 테이블에서 날짜 및 시간 정보를 전송 하는 함수입니다. 처리는 `CTime` 개체 데이터를 전송 하는 동안 중간 처리의 형태로 약간의 오버 헤드를 적용 합니다. 날짜 범위의 `CTime` 개체 수 또한 너무 제한적일 수 일부 응용 프로그램에 대 한 합니다. 새 버전의 `RFX_Date` 함수는 ODBC *TIMESTAMP_STRUCT* 매개 변수 대신를 `CTime` 개체입니다. 자세한 내용은 `RFX_Date` 에 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 에 *MFC 참조*합니다.

##  <a name="_core_using_the_cursor_library"></a> 커서 라이브러리 사용

데이터 원본에 연결 하는 경우-호출한 [cdatabase:: Openex](../../mfc/reference/cdatabase-class.md#openex) 또는 [cdatabase:: Open](../../mfc/reference/cdatabase-class.md#open) -데이터 원본에 대 한 커서 라이브러리를 사용할 것인지를 지정할 수 있습니다. 해당 데이터 원본에 스냅숏 만들기는, 지정는 `CDatabase::useCursorLib` 옵션을 `dwOptions` 매개 변수를 `OpenEx` 에 대해 TRUE를 지정 하거나는 *bUseCursorLib* 매개 변수를 `Open` (기본값은 TRUE)입니다. ODBC 드라이버가 지 원하는 데이터 원본에 다이너셋 열려는 경우에 커서 라이브러리 (해당 다이너셋에 대 한 필요한 일부 드라이버 기능을 마스크)를 사용 하지 마십시오. 이 경우 지정 하지 않으면 `CDatabase::useCursorLib` 에서 `OpenEx` 에 FALSE를 지정 하거나 합니다 *bUseCursorLib* 매개 변수에서 `Open`.

## <a name="see-also"></a>참고자료

[ODBC 기초](../../data/odbc/odbc-basics.md)