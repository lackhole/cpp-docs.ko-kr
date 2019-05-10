---
title: 'TN053: DAO 데이터베이스 클래스에 대 한 사용자 지정 DFX 루틴'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.dfx
helpviewer_keywords:
- MFC, DAO and
- database classes [MFC], DAO
- DAO [MFC], MFC
- DFX (DAO record field exchange) [MFC], custom routines
- TN053
- DAO [MFC], classes
- DFX (DAO record field exchange) [MFC]
- custom DFX routines [MFC]
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
ms.openlocfilehash: b610604c1b7a68128dc9eb6fb5515225ed22b16e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399683"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: DAO 데이터베이스 클래스에 대 한 사용자 지정 DFX 루틴

> [!NOTE]
>  시각적 개체 C++ 환경 및 마법사 지원 하지 않습니다 DAO (하지만 DAO 클래스에 포함 되어 있으며 계속 사용할 수 있습니다). 사용 하는 것이 좋습니다 [OLE DB Templates](../data/oledb/ole-db-templates.md) 하거나 [ODBC 및 MFC](../data/odbc/odbc-and-mfc.md) 새 프로젝트에 대 한 합니다. DAO 기존 응용 프로그램 유지 관리에 사용 해야 합니다.

이 기술 노트는 DAO 레코드 필드 교환 (DFX) 메커니즘을 설명합니다. DFX 루틴의 상황을 이해 하는 데는 `DFX_Text` 함수 예를 자세히 설명 합니다. 이 기술 노트에 정보 추가 원본으로 검사할 수 있는 코드를 다른 개별 DFX 함수입니다. 아마도 필요는 없습니다 사용자 지정 DFX 루틴 만큼 사용자 지정 RFX 루틴 (ODBC 데이터베이스 클래스 사용) 해야 할 수 있습니다.

이 기술 노트에는 다음이 포함 됩니다.

- DFX 개요

