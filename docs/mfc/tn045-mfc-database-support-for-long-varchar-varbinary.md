---
title: 'TN045: Long Varchar-varbinary에 대 한 MFC 데이터베이스 지원'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.data
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: d356f094759775f709838de149769b1671fdf9ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305374"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: Long Varchar/Varbinary에 대 한 c/데이터베이스 지원

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 ODBC를 보내고 검색 하는 방법에 설명 합니다 **SQL_LONGVARCHAR** 하 고 **SQL_LONGVARBINARY** MFC를 사용 하 여 데이터 형식을 데이터베이스 클래스입니다.

## <a name="overview-of-long-varcharvarbinary-support"></a>Long Varchar/Varbinary 지원 개요

ODBC **SQL_LONG_VARCHAR** 하 고 **SQL_LONGBINARY** (긴 데이터 열으로 여기까지 라고도 함) 데이터 형식에서 엄청난 양의 데이터를 포함할 수 있습니다. 3 가지 방법으로이 데이터를 처리할 수 있습니다.

- 에 바인딩하는 `CString` / `CByteArray`합니다.

- 에 바인딩하는 `CLongBinary`합니다.

- 전혀 바인딩하지 및 검색 하지 않으며 보낼 긴 데이터 값을 수동으로 데이터베이스 클래스와 무관 합니다.

각각의 세 가지 방법의 장점 및 단점에 있습니다.

쿼리 매개 변수에 대 한 long 데이터 열을 사용할 수 없습니다. OutputColumns에만 지원 됩니다.

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>CString/CByteArray에 Long 데이터가 열 바인딩

장점

이 방법은 이해 하기 간단 하 고 친숙 한 클래스를 사용 합니다. 프레임 워크를 제공 `CFormView` 에 대 한 지원 `CString` 사용 하 여 `DDX_Text`입니다. 일반 문자열 또는 컬렉션 기능을 많이 해야 합니다 `CString` 및 `CByteArray` 클래스 및 사용자 데이터 값을 보유할 수 로컬로 할당 된 메모리 양을 제어할 수 있습니다. 프레임 워크 중 필드 데이터의 이전 복사본을 유지 `Edit` 또는 `AddNew` 함수 호출 및 프레임 워크 수를 변경 데이터를 자동으로 검색 합니다.

> [!NOTE]
>  이후 `CString` 문자 데이터에 대해 작업을 위해 만들어진 및 `CByteArray` 이진 데이터를 사용할 것이 좋습니다 문자 데이터를 추가 하는 (**SQL_LONGVARCHAR**)에 `CString`, 및 이진 데이터 ( **SQL_LONGVARBINARY**)에 `CByteArray`입니다.

에 대 한 함수는 RFX `CString` 및 `CByteArray` 데이터 열에 대 한 검색된 값을 보유할 할당 된 메모리의 기본 크기를 재정의할 수 있는 추가 인수를 사용할 수 있습니다. 다음 함수 선언에서 nMaxLength 인수 참고:

```
void AFXAPI RFX_Text(CFieldExchange* pFX,
    const char *szName,
    CString& value,
    int nMaxLength = 255,
    int nColumnType =
    SQL_VARCHAR);

void AFXAPI RFX_Binary(CFieldExchange* pFX,
    const char *szName,
    CByteArray& value,
    int nMaxLength = 255);
```

긴 데이터 열을 검색 하는 경우는 `CString` 또는 `CByteArray`, 최대 데이터 양이, 기본적으로 255 바이트를 반환 합니다. 이 항목은 무시 됩니다. 프레임 워크는 예외를 throw 하는 예에서 **AFX_SQL_ERROR_DATA_TRUNCATED**합니다. 다행 스럽게도 명시적으로 늘리려면 nMaxLength 큰 값으로 최대 **maxint와 같습니다**합니다.

