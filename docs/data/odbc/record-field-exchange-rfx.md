---
title: RFX
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
ms.openlocfilehash: 8630fab11728b0c0cd16eee5035df028a8382706
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032221"
---
# <a name="record-field-exchange-rfx"></a>RFX

MFC ODBC 데이터베이스 클래스에는 데이터 원본 간에 데이터 이동 자동화 및 [레코드 집합](../../data/odbc/recordset-odbc.md) 개체입니다. 클래스를 파생 하는 경우 [CRecordset](../../mfc/reference/crecordset-class.md) 대량 행 페치를 사용 하지 않는, 레코드 필드 교환 (RFX) 메커니즘으로 데이터를 전송 합니다.

> [!NOTE]
>  파생 된 대량 행 페치를 구현한 경우 `CRecordset` 클래스를 프레임 워크는 데이터를 전송 대량 레코드 필드 교환 (대량 RFX) 메커니즘을 사용 합니다. 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

RFX (DDX) 대화 상자 데이터 교환 하는 것과 비슷합니다. 레코드 집합의 여러 개의 호출이 필요 데이터 소스 및 레코드 집합의 필드 데이터 멤버 간 데이터 이동 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 프레임 워크 간의 함수와 많은 상호 작용 및 [ODBC](../../data/odbc/odbc-basics.md). RFX 메커니즘은 형식 안전 이며 드는 수 고와 같은 ODBC 함수 호출의 `::SQLBindCol`합니다. DDX에 대한 자세한 내용은 [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md)를 참조하세요.

RFX에 주로 이루어집니다. MFC 응용 프로그램 마법사를 사용 하 여 레코드 집합 클래스를 선언 하는 경우 또는 **클래스 추가** (에 설명 된 대로 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)), RFX에 자동으로 빌드됩니다. 레코드 집합 클래스는 기본 클래스에서 파생 되어야 합니다 `CRecordset` 프레임 워크에서 제공 합니다. MFC 응용 프로그램 마법사를 사용 하면 초기 레코드 집합 클래스를 만들 수 있습니다. **클래스 추가** 필요에 따라 기타 레코드 집합 클래스를 추가할 수 있습니다. 자세한 내용 및 예제를 참조 하세요 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)합니다.

수동으로 하려는 경우 세 가지 경우에는 적은 양의 RFX 코드를 추가 해야 합니다.

- 매개 변수가 있는 쿼리를 사용 합니다. 자세한 내용은 참조 하세요. [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.

- 조인 (두 개 이상의 테이블의 열에 대 한 레코드 집합을 하나 사용)를 수행 합니다. 자세한 내용은 참조 하세요. [레코드 집합: 조인 수행 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)합니다.

- 데이터 열을 동적으로 바인딩하십시오. 매개 변수화 보다 일반적입니다. 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 데이터 열 동적 바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.

RFX에 대 한 고급, 필요한 경우 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)합니다.

다음 항목에서는 레코드 집합 개체를 사용 하 여 세부 정보를 설명 합니다.

- [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)

- [레코드 필드 교환: RFX 함수 사용](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[MFC 애플리케이션 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)