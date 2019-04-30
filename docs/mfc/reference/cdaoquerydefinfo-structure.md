---
title: CDaoQueryDefInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: d88d919bb87f614d140d710aee9df3fdf4fd10bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399735"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo 구조체

`CDaoQueryDefInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 하는 쿼리 정의 개체에 대 한 정보가 들어 있습니다.

## <a name="syntax"></a>구문

```
struct CDaoQueryDefInfo
{
    CString m_strName;               // Primary
    short m_nType;   // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    BOOL m_bUpdatable;               // Secondary
    BOOL m_bReturnsRecords;          // Secondary
    CString m_strSQL;                // All
    CString m_strConnect;            // All
    short m_nODBCTimeout;            // All
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
쿼리 정의 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다. 호출 [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) 이 속성을 직접 검색할 수 있습니다.

*m_nType*<br/>
쿼리 정의 개체의 작업 유형을 나타내는 값입니다. 값은 다음 중 하나일 수 있습니다.

- `dbQSelect` 쿼리 선택-레코드를 선택 합니다.

- `dbQAction` 작업-쿼리 이동 하거나 데이터를 변경 하지만 레코드를 반환 하지 않습니다.

- `dbQCrosstab` 크로스탭-쿼리는 스프레드시트 형식으로 데이터를 반환합니다.

- `dbQDelete` 삭제-쿼리는 지정 된 행 집합을 삭제합니다.

- `dbQUpdate` 업데이트-쿼리가 레코드 집합을 변경 합니다.

- `dbQAppend` 쿼리에 추가-테이블 또는 쿼리의 끝에 새 레코드를 추가합니다.

- `dbQMakeTable` -테이블 만들기 쿼리 레코드 집합에서 새 테이블을 만듭니다.

- `dbQDDL` 쿼리는 데이터 정의-테이블 또는 해당 파트의 구조를 영향을 줍니다.

- `dbQSQLPassThrough` 통과-SQL 문은 중간 처리 하지 않고 데이터베이스 백 엔드에 직접 전달 됩니다.

- `dbQSetOperation` Union-쿼리 2에서 지정 된 모든 레코드의 데이터가 들어 있는 스냅숏 형식 레코드 집합 개체를 만듭니다. 또는 더 많은 테이블이 중복 된 레코드를 제거 합니다. 중복을 포함 하려면 추가 키워드 **모든** 쿼리 정의 SQL 문에 합니다.

- `dbQSPTBulk` 사용한 `dbQSQLPassThrough` 레코드를 반환 하지 않는 쿼리를 지정 합니다.

> [!NOTE]
>  SQL 통과 쿼리를 만들려면 설정 하지 않으면는 `dbQSQLPassThrough` 상수입니다. 이 설정은 자동으로 Microsoft Jet 데이터베이스 엔진에 의해 querydef 개체를 만들고 연결 속성을 설정 합니다.

자세한 내용은 DAO 도움말의 "형식 속성" 항목을 참조 하세요.

*m_dateCreated*<br/>
날짜 및 쿼리 정의 만든 시간입니다. 쿼리 정의 만든 날짜를 직접 검색 하려면 호출을 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다. 자세한 내용은 아래 메모를 참조 하세요. DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조도 합니다.

*m_dateLastUpdated*<br/>
날짜 및 시간 쿼리 정의에 대 한 가장 최근의 변경입니다. 테이블을 마지막으로 수정한 날짜를 직접 검색 하려면 호출을 [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) 쿼리 정의의 멤버 함수입니다. 자세한 내용은 아래 메모를 참조 하세요. 및 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 하세요.

*m_bUpdatable*<br/>
쿼리 정의 변경 수 있는지 여부를 나타냅니다. 쿼리 정의 업데이트할 수 있습니다;이 속성이 TRUE 인 경우 이 고, 그렇지 않습니다. 업데이트 가능 쿼리 정의 개체의 쿼리 정의 변경할 수 있습니다 의미 합니다. 쿼리 정의 업데이트할 수 있는 속성은 TRUE로 설정 쿼리 정의 업데이트할 수 있으면 결과 레코드 집합을 업데이트할 수 없는 경우에. 이 속성을 직접 검색 하려면 쿼리 정의 호출 [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "업데이트할 수 있는 속성" 항목을 참조 하세요.

*m_bReturnsRecords*<br/>
외부 데이터베이스에 SQL 통과 쿼리를 레코드를 반환 하는지 여부를 나타냅니다. 이 속성이 TRUE 인 경우 쿼리는 레코드를 반환 합니다. 이 속성을 직접 검색 하려면 호출 [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)합니다. 일부 SQL 통과 쿼리 외부 데이터베이스에 레코드를 반환 합니다. 예를 들어 SQL **업데이트** SQL 하는 동안 레코드를 반환 하지 않고 레코드를 업데이트 하는 문을 **선택** 문에 레코드를 반환 합니다. 자세한 내용은 DAO 도움말의 "ReturnsRecords 속성" 항목을 참조 하세요.

*m_strSQL*<br/>
쿼리 정의 개체에서 실행 하는 쿼리를 정의 하는 SQL 문입니다. SQL 속성 레코드 선택 방법을, 그룹화 및 정렬 쿼리를 실행 하는 경우를 결정 하는 SQL 문을 포함 합니다. 다이너셋 또는 스냅숏 형식 레코드 집합 개체에 포함 하는 레코드를 선택 하는 쿼리를 사용할 수 있습니다. 또한 레코드를 반환 하지 않고 데이터를 수정 하려면 대량 쿼리를 정의할 수 있습니다. 쿼리 정의 호출에서 직접이 속성의 값을 검색할 수 있습니다 [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) 멤버 함수입니다.

*m_strConnect*<br/>
통과 쿼리를 사용 하는 데이터베이스의 원본에 대 한 정보를 제공 합니다. 이 정보는 연결 문자열의 형식을 사용 합니다. 자세한 내용은 대 한 문자열을 연결 하 고이 속성의 값을 직접 검색 하는 방법에 대 한 정보를 참조 하세요. 합니다 [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) 멤버 함수입니다.

*m_nODBCTimeout*<br/>
Microsoft Jet 데이터베이스 엔진 제한 오류를 하기 전에 대기 하는 시간 (초) 수에는 ODBC 데이터베이스에서 쿼리를 실행할 때 발생 합니다. Microsoft SQL Server와 같은 ODBC 데이터베이스를 사용 하는 경우에 ODBC 서버의 네트워크 트래픽 또는 과도 한 사용으로 인해 지연 나타날 수 있습니다. 무기한 대기 하는 대신 오류를 생성 하기 전에 Microsoft Jet 엔진이 대기 하는 시간을 지정할 수 있습니다. 기본 제한 시간은 60 초입니다. 쿼리 정의 호출에서 직접이 속성의 값을 검색할 수 있습니다 [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "ODBCTimeout 속성" 항목을 참조 하세요.

## <a name="remarks"></a>설명

쿼리 정의 클래스의 개체인 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)합니다. 기본, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) 클래스 멤버 함수 `CDaoDatabase`합니다.

검색 되는 정보는 [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) 멤버 함수에 저장 되는 `CDaoQueryDefInfo` 구조입니다. 호출 `GetQueryDefInfo` 인 QueryDefs 컬렉션 쿼리 정의 개체 저장 된 데이터베이스 개체에 대 한 합니다. `CDaoQueryDefInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoQueryDefInfo` 개체입니다. 클래스 `CDaoDatabase` 모두에서 반환 되는 속성에 직접 액세스 하는 것에 대 한 멤버 함수를 제공 하는 또한을 `CDaoQueryDefInfo` 개체를 호출할 필요가 거의 아마도 `GetQueryDefInfo`합니다.

쿼리 정의 개체의 필드 또는 매개 변수 컬렉션에 새 필드 또는 매개 변수 개체를 추가 하면 기본 데이터베이스에 새 개체에 대해 지정 된 데이터 형식을 지원 하지 않는 경우 예외가 throw 됩니다.

날짜 및 시간 설정에는 쿼리 정의 만들거나 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다. 다중 사용자 환경에서 사용자 가져와야 이러한 설정을 사용 하 여 파일 서버에서 직접 합니다 **시간 net** DateCreated 및 LastUpdated 속성 설정에서 불일치를 방지 하려면 명령입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)
