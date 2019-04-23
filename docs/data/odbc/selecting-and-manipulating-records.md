---
title: 레코드 선택 및 조작
ms.date: 11/04/2016
helpviewer_keywords:
- records, selecting
- record selection, MFC ODBC classes
- ODBC recordsets, selecting records
ms.assetid: 7f0b3a4a-9941-4475-a612-9ec8d15b7691
ms.openlocfilehash: fa8b63dab24c921804c474df73f6b6da192a4cd8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027495"
---
# <a name="selecting-and-manipulating-records"></a>레코드 선택 및 조작

일반적으로 선택 하면 레코드 SQL을 사용 하 여 데이터 원본의 **선택** 레코드 테이블 또는 쿼리 집합은 결과 집합을 얻게 문입니다. 데이터베이스 클래스를 사용 하 여 레코드 집합 개체를 선택 하 고 결과 집합에 액세스. 이 클래스에서 파생 되는 응용 프로그램 관련 클래스의 개체인 [CRecordset](../../mfc/reference/crecordset-class.md)합니다. 레코드 집합 클래스를 정의할 때 사용 하 여 연결할 데이터 원본를 사용 하려면 테이블 및 테이블의 열을 지정 합니다. MFC 응용 프로그램 마법사 또는 **클래스 추가** (에 설명 된 대로 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) 특정 데이터 원본에 연결 된 클래스를 만듭니다. 마법사에서 작성 된 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) 클래스의 멤버 함수 `CRecordset` 테이블 이름을 반환할 합니다. 레코드 집합 클래스를 만드는 마법사를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [MFC 응용 프로그램 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md) 하 고 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)합니다.

사용 하는 [CRecordset](../../mfc/reference/crecordset-class.md) 하면 런타임 시 개체:

- 현재 레코드의 데이터 필드를 검사 합니다.

- 필터링 또는 레코드 집합을 정렬 합니다.

- 기본 SQL 사용자 지정 **선택** 문입니다.

- 선택한 레코드를 스크롤하십시오.

- 추가, 업데이트 또는 삭제 레코드 (데이터 원본 및 레코드 집합을 모두 업데이트할 수 있는 경우).

- 레코드 집합 다시 쿼리를 허용 하는지 여부를 테스트 하 고 레코드 집합의 콘텐츠를 새로 고칩니다.

레코드 집합 개체를 사용 하 여를 완료 하면 닫고 삭제 합니다. 레코드 집합에 대 한 자세한 내용은 참조 하세요. [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)합니다.

## <a name="see-also"></a>참고자료

[ODBC 및 MFC](../../data/odbc/odbc-and-mfc.md)