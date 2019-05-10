---
title: CDaoFieldInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: a5c4013a323c85ad19a3fade20f76852e053362a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399826"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo 구조체

`CDaoFieldInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 필드 개체에 대 한 정보가 들어 있습니다.

## <a name="syntax"></a>구문

```
struct CDaoFieldInfo
{
    CString m_strName;           // Primary
    short m_nType;               // Primary
    long m_lSize;                // Primary
    long m_lAttributes;          // Primary
    short m_nOrdinalPosition;    // Secondary
    BOOL m_bRequired;            // Secondary
    BOOL m_bAllowZeroLength;     // Secondary
    long m_lCollatingOrder;      // Secondary
    CString m_strForeignName;    // Secondary
    CString m_strSourceField;    // Secondary
    CString m_strSourceTable;    // Secondary
    CString m_strValidationRule; // All
    CString m_strValidationText; // All
    CString m_strDefaultValue;   // All
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
필드 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*m_nType*<br/>
필드의 데이터 형식을 나타내는 값입니다. 자세한 내용은 DAO 도움말의 "형식 속성" 항목을 참조 합니다. 이 속성의 값 중 하나일 수 있습니다.

- `dbBoolean` 예/아니요, TRUE/FALSE와 동일

- `dbByte` Byte

- `dbInteger` 짧은

- `dbLong` Long

- `dbCurrency` 통화; MFC 클래스 참조 [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle` 단일

- `dbDouble` Double

- `dbDate` 날짜/시간 MFC 클래스 참조 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` 텍스트 MFC 클래스 참조 [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` 긴 이진 (OLE 개체) MFC 클래스를 사용 하는 것이 좋습니다 [CByteArray](../../mfc/reference/cbytearray-class.md) 클래스 대신 `CLongBinary` 으로 `CByteArray` 다양 하 고 쉽게 사용할 수 있습니다.

- `dbMemo` 메모; MFC 클래스 참조 `CString`

- `dbGUID` 전역적으로 고유 식별자/Universally Unique Identifier 원격 프로시저 호출을 사용 합니다. 자세한 내용은 DAO 도움말의 "형식 속성" 항목을 참조 하세요.

> [!NOTE]
>  문자열 데이터 형식의 이진 데이터에 대해 사용 하지 마세요. 이렇게 하면 오버 헤드가 증가 하 고 예상치 못한 변환의 결과 유니코드/ANSI 변환 계층을 통해 전달할 데이터입니다.

*m_lSize*<br/>
텍스트 또는 텍스트 또는 숫자 값을 포함 하는 필드 개체의 고정된 크기를 포함 하는 DAO 필드 개체를 바이트 단위로 최대 크기를 나타내는 값입니다. 세부 정보를 DAO 도움말의 "크기 속성" 항목을 참조 하세요. 크기는 다음 값 중 하나일 수 있습니다.

|형식|크기(바이트)|설명|
|----------|--------------------|-----------------|
|`dbBoolean`|1바이트|예/아니요 (True/False와 동일)|
|`dbByte`|1|Byte|
|`dbInteger`|2|정수|
|`dbLong`|4|Long|
|`dbCurrency`|8|통화 ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Single|
|`dbDouble`|8|Double|
|`dbDate`|8|날짜/시간 ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|텍스트 ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|긴 이진 (OLE 개체 [CByteArray](../../mfc/reference/cbytearray-class.md); 대신 사용 하 여 `CLongBinary`)|
|`dbMemo`|0|메모 ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|전역적으로 고유 식별자/Universally Unique Identifier 원격 프로시저 호출을 사용 합니다.|

*m_lAttributes*<br/>
테이블 정의 레코드 집합, 쿼리 또는 인덱스 개체를 포함 하는 필드 개체의 특성을 지정 합니다. 반환 된 값이이 상수를 사용 하 여 만든 총 수는 C++ 비트 OR (**&#124;**) 연산자:

- `dbFixedField` 필드 크기 (숫자 필드에 대 한 기본값) 고정 됩니다.

- `dbVariableField` 필드 크기가 변수 (텍스트 필드에만 해당)입니다.

- `dbAutoIncrField` 새 레코드의 필드 값을 변경할 수 없는 고유한 long 정수로 자동으로 증가 됩니다. Microsoft Jet 데이터베이스 테이블에 대해서만 지원 합니다.

- `dbUpdatableField` 필드 값을 변경할 수 있습니다.

- `dbDescending` 필드를 내림차순으로 정렬 됩니다 (Z-A 0 100) 순서 (MFC 개체 자체 테이블 정의 개체에 포함 된 인덱스에서에서 인덱스 개체의 필드 컬렉션에 필드 개체에만 적용 됨). 이 상수를 생략 하면 필드를 오름차순으로 정렬 됩니다 (A-Z 또는 0-100) 순서 (기본값).

이 속성의 설정을 검사 하는 경우 사용할 수 있습니다는 C++ 비트-및 연산자 (**&**) 특정 특성을 테스트 합니다. 여러 특성을 설정할 때 비트 OR를 사용 하 여 적절 한 상수를 결합 하 여 결합 수 있습니다 (**&#124;**) 연산자. 세부 정보를 DAO 도움말의 "특성 속성" 항목을 참조 하세요.

*m_nOrdinalPosition*<br/>
다른 필드를 기준으로 표시 되는 DAO 필드 개체를 나타내는 필드를 원하는 숫자 순서를 지정 하는 값입니다. 이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다. 자세한 내용은 DAO 도움말의 "OrdinalPosition Property" 항목을 참조 합니다.

*m_bRequired*<br/>
DAO 필드를 Null이 아닌 값을 필요한 지 여부를 나타냅니다. 이 속성이 TRUE 이면 필드는 Null 값이 없도록 합니다. FALSE로 설정 되어 필요한 경우 필드 AllowZeroLength 및 ValidationRule 속성 설정에 지정 된 조건을 충족 하는 값 뿐만 아니라 Null 값 포함 될 수 있습니다. 세부 정보를 DAO 도움말의 "필수 속성" 항목을 참조 하세요. 사용 하 여 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.

*m_bAllowZeroLength*<br/>
나타냅니다 있는지 여부를 빈 문자열 ("")은 텍스트 또는 메모 데이터 형식과 DAO 필드 개체의 유효한 값입니다. 이 속성이 TRUE 인 경우 빈 문자열은 유효한 값입니다. 이 속성은 필드의 값을 설정 하려면 빈 문자열을 사용할 수 없다는 확인을 FALSE로 설정할 수 있습니다. 자세한 내용은 DAO 도움말의 "AllowZeroLength Property" 항목을 참조 합니다. 사용 하 여 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.

*m_lCollatingOrder*<br/>
문자열 비교 또는 정렬에 대 한 텍스트의 정렬 순서를 지정합니다. 자세한 내용은 "사용자 지정 Windows 레지스트리 설정에 대 한 데이터 액세스" DAO 도움말의 항목을 참조 합니다. 목록을 반환할 수 있는 값에 대 한 참조를 `m_lCollatingOrder` 의 멤버는 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 구조입니다. 사용 하 여 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.

*m_strForeignName*<br/>
관계, 기본 테이블의 필드에 해당 하는 외부 테이블에서 DAO 필드 개체의 이름을 지정 하는 값입니다. 자세한 내용은 DAO 도움말의 "ForeignName Property" 항목을 참조 합니다.

*m_strSourceField*<br/>
테이블 정의 레코드 집합 또는 쿼리 정의 개체를 포함 하는 DAO 필드 개체에 대 한 데이터 원본에는 필드의 이름을 나타냅니다. 이 속성 필드 개체에 연결 된 원본 필드 이름을 나타냅니다. 예를 들어, 이름이 기본 테이블의 필드 이름에 관련 없는 쿼리 필드에 있는 데이터의 원본 소스를 확인 하려면이 속성을 사용할 수 있습니다. 세부 정보, DAO 도움말의 "원본 필드, SourceTable 속성" 항목을 참조 합니다. 사용 하 여 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.

*m_strSourceTable*<br/>
테이블 정의 레코드 집합 또는 쿼리 정의 개체를 포함 하는 DAO 필드 개체에 대 한 데이터 원본에는 테이블의 이름을 나타냅니다. 이 속성 필드 개체에 연결 된 원본 테이블 이름을 나타냅니다. 예를 들어, 이름이 기본 테이블의 필드 이름에 관련 없는 쿼리 필드에 있는 데이터의 원본 소스를 확인 하려면이 속성을 사용할 수 있습니다. 세부 정보, DAO 도움말의 "원본 필드, SourceTable 속성" 항목을 참조 합니다. 사용 하 여 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.

*m_strValidationRule*<br/>
이 변경 되거나 테이블에 추가 되는 필드의 데이터 유효성을 검사 하는 값입니다. 자세한 내용은 DAO 도움말의 "ValidationRule Property" 항목을 참조 합니다. 사용 하 여 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.

테이블 정의 대 한 관련된 정보를 참조 하세요. 합니다 `m_strValidationRule` 의 멤버는 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 구조입니다.

*m_strValidationText*<br/>
DAO 필드 개체의 값은 ValidationRule 속성 설정으로 지정 된 유효성 검사 규칙을 충족 하지 않으면 응용 프로그램에서 표시 하는 메시지의 텍스트를 지정 하는 값입니다. 세부 정보를 DAO 도움말의 "유효성 검사 텍스트 속성" 항목을 참조 하세요. 사용 하 여 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.

*m_strDefaultValue*<br/>
DAO 필드 개체의 기본 값입니다. 새 레코드가 만들어지면 DefaultValue 속성 설정은 자동으로 입력 값으로 필드에 대 한 합니다. 세부 정보를 DAO 도움말의 "DefaultValue 속성" 항목을 참조 하세요. 사용 하 여 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.

## <a name="remarks"></a>설명

기본, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 `GetFieldInfo` 클래스의 멤버 함수 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), 및 [ CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)합니다.

필드 개체는 MFC 클래스에 의해 표시 되지 않습니다. 대신 MFC 개체 클래스의 기본 DAO 개체는 필드 개체의 컬렉션을 포함 합니다. [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)하십시오 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), 및 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)합니다. 이러한 클래스의 필드 정보를 일부 개별 항목에 액세스 하는 멤버 함수를 제공 하거나 사용 하 여 한 번에 모두 액세스할 수 있습니다는 `CDaoFieldInfo` 를 호출 하 여 개체를 `GetFieldInfo` 포함 하는 개체의 멤버 함수입니다.

개체 속성을 검사 하기 위한 용도 외에 사용할 수 있습니다 `CDaoFieldInfo` 테이블 정의에서 새 필드 만들기에 대 한 입력된 매개 변수를 생성 합니다. 간단한 옵션은이 작업을 수행할 수 있지만 보다 세부적으로 제어를 원하는 경우에 버전을 사용할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) 를 사용 하는 한 `CDaoFieldInfo` 매개 변수입니다.

검색 되는 정보는 `GetFieldInfo` (필드를 포함 하는 클래스)의 멤버 함수에 저장 되는 `CDaoFieldInfo` 구조입니다. 호출 된 `GetFieldInfo` 포함 하는 해당 필드 컬렉션 필드 개체 저장 된 개체의 멤버 함수입니다. `CDaoFieldInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoFieldInfo` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
