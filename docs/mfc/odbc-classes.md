---
title: ODBC 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
ms.openlocfilehash: 75e022ea3e5de4a57f0ef2b1e3f312654c2889ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237777"
---
# <a name="odbc-classes"></a>ODBC 클래스

이러한 클래스는 다양 한 개방형 데이터베이스 연결 (ODBC) 드라이버를 사용할 수 있는 데이터베이스에 쉽게 액세스할 수 있도록 다른 응용 프로그램 프레임 워크 클래스를 사용 하 여 작동 합니다.

ODBC 데이터베이스를 사용 하는 프로그램 해야 적어도 `CDatabase` 개체 및 `CRecordset` 개체입니다.

[CDatabase](../mfc/reference/cdatabase-class.md)<br/>
데이터 원본에서 작동할 수 있는 데이터 원본에 연결을 캡슐화 합니다.

[CRecordset](../mfc/reference/crecordset-class.md)<br/>
데이터 원본에서 선택한 레코드 집합을 캡슐화 합니다. 레코드 집합 사용 (추가, 편집 및 레코드를 삭제 하는 중) 레코드를 업데이트, 필터를 사용 하 여 선택 영역을 한 정하는 레코드 스크롤 선택 항목을 정렬 하 고 가져온 정보를 사용 하 여 선택을 매개 변수화 또는 런타임 시 계산.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
양식을 제공 레코드 집합 개체에 직접 연결 하는 보기입니다. 대화 상자 데이터 교환 (DDX) 메커니즘의 레코드 집합 및 레코드 뷰에서의 컨트롤 간에 데이터를 교환 합니다. 모든 폼 보기와 같은 레코드 뷰는 대화 상자 템플릿 리소스를 기반으로 합니다. 레코드 뷰는 레코드 집합의 레코드를 이동, 레코드를 업데이트 및 레코드 보기를 닫으면 관련된 레코드 집합을 닫는 지원 합니다.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
결과 데이터 액세스에서 오류에서 처리는 예외입니다. 이 클래스에는 클래스 라이브러리의 예외 처리 메커니즘에 다른 예외 클래스와 동일한 용도로 사용 됩니다.

[CFieldExchange](../mfc/reference/cfieldexchange-class.md)<br/>
필드 데이터 멤버 및 매개 변수 데이터 멤버 레코드 집합 개체와 데이터 원본에 있는 해당 테이블 열 간에 데이터를 교환 하는 레코드 필드 교환 (RFX)를 지원 하기 위한 컨텍스트 정보를 제공 합니다. 클래스와 유사 [CDataExchange](../mfc/reference/cdataexchange-class.md), 마찬가지로 (DDX) 대화 상자 데이터 교환에 사용 됩니다.

## <a name="related-classes"></a>관련된 클래스

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
비트맵 같은 이진 큰 개체 (BLOB) 저장소에 대 한 핸들을 캡슐화합니다. `CLongBinary` 개체는 데이터베이스 테이블에 저장 된 큰 데이터 개체를 관리 하는 데 사용 됩니다.

[CDBVariant](../mfc/reference/cdbvariant-class.md)<br/>
값의 데이터 형식에 대 한 걱정 없이 값을 저장할 수 있습니다. `CDBVariant` 데이터 형식의 공용 구조체에 저장 된 현재 값을 추적 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
