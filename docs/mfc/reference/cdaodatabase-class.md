---
title: CDaoDatabase 클래스
ms.date: 11/04/2016
f1_keywords:
- CDaoDatabase
- AFXDAO/CDaoDatabase
- AFXDAO/CDaoDatabase::CDaoDatabase
- AFXDAO/CDaoDatabase::CanTransact
- AFXDAO/CDaoDatabase::CanUpdate
- AFXDAO/CDaoDatabase::Close
- AFXDAO/CDaoDatabase::Create
- AFXDAO/CDaoDatabase::CreateRelation
- AFXDAO/CDaoDatabase::DeleteQueryDef
- AFXDAO/CDaoDatabase::DeleteRelation
- AFXDAO/CDaoDatabase::DeleteTableDef
- AFXDAO/CDaoDatabase::Execute
- AFXDAO/CDaoDatabase::GetConnect
- AFXDAO/CDaoDatabase::GetName
- AFXDAO/CDaoDatabase::GetQueryDefCount
- AFXDAO/CDaoDatabase::GetQueryDefInfo
- AFXDAO/CDaoDatabase::GetQueryTimeout
- AFXDAO/CDaoDatabase::GetRecordsAffected
- AFXDAO/CDaoDatabase::GetRelationCount
- AFXDAO/CDaoDatabase::GetRelationInfo
- AFXDAO/CDaoDatabase::GetTableDefCount
- AFXDAO/CDaoDatabase::GetTableDefInfo
- AFXDAO/CDaoDatabase::GetVersion
- AFXDAO/CDaoDatabase::IsOpen
- AFXDAO/CDaoDatabase::Open
- AFXDAO/CDaoDatabase::SetQueryTimeout
- AFXDAO/CDaoDatabase::m_pDAODatabase
- AFXDAO/CDaoDatabase::m_pWorkspace
helpviewer_keywords:
- CDaoDatabase [MFC], CDaoDatabase
- CDaoDatabase [MFC], CanTransact
- CDaoDatabase [MFC], CanUpdate
- CDaoDatabase [MFC], Close
- CDaoDatabase [MFC], Create
- CDaoDatabase [MFC], CreateRelation
- CDaoDatabase [MFC], DeleteQueryDef
- CDaoDatabase [MFC], DeleteRelation
- CDaoDatabase [MFC], DeleteTableDef
- CDaoDatabase [MFC], Execute
- CDaoDatabase [MFC], GetConnect
- CDaoDatabase [MFC], GetName
- CDaoDatabase [MFC], GetQueryDefCount
- CDaoDatabase [MFC], GetQueryDefInfo
- CDaoDatabase [MFC], GetQueryTimeout
- CDaoDatabase [MFC], GetRecordsAffected
- CDaoDatabase [MFC], GetRelationCount
- CDaoDatabase [MFC], GetRelationInfo
- CDaoDatabase [MFC], GetTableDefCount
- CDaoDatabase [MFC], GetTableDefInfo
- CDaoDatabase [MFC], GetVersion
- CDaoDatabase [MFC], IsOpen
- CDaoDatabase [MFC], Open
- CDaoDatabase [MFC], SetQueryTimeout
- CDaoDatabase [MFC], m_pDAODatabase
- CDaoDatabase [MFC], m_pWorkspace
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
ms.openlocfilehash: d1e9db1ddebe05d42cbb8c4ba242938d6d86cc81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399843"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase 클래스

데이터 작업을 할 수 있는 통로인 데이터베이스에 대한 연결을 나타냅니다.