> [!NOTE]
>  NMaxLength의 값의 로컬 버퍼를 설정 하려면 MFC에서 사용 되는 `SQLBindColumn` 함수입니다. 이 데이터의 저장소에 대 한 로컬 버퍼 및 ODBC 드라이버에서 반환 되는 데이터 양을 실제로 영향을 주지 않습니다. `RFX_Text` 및 `RFX_Binary` 만 사용 하 여 하나를 수행 `SQLFetch` 백 엔드 데이터베이스에서 데이터를 검색할 수 있습니다. 각 ODBC 드라이버는 단일 인출에서 반환할 수 있습니다 하는 데이터의 양에 따라 다양 한 제한이 있습니다. 이 제한은 있으며이 경우는 예외에 nMaxLength, 설정 된 값 보다 훨씬 더 작은 수 있습니다 **AFX_SQL_ERROR_DATA_TRUNCATED** throw 됩니다. 이러한 상황을 사용 하도록 전환 `RFX_LongBinary` of `RFX_Text` 또는 `RFX_Binary` 모든 데이터를 검색할 수 있도록 합니다.

ClassWizard 바인딩합니다를 **SQL_LONGVARCHAR** 에 `CString`, 또는 **SQL_LONGVARBINARY** 에 `CByteArray` 를. Long 데이터가 열에는 검색 255 바이트 이상의 할당 하려는 경우 다음 nMaxLength 명시적 값을 제공할 수 있습니다.

Long 데이터가 열에 바인딩된 경우는 `CString` 또는 `CByteArray`를 SQL_에 바인딩될 때 하는 것과 마찬가지로 작동 필드 업데이트**VARCHAR** 또는 SQL_**VARBINARY**합니다. 하는 동안 `Edit`, 데이터 값이 이상 떨어진 경우 비교 캐시 `Update` 데이터 변경에는 귀찮은 설정 및 열에 대 한 값을 적절 하 게 Null 값을 검색 하기 위해 호출 됩니다.

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>CLongBinary에 Long 데이터가 열 바인딩

더 긴 데이터 열에 있을 경우 **maxint와 같습니다** 데이터의 바이트, 아마도 고려해 야 검색에 `CLongBinary`합니다.

장점

이 최대 사용 가능한 메모리 전체 긴 데이터 열을 검색합니다.

단점

데이터는 메모리에 보관 됩니다. 또한이 방법은 매우 많은 양의 데이터에 대 한 많은 비용이 들거나 실행 합니다. 호출 해야 합니다 `SetFieldDirty` 바인딩된 데이터 필드를 확인 하는 멤버에 포함 되어는 `Update` 작업 합니다.

긴 데이터 열을 검색 하는 경우는 `CLongBinary`, 데이터베이스 클래스는 long 데이터 열의 전체 크기를 확인 한 후 할당을 `HGLOBAL` 전체 데이터 값을 저장 하는 데 충분히 큰 메모리 세그먼트입니다. 다음 데이터베이스 클래스에 할당 된 전체 데이터 값을 검색 `HGLOBAL`합니다.

데이터 원본 열 긴 데이터의 예상된 크기를 반환할 수 없습니다, 프레임 워크는 예외를 throw 합니다 **AFX_SQL_ERROR_SQL_NO_TOTAL**합니다. 경우 할당 된 `HGLOBAL` 실패 하면 표준 메모리 예외를 throw 됩니다.

Classwizard 함께 바인딩합니다는 **SQL_LONGVARCHAR** 또는 **SQL_LONGVARBINARY** 에 `CLongBinary` 있습니다. 선택 `CLongBinary` 멤버 변수 추가 대화 상자에서 변수 형식으로 합니다. 클래스 마법사는 다음 추가 `RFX_LongBinary` 호출에 `DoFieldExchange` 호출 하 고 바인딩된 필드의 총 수를 증가 시킵니다.

긴 데이터 열 값을 업데이트 하려면 먼저 했는지 할당 된 `HGLOBAL` 를 호출 하 여 새 데이터를 저장할 수 있도록 충분히 큰 **:: GlobalSize** 에 *m_hData* 의 멤버는 `CLongBinary`합니다. 너무 작은 경우 릴리스는 `HGLOBAL` 및 적절 한 크기를 할당 합니다. 설정한 *m_dwDataLength* 새 크기를 반영 하도록 합니다.

그렇지 않은 경우, *m_dwDataLength* 크기 보다 크면 변경 하려는 데이터의 수 중 하나를 해제 하 고 다시 할당 합니다 `HGLOBAL`, 하거나 할당 된 상태로 둡니다. 실제로 사용 된 바이트 수를 지정 해야 *m_dwDataLength*합니다.