- [예제](#_mfcnotes_tn053_examples) DAO 레코드 필드 교환 및 동적 바인딩 사용

- [DFX의 작동 원리](#_mfcnotes_tn053_how_dfx_works)

- [사용자 지정 DFX 루틴의 용도](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [DFX_Text의 세부 정보](#_mfcnotes_tn053_details_of_dfx_text)

**DFX 개요**

DAO 레코드 필드 교환 메커니즘 (DFX) 검색 하 고 데이터를 사용 하는 경우 업데이트 프로시저를 간소화 되는 `CDaoRecordset` 클래스입니다. 데이터 멤버를 사용 하 여 간소화 됩니다는 `CDaoRecordset` 클래스입니다. 파생 시켜 `CDaoRecordset`, 테이블 또는 쿼리의 각 필드를 나타내는 파생 된 클래스에 데이터 멤버를 추가할 수 있습니다. 이 "정적 바인딩" 메커니즘은 간단 하지만 모든 응용 프로그램에 대해 선택한 데이터 인출/update 메서드를 되지 않을 수 있습니다. DFX는 현재 레코드가 변경 될 때마다 모든 바인딩된 필드를 검색 합니다. 통화 변경 되 면 모든 필드를 페치 하지 않아도 되는 성능에 민감한 응용 프로그램을 개발 하는 경우 "동적 바인딩"을 통해 `CDaoRecordset::GetFieldValue` 고 `CDaoRecordset::SetFieldValue` 데이터 액세스 메서드를 원하는 수 있습니다.

> [!NOTE]
>  DFX 및 동적 바인딩 되므로 상호 배타적인 정적 및 동적 바인딩에 혼합 사용을 사용할 수 있습니다.

## <a name="_mfcnotes_tn053_examples"></a> DAO 레코드 필드 교환만 예제 1-사용

(가정 `CDaoRecordset` -클래스를 파생 `CMySet` 아직 열려)

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**예제 2 — 동적 바인딩만 사용**

(사용 하 여 가정 `CDaoRecordset` 클래스 `rs`, 이미 열려 및)

```
// Add a new record to the customers table
COleVariant  varFieldValue1 (_T("MSFT"),
    VT_BSTRT);

//Note: VT_BSTRT flags string type as ANSI,
    instead of UNICODE default
COleVariant  varFieldValue2  (_T("Microsoft"),
    VT_BSTRT);

rs.AddNew();

rs.SetFieldValue(_T("Customer_ID"),
    varFieldValue1);

rs.SetFieldValue(_T("Customer_Name"),
    varFieldValue2);

rs.Update();
```

**예제 3 — 사용의 DAO 레코드 필드 교환 및 동적 바인딩**

(사용 하 여 직원 데이터를 검색 가정 `CDaoRecordset`-클래스를 파생 `emp`)

```
// Get the employee's data so that it can be displayed
emp.MoveNext();

// If user wants to see employee's photograph,
// fetch it
COleVariant varPhoto;
if (bSeePicture)
    emp.GetFieldValue(_T("photo"),
    varPhoto);

// Display the data
PopUpEmployeeData(emp.m_strFirstName,
    emp.m_strLastName,
    varPhoto);
```

## <a name="_mfcnotes_tn053_how_dfx_works"></a> DFX의 작동 원리

DFX 메커니즘은 MFC ODBC 클래스에서 사용 하는 레코드 필드 RFX (교환) 메커니즘을 비슷한 방식으로 작동 합니다. RFX와 DFX의 원칙 동일 하지만 내부 차이가 많습니다. DFX 함수 디자인 거의 모든 코드는 개별 DFX 루틴에 의해 공유 되는 경우 만 가장 높은 수준 DFX에서 몇 가지 작업을 수행 합니다.

- DFX SQL 구문 **선택** 절과 SQL **매개 변수** 필요한 경우 절.

- DFX 생성 DAO의에서 사용 하는 바인딩 구조의 `GetRows` 함수 (나중에 자세히 설명).

- DFX (이중 버퍼링 사용) 하는 경우 커밋되지 않은 데이터 필드를 검색 하는 데 사용 되는 데이터 버퍼를 관리 합니다.

- DFX 관리 합니다 **NULL** 하 고 **귀찮은** 상태 배열 및 업데이트에 필요한 경우 값을 설정 합니다.

메커니즘은 DFX의 핵심은 `CDaoRecordset` 파생 클래스의 `DoFieldExchange` 함수입니다. 이 함수는 작업을 적절 한 형식의 개별 DFX 함수를 호출을 디스패치합니다. 호출 하기 전에 `DoFieldExchange` 내부 MFC 함수 작업 유형을 설정 합니다. 다음 목록에는 다양 한 작업 유형 및 간략 한 설명을 보여 줍니다.

|작업|설명|
|---------------|-----------------|
|`AddToParameterList`|빌드 매개 변수 절|
|`AddToSelectList`|빌드 SELECT 절|
|`BindField`|구조를 바인딩 설정|
|`BindParam`|매개 변수 값 설정|
|`Fixup`|NULL 상태를 설정합니다.|
|`AllocCache`|변경 확인에 대 한 캐시를 할당합니다.|
|`StoreField`|캐시에 현재 레코드를 저장합니다.|
|`LoadField`|멤버 값으로 복원 캐시|
|`FreeCache`|캐시를 해제합니다.|
|`SetFieldNull`|상태 및 NULL 값 집합 필드|
|`MarkForAddNew`|필드 변경 되지 않은 경우 NULL 의사를 표시합니다.|
|`MarkForEdit`|표시 필드 커밋되지 않은 경우 캐시에 일치 하지 않습니다.|
|`SetDirtyField`|집합에는 커밋된 것으로 표시 하는 값 필드|

다음 섹션에서는 각 작업에 대해 자세히 설명 됩니다 `DFX_Text`합니다.

DAO 레코드 필드 교환 프로세스에 대해 이해 하는 가장 중요 한 기능은 사용 한다는 것입니다는 `GetRows` 함수는 `CDaoRecordset` 개체입니다. DAO `GetRows` 함수는 여러 가지 방법으로 작동할 수 있습니다. 이 기술 노트에서는 아주 잠시 동안만 설명 `GetRows` 처럼이 기술 노트의 범위를 벗어납니다.

DAO `GetRows` 에서 여러 가지 방법으로 작업할 수 있습니다.

- 여러 레코드 및 여러 데이터 필드를 한 번에 인출할 수 있습니다 것입니다. 따라서 복잡 하지만 큰 데이터 구조 및 각 필드에 적절 한 오프셋을 사용 하 여 처리를 사용 하 여 더 빠른 데이터 액세스 및 구조 데이터의 각 레코드에 대 한 합니다. MFC는 메커니즘을 가져오는이 여러 레코드의 활용 하지 않습니다.

- 또 다른 방법은 `GetRows` 수 작업 데이터의 하나의 레코드에 대 한 각 필드의 검색된 된 데이터에 대 한 바인딩 주소를 지정 하는 프로그래머를 허용 하는 것입니다.

- DAO는 또한 "콜백할" 가변 길이 열에 대 한 호출자가 호출자가 메모리를 할당할 수 있도록 합니다. 이 두 번째 기능은 클래스의 멤버에 직접 저장소 데이터의 허용 수 있을 뿐만 아니라 데이터의 복사본 수를 최소화 하면 이점이 (의 `CDaoRecordset` 파생 클래스). 이 두 번째 메커니즘은 MFC에서의 데이터 멤버에 바인딩할 사용 방법은 `CDaoRecordset` 클래스를 파생 합니다.

##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> 사용자 지정 DFX 루틴의 용도

DFX 함수에서 구현 되는 가장 중요 한 작업에 성공적으로 호출 하려면 필요한 데이터 구조를 설정 하는 기능이 있어야 합니다.이 토론에서 명백한 것 `GetRows`입니다. DFX 함수도 지원 해야 하는 작업도 있지만 중요 또는 올바르게 준비로 복잡 한으로 여러 가지를 `GetRows` 호출 합니다.

DFX 사용 온라인 설명서에서 설명 되어 있습니다. 기본적으로, 두 가지 요구 사항이 있습니다. 첫째, 멤버를에 추가 해야 합니다는 `CDaoRecordset` 각 바인딩된 필드 및 매개 변수 클래스를 파생 합니다. 이 `CDaoRecordset::DoFieldExchange` 재정의 해야 합니다. 데이터 멤버의 형식에 중요 합니다. 최소한 해당 형식으로 변환할 수 또는 데이터베이스의 필드에서 데이터와 일치 해야 합니다. 예를 들어 정수 (long)를 같은 데이터베이스에 있는 숫자 필드 항상 텍스트로 변환 및 바인딩할 수는 `CString` 멤버 하지만 데이터베이스의 텍스트 필드 하지 않을 수 있습니다 정수 (long) 등의 숫자 표현으로 변환 하 고 긴 integ 바인딩할 er 멤버입니다. DAO 및 Microsoft Jet 데이터베이스 엔진의 변환 대신 MFC에 대 한 책임이 있습니다.

##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> DFX_Text의 세부 정보

이전에 설명한 대로 DFX의 작동 원리를 설명 하는 가장 좋은 방법은 예제를 통해 작동 방법은입니다. 내부 구조를 통과 하는이 목적을 위해 `DFX_Text` DFX 적어도 기본적으로 이해를 제공 하는 데 상당히 잘 작동 해야 합니다.

- `AddToParameterList`

   이 작업은 SQL을 빌드합니다 **매개 변수** 절 ("`Parameters <param name>, <param type> ... ;`") Jet가 필요 합니다. 각 매개 변수는 명명 된 이며 (지정 된 대로 RFX 호출에서) 입력 합니다. 함수를 참조 `CDaoFieldExchange::AppendParamType` 개별 형식의 이름을 참조 하는 함수입니다. 경우 `DFX_Text`에 사용 되는 형식은 **텍스트**합니다.

- `AddToSelectList`

   SQL을 빌드합니다 **선택** 절. 보다시피 상당히 DFX 호출에서 지정 된 열 이름을 단순히 그대로 추가 ("`SELECT <column name>, ...`").

- `BindField`

   작업의 가장 복잡 합니다. 앞서 언급 했 듯이이 DAO 바인딩 구조의 사용한 `GetRows` 설정 됩니다. 코드에서 알 수 있듯이 `DFX_Text` 유형의 구조에 대 한 정보를 사용 하는 DAO 형식 포함 (**DAO_CHAR** 하거나 **DAO_WCHAR** 의 경우 `DFX_Text`). 또한 사용 되는 바인딩의 유형도 설정 됩니다. 이전 섹션에서 `GetRows` 설명 아주 잠시 동안만 사용 했지만 MFC에서 사용 되는 바인딩의 형식이 항상 직접 주소 바인딩을 설명 하는 데 충분 (**DAOBINDING_DIRECT**). 또한 가변 길이 열 바인딩에 대 한 (같은 `DFX_Text`) MFC에서 메모리 할당을 제어 하 고 올바른 길이의 주소를 지정할 수 있도록 콜백 바인딩을 사용 합니다. 즉 해당 MFC 항상 알 수 DAO 있으므로 다음 바인딩 멤버 변수에 직접 데이터를 넣을 "where"입니다. 바인딩 구조의 나머지는 메모리 할당 콜백 함수 및 열 바인딩 (열 이름으로 바인딩) 형식 주소 등 포함 됩니다.

- `BindParam`

   이 작업은 호출 하는 간단한 작업 `SetParamValue` 매개 변수 멤버에 지정 된 매개 변수 값을 사용 하 여 합니다.

- `Fixup`

   채웁니다 합니다 **NULL** 각 필드에 대 한 상태입니다.

- `SetFieldNull`

   이 작업으로 각 필드의 상태를 표시만 **NULL** 멤버 변수의 값을 설정 하 고 **PSEUDO_NULL**합니다.

- `SetDirtyField`

   호출 `SetFieldValue` 더티로 표시 되어 각 필드에 대 한 합니다.

나머지 모든 작업 데이터 캐시를 사용 하 여만 처리 합니다. 데이터 캐시는 특정 작업을 간단 하 게 하는 데 사용 되는 현재 레코드에 있는 데이터의 버퍼를 추가 합니다. 예를 들어, "더티" 필드를 자동으로 검색할 수 있습니다. 온라인 설명서에 설명 된 대로 해당 해제할 수 있습니다 완전히 또는 필드 수준입니다. 버퍼의 구현에서 지도 사용합니다. 이 맵에 "바인딩된" 필드의 주소를 사용 하 여 데이터의 동적으로 할당 된 복사본을 일치 시키는 데 사용 됩니다 (또는 `CDaoRecordset` 데이터 멤버를 파생).

- `AllocCache`

   동적으로 캐시 된 필드 값을 할당 하 고 지도에 추가.

- `FreeCache`

   캐시 된 필드 값을 삭제 된 데이터베이스 맵에서 제거 합니다.

- `StoreField`

   데이터 캐시에 현재 필드 값을 복사합니다.

- `LoadField`

   필드 멤버에 캐시 된 값을 복사합니다.

- `MarkForAddNew`

   확인 하는 경우 현재 필드 값이 아닌**NULL** 하 고 필요한 경우 커밋되지 않은 표시 합니다.

- `MarkForEdit`

   데이터 캐시를 사용 하 여 현재 필드 값과 비교 하 고 필요한 경우 커밋되지 않은 데이터를 표시 합니다.

> [!TIP]
> 표준 데이터 형식에 대 한 기존 DFX 루틴에서 사용자 지정 DFX 루틴을 모델링 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
