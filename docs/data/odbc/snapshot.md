---
title: 스냅숏
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], snapshots
- cursors [ODBC], static
- recordsets, snapshots
- snapshots, support in ODBC
- static cursors
- ODBC recordsets, snapshots
- cursor library [ODBC], snapshots
- snapshots
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
ms.openlocfilehash: 5999f89156d895ff0c87c892be892c6a614a0132
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330039"
---
# <a name="snapshot"></a>스냅숏

스냅숏은은 스냅숏이 만들어진 시점에 존재 했던 상태로 데이터의 정적 뷰를 반영 하는 레코드 집합입니다. 스냅숏을 열고 모든 레코드를 이동 하는 경우 포함 된 여러 레코드 집합 및 스냅숏을 호출 하 여 다시 작성할 때까지 해당 값이 바뀌지 않는 `Requery`합니다.

> [!NOTE]
>  이 항목에서는 MFC ODBC 클래스에 적용됩니다. MFC ODBC 클래스 대신 MFC DAO 클래스를 사용 하는 경우 [cdaorecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open) 스냅숏 형식 레코드 집합에 대 한 합니다.

데이터베이스 클래스를 사용 하 여 업데이트 가능 또는 읽기 전용 스냅숏을 만들 수 있습니다. 다이너셋, 달리를 업데이트할 수 있는 스냅숏 레코드 값을 다른 사용자가 수행한 변경 내용을 반영 하지 않습니다 않지만 업데이트 및 삭제 사용자 프로그램에서 수행한 반영 합니다. 호출할 때까지 스냅숏으로 추가 된 레코드 스냅숏으로 표시 되지 않습니다 `Requery`합니다.

> [!TIP]
>  스냅숏은은 ODBC 정적 커서입니다. 정적 커서 실제로 가져오지 못합니다 데이터 행을 해당 레코드를 스크롤할 때까지. 모든 레코드를 즉시 검색을 위해 레코드 집합의 끝으로 스크롤하여를 확인 하려는 첫 번째 레코드를 스크롤합니다. 그러나 끝으로 스크롤하면 추가 오버 헤드가 수반 및 성능이 저하 note 합니다.

스냅숏은 데이터가 보고서를 생성 하거나 계산을 수행할 때 처럼 작업을 하는 동안 고정 되어 있는 경우 가장 중요 합니다. 이 경우에 데이터 원본 수 상당히 달라 집니다, 스냅숏에서 않으므로 수시로 다시 작성 해야 할 수 있습니다.

스냅숏 지원은 위치 지정 업데이트 (업데이트 필요) Level 1 드라이버에 대 한 및 정적 커서를 제공 하는 ODBC 커서 라이브러리를 기반으로 합니다. 커서 라이브러리 DLL이이 지원에 대 한 메모리에 로드 되어야 합니다. 생성 하는 경우는 `CDatabase` 개체와 호출 해당 `OpenEx` 지정 해야 멤버 함수는 `CDatabase::useCursorLib` 옵션을를 *dwOptions* 매개 변수입니다. 호출 하는 경우는 `Open` 커서 라이브러리 멤버 함수는 기본적으로 로드 됩니다. 다이너셋 스냅숏 대신를 사용 하는 경우 커서 라이브러리를 로드 하지 않을 수 있습니다.

ODBC 커서 라이브러리 때 로드 된 경우에 사용할 수 있는 스냅숏이 `CDatabase` 생성 된 개체 또는 사용 하는 ODBC 드라이버는 정적 커서를 지원 합니다.

> [!NOTE]
>  일부 ODBC 드라이버에서는 스냅숏 (정적 커서)을 업데이트 하지 못할 수도 있습니다. 지원 되는 커서 유형에 대해 드라이버 설명서를 지 원하는 동시성 유형은 확인 합니다. 업데이트할 수 있는 스냅숏을 보장 하기 위해 만들 때 커서 라이브러리를 메모리로 로드 있는지 확인 한 `CDatabase` 개체입니다. 자세한 내용은 참조 하세요. [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)합니다.

> [!NOTE]
>  스냅숏과 다이너셋 둘 다 사용 하려는 경우 두 가지에 기반 해야 `CDatabase` 개체 (두 개의 서로 다른 연결).

모든 레코드 집합을 사용 하 여 속성 스냅숏 공유에 대 한 자세한 내용은 참조 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)합니다. ODBC 및 스냅숏, ODBC 커서 라이브러리를 포함 하는 방법에 대 한 자세한 내용은 참조 [ODBC](../../data/odbc/odbc-basics.md)합니다.

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)