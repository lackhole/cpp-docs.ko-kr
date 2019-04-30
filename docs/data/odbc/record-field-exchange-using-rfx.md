---
title: '레코드 필드 교환: RFX 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: 2a029f653753363e08b3c4f8b9fceab6295924af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395653"
---
# <a name="record-field-exchange-using-rfx"></a>레코드 필드 교환: RFX 사용

이 항목에서는 프레임 워크의 용도 관련 하 여 RFX 사용 하려면 무엇을 설명 합니다.

> [!NOTE]
>  이 항목에서 파생 된 클래스에 적용 됩니다 [CRecordset](../../mfc/reference/crecordset-class.md) 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 대량 레코드 필드 교환 (대량 RFX) 구현 됩니다. 대량 RFX RFX와 비슷합니다. 차이점을 이해 하려면 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

다음 항목에서는 관련된 정보를 포함 합니다.

- [레코드 필드 교환: 마법사 코드 사용](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) RFX의 주요 구성 요소를 소개 하 고 코드를 설명 하는 MFC 응용 프로그램 마법사 및 **클래스 추가** (에 설명 된 대로 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) 작성 RFX와 마법사 코드를 수정 하려는 방식을 지원 하도록

- [레코드 필드 교환: RFX 함수 사용](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) RFX 함수에 대 한 호출을 작성에 설명 하 `DoFieldExchange` 재정의 합니다.

다음 표에서를 용도 프레임 워크와 관련 하 여 역할을 보여 줍니다.

### <a name="using-rfx-you-and-the-framework"></a>RFX 사용: 및 프레임 워크

|사용자|프레임워크|
|---------|-------------------|
|마법사를 사용 하 여 레코드 집합 클래스를 선언 합니다. 필드 데이터 멤버의 이름과 데이터 형식을 지정 합니다.|마법사에서 파생 되는 `CRecordset` 클래스 및 쓰기를 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 를 재정의 각 필드 데이터 멤버에 대 한 호출을 함수는 RFX를 포함 하 여 합니다.|
|(선택 사항) 클래스에 필요한 매개 변수 데이터 멤버를 수동으로 추가 합니다. RFX 함수 호출에 수동으로 추가 `DoFieldExchange` 각 매개 변수 데이터 멤버에 대 한 호출을 추가 [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 매개 변수 그룹에 대 한 매개 변수에서의 총 수를 지정 하 고 [m_nParams ](../../mfc/reference/crecordset-class.md#m_nparams). 참조 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.||
|(선택 사항) 필드 데이터 멤버에 수동으로 추가 열을 바인딩하십시오. 수동으로 늘리려면 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)합니다. 참조 [레코드 집합: (ODBC) 데이터 열 동적 바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.||
|레코드 집합 클래스의 개체를 생성 합니다. 개체를 사용 하기 전에 값을 설정할 매개 변수의 데이터 멤버 있는 경우.|효율성을 높이기 위해 프레임 워크를 워크가 미리 ODBC를 사용 하 여 매개 변수를 바인딩합니다. 매개 변수 값을 전달 하는 경우 프레임 워크 데이터 원본에 전달 합니다. 정렬 및/또는 필터 문자열을 변경 하지 않은 재쿼리에 대 한 매개 변수 값만 전송 됩니다.|
|사용 하 여 레코드 집합 개체를 엽니다 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open)합니다.|레코드 집합의 쿼리를 실행, 호출 및 레코드 집합의 필드 데이터 멤버 열을 바인딩합니다 `DoFieldExchange` 첫 번째 선택 된 레코드 및 레코드 집합의 필드 데이터 멤버 간에 데이터를 교환 합니다.|
|사용 하 여 레코드 집합 스크롤 [CRecordset::Move](../../mfc/reference/crecordset-class.md#move) 또는 메뉴 또는 도구 모음 명령입니다.|호출 `DoFieldExchange` 새 현재 레코드에서 필드 데이터 멤버에 데이터를 전송 합니다.|
|추가, 업데이트 및 레코드를 삭제 합니다.|호출 `DoFieldExchange` 데이터 원본에 데이터를 전송 합니다.|

## <a name="see-also"></a>참고자료

[RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[레코드 집합 합계 및 다른 집계 결과 구하기(ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange 클래스](../../mfc/reference/cfieldexchange-class.md)<br/>
[매크로, 전역 함수 및 전역 변수](../../mfc/reference/mfc-macros-and-globals.md)