## <a name="how-updating-a-clongbinary-works"></a>방법을 업데이트는 CLongBinary 작동

것을 이해 하는 데 필요한 방법을 업데이트는 `CLongBinary` 작동 하지만 데이터 원본에 긴 데이터 값을 보내는 방법에 대 한 예로 유용할 수 있습니다 아래에 설명 된 세 번째이 메서드를 선택 하는 경우.

> [!NOTE]
>  에 대 한 순서 대로 `CLongBinary` 업데이트에 포함 될 필드 명시적으로 호출 해야 `SetFieldDirty` 필드에 대 한 합니다. Null 설정 비롯 한 필드를 변경 하는 경우 호출 해야 `SetFieldDirty`합니다. 도 호출 해야 합니다 `SetFieldNull`, 되 고 두 번째 매개 변수 **FALSE**, 필드가 값을 가진 것으로 표시 합니다.

업데이트 하는 경우는 `CLongBinary` 필드에 데이터베이스 클래스를 사용 하 여 ODBC의 **DATA_AT_EXEC** 메커니즘 (ODBC 설명서를 참조 `SQLSetPos`의 rgbValue 인수). 프레임 워크를 가리키는 대신 insert 또는 update 문을 준비 하는 경우는 `HGLOBAL` 데이터를 포함 하는 *주소* 의 합니다 `CLongBinary` 으로 설정 됩니다는 *값* 열 대신, 길이 표시기로 설정 하 고 **SQL_DATA_AT_EXEC**합니다. Update 문의 데이터 원본에 보내면 나중 `SQLExecDirect` 돌아갑니다 **SQL_NEED_DATA**합니다. 이 열에 대 한 매개 변수 값의 주소가 실제로 인지 프레임 워크가 경고는 `CLongBinary`합니다. 프레임 워크 호출 `SQLGetData` 번 작은 버퍼를 사용 하 여 데이터의 실제 길이 반환 하려면 드라이버가 필요 합니다. Binary large object (BLOB)의 실제 길이 반환 하는 드라이버, MFC 다시 BLOB을 인출 하는 데 필요한 만큼 공간을 할당 합니다. 데이터 원본 반환 **SQL_NO_TOTAL**, BLOB의 크기를 확인할 수 없음을 나타내는, MFC 만들어집니다 작은 블록입니다. 기본 초기 크기는 64k 및 후속 블록 크기를 두 배로 됩니다. 예를 들어, 두 번째 128k 됩니다, 그리고 세 번째는 256 K입니다. 초기 크기는 구성할 수 있습니다.

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>바인딩되지 않습니다. SQLGetData 사용 하 여 ODBC에서 직접 데이터를 검색 하 고 전송

이 메서드를 사용 하 여 완전히 데이터베이스 클래스를 사용 하지 않고 긴 데이터 열을 사용 하 여 처리 합니다.

장점

필요한 경우 디스크 또는 동적으로 데이터 양을 결정 검색할 데이터를 캐시할 수 있습니다.

단점

프레임 워크의 얻지 `Edit` 또는 `AddNew` 지원 하 고 작성 해야 코드를 직접 기본 기능을 수행 하도록 (`Delete` 열 수준 작업을 아니므로 하지만 작동).

이 경우 긴 데이터 열, 레코드 집합의 select 목록에 있어야 하지만 프레임 워크에서에 바인딩되어 있지 해야 합니다. 작업을 수행 하는 한 가지 방법은이 통해 사용자 고유의 SQL 문을 제공 `GetDefaultSQL` 또는 lpszSQL 인수로 `CRecordset`의 `Open` 함수 및 RFX_ 함수 호출을 사용 하 여 추가 열을 바인딩하지 않습니다. ODBC 바인딩된 필드의 오른쪽에 바인딩되지 않은 필드가 나타나도록 해야, 하므로 select 목록의 끝에 바인딩되지 않은 열 또는 열을 추가 합니다.

> [!NOTE]
>  사용 하 여 변경 내용을 처리 되지 것입니다 프레임 워크에서 긴 데이터 열에 바인딩되지 않은, 때문에 `CRecordset::Update` 호출 합니다. 만들고 필요한 SQL 송신 해야 **삽입** 하 고 **업데이트** 문을 직접.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