## <a name="syntax"></a>구문

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|`CDaoDatabase` 개체를 생성합니다. 호출 `Open` 데이터베이스에 개체를 연결 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDaoDatabase::CanTransact](#cantransact)|데이터베이스에서 트랜잭션을 지원 하면 0이 아닌 값을 반환 합니다.|
|[CDaoDatabase::CanUpdate](#canupdate)|0이 아닌 경우 반환 된 `CDaoDatabase` 개체는 업데이트할 수 있는 (읽기 전용이 아닌).|
|[CDaoDatabase::Close](#close)|데이터베이스 연결을 닫습니다.|
|[CDaoDatabase::Create](#create)|기본 DAO 데이터베이스 개체를 만들고 초기화 된 `CDaoDatabase` 개체입니다.|
|[CDaoDatabase::CreateRelation](#createrelation)|데이터베이스에서 테이블 간의 새 관계를 정의합니다.|
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|데이터베이스의 QueryDefs 컬렉션에 저장 하는 쿼리 정의 개체를 삭제 합니다.|
|[CDaoDatabase::DeleteRelation](#deleterelation)|데이터베이스에서 테이블 간의 기존 관계를 삭제합니다.|
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|데이터베이스에서 테이블의 정의 삭제합니다. 이 실제 테이블 및 모든 해당 데이터를 삭제합니다.|
|[CDaoDatabase::Execute](#execute)|작업 쿼리를 실행합니다. 호출 `Execute` 예외를 throw 하는 결과 반환 하는 쿼리에 대 한 합니다.|
|[CDaoDatabase::GetConnect](#getconnect)|연결할 때 사용할 연결 문자열을 반환 합니다 `CDaoDatabase` 데이터베이스 개체입니다. ODBC에 사용 됩니다.|
|[CDaoDatabase::GetName](#getname)|현재 사용 중인 데이터베이스의 이름을 반환합니다.|
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|데이터베이스에 대해 정의 된 쿼리의 수를 반환 합니다.|
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|데이터베이스에 정의 된 지정 된 쿼리 정보를 반환 합니다.|
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|반환 초 후 데이터베이스 쿼리 작업 시간이 초과 됩니다. 모든 후속 영향을 줍니다 열고, 새로 추가, 업데이트 및 작업 및 ODBC 데이터 원본에서 다른 작업 (전용) 같은 편집 `Execute` 호출 합니다.|
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|마지막 업데이트의 영향을 받는 레코드 수를 반환 합니다. 편집 또는 추가 작업을 호출 하 여 `Execute`입니다.|
|[CDaoDatabase::GetRelationCount](#getrelationcount)|데이터베이스의 테이블 간에 정의 된 관계 수를 반환 합니다.|
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|데이터베이스의 테이블 간에 정의 된 관계를 지정된 하는 방법에 대 한 정보를 반환 합니다.|
|[CDaoDatabase::GetTableDefCount](#gettabledefcount)|데이터베이스에 정의 된 테이블의 수를 반환 합니다.|
|[CDaoDatabase::GetTableDefInfo](#gettabledefinfo)|데이터베이스에 지정된 된 테이블에 대 한 정보를 반환합니다.|
|[CDaoDatabase::GetVersion](#getversion)|데이터베이스에 연결 된 데이터베이스 엔진의 버전을 반환 합니다.|
|[CDaoDatabase::IsOpen](#isopen)|0이 아닌 경우 반환 된 `CDaoDatabase` 개체는 현재 데이터베이스에 연결 됩니다.|
|[CDaoDatabase::Open](#open)|데이터베이스에 대 한 연결을 설정합니다.|
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|데이터베이스 (초) 수 쿼리 (ODBC 데이터 원본에만 해당)에 대 한 작업 집합에는 시간이 초과 됩니다. 열고 하 새로 추가 업데이트 및 삭제 작업 하는 모든 후속 영향을 줍니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|기본 DAO 데이터베이스 개체에 대 한 포인터입니다.|
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|에 대 한 포인터를 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 데이터베이스를 포함 하는 트랜잭션 공간을 정의 하는 개체입니다.|

## <a name="remarks"></a>설명

지원 되는 데이터베이스 형식에 대 한 내용은 참조는 [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) 멤버 함수입니다. 하나 이상의 할 수 있습니다 `CDaoDatabase` 작업 영역의 지정"," 나타내는 개체를 한 번에 활성화할를 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체입니다. 작업 영역 데이터베이스 컬렉션 이라고 하는 열려 있는 데이터베이스 개체의 컬렉션을 유지 합니다.

> [!NOTE]
>  MFC DAO 데이터베이스 클래스로 변경 ODBC를 기반으로 MFC 데이터베이스 클래스와에서 다릅니다. 모든 DAO 데이터베이스 클래스 이름 "CDao" 접두사가 있습니다. 클래스 `CDaoDatabase` ODBC 클래스와 비슷한 인터페이스를 제공 [CDatabase](../../mfc/reference/cdatabase-class.md)합니다. 주요 차이점은 `CDatabase` DBMS에 대 한 DBMS 개방형 데이터베이스 연결 (ODBC) 및 ODBC 드라이버를 통해 액세스 합니다. `CDaoDatabase` Microsoft Jet 데이터베이스 엔진을 기반으로 하는 데이터 액세스 개체 (DAO)를 통해 데이터에 액세스 합니다. 일반적으로 기반으로 DAO MFC 클래스는 ODBC를 기반으로 MFC 클래스 보다 더욱 강력한 DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 비롯 하 여 데이터를 액세스할 수 있습니다. DAO 기반 클래스는 또한 직접 DAO 호출 하지 않고도 클래스를 통해 테이블을 추가 하는 등의 데이터 정의 언어 (DDL) 작업을 지원 합니다.

## <a name="usage"></a>사용

레코드 집합 개체를 만들 때 암시적으로 데이터베이스 개체를 만들 수 있습니다. 하지만 데이터베이스 개체를 명시적으로 만들 수도 있습니다. 명시적으로 사용 하 여 기존 데이터베이스를 사용 하려면 `CDaoDatabase`, 다음 중 하나를 수행 합니다.

- 생성 된 `CDaoDatabase` 개방적이 고에 대 한 포인터를 전달 하는 개체를 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 개체입니다.

- 생성 또는 `CDaoDatabase` (MFC 임시 작업 영역 개체를 생성 하는 데 사용) 작업 영역을 지정 하지 않고 개체입니다.

새 Microsoft Jet을 만들려면 (합니다. MDB) 데이터베이스 생성을 `CDaoDatabase` 개체와 호출 해당 [만들기](#create) 멤버 함수입니다. 수행할 *되지* 호출 `Open` 후 `Create`합니다.

기존 데이터베이스를 열려면 생성을 `CDaoDatabase` 개체와 호출 해당 [엽니다](#open) 멤버 함수입니다.

이러한 기술 중 하나는 DAO 데이터베이스 개체를 작업 영역 데이터베이스 컬렉션에 추가 하 고 데이터에 대 한 연결을 엽니다. 그런 다음 생성 하는 경우 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)를 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), 또는 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 이러한 개체에 대 한 생성자를 전달 하는 연결 된 데이터베이스에서 작동 하는 것에 대 한 개체를 에 대 한 포인터에 `CDaoDatabase` 개체입니다. 과정을 마치면 연결을 사용 하 여 호출 합니다 [닫기](#close) 멤버 함수를 제거는 `CDaoDatabase` 개체입니다. `Close` 이전에 닫지 않은 모든 레코드 집합을 닫습니다.

## <a name="transactions"></a>트랜잭션

데이터베이스 트랜잭션 처리 작업 영역 수준에서 제공 됩니다-참조를 [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)를 [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), 및 [롤백](../../mfc/reference/cdaoworkspace-class.md#rollback) 클래스의 멤버 함수 `CDaoWorkspace` .

## <a name="odbc-connections"></a>ODBC 연결

ODBC 데이터 원본을 사용 하는 권장된 방법은 Microsoft Jet에 외부 테이블을 연결 하는 것 (합니다. MDB) 데이터베이스입니다.

## <a name="collections"></a>컬렉션

각 데이터베이스에 테이블 정의 쿼리 정의 레코드 집합 및 개체 관계의 고유한 컬렉션 유지 관리합니다. 클래스 `CDaoDatabase` 이러한 개체를 조작 하기 위한 멤버 함수를 제공 합니다.

> [!NOTE]
>  개체는 MFC 데이터베이스 개체에 있는 DAO의 경우에 저장 됩니다. MFC 개체 관계 아니라 테이블 정의 쿼리 및 레코드 집합 개체에 대 한 클래스를 제공합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

##  <a name="cantransact"></a>  CDaoDatabase::CanTransact

데이터베이스 트랜잭션이 있는지 여부를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL CanTransact();
```

### <a name="return-value"></a>반환 값

0이 아닌 데이터베이스에서 트랜잭션을; 지원 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

트랜잭션은은 데이터베이스의 작업 영역에서 관리 됩니다.

##  <a name="canupdate"></a>  CDaoDatabase::CanUpdate

확인 하려면이 멤버 함수를 호출 하는지 여부를 `CDaoDatabase` 개체 업데이트를 허용 합니다.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>반환 값

0이 아닌 값을 `CDaoDatabase` 업데이트를 허용 하는 개체, 그렇지 않으면 0, 어느 것을 나타내는 전달 TRUE *bReadOnly* 열릴 때를 `CDaoDatabase` 개체나 데이터베이스 자체는 읽기 전용입니다. 참조 된 [열려](#open) 멤버 함수입니다.

### <a name="remarks"></a>설명

데이터베이스 업데이트 가능성에 대 한 내용은 DAO 도움말의 "업데이트할 수 있는 속성" 항목을 참조 하세요.

##  <a name="cdaodatabase"></a>  CDaoDatabase::CDaoDatabase

`CDaoDatabase` 개체를 생성합니다.

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>매개 변수

*pWorkspace*<br/>
에 대 한 포인터를 `CDaoWorkspace` 새 데이터베이스 개체를 포함 하는 개체입니다. 생성자는 임시 만듭니다 NULL의 기본값을 수락 하면 `CDaoWorkspace` 기본 DAO 작업 영역을 사용 하는 개체입니다. 통해 작업 영역 개체에 대 한 포인터를 가져올 수 있습니다 합니다 [m_pWorkspace](#m_pworkspace) 데이터 멤버입니다.

### <a name="remarks"></a>설명

새 Microsoft Jet을 만드는 경우 개체를 생성 한 후 (합니다. MDB) 데이터베이스, 개체의 호출 [만들기](#create) 멤버 함수입니다. 인 경우 대신 개체의 호출 기존 데이터베이스 열기 [열고](#open) 멤버 함수입니다.

호출 해야 개체를 완료 하면 해당 [닫습니다](#close) 멤버 함수를 삭제 한 다음는 `CDaoDatabase` 개체입니다.

있습니다 것이 편리할 수도 포함 하는 `CDaoDatabase` 문서 클래스에는 개체입니다.

> [!NOTE]
>  `CDaoDatabase` 열면 개체도 암시적으로 생성 한 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 하 여 기존에 대 한 포인터를 전달 하지 않고 개체 `CDaoDatabase` 개체입니다. 레코드 집합 개체를 닫을 때이 데이터베이스 개체가 닫혀 있습니다.

##  <a name="close"></a>  CDaoDatabase::Close

데이터베이스 연결을 닫고 모든 열려 있는 레코드 집합이, 테이블 정의 데이터베이스에 연결 된 쿼리 정의 하려면이 멤버 함수를 호출 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

이러한 개체를 직접이 멤버 함수를 호출 하기 전에 것이 좋습니다. 닫기는 `CDaoDatabase` 개체에 연결 된 데이터베이스 컬렉션에서 제거 [작업 영역](../../mfc/reference/cdaoworkspace-class.md)합니다. 때문에 `Close` 제거 하지 않습니다는 `CDaoDatabase` 개체를 열거나 동일한 데이터베이스 또는 다른 데이터베이스 개체를 다시 사용할 수 있습니다.

> [!CAUTION]
>  호출 된 [업데이트](../../mfc/reference/cdaorecordset-class.md#update) 멤버 함수 (있는 경우 보류 중인 편집 내용이) 및 `Close` 데이터베이스를 닫기 전에 모든 열린 레코드 집합 개체에서 멤버 함수입니다. 선언 하는 함수를 종료 하는 경우 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 또는 `CDaoDatabase` 개체가 스택에 데이터베이스가 닫혀, 저장 되지 않은 모든 변경 내용이 손실 됩니다, 보류 중인 모든 트랜잭션이 롤백되고 데이터에 모든 보류 중인 편집 내용이 손실 됩니다.

> [!CAUTION]
>  모든 레코드 집합 개체는 열려 데이터베이스 개체를 닫으려는 경우, 해당 특정 작업 영역에 속하는 모든 데이터베이스 개체가 열려 있는 동안 작업 영역 개체를 닫으려는 경우 해당 레코드 집합 개체가 닫히고 수 있는 모든 보류 중인 업데이트 또는 편집 롤백됩니다. 개체를 닫는 작업 영역에 속하는 모든 데이터베이스 개체가 열려 있는 동안 시도 하면 작업이 닫히기 닫히지 않은 레코드 집합 개체에서 발생할 수 있는 특정 작업 영역 개체에 속하는 모든 데이터베이스 개체를 닫습니다. 데이터베이스 개체를 닫지 않는 경우 MFC 디버그 빌드에 어설션 오류를 보고 합니다.

함수의 범위 외부 데이터베이스 개체 정의 닫지 않고 함수를 종료 하는 경우에 데이터베이스 개체에 명시적으로 닫을 때까지 열린 상태로 유지 됩니다 또는 이전에 정의 된 모듈 범위를 벗어납니다.

##  <a name="create"></a>  CDaoDatabase::Create

새 Microsoft Jet을 만들려면 (합니다. MDB)를 생성 한 후에이 멤버 함수를 호출, 데이터베이스는 `CDaoDatabase` 개체입니다.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
사용자가 만드는 데이터베이스 파일의 이름을 나타내는 문자열 식입니다. 수의 전체 경로 파일 이름 같은 "c:\\\MYDB 합니다. MDB "로 설정 합니다. 이름을 제공 해야 합니다. 파일 이름 확장명을 제공 하지 않습니다 하는 경우. MDB 추가 됩니다. 네트워크 경로 네트워크에서 일관 된 명명 규칙 (UNC)를 지 원하는 경우 같은 지정할 수도 있습니다 "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB"입니다. Microsoft Jet만 (합니다. 이 멤버 함수를 사용 하 여 MDB) 데이터베이스 파일을 만들 수 있습니다. (이중 백슬래시 문자열 리터럴에서 필요 하기 때문에 "\\" 됩니다는 C++ 문자를 이스케이프 합니다.)

*lpszLocale*<br/>
데이터베이스 만들기에 대 한 정렬 순서를 지정 하는 데 사용 하는 문자열 식입니다. 기본값은 `dbLangGeneral`입니다. 가능한 값은 다음과 같습니다.

- `dbLangGeneral` 영어, 독일어, 프랑스어, 포르투갈어, 이탈리아어, 및 현대 스페인어

- `dbLangArabic` 아랍어

- `dbLangCyrillic` 러시아어

- `dbLangCzech` Czech

- `dbLangDutch` 네덜란드어

- `dbLangGreek` 그리스어

- `dbLangHebrew` 히브리어

- `dbLangHungarian` 헝가리어

- `dbLangIcelandic` 아이슬란드어

- `dbLangNordic` 노르딕 언어 (Microsoft Jet 데이터베이스 엔진 버전 1.0만)

- `dbLangNorwdan` 노르웨이어 및 덴마크어

- `dbLangPolish` 폴란드어

- `dbLangSpanish` 전통 스페인어

- `dbLangSwedfin` 스웨덴어 및 핀란드어

- `dbLangTurkish` 터키어

*dwOptions*<br/>
하나 이상의 옵션을 나타내는 정수입니다. 가능한 값은 다음과 같습니다.

- `dbEncrypt` 암호화 된 데이터베이스를 만듭니다.

- `dbVersion10` Microsoft Jet 데이터베이스 버전 1.0 사용 하 여 데이터베이스를 만듭니다.

- `dbVersion11` Microsoft Jet 데이터베이스 버전 1.1 사용 하 여 데이터베이스를 만듭니다.

- `dbVersion20` Microsoft Jet 데이터베이스 버전 2.0 사용 하 여 데이터베이스를 만듭니다.

- `dbVersion30` Microsoft Jet 데이터베이스 버전 3.0 사용 하 여 데이터베이스를 만듭니다.

암호화 상수를 생략 하면는 암호화 되지 않은 데이터베이스가 만들어집니다. 버전 상수가 하나만 지정할 수 있습니다. 버전 상수를 생략 하면 Microsoft Jet 데이터베이스 버전 3.0을 사용 하는 데이터베이스 생성 됩니다.

> [!CAUTION]
>  데이터베이스 암호화 되지 않은 경우, 직접 데이터베이스를 구성 하는 이진 디스크 파일을 읽는 데 사용자/암호 보안을 구현 하는 경우에 합니다.

### <a name="remarks"></a>설명

`Create` 데이터베이스 파일 및 기본 DAO 데이터베이스 개체를 만들고 초기화 합니다 C++ 개체입니다. 개체는 연결 된 작업 영역 데이터베이스 컬렉션에 추가 됩니다. 데이터베이스 개체가 열린 상태입니다. 호출 하지 마세요 `Open*` 후 `Create`합니다.

> [!NOTE]
>  사용 하 여 `Create`, Microsoft Jet만 만들 수 있습니다 (합니다. MDB) 데이터베이스입니다. ODBC 데이터베이스 또는 ISAM 데이터베이스를 만들 수 없습니다.

##  <a name="createrelation"></a>  CDaoDatabase::CreateRelation

데이터베이스의 기본 테이블에 하나 이상의 필드에 있는 외래 테이블 (데이터베이스에 다른 테이블)에서 하나 이상의 필드 사이의 관계를 설정 하려면이 멤버 함수를 호출 합니다.

```
void CreateRelation(
    LPCTSTR lpszName,
    LPCTSTR lpszTable,
    LPCTSTR lpszForeignTable,
    long lAttributes,
    LPCTSTR lpszField,
    LPCTSTR lpszForeignField);

void CreateRelation(CDaoRelationInfo& relinfo);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
관계 개체의 고유 이름입니다. 이름을 문자로 시작 해야 하며 40 자까지 포함할 수 있습니다. 숫자를 포함할 수 있습니다 및 밑줄 문자 이지만 문장 부호 또는 공백을 포함할 수 없습니다.

*lpszTable*<br/>
관계의 기본 테이블의 이름입니다. 테이블 없으면 MFC 형식의 예외를 throw [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.

*lpszForeignTable*<br/>
관계의 외래 테이블의 이름입니다. 테이블 없으면 MFC 형식의 예외를 throw 하는 `CDaoException`합니다.

*lAttributes*<br/>
관계 형식에 대 한 정보를 포함 하는 long 값입니다. 무엇 보다도 참조 무결성을 적용 하려면이 값을 사용할 수 있습니다. 비트 OR 연산자를 사용할 수 있습니다 ( **&#124;** ) (으로 조합 적합)는 다음 값 중 하나를 결합 합니다.

- `dbRelationUnique` 관계가 한 일입니다.

- `dbRelationDontEnforce` 관계 없는 (참조 무결성)를 적용 합니다.

- `dbRelationInherited` 관계는 두 개의 연결 된 테이블을 포함 하는 현재 데이터베이스에 존재 합니다.

- `dbRelationUpdateCascade` 업데이트도 함께 복사 (에 단계적 대 한 자세한 설명 참조).

- `dbRelationDeleteCascade` 삭제가 계단식으로 배열 됩니다.

*lpszField*<br/>
기본 테이블에 있는 필드의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터 (로 명명 *lpszTable*).

*lpszForeignField*<br/>
외래 테이블의 필드 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터 (로 명명 *lpszForeignTable*).

*relinfo*<br/>
에 대 한 참조를 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 만들려는 관계에 대 한 정보를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

쿼리 또는 외부 데이터베이스에서 연결 된 테이블 관계를 포함할 수 없습니다.

관계의 두 테이블 각각의 필드 하나를 포함 하는 경우 첫 번째 버전의 함수를 사용 합니다. 관계는 여러 필드를 포함 하는 경우 두 번째 버전을 사용 합니다. 관계에서는 필드의 최대 수는 14입니다.

이 작업 내부 DAO 관계 개체를 만들지만 관계 개체의 MFC의 캡슐화는 클래스 내에 포함 되어 있으므로이 MFC 구현 세부 정보 `CDaoDatabase`합니다. MFC는 관계에 대 한 클래스를 제공 하지 않습니다.

하위 작업을 활성화 하려면 개체의 특성 관계를 설정 하면 데이터베이스 엔진이 자동으로 업데이트 하거나이 관련된 기본 키 테이블에 변경 되 면 하나 이상의 다른 테이블의 레코드를 삭제 합니다.

예를 들어 Customers 테이블과 Orders 테이블 간의 cascade delete 관계를 설정 합니다. Customers 테이블에서 레코드를 삭제 하면 해당 고객에 게 관련 Orders 테이블의 레코드도 삭제 됩니다. 또한 주문 테이블과 다른 테이블 간의 cascade delete 관계를 설정 하는 경우 Customers 테이블에서 레코드를 삭제 하면 해당 테이블의 레코드 삭제 자동으로 됩니다.

관련된 내용은 DAO 도움말의 "CreateRelation 메서드" 항목을 참조 합니다.

##  <a name="deletequerydef"></a>  CDaoDatabase::DeleteQueryDef

지정 된 쿼리 정의 삭제 하려면이 멤버 함수를 호출-저장 된 쿼리-에서 `CDaoDatabase` 개체의 QueryDefs 컬렉션입니다.

```
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
삭제에 저장 된 쿼리의 이름입니다.

### <a name="remarks"></a>설명

그런 다음 쿼리 하는 데이터베이스에 더 이상 정의 됩니다.

쿼리 정의 개체를 만드는 방법에 대 한 자세한 내용은 클래스를 참조 하세요 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)합니다. 특정 연결 되는 쿼리 정의 개체 `CDaoDatabase` 생성 하는 경우 개체는 `CDaoQueryDef` 개체를 데이터베이스 개체에 대 한 포인터 전달 합니다.

##  <a name="deleterelation"></a>  CDaoDatabase::DeleteRelation

데이터베이스 개체의 관계 컬렉션에서 기존 관계를 삭제 하려면이 멤버 함수를 호출 합니다.

```
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
삭제할 관계의 이름입니다.

### <a name="remarks"></a>설명

그런 다음 관계를 더 이상 존재합니다.

관련된 정보에 대 한 "Delete 메서드" DAO 도움말의 항목을 참조 합니다.

##  <a name="deletetabledef"></a>  CDaoDatabase::DeleteTableDef

지정된 된 테이블 및 모든 해당 데이터를 삭제 하려면이 멤버 함수를 호출 합니다 `CDaoDatabase` 개체의 TableDefs 컬렉션입니다.

```
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
삭제 하려면 테이블 정의의 이름입니다.

### <a name="remarks"></a>설명

그런 다음 해당 테이블 데이터베이스에 더 이상 정의 됩니다.

> [!NOTE]
>  매우를 시스템 테이블을 삭제 하지 않도록 주의 해야 합니다.

테이블 정의 개체를 만드는 방법에 대 한 자세한 내용은 클래스를 참조 하세요 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)합니다. 테이블 정의 개체를 특정와 연결 되 `CDaoDatabase` 생성 하는 경우 개체는 `CDaoTableDef` 개체를 데이터베이스 개체에 포인터를 전달 합니다.

관련된 정보에 대 한 "Delete 메서드" DAO 도움말의 항목을 참조 합니다.

##  <a name="execute"></a>  CDaoDatabase::Execute

작업 쿼리를 실행 하거나 데이터베이스에서 SQL 문을 실행 하려면이 멤버 함수를 호출 합니다.

```
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>매개 변수

*lpszSQL*<br/>
유효한 SQL 명령이 실행을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*nOptions*<br/>
쿼리의 무결성에 관련 된 옵션을 지정 하는 정수입니다. 비트 OR 연산자를 사용할 수 있습니다 ( **&#124;** ) 다음 상수 중 하나를 결합할 수 (적합 한 조합을 제공-예를 들어 하는 결합 하지 `dbInconsistent` 사용 하 여 `dbConsistent`).

- `dbDenyWrite` 다른 사용자에 게 쓰기 권한을 거부 합니다.

- `dbInconsistent` (기본값) 일관성 없는 업데이트 합니다.

- `dbConsistent` 일관 된 업데이트 합니다.

- `dbSQLPassThrough` SQL 통과 합니다. SQL 문이 처리에 대 한 ODBC 데이터 원본에 전달 합니다.

- `dbFailOnError` 오류가 발생 하면 업데이트에 게 배포 합니다.

- `dbSeeChanges` 다른 사용자가 편집 하는 데이터를 변경 하는 경우 런타임 오류를 생성 합니다.

> [!NOTE]
>  둘 다 `dbInconsistent` 및 `dbConsistent` 포함 됩니다 또는 모두를 포함 하는 경우 결과 기본 옵션입니다. 이러한 상수 설명은, DAO 도움말의 "메서드 실행" 항목을 참조 합니다.

### <a name="remarks"></a>설명

`Execute` 작업 쿼리 또는 결과 반환 하지 않는 통과 쿼리를 SQL에 대해서만 작동 합니다. 레코드를 반환 하는 select 쿼리에 작동 하지 않습니다.

정의 및 작업 쿼리에 대 한 정보를 "쿼리 동작" 및 DAO 도움말의 "메서드 실행" 항목을 참조 합니다.

> [!TIP]
>  구문이 정확 하면서 SQL 문과 올바른 사용 권한을 지정는 `Execute` 멤버 함수가 실패 하지 않으면 단일 행을 수정 되거나 삭제 될 수 있습니다. 따라서 항상 사용 합니다 `dbFailOnError` 옵션을 사용 하는 경우는 `Execute` 멤버 함수는 업데이트 실행 또는 삭제 쿼리를 합니다. 이 옵션을 사용 하면 형식의 예외를 throw 하는 MFC [CDaoException](../../mfc/reference/cdaoexception-class.md) 영향을 받는 레코드의 잠겨 및 업데이트 하거나 삭제할 수 없는 경우 모든 성공적인 변경 내용을 롤백합니다. 항상 호출할 수 있는 참고 `GetRecordsAffected` 영향을 받은 레코드 수를 확인 합니다.

호출 된 [GetRecordsAffected](#getrecordsaffected) 최신 영향을 받는 레코드의 수를 확인 하려면 데이터베이스 개체의 멤버 함수 `Execute` 호출 합니다. 예를 들어 `GetRecordsAffected` 삭제, 업데이트 또는 삽입 작업 쿼리를 실행 하는 경우 레코드의 수에 대 한 정보를 반환 합니다. 반환 된 개수 하위를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 하는 것을 반영 되지 않습니다.

`Execute` 레코드 집합을 반환 하지 않습니다. 사용 하 여 `Execute` MFC 형식의 예외를 throw 하면 레코드를 선택 하는 쿼리 `CDaoException`합니다. (방법이 없는 `ExecuteSQL` 멤버 함수 비슷합니다 `CDatabase::ExecuteSQL`.)

##  <a name="getconnect"></a>  CDaoDatabase::GetConnect

연결할 때 사용할 연결 문자열을 검색 하려면이 멤버 함수를 호출 합니다 `CDaoDatabase` ODBC 또는 ISAM 데이터베이스에는 개체입니다.

```
CString GetConnect();
```

### <a name="return-value"></a>반환 값

하는 경우 연결 문자열 [열려](#open) ODBC 데이터 원본에서 성공적으로 호출 그렇지 않은 빈 문자열입니다. Microsoft Jet 용 (합니다. MDB) 데이터베이스 문자열은 항상 비어 사용에 대 한 설정 하지 않으면를 `dbSQLPassThrough` 옵션 사용 합니다 [Execute](#execute) 멤버 함수 또는 레코드 집합을 열 때 사용 합니다.

### <a name="remarks"></a>설명

열려 있는 데이터베이스 또는 통과 쿼리를 사용 하는 데이터베이스의 원본에 대 한 정보를 제공 하는 문자열입니다. 데이터베이스 형식 지정자 및 0 개 이상의 매개 변수를 세미콜론으로 구분 된 연결 문자열 구성 됩니다.

> [!NOTE]
>  MFC DAO 클래스를 사용 하 여 ODBC 통해 데이터 원본에 연결할 연결 된 테이블을 통한 연결 보다 덜 효율적입니다.

> [!NOTE]
>  ODBC 및 필요에 따라 특정 ISAM 드라이버 추가 정보를 전달 하는 연결 문자열 사용 됩니다. 에 대 한 사용 되지 않습니다. MDB 데이터베이스입니다. Microsoft Jet 데이터베이스 기본 테이블에 대 한 연결 문자열은 빈 문자열 ("") 사용 하는 경우 해당 SQL 통과 쿼리를 위한 위 반환 값에서 설명한 대로 제외 하 고 있습니다.

참조를 [열고](#open) 연결 문자열은 생성 하는 방법에 대 한 멤버 함수입니다. 연결 문자열 설정 되 면를 `Open` 호출을 사용할 수 있습니다 나중에 데이터베이스의 사용자 ID, 암호 또는 ODBC 데이터 원본 유형, 경로 확인 하는 설정을 확인 합니다.

##  <a name="getname"></a>  CDaoDatabase::GetName

기존 데이터베이스 파일의 이름인 현재 열려 있는 데이터베이스의 이름 또는 등록 된 ODBC 데이터 원본의 이름을 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetName();
```

### <a name="return-value"></a>반환 값

성공할 경우 데이터베이스의 파일 이름과 전체 경로 그렇지 않으면 빈 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.

### <a name="remarks"></a>설명

네트워크에서 일관 된 명명 규칙 (UNC)를 지 원하는 네트워크 경로 지정할 수도 있습니다-예를 들어, "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB 합니다. MDB "로 설정 합니다. (이중 백슬래시 문자열 리터럴에서 필요 하기 때문에 "\\" 됩니다는 C++ 문자를 이스케이프 합니다.)

예를 들어 제목에는이 이름이 표시 하려면 할 수 있습니다. 이름을 검색 하는 동안 오류가 발생 하는 경우 MFC 형식의 예외를 throw [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.

> [!NOTE]
>  성능 향상을 위해 외부 데이터베이스에 액세스할 때 좋습니다 Microsoft Jet 데이터베이스에 외부 데이터베이스 테이블을 연결 하는 (합니다. MDB) 데이터 원본에 직접 연결 하는 대신 합니다.

데이터베이스 유형 파일 또는 디렉터리를 가리키는 경로, 다음과 같이 표시 됩니다.

|경로 이름 가리키는...|데이터베이스 유형|
|--------------------------|-------------------|
|. MDB 파일|Microsoft Jet 데이터베이스 (Microsoft Access)|
|포함 된 디렉터리입니다. DBF 파일|dBASE 데이터베이스|
|포함 된 디렉터리입니다. XLS 파일|Microsoft Excel 데이터베이스|
|포함 된 디렉터리입니다. PDX 파일|Paradox 데이터베이스|
|적절 하 게 서식이 지정 된 텍스트 데이터베이스 파일이 포함 된 디렉터리|텍스트 형식으로 데이터베이스|

SQL Server 및 Oracle과 같은 ODBC 데이터베이스에 대 한 데이터베이스의 연결 문자열은 ODBC에서 등록 된 데이터 원본 이름 (DSN)를 식별 합니다.

##  <a name="getquerydefcount"></a>  CDaoDatabase::GetQueryDefCount

데이터베이스의 QueryDefs 컬렉션에 정의 된 쿼리의 수를 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetQueryDefCount();
```

### <a name="return-value"></a>반환 값

데이터베이스에 정의 된 쿼리의 수입니다.

### <a name="remarks"></a>설명

`GetQueryDefCount` QueryDefs 컬렉션에서 모든 쿼리를 반복 해야 할 경우 유용 합니다. 참조 컬렉션에서 지정 된 쿼리에 대 한 정보를 얻으려면 [GetQueryDefInfo](#getquerydefinfo)합니다.

##  <a name="getquerydefinfo"></a>  CDaoDatabase::GetQueryDefInfo

다양 한 종류의 데이터베이스에 정의 된 쿼리 정보를 가져오려면이 함수를 호출 합니다.

```
void GetQueryDefInfo(
    int nIndex,
    CDaoQueryDefInfo& querydefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetQueryDefInfo(
    LPCTSTR lpszName,
    CDaoQueryDefInfo& querydefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
미리 정의 된 쿼리에서 인덱스에서 조회에 대 한 데이터베이스의 QueryDefs 컬렉션의 인덱스입니다.

*querydefinfo*<br/>
에 대 한 참조를 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.

*dwInfoOptions*<br/>
검색할 레코드 집합에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 어떤 문제를 일으킬 있습니다 레코드 집합에 대 한 반환 하는 함수 함께 나와 있습니다.

- (기본값) AFX_DAO_PRIMARY_INFO 이름, 형식

- 더하기 AFX_DAO_SECONDARY_INFO 기본 정보: 만든 날짜, 반환 레코드를 업데이트할 수 있는 마지막 업데이트 날짜

- AFX_DAO_ALL_INFO 기본 및 보조 데이터베이스 정보가 더하기: SQL, Connect, ODBCTimeout

*lpszName*<br/>
이름별 조회에 대 한 데이터베이스에 정의 된 쿼리의 이름을 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

데이터베이스의 QueryDefs 컬렉션에서 인덱스로 또는 쿼리의 이름으로 쿼리를 선택할 수 있도록 두 버전의 함수가 제공 됩니다.

반환 되는 정보에 대 한 *querydefinfo*를 참조 합니다 [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) 구조입니다. 이 구조에 대 한 설명에서 위에 나열 된 정보 항목에 해당 하는 멤버가 *dwInfoOptions*합니다. 한 수준의 정보를 요청 하는 경우 모든 이전 수준의 정보를 가져옵니다.

##  <a name="getquerytimeout"></a>  CDaoDatabase::GetQueryTimeout

현재 연결 된 데이터베이스의 후속 작업 시간이 초과 하기 전까지 허용 시간 (초) 수를 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetQueryTimeout();
```

### <a name="return-value"></a>반환 값

초에서 제한 시간 값을 포함 하는 short 정수입니다.

### <a name="remarks"></a>설명

네트워크 액세스 문제, 과도 한 쿼리 처리 시간 등으로 인해 작업 시간이 초과 될 수 있습니다. 열려 있는 모든 설정이 적용 되는 동안에 영향을, 새로 추가, 업데이트 및 삭제 작업와 관련 된 모든 레코드 집합에 `CDaoDatabase` 개체입니다. 호출 하 여 현재 제한 시간 설정을 변경할 수 있습니다 [SetQueryTimeout](#setquerytimeout)합니다. 연 후 레코드 집합에 대 한 쿼리 제한 시간 값을 변경 하는 경우에 레코드 집합에 대 한 값을 변경 되지 않습니다. 예를 들어, 후속 [이동](../../mfc/reference/cdaorecordset-class.md#move) 작업 새 값을 사용 하지 않습니다. 기본값은 데이터베이스 엔진 초기화 될 때 처음 설정 됩니다.

쿼리 제한 시간에 대 한 기본 값은 Windows 레지스트리에서 가져옵니다. 레지스트리 설정이 없는 경우 기본값은 60 초입니다. 일부 데이터베이스 쿼리 제한 시간 값을 설정 하는 기능을 지원 합니다. 쿼리 제한 시간 값이 0으로 설정한 경우 시간 제한 없이 발생 합니다. 및 데이터베이스와의 통신에 응답 하지 않을 수 있습니다. 이 동작은 개발 하는 동안 유용할 수 있습니다. 호출에 실패 하는 경우 MFC 형식의 예외를 throw [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.

관련된 정보 DAO 도움말의 "QueryTimeout 속성" 항목을 참조 하세요.

##  <a name="getrecordsaffected"></a>  CDaoDatabase::GetRecordsAffected

가장 최근 호출에 의해 영향을 받은 레코드 수를 확인 하려면이 멤버 함수를 호출 합니다 [Execute](#execute) 멤버 함수입니다.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>반환 값

영향을 받는 레코드 수를 포함 하는 long 정수입니다.

### <a name="remarks"></a>설명

반환 값에는 삭제, 업데이트 또는 쿼리를 실행 하 여 삽입 된 레코드 수가 포함 됩니다. `Execute`합니다. 반환 된 개수 하위를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 하는 것을 반영 되지 않습니다.

관련된 내용은 DAO 도움말의 "RecordsAffected Property" 항목을 참조 합니다.

##  <a name="getrelationcount"></a>  CDaoDatabase::GetRelationCount

데이터베이스의 테이블 간에 정의 된 관계의 번호를 가져오려면이 함수를 호출 합니다.

```
short GetRelationCount();
```

### <a name="return-value"></a>반환 값

데이터베이스의 테이블 간에 정의 된 관계의 수입니다.

### <a name="remarks"></a>설명

`GetRelationCount` 데이터베이스의 관계 컬렉션에 정의 된 모든 관계를 반복 해야 할 경우 유용 합니다. 참조 컬렉션에서 지정 된 관계에 대 한 정보를 얻으려면 [GetRelationInfo](#getrelationinfo)합니다.

관계의 개념을 설명 하기 위해를 Suppliers 테이블 및 제품 테이블에 일 대 다 관계를 가질 수 있는 것이 좋습니다. 공급자는이 관계에 있는 둘 이상의 제품을 제공할 수 있습니다. 다른 관계는 한 일 및 다 대 다입니다.

##  <a name="getrelationinfo"></a>  CDaoDatabase::GetRelationInfo

데이터베이스의 관계 컬렉션에 지정 된 관계에 대 한 정보를 가져오려면이 함수를 호출 합니다.

```
void GetRelationInfo(
    int nIndex,
    CDaoRelationInfo& relinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetRelationInfo(
    LPCTSTR lpszName,
    CDaoRelationInfo& relinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스에서 조회에 대 한 데이터베이스의 관계 컬렉션에서 관계 개체의 인덱스입니다.

*relinfo*<br/>
에 대 한 참조를 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.

*dwInfoOptions*<br/>
검색할 관계에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 어떤 문제를 일으킬 있습니다 관계에 대 한 반환 하는 함수 함께 나와 있습니다.

- 이름, 테이블, 외래 테이블 AFX_DAO_PRIMARY_INFO (기본값)

- AFX_DAO_SECONDARY_INFO 특성을 필드 정보

필드 정보를 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) 관계에 관련 된 기본 테이블에서 필드를 포함 하는 개체입니다.

*lpszName*<br/>
이름별 조회 관계 개체의 이름을 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

이 함수의 두 가지 버전 인덱스 또는 이름으로 액세스를 제공합니다. 반환 되는 정보에 대 한 *relinfo*를 참조 합니다 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 구조입니다. 이 구조에 대 한 설명에서 위에 나열 된 정보 항목에 해당 하는 멤버가 *dwInfoOptions*합니다. 한 수준 정보를 요청 하는 경우 또한도 모든 이전 수준 정보를 가져옵니다.

> [!NOTE]
>  하위 작업을 활성화 하려면 개체의 특성 관계를 설정 하는 경우 (`dbRelationUpdateCascades` 또는 `dbRelationDeleteCascades`), Microsoft Jet 데이터베이스 엔진 자동으로 업데이트 하거나 레코드에서 하나를 삭제 또는 다른 테이블에 변경 되 면 관련 기본 키 테이블입니다. 예를 들어 Customers 테이블과 Orders 테이블 간의 cascade delete 관계를 설정 합니다. Customers 테이블에서 레코드를 삭제 하면 해당 고객에 게 관련 Orders 테이블의 레코드도 삭제 됩니다. 또한 주문 테이블과 다른 테이블 간의 cascade delete 관계를 설정 하는 경우 Customers 테이블에서 레코드를 삭제 하면 해당 테이블의 레코드 삭제 자동으로 됩니다.

##  <a name="gettabledefcount"></a>  CDaoDatabase::GetTableDefCount

데이터베이스에 정의 된 테이블 수를 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetTableDefCount();
```

### <a name="return-value"></a>반환 값

데이터베이스에 정의 된 테이블 정의의 수입니다.

### <a name="remarks"></a>설명

`GetTableDefCount` 데이터베이스의 테이블 정의 컬렉션의 모든 테이블 정의 반복 해야 할 경우 유용 합니다. 참조 컬렉션에서 지정된 된 테이블에 대 한 정보를 얻으려면 [GetTableDefInfo](#gettabledefinfo)합니다.

##  <a name="gettabledefinfo"></a>  CDaoDatabase::GetTableDefInfo

다양 한 종류의 데이터베이스에 정의 된 테이블에 대 한 정보를 가져오려면이 함수를 호출 합니다.

```
void GetTableDefInfo(
    int nIndex,
    CDaoTableDefInfo& tabledefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetTableDefInfo(
    LPCTSTR lpszName,
    CDaoTableDefInfo& tabledefinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스에서 조회에 대 한 데이터베이스의 테이블 정의 컬렉션의 테이블 정의 개체의 인덱스입니다.

*tabledefinfo*<br/>
에 대 한 참조를 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.

*dwInfoOptions*<br/>
검색할 테이블에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 어떤 문제를 일으킬 있습니다 관계에 대 한 반환 하는 함수 함께 나와 있습니다.

- 업데이트할 수 (기본값) AFX_DAO_PRIMARY_INFO 이름 특성

- 더하기 AFX_DAO_SECONDARY_INFO 기본 정보: 만든 날짜, 날짜, 마지막으로 업데이트 원본 테이블 이름, 연결

- AFX_DAO_ALL_INFO 기본 및 보조 데이터베이스 정보가 더하기: 유효성 검사 규칙 유효성 검사 텍스트 레코드 수

*lpszName*<br/>
이름별 조회에 대 한 테이블 정의 개체의 이름입니다.

### <a name="remarks"></a>설명

데이터베이스의 테이블 정의 컬렉션의 인덱스 또는 테이블의 이름으로 테이블을 선택할 수 있도록 두 버전의 함수가 제공 됩니다.

반환 되는 정보에 대 한 *tabledefinfo*를 참조 합니다 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 구조입니다. 이 구조에 대 한 설명에서 위에 나열 된 정보 항목에 해당 하는 멤버가 *dwInfoOptions*합니다. 한 수준 정보를 요청 하면도 모든 이전 수준에 대 한 정보 가져오기

> [!NOTE]
>  AFX_DAO_ALL_INFO 옵션 느린를 가져올 수 있는 정보를 제공 합니다. 이 경우 테이블의 레코드 수를 계산 시간이 오래 걸릴 경우 레코드 수 수 있습니다.

##  <a name="getversion"></a>  CDaoDatabase::GetVersion

Microsoft Jet 데이터베이스 파일의 버전을 확인 하려면이 멤버 함수를 호출 합니다.

```
CString GetVersion();
```

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 연결 된 데이터베이스 파일의 버전을 나타내는입니다.

### <a name="remarks"></a>설명

반환 된 값 "major.minor"; 버전 번호를 나타냅니다. 예를 들어, "3.0"입니다. 제품 버전 번호 (예: 3.0) 버전 번호 (3), 마침표 및 릴리스 번호 (0)으로 구성 됩니다. 날짜는 버전 1.0, 1.1, 2.0 및 3.0 됩니다.

관련된 내용은 DAO 도움말의 "버전 Property" 항목을 참조 합니다.

##  <a name="isopen"></a>  CDaoDatabase::IsOpen

확인 하려면이 멤버 함수를 호출 하는지 여부를 `CDaoDatabase` 개체가 데이터베이스에 현재 열려 있는 합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 값을 `CDaoDatabase` 개체가 현재 열려 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

##  <a name="m_pdaodatabase"></a>  CDaoDatabase::m_pDAODatabase

DAO 데이터베이스 개체가 기본 OLE 인터페이스에 대 한 포인터를 `CDaoDatabase` 개체입니다.

### <a name="remarks"></a>설명

DAO 인터페이스를 직접 액세스 해야 하는 경우에이 포인터를 사용 합니다.

DAO 호출 하는 방법에 대 한 정보에 대 한 참조를 직접 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.

##  <a name="m_pworkspace"></a>  CDaoDatabase::m_pWorkspace

에 대 한 포인터를 포함 합니다 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 데이터베이스 개체를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

작업 영역에 직접 액세스 해야 할 경우에이 포인터를 사용 하 여-예를 들어 workspace의 데이터베이스 컬렉션에서 다른 데이터베이스 개체에 대 한 포인터를 가져오려고 합니다.

##  <a name="open"></a>  CDaoDatabase::Open

새로 생성 된 초기화 하려면이 멤버 함수를 호출 해야 `CDaoDatabase` 기존 데이터베이스를 나타내는 개체입니다.

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
기존 Microsoft Jet의 이름인 문자열 식 (합니다. MDB) 데이터베이스 파일입니다. 파일 이름 확장명이 있으면 필요 합니다. 네트워크 경로 네트워크에서 일관 된 명명 규칙 (UNC)를 지 원하는 경우 같은 지정할 수도 있습니다 "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB 합니다. MDB "로 설정 합니다. (이중 백슬래시 문자열 리터럴에서 필요 하기 때문에 "\\" 됩니다는 C++ 문자를 이스케이프 합니다.)

사용 하는 경우 몇 가지 사항을 고려해 야 *lpszName*합니다. 하는 경우 해당:

- MFC 형식의 예외를 throw 하는 다른 사용자에 의해 단독 액세스를 위해 이미 열려 있는 데이터베이스를 가리킵니다 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다. 데이터베이스를 사용할 수 없는 프로그램 사용자에 게 알려야 하는 예외를 트래핑 합니다.

- 이 빈 문자열 ("") 및 *lpszConnect* "ODBC;"는 사용자 데이터베이스를 선택할 수 있도록 등록 된 모든 ODBC 데이터 원본 이름 목록을 하는 대화 상자가 표시 됩니다. ODBC 데이터 원본에 대 한 직접 연결 하지 마십시오 연결 된 테이블을 대신 사용 합니다.

- 그렇지 않은 경우 기존 데이터베이스 또는 유효한 ODBC 데이터 원본 이름, MFC 형식의 예외 throw 참조 하지 않습니다 `CDaoException`합니다.

> [!NOTE]
>  DAO 오류 코드에 대 한 자세한 내용은 참조는 DAOERR 합니다. H 파일입니다. 관련된 정보 "트랩 가능한 DAO 도움말에서 Data Access Errors" 항목을 참조 하세요.

*bExclusive*<br/>
TRUE 이면 데이터베이스가 데이터베이스 공유 액세스를 위해 열어야 하는 경우 전용 (비공유) 액세스 하 고 FALSE 열어야 하는 부울 값입니다. 이 인수를 생략 하면 데이터베이스 공유 액세스를 위해 열려 있습니다.

*bReadOnly*<br/>
TRUE 이면 데이터베이스가 데이터베이스 읽기/쓰기 액세스를 위해 열어야 하는 경우 읽기 전용으로 액세스 하 고 FALSE 열어야 하는 부울 값입니다. 이 인수를 생략 하면 데이터베이스 읽기/쓰기 액세스를 위해 열려 있습니다. 이 특성을 상속 하는 모든 종속 레코드 집합.

*lpszConnect*<br/>
데이터베이스를 여는 데 사용 하는 문자열 식입니다. 이 문자열은 ODBC 인수를 연결 합니다. 소스 문자열을 제공할 전용 및 읽기 전용 인수를 지정 해야 합니다. 데이터베이스가 Microsoft Jet 데이터베이스 (합니다. MDB)에이 문자열이 비어 있습니다. (""). 기본값에 대 한 구문을 — **_T**("")-유니코드 뿐만 아니라 ANSI 이식성이 응용 프로그램의 빌드를 제공 합니다.

### <a name="remarks"></a>설명

`Open` 기본 DAO 개체를 사용 하 여 데이터베이스를 연결합니다. 초기화 될 때까지 테이블 정의 레코드 집합, 쿼리 정의 개체를 생성 하는 데이터베이스 개체를 사용할 수 없습니다. `Open` 연결 된 작업 영역 데이터베이스 컬렉션에 데이터베이스 개체를 추가합니다.

다음과 같이 매개 변수를 사용 합니다.

- Microsoft Jet를 여는 경우 (합니다. MDB) 데이터베이스를 사용 하 여는 *lpszName* 매개 변수 및 빈 문자열이 전달 된 *lpszConnect* 매개 변수 또는 형식의 암호 문자열로 전달 "; PWD 암호 = "데이터베이스가 암호로 보호 된 경우 (합니다. MDB 데이터베이스에만 해당)입니다.

- ODBC 데이터 소스를 여는 경우에 유효한 ODBC 연결 문자열을 전달 *lpszConnect* 에 빈 문자열이 *lpszName*합니다.

관련된 내용은 DAO 도움말의 "OpenDatabase 메서드" 항목을 참조 합니다.

> [!NOTE]
>  ISAM 데이터베이스 및 ODBC 데이터 소스를 포함 하 여 외부 데이터베이스에 액세스할 때 성능 향상을 위해 것이 좋습니다 Microsoft Jet 엔진 데이터베이스에 외부 데이터베이스 테이블을 연결 하는 (합니다. MDB) 데이터 원본에 직접 연결 하는 대신 합니다.

있기 연결 시도가 시간 초과 대 한 경우, 예를 들어 DBMS 호스트를 사용할 수 없습니다. 연결 시도가 실패 하면 `Open` 형식의 예외를 throw [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.

나머지 설명을 ODBC 데이터베이스에만 적용 됩니다.

데이터베이스의 매개 변수 및 ODBC 데이터베이스 인지에 `Open` 호출에 연결 하는 데 충분 한 정보가 없는, ODBC 드라이버 사용자 로부터 필요한 정보를 가져오기 위한 대화 상자를 엽니다. 호출 하는 경우 `Open`, 연결 문자열에 *lpszConnect*를 호출 하 여 사용할 수 있고 개인적으로 저장 되며 합니다 [GetConnect](#getconnect) 멤버 함수입니다.

호출 하기 전에 사용자가 직접 대화 상자를 열 수 있습니다 `Open` 정보를 가져오려면 암호와 같은 사용자의 다음 추가 정보를 전달할 연결 문자열에 `Open`입니다. 또는 응용 프로그램 호출의 시간을 재사용할 수 있도록 해당 다음 (아마도 Windows 레지스트리)에 전달 하는 연결 문자열을 저장 하는 것이 좋습니다 `Open` 에 `CDaoDatabase` 개체입니다.

여러 수준의 로그인 권한 부여에 대 한 연결 문자열을 사용할 수도 있습니다 (각각 다른 `CDaoDatabase` 개체) 또는 다른 데이터베이스 관련 정보를 전달 합니다.

##  <a name="setquerytimeout"></a>  CDaoDatabase::SetQueryTimeout

후속 작업을 데이터베이스 연결된 시간이 초과 하기 전까지 허용 시간 (초) 기본값을 재정의 하려면이 멤버 함수를 호출 합니다.

```
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>매개 변수

*nSeconds*<br/>
쿼리 시도 하기 전까지 허용 시간 (초) 수 시간이 초과 됩니다.

### <a name="remarks"></a>설명

네트워크 액세스 문제, 과도 한 쿼리 처리 시간 및 등으로 인해 작업 시간이 초과 될 수 있습니다. 호출 `SetQueryTimeout` 레코드 집합을 열기 전에 또는 레코드 집합의 호출 하기 전에 [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew)하십시오 [업데이트](../../mfc/reference/cdaorecordset-class.md#update), 또는 [삭제](../../mfc/reference/cdaorecordset-class.md#delete) 쿼리를 변경 하려는 경우 멤버 함수 시간 제한 값입니다. 설정은 모든 후속 [엽니다](../../mfc/reference/cdaorecordset-class.md#open)를 `AddNew`, `Update`, 및 `Delete` 와 연결 된 모든 레코드 집합에 대 한 호출 `CDaoDatabase` 개체입니다. 연 후 레코드 집합에 대 한 쿼리 제한 시간 값을 변경 하는 경우에 레코드 집합에 대 한 값을 변경 되지 않습니다. 예를 들어, 후속 [이동](../../mfc/reference/cdaorecordset-class.md#move) 작업 새 값을 사용 하지 않습니다.

쿼리 제한 시간에 대 한 기본값은 60 초입니다. 일부 데이터베이스 쿼리 제한 시간 값을 설정 하는 기능을 지원 합니다. 쿼리 제한 시간 값이 0으로 설정한 경우 시간 제한 없이 발생 합니다. 데이터베이스와의 통신에 응답 하지 않을 수 있습니다. 이 동작은 개발 하는 동안 유용할 수 있습니다.

관련된 정보 DAO 도움말의 "QueryTimeout 속성" 항목을 참조 하세요.

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDatabase 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
