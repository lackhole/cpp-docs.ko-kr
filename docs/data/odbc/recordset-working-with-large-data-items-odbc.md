---
title: '레코드 집합: 대형 데이터 항목 (ODBC)를 사용 하 여 작업'
ms.date: 11/04/2016
helpviewer_keywords:
- BLOB (binary large object), recordsets
- ODBC recordsets, binary large objects
- recordsets, binary large objects
- binary large objects
- CLongBinary class, using in recordsets
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
ms.openlocfilehash: 3ba8d4af5b0781c425dd3b1223e2208b279f055e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230984"
---
# <a name="recordset-working-with-large-data-items-odbc"></a>레코드 집합: 대형 데이터 항목 (ODBC)를 사용 하 여 작업

이 항목에서는 MFC ODBC 클래스와 MFC DAO 클래스에 적용 됩니다.

> [!NOTE]
>  MFC DAO 클래스를 사용 하는 경우 클래스를 사용 하 여 대형 데이터 항목을 관리 [CByteArray](../../mfc/reference/cbytearray-class.md) 클래스 대신 [CLongBinary](../../mfc/reference/clongbinary-class.md)합니다. MFC ODBC 클래스를 사용 하 여 대량 행 페치를 사용 하는 경우 사용 하 여 `CLongBinary` 대신 `CByteArray`합니다. 대량 행 페치에 대 한 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

데이터베이스 대형 비트맵 (직원 사진을, maps, 제품, OLE 개체 및 등의 사진을)와 같은 데이터를 저장할 수 있다고 가정 합니다. 이러한 종류의 데이터는 라고도 Binary Large Object (또는 BLOB) 때문에:

- 각 필드 값이 큽니다.

- 숫자 및 기타 단순 데이터 유형의 경우는 달리 크기를 예측할 수 없습니다.

- 데이터는 프로그램의 일정치.

이 항목에서는 이러한 개체로 작업 하기 위한 데이터베이스 클래스에서 제공 하는 지원 기능을 설명 합니다.

##  <a name="_core_managing_large_objects"></a> 큰 개체를 관리합니다.

레코드 집합에는 이진 대형 개체 관리를 쉽게 해결 하기 위해 두 가지입니다. 클래스를 사용할 수 있습니다 [CByteArray](../../mfc/reference/cbytearray-class.md) 클래스를 사용할 수 있습니다 [CLongBinary](../../mfc/reference/clongbinary-class.md)합니다. 일반적으로 `CByteArray` 는 큰 이진 데이터를 관리 하는 기본 방법입니다.

`CByteArray` 보다 오버 헤드가 더 많이 `CLongBinary` 이지만 더욱 강력한에 설명 된 대로 [CByteArray 클래스](#_core_the_cbytearray_class)합니다. `CLongBinary` 에 대해 간략하게 설명 되어 [CLongBinary 클래스](#_core_the_clongbinary_class)합니다.

사용에 대 한 자세한 내용은 `CByteArray` 대형 데이터 항목을 사용 하려면 참조 [기술 참고 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)합니다.

##  <a name="_core_the_cbytearray_class"></a> CByteArray 클래스

`CByteArray` MFC 컬렉션 클래스 중 하나입니다. `CByteArray` 개체는 바이트의 동적 배열을 저장-필요에 따라 배열 커질 수 있습니다. 클래스는 빠른 액세스 인덱스로, 기본 제공와 마찬가지로 C++ 배열입니다. `CByteArray` 개체 직렬화 하 고 진단용으로 덤프할 수 있습니다. 가져오기 및 지정 된 바이트를 설정, 삽입 및 바이트를 추가 및 1 바이트 또는 모든 바이트를 제거 하기 위한 멤버 함수를 제공 하는 클래스입니다. 이러한 기능 이진 데이터를 더 쉽게 구문 분석을 확인 합니다. 예를 들어 이진 개체 OLE 개체 이면 실제 개체에 연결할 일부 헤더 바이트를 통해 작업 하는 것이 해야 합니다.

##  <a name="_core_using_cbytearray_in_recordsets"></a> CByteArray를 사용 하 여 레코드 집합

형식 레코드 집합의 필드 데이터 멤버를 제공 하 여 `CByteArray`에 고정 된 기본 제공 [RFX](../../data/odbc/record-field-exchange-rfx.md) 조작할 수 있습니다 및 레코드 집합 및 데이터 원본 간에 이러한 개체의 전송을 관리할 수는 개체 내의 데이터입니다. RFX 검색된 데이터에 대 한 특정 사이트도 필요 하 고 기본 데이터에 액세스 하는 방법이 필요 합니다.

사용에 대 한 자세한 내용은 `CByteArray` 대형 데이터 항목을 사용 하려면 참조 [기술 참고 45](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)합니다.

##  <a name="_core_the_clongbinary_class"></a> CLongBinary 클래스

A [CLongBinary](../../mfc/reference/clongbinary-class.md) 주위 간단한 셸 개체가 `HGLOBAL` 힙에 할당 된 저장소의 블록에 대 한 핸들입니다. 이진 대형 개체를 포함 하는 테이블 열을 바인딩할 때 RFX 할당 합니다 `HGLOBAL` 레코드 집합에 데이터를 전송 해야 하 고 있는 핸들을 저장할 때 처리를 `CLongBinary` 레코드 집합의 필드입니다.

를 사용 하 여는 `HGLOBAL` 처리할 `m_hData`으로 처리할 수 있습니다 하나에서 데이터에 운영 데이터 자체를 사용 하 여 작업 합니다. 이 경우 [CByteArray](../../mfc/reference/cbytearray-class.md) 기능을 추가 합니다.

> [!CAUTION]
>  CLongBinary 개체는 함수 호출에서 매개 변수로 사용할 수 없습니다. 또한 호출 하는 구현과 `::SQLGetData`으로 스크롤할 수 있는 스냅숏에 대 한 스크롤 속도가 느려집니다. 이 발생할 수 있습니다 사용 하는 경우는 `::SQLGetData` 동적 스키마 열을 검색 하기 위해 직접 호출 합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합 합계 및 다른 집계 결과 구하기(ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)