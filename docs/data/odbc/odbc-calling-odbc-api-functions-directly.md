---
title: 'ODBC: ODBC API 함수 직접 호출'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
ms.openlocfilehash: 435df301ad54c7ff5b2f0e46190e3dad7e9c07f1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026385"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API 함수 직접 호출

데이터베이스 클래스를 제공 하기 위한 간단한 인터페이스를 [데이터 원본](../../data/odbc/data-source-odbc.md) 는 ODBC 보다 합니다. 결과적으로, 클래스는 모든 ODBC API를 캡슐화 하지 않습니다. 클래스의 기능을 벗어나는 모든 기능에 대 한 ODBC API 함수를 직접 호출 해야 합니다. ODBC 카탈로그 함수를 호출 해야 하는 예를 들어, (`::SQLColumns`, `::SQLProcedures`, `::SQLTables`, 등) 직접.

> [!NOTE]
>  ODBC 데이터 소스는 이 항목에서 설명하는 MFC ODBC 클래스뿐 아니라 MFC Data Access Object(DAO) 클래스를 통해서도 액세스할 수 있습니다.

직접 ODBC API 함수를 호출 프레임 워크 없이 호출 된 경우 수행 동일한 단계를 수행 해야 합니다. 이러한 단계는:

- 호출이 반환 결과 대 한 저장소를 할당 합니다.

- ODBC 전달 `HDBC` 또는 `HSTMT` 함수의 매개 변수 시그니처에 따라 처리 합니다. 사용 된 [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) ODBC 핸들을 검색 하는 매크로입니다.

   멤버 변수 `CDatabase::m_hdbc` 고 `CRecordset::m_hstmt` 를 사용 하 여 할당 하 고 이러한 직접 초기화할 필요가 없습니다.

- 아마도 준비 하거나 기본 호출은 후속 추가 ODBC 함수를 호출 합니다.

- 완료 하면 저장소 할당을 취소 합니다.

다음이 단계에 대 한 자세한 내용은 참조 하세요. 합니다 [개방형 데이터베이스 연결 (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) MSDN 설명서에서 SDK.

이러한 단계 외에도 함수 반환 값을 확인 하려면 프로그램 비동기 호출을 완료 하 고 기다리고 있지 않도록 추가 단계를 수행 해야 합니다. AFX_SQL_ASYNC 및 AFX_SQL_SYNC 매크로 사용 하 여 마지막 단계를 간소화할 수 있습니다. 자세한 내용은 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 에 *MFC 참조*합니다.

## <a name="see-also"></a>참고자료

[ODBC 기본 사항](../../data/odbc/odbc-basics.md)
