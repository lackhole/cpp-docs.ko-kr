---
title: 'TN043: RFX 루틴'
ms.date: 06/28/2018
f1_keywords:
- RFX
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
ms.openlocfilehash: 18820c7d17ddea355490ee32679d5d690ec3533e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305400"
---
# <a name="tn043-rfx-routines"></a>TN043: RFX 루틴

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 레코드 필드 교환 (RFX) 아키텍처를 설명합니다. 또한 작성 하는 방법 설명를 **RFX_** 프로시저입니다.

## <a name="overview-of-record-field-exchange"></a>레코드 필드 교환 개요

모든 레코드 집합 필드 함수 완료 하는 C++ 코드입니다. 특수 리소스 또는 magic 매크로 없는 합니다. 메커니즘의 핵심은 모든 레코드 집합 파생된 클래스에서 재정의 되어야 하는 가상 함수입니다. 항상이 폼에서 발견 되었습니다.

```cpp
void CMySet::DoFieldExchange(CFieldExchange* pFX)
{
    //{{AFX_FIELD_MAP(CMySet)
        <recordset exchange field type call>
        <recordset exchange function call>
    //}}AFX_FIELD_MAP
}
```

특별 한 형식 AFX 주석을 ClassWizard를 찾아이 함수 내에서 코드를 편집할 수 있습니다. 특별 한 형식 설명을 외부 클래스 마법사를 사용 하 여 호환 되지 않는 코드를 배치 되어야 합니다.

위의 예에서 \<recordset_exchange_field_type_call > 형식:

```cpp
pFX->SetFieldType(CFieldExchange::outputColumn);
```

및 \<recordset_exchange_function_call > 형식:

```cpp
RFX_Custom(pFX, "Col2", m_Col2);
```

대부분의 **RFX_** 함수 3 개 인수를 위에 표시 된 대로 하지만 일부 (예: `RFX_Text` 및 `RFX_Binary`) 추가 선택적 인수를 포함 합니다.

둘 이상의 **RFX_** 각각에 포함 될 수 있습니다 `DoDataExchange` 함수입니다.

MFC를 사용 하 여 제공 하는 모든 레코드 필드 교환 루틴의 목록은 ' afxdb.h'를 참조 하세요.

레코드 집합 필드 호출은 필드의 데이터를 저장 하는 메모리 위치 (일반적으로 데이터 멤버)을 등록 하는 방법을 `CMySet` 클래스입니다.

## <a name="notes"></a>노트

레코드 집합 필드 함수 에서만 작동 하도록 설계 됩니다는 `CRecordset` 클래스입니다. 다른 MFC 클래스에서 일반적으로 사용할 수 없습니다.

표준 데이터의 초기 값을 설정 C++ 블록에 일반적으로 생성자 `//{{AFX_FIELD_INIT(CMylSet)` 하 고 `//}}AFX_FIELD_INIT` 주석입니다.

각 **RFX_** 함수까지 필드를 편집 하는 준비 과정에서 필드를 보관 하는 필드의 변경 상태를 반환 하는 다양 한 작업을 지원 해야 합니다.

호출 하는 각 함수 `DoFieldExchange` (예를 들어 `SetFieldNull`를 `IsFieldDirty`)를 자체 초기화에 대 한 호출 주위에 `DoFieldExchange`입니다.

## <a name="how-does-it-work"></a>어떻게 작동 하나요

레코드 필드 교환을 사용 하려면 다음을 이해할 필요가 없습니다. 그러나 이해 백그라운드에서이 과정에서는 exchange 프로시저를 직접 작성 합니다.

`DoFieldExchange` 멤버 함수는 매우 유사 합니다 `Serialize` 멤버 함수-가져오거나 간에 클래스의 멤버 데이터에는 외부 형태로 (ODBC 쿼리 결과에서이 사례 열)에서 데이터를 설정 하는 일을 담당 합니다. *pFX* 매개 변수 데이터 교환을 수행 하기 위한 컨텍스트가 유사 합니다 *CArchive* 매개 변수를 `CObject::Serialize`입니다. *pFX* (을 `CFieldExchange` 개체)에 비슷하지만, 작업 표시기 있지만 일반화 한를 *CArchive* 방향 플래그. RFX 함수는 다음 작업을 지원 해야 할 수 있습니다.

- `BindParam` -ODBC 매개 변수 데이터를 검색 해야 위치 표시

- `BindFieldToColumn` -여기서 ODBC 해야 검색/입금 outputColumn 데이터를 표시 합니다.

- `Fixup` -설정 `CString/CByteArray` 길이, NULL 상태 비트 설정

- `MarkForAddNew` -표시 더티 값 AddNew 호출 이후 변경 된 경우

- `MarkForUpdate` -표시 값 편집 호출 이후 변경 된 경우 부적절 한

- `Name` -더티 표시 된 필드에 대 한 필드 이름을 추가 합니다.

- `NameValue` -추가 "\<열 이름 > =" 더티 표시 된 필드에 대 한

- `Value` -추가 ""와 같은 구분 기호 뒤에 ',' 또는 ' '

- `SetFieldDirty` --상태 비트 커밋되지 않은 데이터 (예: 변경된) 필드를 설정 하는 중

- `SetFieldNull` --필드에 null 값을 나타내는 상태 비트를 설정 하는 중

- `IsFieldDirty` -더티 상태 비트의 값을 반환 합니다.

- `IsFieldNull` -Null 상태 비트의 값을 반환 합니다.

