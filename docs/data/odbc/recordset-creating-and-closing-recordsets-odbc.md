---
title: '레코드 집합: 만들 레코드 집합 및 닫기 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, creating
- recordsets, creating
- recordsets, opening
- recordsets, closing
- ODBC recordsets, closing
- ODBC recordsets, opening
ms.assetid: 8d2aac23-4396-4ce2-8c60-5ecf1b360d3d
ms.openlocfilehash: 5d5dae5bc766c0cfc31b4fb76f7fe104be0dbd74
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041269"
---
# <a name="recordset-creating-and-closing-recordsets-odbc"></a>레코드 집합: 만들 레코드 집합 및 닫기 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

레코드 집합을 사용 하려면 레코드 집합 개체를 생성 하 고 호출 후 해당 `Open` 멤버 함수는 레코드 집합의 쿼리를 실행 하 고 레코드를 선택 합니다. 레코드 집합을 사용 하 여를 완료 하면 닫고 개체를 제거 합니다.

이 항목에 설명 합니다.

- [레코드 집합 개체를 만드는 방법과 시기](#_core_creating_recordsets_at_run_time)합니다.

- [매개 변수화, 필터링, 정렬 또는 잠금을 레코드 집합의 동작을 한정할 수 있습니다 시기와 방법을](#_core_setting_recordset_options)합니다.

- [레코드 집합 개체를 닫는 방법과 시기](#_core_closing_a_recordset)합니다.

##  <a name="_core_creating_recordsets_at_run_time"></a> 런타임에 레코드 집합 만들기

프로그램에서 레코드 집합 개체를 만들 수 있습니다, 전에 일반적으로 응용 프로그램 관련 레코드 집합 클래스를 작성 합니다. 이 예비 단계에 대 한 자세한 내용은 참조 하세요. [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)합니다.

데이터 원본에서 레코드를 선택 해야 할 때 스냅숏 개체를 엽니다. 만들 개체의 형식을 수행 해야 하는 새로운 종속 응용 프로그램에서 ODBC 드라이버 지원에 데이터를 사용 하 여 합니다. 자세한 내용은 [다이너셋](../../data/odbc/dynaset.md) 하 고 [스냅숏](../../data/odbc/snapshot.md)합니다.

#### <a name="to-open-a-recordset"></a>레코드 집합을 열려면

1. 개체를 생성 하면 `CRecordset`-클래스를 파생 합니다.

   힙의 또는 함수의 스택 프레임에서 개체를 생성할 수 있습니다.

1. 필요에 따라 기본 레코드 집합 동작을 수정 합니다. 사용 가능한 옵션에 대해서 [레코드 집합 옵션 설정](#_core_setting_recordset_options)합니다.

1. 개체의 호출 [열고](../../mfc/reference/crecordset-class.md#open) 멤버 함수입니다.

생성자에서 전달에 대 한 포인터를 `CDatabase` 개체 또는 프레임 워크를 생성 하는 임시 데이터베이스 개체를 사용 하는 NULL을 반환 하는 연결 문자열에 따라 엽니다 전달 합니다 [GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) 멤버 함수. `CDatabase` 개체 데이터 소스에 이미 연결 되어 있습니다.

에 대 한 호출 `Open` SQL를 사용 하 여 데이터 원본에서 레코드를 선택 합니다. 첫 번째 레코드 (해당 되는 경우)를 선택 합니다. 현재 레코드가 됩니다. 이 레코드의이 필드의 값은 레코드 집합 개체의 필드 데이터 멤버에 저장 됩니다. 레코드가 선택 된 경우 모두를 `IsBOF` 및 `IsEOF` 멤버 함수는 0을 반환 합니다.

사용자 [열려](../../mfc/reference/crecordset-class.md#open) 호출을 할 수 있습니다.

- 레코드 집합이 다이너셋 또는 스냅숏 인지 여부를 지정 합니다. 레코드 집합 스냅숏으로 기본적으로 열립니다. 또는 앞 으로만 이동 가능한 레코드 집합에서 앞 으로만 스크롤을 한 번에 하나의 레코드를 허용 하는 지정할 수 있습니다.

   기본적으로 레코드 집합에 저장 된 기본 형식을 사용 하 여 `CRecordset` 데이터 멤버 `m_nDefaultType`합니다. 초기화 하는 코드를 작성 하는 마법사 `m_nDefaultType` 마법사에서 선택한 레코드 집합 형식입니다. 이 기본값을 적용 하는 대신 다른 레코드 집합 형식이 대체할 수 있습니다.

- 기본 SQL을 대체 하는 문자열을 지정 **선택** 레코드 집합에서 생성 하는 문입니다.

- 읽기 전용 또는 추가 전용 레코드 집합 인지 여부를 지정 합니다. 레코드 집합은 전체 기본적으로 업데이트가 가능 하지만 새 레코드만 추가 하는 제한할 수 있습니다 하거나 모든 업데이트를 차단할 수 있습니다.

다음 예제에서는 클래스의 읽기 전용 스냅숏 개체를 사용 하 여 방법 `CStudentSet`, 하는 응용 프로그램 관련 클래스:

```cpp
// Construct the snapshot object
CStudentSet rsStudent( NULL );
// Set options if desired, then open the recordset
if(!rsStudent.Open(CRecordset::snapshot, NULL, CRecordset::readOnly))
    return FALSE;
// Use the snapshot to operate on its records...
```

호출한 후 `Open`, 개체 멤버 함수 및 데이터 멤버를 사용 하 여 레코드를 사용 하 여 작동 합니다. 일부 경우에서 쿼리하거나 데이터 원본에서 발생 한 변경 내용을 포함 하는 레코드 집합을 새로 고치지는 것이 좋습니다. 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 레코드 집합 다시 쿼리](../../data/odbc/recordset-requerying-a-recordset-odbc.md)합니다.

> [!TIP]
>  개발 중 사용할 연결 문자열에는 최종 사용자가 동일한 연결 문자열을 사용할 수 없습니다. 이런 맥락에서 응용 프로그램을 일반화 하는 방법에 대 한 아이디어를 참조 하세요. [데이터 원본: 연결 관리 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)합니다.

##  <a name="_core_setting_recordset_options"></a> 레코드 집합 옵션 설정

레코드 집합 개체를 생성 하지만 호출 하기 전에 `Open` 레코드를 선택 하려면 레코드 집합의 동작을 제어 하는 몇 가지 옵션을 설정 수 있습니다. 모든 레코드 집합에 대해 다음을 수행할 수 있습니다.

- 지정 된 [필터](../../data/odbc/recordset-filtering-records-odbc.md) 레코드 선택을 제한 하 합니다.

- 지정 된 [정렬](../../data/odbc/recordset-sorting-records-odbc.md) 레코드 순서입니다.

- 지정할 [매개 변수](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 가져오거나 런타임에 계산 된 정보를 사용 하 여 레코드를 선택할 수 있도록 합니다.

조건이 올바른 경우에 다음과 같은 옵션을 설정할 수 있습니다.

- 레코드 집합을 업데이트할 수이 고 잠금 옵션을 지원 하는 경우 지정 된 [잠금](../../data/odbc/recordset-locking-records-odbc.md) 업데이트에 사용 되는 메서드.

> [!NOTE]
>  레코드 선택의 영향을 줄이 옵션을 설정 해야 이러한 호출 하기 전에 `Open` 멤버 함수입니다.

##  <a name="_core_closing_a_recordset"></a> 레코드 집합을 닫으면

레코드 집합을 사용 하 여를 완료 하면 삭제 하 고 메모리 할당을 취소 해야 합니다.

#### <a name="to-close-a-recordset"></a>레코드 집합을 닫으려면

1. 호출 해당 [닫기](../../mfc/reference/crecordset-class.md#close) 멤버 함수입니다.

1. 레코드 집합 개체를 삭제 합니다.

   함수의 스택 프레임에 선언한 경우 개체는 개체가 범위를 벗어날 때 자동으로 삭제 됩니다. 그렇지 않은 경우 사용 합니다 **삭제** 연산자입니다.

`Close` 레코드 집합의 해제 `HSTMT` 처리 합니다. 제거 하지 않습니다는 C++ 개체입니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)<br/>
[레코드 집합: 추가, 업데이트 및 삭제할 레코드 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)