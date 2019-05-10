---
title: CDaoTableDefInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDefInfo
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
ms.openlocfilehash: 5785ed19c6929e19c7d376efa012dd1c059611c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152100"
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo 구조체

`CDaoTableDefInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 테이블 정의 개체에 대 한 정보가 들어 있습니다.

## <a name="syntax"></a>구문

```
struct CDaoTableDefInfo
{
    CString m_strName;               // Primary
    BOOL m_bUpdatable;               // Primary
    long m_lAttributes;              // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    CString m_strSrcTableName;       // Secondary
    CString m_strConnect;            // Secondary
    CString m_strValidationRule;     // All
    CString m_strValidationText;     // All
    long m_lRecordCount;             // All
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
테이블 정의 개체의 고유 이름을 지정 합니다. 이 속성의 값을 직접 검색 하려면 테이블 정의 개체의 호출 [GetName](../../mfc/reference/cdaotabledef-class.md#getname) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*m_bUpdatable*<br/>
테이블에 변경 내용을 적용할 수 있는지 여부를 나타냅니다. 테이블은 업데이트할 수 있는지 여부를 확인 하는 빠른 방법은 여는 한 `CDaoTableDef` 테이블에 대 한 개체와 개체의 호출 [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) 멤버 함수입니다. `CanUpdate` 항상 0이 아닌 (TRUE 반환)는 새로 만든된 테이블 정의 개체와 연결 된 테이블 정의 개체에 대 한 0 (FALSE)에 대 한 합니다. 새 테이블 정의 개체는 현재 사용자에 대 한 쓰기 권한이 있는 데이터베이스에만 추가할 수 있습니다. 테이블에만 업데이트할 수 없는 필드를 포함 하는 경우 `CanUpdate` 0을 반환 합니다. 하나 이상의 필드를 업데이트할 수 있는 경우 `CanUpdate` 0이 아닌 값을 반환 합니다. 업데이트할 수 있는 필드에만 편집할 수 있습니다. 자세한 내용은 DAO 도움말의 "업데이트할 수 있는 속성" 항목을 참조 하세요.

*m_lAttributes*<br/>
테이블 정의 개체를 나타내는 테이블의 특성을 지정 합니다. 테이블 정의의 현재 속성을 검색 하려면 해당 [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) 멤버 함수입니다. 반환 된 값이 긴 상수의 조합일 수 있습니다 (비트 OR를 사용 하 여 (**&#124;**) 연산자).

- `dbAttachExclusive` Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대 한 테이블이 배타적으로 사용에 대 한 열린 연결 된 테이블을 나타냅니다.

- `dbAttachSavePWD` Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대 한 사용자 ID와 연결 된 테이블에 대 한 암호는 연결 정보를 사용 하 여 저장을 나타냅니다.

- `dbSystemObject` 테이블은 Microsoft Jet 데이터베이스 엔진에 의해 제공 된 시스템 테이블을 나타냅니다. 읽기 전용입니다.

- `dbHiddenObject` 테이블이 (임시 사용 하 여에) 대 한 Microsoft Jet 데이터베이스 엔진에 의해 제공 된 숨겨진된 테이블을 나타냅니다. 읽기 전용입니다.

- `dbAttachedTable` 테이블이 Paradox 데이터베이스와 같은 비 ODBC 데이터베이스에서 연결 된 테이블을 나타냅니다.

- `dbAttachedODBC` 테이블은 Microsoft SQL Server와 같은 ODBC 데이터베이스에서 연결 된 테이블을 나타냅니다.

*m_dateCreated*<br/>
날짜 및 테이블을 만든 시간입니다. 테이블을 만든 날짜를 직접 검색 하려면 호출을 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다. 자세한 내용은 아래 메모를 참조 하세요. 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.

*m_dateLastUpdated*<br/>
날짜 및 시간 테이블의 디자인에 대 한 가장 최근의 변경입니다. 테이블을 마지막으로 수정한 날짜를 직접 검색 하려면 호출을 [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다. 자세한 내용은 아래 메모를 참조 하세요. 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.

*m_strSrcTableName*<br/>
있는 경우 연결 된 테이블의 이름을 지정 합니다. 호출 된 소스 테이블 이름을 직접 검색 하려면 합니다 [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다.

*m_strConnect*<br/>
열려 있는 데이터베이스의 원본에 대 한 정보를 제공합니다. 호출 하 여이 속성을 확인할 수 있습니다 합니다 [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) 멤버 함수에 `CDaoTableDef` 개체입니다. 에 대 한 자세한 정보에 대 한 연결 문자열, 참조 `GetConnect`합니다.

*m_strValidationRule*<br/>
변경 되거나 테이블에 추가 될 때 처럼 테이블 정의 필드의 데이터 유효성을 검사 하는 값입니다. 유효성 검사는 Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대해서만 지원 됩니다. 유효성 검사 규칙을 직접 검색 하려면 호출을 [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다. 관련된 내용은 DAO 도움말의 "ValidationRule Property" 항목을 참조 합니다.

*m_strValidationText*<br/>
ValidationRule 속성에 지정 된 유효성 검사 규칙을 만족 하지 않을 경우 응용 프로그램을 표시 하는 메시지의 텍스트를 지정 하는 값입니다. 관련된 정보 DAO 도움말의 "유효성 검사 텍스트 속성" 항목을 참조 하세요.

*m_lRecordCount*<br/>
테이블 정의 개체에 액세스 하는 레코드의 수입니다. 이 속성 설정은 읽기 전용입니다. Record count를 직접 검색 하려면 호출을 [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) 멤버 함수는 `CDaoTableDef` 개체입니다. 에 대 한 설명서 `GetRecordCount` record count 추가 설명 합니다. 이 개수를 검색 수 있는 시간이 많이 걸리는 작업 테이블 레코드 수를 포함 하는 경우 note 합니다.

## <a name="remarks"></a>설명

테이블 정의 클래스의 개체인 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)합니다. 기본, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) 클래스 멤버 함수 `CDaoDatabase`합니다.

검색 되는 정보는 [CDaoDatabase::GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) 멤버 함수에 저장 되는 `CDaoTableDefInfo` 구조입니다. 호출을 `GetTableDefInfo` 멤버 함수는 `CDaoDatabase` 인 TableDefs 컬렉션의 테이블 정의 개체는 저장 된 개체입니다. `CDaoTableDefInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoTableDefInfo` 개체입니다.

날짜 및 시간 설정에는 기본 테이블을 만들거나 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다. 다중 사용자 환경에서 사용자가 이러한는 DateCreated 불일치를 방지 하기 위해 파일 서버에서 직접 설정 및 LastUpdated 속성 설정을 가져와야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)
