---
title: '레코드 필드 교환: RFX 함수 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], data types
- data types [C++], ODBC record field exchange
- RFX (ODBC) [C++], function syntax and parameters
- DoFieldExchange method, and RFX functions
- ODBC [C++], RFX
- RFX (ODBC) [C++], data types
- function calls, RFX functions
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
ms.openlocfilehash: dc717336a5279e7eda1b7c39b19a7c76f9055cd3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395692"
---
# <a name="record-field-exchange-using-the-rfx-functions"></a>레코드 필드 교환: RFX 함수 사용

이 항목의 본문을 구성 하는 RFX 함수 호출을 사용 하는 방법에 설명 하 `DoFieldExchange` 재정의 합니다.

> [!NOTE]
>  이 항목에서 파생 된 클래스에 적용 됩니다 [CRecordset](../../mfc/reference/crecordset-class.md) 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 대량 레코드 필드 교환 (대량 RFX) 구현 됩니다. 대량 RFX RFX와 비슷합니다. 차이점을 이해 하려면 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

RFX 전역 함수는 레코드 집합에서 데이터 원본 및 필드 데이터 멤버의 열 간에 데이터를 교환 합니다. 레코드 집합의는 RFX 함수 호출을 작성할 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 멤버 함수입니다. 이 항목에서는 함수를 간략히 설명 하 고 함수를 사용할 수 있는 RFX에 대 한 데이터 형식을 보여 줍니다. [기술 참고 43](../../mfc/tn043-rfx-routines.md) 추가 데이터 형식에 대 한 고유한 RFX 함수를 작성 하는 방법에 설명 합니다.

##  <a name="_core_rfx_function_syntax"></a> RFX 함수 구문

세 가지 매개 변수를 사용 하는 각 RFX 함수 (및 선택적 다섯 번째 또는 네 번째 매개 변수 사용):

- 에 대 한 포인터를 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체입니다. 간단히 전달 합니다 `pFX` 포인터가 전달 `DoFieldExchange`합니다.

- 데이터 원본에 해당 열의 이름을 표시 됩니다.

- 해당 필드 데이터 멤버 또는 레코드 집합 클래스에서 매개 변수 데이터 멤버의 이름입니다.

- (선택 사항) 일부 함수, 전송 되는 배열 또는 문자열의 최대 길이입니다. 기본값은 255 바이트 있지만 변경 하는 것이 좋습니다. 최대 크기를 기준으로 하는 최대 크기는 `CString` 개체 — **INT_MAX** (2147483647) 바이트인-드라이버 한계값 크기는 아마도 하지만 합니다.

- (선택 사항) 에 `RFX_Text` 함수, 경우에 따라 사용할 다섯 번째 매개 변수 열의 데이터 형식을 지정 합니다.

자세한 내용은 아래 RFX 함수 참조 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 에 *클래스 라이브러리 참조*합니다. 매개 변수 사용의 경우 수행할 수 있는 특별 한 예 [레코드 집합: 합계 및 다른 집계 결과 (ODBC) 구하기](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)합니다.

##  <a name="_core_rfx_data_types"></a> RFX 데이터 형식

클래스 라이브러리는 다양 한 데이터 형식 데이터 원본 및 레코드 집합 간의 전송에 대해 RFX 함수를 제공 합니다. 다음 목록에는 데이터 형식에 의해 RFX 함수 요약 되어 있습니다. 사용자 고유의 RFX 함수 호출 작성 해야 하는 경우에 데이터 형식으로 이러한 함수에서 선택 합니다.

|함수|데이터 형식|
|--------------|---------------|
|`RFX_Bool`|**BOOL**|
|`RFX_Byte`|**BYTE**|
|`RFX_Binary`|`CByteArray`|
|`RFX_Double`|**double**|
|`RFX_Single`|**float**|
|`RFX_Int`|**int**|
|`RFX_Long`|**long**|
|`RFX_LongBinary`|`CLongBinary`|
|`RFX_Text`|`CString`|
|`RFX_Date`|`CTime`|


자세한 내용은 아래 RFX 함수 설명서를 참조 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md) 에 *클래스 라이브러리 참조*합니다. 하는 방법에 대 한 자세한 C++ SQL 데이터 형식으로 데이터 형식 맵 ANSI SQL 데이터 형식 매핑 표를 참조 하려면 C++ 의 데이터 형식 [SQL: SQL 및 C++ 데이터 형식 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)합니다.

## <a name="see-also"></a>참고자료

[RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[레코드 집합 레코드 집합 매개 변수화(ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[레코드 집합 데이터 열 동적 바인딩(ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange 클래스](../../mfc/reference/cfieldexchange-class.md)