- `IsFieldNullable` -필드는 NULL 값을 포함할 수 있는 경우 TRUE를 반환

- `StoreField` -보관 필드 값

- `LoadField` --보관 된 필드 값을 로드 하는 중

- `GetFieldInfoValue` -필드의 일반 정보를 반환 합니다.

- `GetFieldInfoOrdinal` -필드의 일반 정보를 반환 합니다.

## <a name="user-extensions"></a>사용자 확장

기본 RFX 메커니즘을 확장 하는 방법은 여러 가지가 있습니다. 다음과 같은 작업을 수행할 수 있습니다.

- 새 데이터 형식을 추가 합니다. 예를 들어:

    ```cpp
    CBookmark
    ```

- 새 exchange 프로시저 (RFX_)를 추가 합니다.

    ```cpp
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
        const char *szName,
        BIGINT& value);
    ```

- 가 합니다 `DoFieldExchange` 멤버 함수는 조건에 따라 추가 RFX 호출 또는 모든 기타 유효한 포함 C++ 문입니다.

    ```cpp
    while (posExtraFields != NULL)
    {
        RFX_Text(pFX,
        m_listName.GetNext(posExtraFields),
        m_listValue.GetNext(posExtraValues));
    }
    ```

> [!NOTE]
> 이러한 코드 classwizard 함께 사용 하 여 편집할 수 없습니다 하 고 특별 한 형식 설명 외에 사용 해야 합니다.

## <a name="writing-a-custom-rfx"></a>사용자 지정 RFX 작성

사용자 고유의 사용자 지정 RFX 함수를 작성 하려면 기존 RFX 함수를 복사 하 고 용도 맞게를 수정 하는 것이 좋습니다. 복사할 오른쪽 RFX 선택 작업 훨씬 쉽게 수 있습니다. 일부 RFX 함수에 복사할 결정할 때 고려해 야 하는 몇 가지 고유한 속성이 있습니다.

`RFX_Long` 및 `RFX_Int`: 이들은 단순한 RFX 함수입니다. 데이터 값에 특수 한 모든 해석은 필요가 및 데이터 크기가 고정 되어 있습니다.

`RFX_Single` 및 `RFX_Double`: RFX_Long 및 RFX_Int 위의 경우와 마찬가지로 이러한 함수는 간단 하 고 가능 기본 구현의 광범위 하 게 사용 합니다. 하지만 부동 소수점 라이브러리는 명시적으로 참조 하는 경우에 런타임을 로드할 수 있도록 dbflt.cpp dbrfx.cpp, 대신에 저장 됩니다.

`RFX_Text` 및 `RFX_Binary`: 이 두 함수는 문자열/이진 정보를 저장 하는 정적 버퍼를 미리 할당 및 등록 (& v) 대신 ODBC SQLBindCol를 사용 하 여 이러한 버퍼를 등록 해야 합니다. 이 때문에이 두 함수를 사용 하면 특별 한 경우 코드의 많은 합니다.

`RFX_Date`: ODBC는 고유한 TIMESTAMP_STRUCT 데이터 구조에 날짜 및 시간 정보를 반환합니다. 이 함수는 TIMESTAMP_STRUCT "프록시"로 날짜 시간 데이터 보내기 및 받기에 대 한 동적으로 할당 합니다. 다양 한 작업 간에 날짜 및 시간 정보를 전송 해야는 C++ `CTime` 개체 및 TIMESTAMP_STRUCT 프록시입니다. 이 인해이 함수 상당히 이지만 데이터 전송에 대 한 프록시를 사용 하는 방법의 좋은 예입니다.

`RFX_LongBinary`: 이것이 유일한 클래스 라이브러리 데이터를 보내고 받도록 열 바인딩을 사용 하지 않는 RFX 함수입니다. 이 함수 무시 BindFieldToColumn 작업 대신 수정 작업 중 들어오는 SQL_LONGVARCHAR 또는 SQL_LONGVARBINARY 데이터를 저장할 저장소를 할당 하 고 할당 된 저장소에 값을 검색에 대 한 SQLGetData 호출을 수행 합니다. 데이터 원본 (예: NameValue 및 값 작업)에 데이터 값을 다시 보낼 준비를 하는 경우이 함수는 ODBC의 DATA_AT_EXEC 기능을 사용 합니다. 참조 [기술 참고 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) SQL_LONGVARBINARY 및 SQL_LONGVARCHARs 작업에 대 한 자세한 내용은 합니다.

자신의 코드를 작성 하는 경우 **RFX_** 함수를 자주 해야 사용할 수 `CFieldExchange::Default` 지정된 된 작업을 구현 합니다. 해당 작업에 대 한 기본 구현을 살펴보겠습니다. 작성 해야 할 작업을 수행 하는 경우에 **RFX_** 함수를 위임할 수 있습니다는 `CFieldExchange::Default`합니다. 호출 하는 예제를 확인할 수 있습니다 `CFieldExchange::Default` dbrfx.cpp에서

호출 하는 것이 반드시 `IsFieldType` RFX 함수 및 반환 FALSE를 반환 하는 경우에 즉시 시작 합니다. 이 메커니즘에서 수행 하는 매개 변수 작업을 유지 *outputColumns*, 또는 그 반대로 (호출 처럼 `BindParam` 에 *outputColumn*). 또한 `IsFieldType` 자동으로 추적 합니다 수가 *outputColumns* (*m_nFields*) 및 매개 변수 (*m_nParams*).

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
