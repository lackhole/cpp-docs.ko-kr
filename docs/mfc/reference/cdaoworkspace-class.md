---
title: CDaoWorkspace 클래스
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspace
- AFXDAO/CDaoWorkspace
- AFXDAO/CDaoWorkspace::CDaoWorkspace
- AFXDAO/CDaoWorkspace::Append
- AFXDAO/CDaoWorkspace::BeginTrans
- AFXDAO/CDaoWorkspace::Close
- AFXDAO/CDaoWorkspace::CommitTrans
- AFXDAO/CDaoWorkspace::CompactDatabase
- AFXDAO/CDaoWorkspace::Create
- AFXDAO/CDaoWorkspace::GetDatabaseCount
- AFXDAO/CDaoWorkspace::GetDatabaseInfo
- AFXDAO/CDaoWorkspace::GetIniPath
- AFXDAO/CDaoWorkspace::GetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::GetLoginTimeout
- AFXDAO/CDaoWorkspace::GetName
- AFXDAO/CDaoWorkspace::GetUserName
- AFXDAO/CDaoWorkspace::GetVersion
- AFXDAO/CDaoWorkspace::GetWorkspaceCount
- AFXDAO/CDaoWorkspace::GetWorkspaceInfo
- AFXDAO/CDaoWorkspace::Idle
- AFXDAO/CDaoWorkspace::IsOpen
- AFXDAO/CDaoWorkspace::Open
- AFXDAO/CDaoWorkspace::RepairDatabase
- AFXDAO/CDaoWorkspace::Rollback
- AFXDAO/CDaoWorkspace::SetDefaultPassword
- AFXDAO/CDaoWorkspace::SetDefaultUser
- AFXDAO/CDaoWorkspace::SetIniPath
- AFXDAO/CDaoWorkspace::SetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::SetLoginTimeout
- AFXDAO/CDaoWorkspace::m_pDAOWorkspace
helpviewer_keywords:
- CDaoWorkspace [MFC], CDaoWorkspace
- CDaoWorkspace [MFC], Append
- CDaoWorkspace [MFC], BeginTrans
- CDaoWorkspace [MFC], Close
- CDaoWorkspace [MFC], CommitTrans
- CDaoWorkspace [MFC], CompactDatabase
- CDaoWorkspace [MFC], Create
- CDaoWorkspace [MFC], GetDatabaseCount
- CDaoWorkspace [MFC], GetDatabaseInfo
- CDaoWorkspace [MFC], GetIniPath
- CDaoWorkspace [MFC], GetIsolateODBCTrans
- CDaoWorkspace [MFC], GetLoginTimeout
- CDaoWorkspace [MFC], GetName
- CDaoWorkspace [MFC], GetUserName
- CDaoWorkspace [MFC], GetVersion
- CDaoWorkspace [MFC], GetWorkspaceCount
- CDaoWorkspace [MFC], GetWorkspaceInfo
- CDaoWorkspace [MFC], Idle
- CDaoWorkspace [MFC], IsOpen
- CDaoWorkspace [MFC], Open
- CDaoWorkspace [MFC], RepairDatabase
- CDaoWorkspace [MFC], Rollback
- CDaoWorkspace [MFC], SetDefaultPassword
- CDaoWorkspace [MFC], SetDefaultUser
- CDaoWorkspace [MFC], SetIniPath
- CDaoWorkspace [MFC], SetIsolateODBCTrans
- CDaoWorkspace [MFC], SetLoginTimeout
- CDaoWorkspace [MFC], m_pDAOWorkspace
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
ms.openlocfilehash: 6aa404c5eb543db198043dba68d55a4b925739c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253727"
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace 클래스

단일 사용자가 로그인부터 로그인까지 암호로 보호되고 명명된 데이터베이스 세션을 관리합니다.

## <a name="syntax"></a>구문

```
class CDaoWorkspace : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|작업 영역 개체를 생성합니다. 그런 다음 호출 `Create` 또는 `Open`합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDaoWorkspace::Append](#append)|데이터베이스 엔진의 작업 영역 컬렉션에 새로 만든된 작업 영역을 추가합니다.|
|[CDaoWorkspace::BeginTrans](#begintrans)|작업 영역에서 열린 모든 데이터베이스에 적용 되는 새 트랜잭션을 시작 합니다.|
|[CDaoWorkspace::Close](#close)|작업 영역 및 모든 포함 하는 개체를 닫습니다. 보류 중인 트랜잭션이 롤백됩니다.|
|[CDaoWorkspace::CommitTrans](#committrans)|현재 트랜잭션을 완료 하 고 변경 내용을 저장 합니다.|
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|압축 하거나 중복 데이터베이스.|
|[CDaoWorkspace::Create](#create)|새 DAO workspace 개체를 만듭니다.|
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|Workspace의 데이터베이스 컬렉션에서 DAO 데이터베이스 개체의 수를 반환합니다.|
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|Workspace의 데이터베이스 컬렉션에 정의 된 지정된 된 DAO 데이터베이스에 대 한 정보를 반환 합니다.|
|[CDaoWorkspace::GetIniPath](#getinipath)|Windows 레지스트리에서 엔진의 초기화 설정을 Microsoft Jet 데이터베이스의 위치를 반환합니다.|
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|데이터 원본에 여러 연결을 강제 적용 같은 ODBC 데이터 소스와 관련 된 여러 트랜잭션을 통해 격리 되는지 여부를 나타내는 값을 반환 합니다.|
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|사용자가 ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수를 반환 합니다.|
|[CDaoWorkspace::GetName](#getname)|Workspace 개체에 대 한 사용자 정의 이름을 반환합니다.|
|[CDaoWorkspace::GetUserName](#getusername)|작업 영역을 만들 때 사용자 이름을 지정을 반환 합니다. 작업 영역 소유자의 이름입니다.|
|[CDaoWorkspace::GetVersion](#getversion)|작업 영역과 연결 된 데이터베이스 엔진의 버전을 포함 하는 문자열을 반환 합니다.|
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|데이터베이스 엔진의 작업 영역 컬렉션에서 DAO 작업 영역 개체의 수를 반환합니다.|
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|데이터베이스 엔진의 작업 영역 컬렉션에 정의 된 지정한 DAO 작업 영역에 대 한 정보를 반환 합니다.|
|[CDaoWorkspace::Idle](#idle)|데이터베이스 엔진을 백그라운드 작업을 수행할 수 있습니다.|
|[CDaoWorkspace::IsOpen](#isopen)|작업 영역이 0이 아닌 반환을 엽니다.|
|[CDaoWorkspace::Open](#open)|DAO의 기본 작업 영역과 연결 된 작업 영역 개체를 명시적으로 열립니다.|
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|손상된 된 데이터베이스를 복구 하려고 합니다.|
|[CDaoWorkspace::Rollback](#rollback)|현재 트랜잭션을 종료 하 고 변경 내용을 저장 하지 않습니다.|
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|데이터베이스 엔진에 특정 암호 없이 작업 영역 개체를 만들 때 사용 되는 암호를 설정 합니다.|
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|데이터베이스 엔진에는 특정 사용자 이름 없이 작업 영역 개체를 만들 때 사용 하는 사용자 이름을 설정 합니다.|
|[CDaoWorkspace::SetIniPath](#setinipath)|Windows 레지스트리에서 위치의 Microsoft Jet 데이터베이스 엔진의 초기화 설정의 설정합니다.|
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|데이터 원본에 여러 연결을 강제 적용 하 여 동일한 ODBC 데이터 소스와 관련 된 여러 트랜잭션을 격리 여부를 지정 합니다.|
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|사용자가 ODBC 데이터 원본에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수를 설정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|기본 DAO workspace 개체를 가리킵니다.|

## <a name="remarks"></a>설명

대부분의 경우에서 여러 작업 영역을 하지 않아도 됩니다 하 고 명시적 작업 영역 개체를 만들 필요가 없습니다. 데이터베이스 및 레코드 집합 개체를 열면 DAO의 기본 작업 영역을 사용 합니다. 그러나에서 필요한 경우에 추가 작업 영역 개체를 만들어 한 번에 여러 세션을 실행할 수 있습니다. 각 작업 영역의 개체는 자체 데이터베이스 컬렉션에 여러 열린 데이터베이스 개체를 포함할 수 있습니다. MFC에서 작업 영역은 주로 트랜잭션 관리자는 동일한 "트랜잭션 공간입니다."에서 모든 열려 있는 데이터베이스의 집합 지정

> [!NOTE]
>  DAO 데이터베이스 클래스로 개방형 데이터베이스 연결 (ODBC)에 따라 MFC 데이터베이스 클래스와에서 다릅니다. 모든 DAO 데이터베이스 클래스 이름 "CDao" 접두사가 있습니다. 일반적으로 기반으로 DAO MFC 클래스는 ODBC를 기반으로 MFC 클래스 보다 더 수 있습니다. DAO 기반 클래스를 사용 하는 ODBC 드라이버를 포함 하 여 Microsoft Jet 데이터베이스 엔진을 통해 데이터에 액세스 합니다. 또한 데이터베이스를 만들고 테이블 및 필드는 클래스를 통해 직접 DAO 호출 하지 않고도 추가 같은 데이터 정의 언어 (DDL) 작업을 지원 합니다.

## <a name="capabilities"></a>기능

클래스 `CDaoWorkspace` 다음 기능을 제공 합니다.

- 명시적 액세스 데이터베이스 엔진을 초기화 하 여 만든 기본 작업 영역에 필요한 경우. 일반적으로 사용할 DAO의 기본 작업 영역 암시적으로 데이터베이스 및 레코드 집합 개체를 만들어 합니다.

- 작업 영역에서 모든 데이터베이스에 트랜잭션을 적용 하는 트랜잭션 공간을 엽니다. 별도 트랜잭션 공간을 관리 하는 추가 작업 영역을 만들 수 있습니다.

- 내부 Microsoft Jet 데이터베이스 엔진의 여러 속성에 대 한 인터페이스 (정적 멤버 함수는 참조). 열기 또는 작업 영역을 만들기 전에 정적 멤버 함수 호출 또는 만들기를 열고 데이터베이스 엔진을 초기화 합니다.

- 에 추가 된 모든 활성 작업 영역을 저장 하는 데이터베이스 엔진의 작업 영역 컬렉션에 액세스 합니다. 또한 만들 하 고 작업 영역 컬렉션에 추가 하지 않고 작업할 수 있습니다.

## <a name="security"></a>보안

MFC dao에서 보안 제어에 사용 되는 사용자 및 그룹 컬렉션을 구현 하지 않습니다. DAO의 이러한 측면을 해야 하는 경우 프로그램 해야 해당 직접 DAO 인터페이스를 직접 호출을 통해. 정보를 참조 하세요 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.

## <a name="usage"></a>사용

클래스를 사용할 수 있습니다 `CDaoWorkspace` 에:

- 기본 작업 영역을 명시적으로 열어야 합니다.

   일반적으로 기본 작업 영역 사용은 암시적-새 열 때 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다. 하지만 명시적으로 액세스 해야 합니다.-예를 들어 데이터베이스 엔진이 속성에 액세스 하거나 작업 영역 컬렉션을 합니다. 아래의 "기본 작업 영역의 암시적 사용"을 참조 하십시오.

- 새 작업 영역을 만듭니다. 호출 [Append](#append) 작업 영역 컬렉션에 추가 하려는 경우.

- 작업 영역 컬렉션에서 기존 작업 영역을 엽니다.

새 작업 영역을 만드는 아직 없으면 컬렉션이 아래에서 설명 하는 작업 영역에는 [만들기](#create) 멤버 함수입니다. 작업 영역의 개체는 어떤 방식으로 데이터베이스 엔진 세션 간에 유지 되지 않습니다. 응용 프로그램이 MFC를 정적으로 링크 하는 경우 응용 프로그램을 끝내기 데이터베이스 엔진을 초기화 하지 않습니다. 응용 프로그램이 MFC를 사용 하 여 동적으로 연결 하는 경우에 MFC DLL을 언로드할 때 데이터베이스 엔진 초기화 되지 않았습니다.

명시적으로 기본 작업 영역 열기 또는 작업 영역 컬렉션에서 기존 작업 영역을 열고 아래에 설명 되어는 [열고](#open) 멤버 함수입니다.

사용 하 여 작업 영역을 닫으면 작업 영역 세션을 종료 합니다 [닫기](#close) 멤버 함수입니다. `Close` 닫지 않은 이전에 커밋되지 않은 트랜잭션을 롤백하고 데이터베이스를 닫습니다.

## <a name="transactions"></a>트랜잭션

DAO 작업 영역 수준에서 트랜잭션 관리 따라서 트랜잭션이 열려 있는 여러 데이터베이스를 사용 하 여 작업 영역에 모든 데이터베이스에 적용 됩니다. 예를 들어 두 개의 데이터베이스는 커밋되지 않은 업데이트 하 호출 [CommitTrans](#committrans), 업데이트를 모두 커밋됩니다. 단일 데이터베이스에 대 한 트랜잭션 제한 하려는 경우에에 대 한 별도 작업 영역 개체를 해야 합니다.

## <a name="implicit-use-of-the-default-workspace"></a>암시적 기본 작업 영역 사용

MFC는 DAO의 기본 작업 영역에서 암시적으로 다음과 같은 상황을 사용합니다.

- 새 만들면 `CDaoDatabase` 개체 있지만 그렇게 하지 않으면 기존를 통해 `CDaoWorkspace` MFC 개체를 만듭니다 임시 작업 영역, DAO의 기본 작업 영역에 해당 하는 개체입니다. 이렇게 하면 여러 데이터베이스에 대 한 데이터베이스 개체의 모든 기본 작업 영역을 사용 하 여 연결 됩니다. 통해 데이터베이스의 작업 영역에 액세스할 수 있습니다는 `CDaoDatabase` 데이터 멤버입니다.

- 마찬가지로, 만드는 경우는 `CDaoRecordset` 개체에 대 한 포인터를 제공 하지 않고는 `CDaoDatabase` 개체, MFC 임시 데이터베이스 개체를 만듭니다 및 확장을 임시 작업 영역 개체를 합니다. 레코드 집합의 데이터베이스 및 간접적으로 해당 작업 영역을 통해 액세스할 수 있습니다는 `CDaoRecordset` 데이터 멤버입니다.

## <a name="other-operations"></a>기타 작업

다른 데이터베이스 작업과 제공 되는데, 예: 손상된 된 데이터베이스를 복구 또는 데이터베이스를 압축 합니다.

직접 DAO 호출 및 DAO 보안에 대 한 정보를 참조 하세요 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoWorkspace`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

##  <a name="append"></a>  CDaoWorkspace::Append

이 멤버 함수를 호출한 후 호출 [만들기](#create)합니다.

```
virtual void Append();
```

### <a name="remarks"></a>설명

`Append` 새로 만든된 작업 영역 개체를 데이터베이스 엔진의 작업 영역 컬렉션에 추가합니다. 작업 영역 데이터베이스 엔진 세션 간에 유지 되지 않습니다. 디스크에 없는 메모리에만 저장 됩니다. 작업 영역을 추가할 필요가 없습니다. 그렇지 않으면 여전히 사용할 수 있습니다.

추가 된 작업 영역을 계속 활성에서 작업 영역 컬렉션에서 열린 상태로 호출할 때까지 해당 [닫기](#close) 멤버 함수입니다.

관련된 내용은 DAO 도움말의 "메서드 추가" 항목을 참조 합니다.

##  <a name="begintrans"></a>  CDaoWorkspace::BeginTrans

트랜잭션을 시작 하도록이 멤버 함수를 호출 합니다.

```
void BeginTrans();
```

### <a name="remarks"></a>설명

호출한 후 `BeginTrans`, 트랜잭션을 커밋할 때 데이터 또는 데이터베이스 구조에 업데이트 내용이 적용 됩니다. 작업 영역에서는 단일 트랜잭션 공간을 정의 하므로 트랜잭션 작업 영역에서 열려 있는 모든 데이터베이스에 적용 됩니다. 트랜잭션을 완료 하는 방법은 두 가지:

- 호출 된 [CommitTrans](#committrans) 트랜잭션을 커밋하고 데이터 원본에 변경 내용을 저장 하는 멤버 함수입니다.

- 호출 또는 합니다 [롤백](#rollback) 트랜잭션을 취소 하려면 멤버 함수입니다.

모든 보류 중인 트랜잭션을 롤백합니다 트랜잭션이 보류 중일 때 workspace 개체 또는 데이터베이스 개체를 닫기입니다.

다른 ODBC 데이터 원본에서 하나의 ODBC 데이터 원본에서 트랜잭션을 격리 하는 경우 참조를 [SetIsolateODBCTrans](#setisolateodbctrans) 멤버 함수입니다.

##  <a name="cdaoworkspace"></a>  CDaoWorkspace::CDaoWorkspace

`CDaoWorkspace` 개체를 생성합니다.

```
CDaoWorkspace();
```

### <a name="remarks"></a>설명

생성 한 후는 C++ 개체를 두 가지 옵션이 있습니다.

- 개체의 호출 [엽니다](#open) 멤버 함수를 기본 작업 영역을 열려면 또는 작업 영역 컬렉션에서 기존 개체를 엽니다.

- 개체의 호출 또는 [만들기](#create) 멤버 함수를 새 DAO 작업 영역 개체를 만듭니다. 통해 참조할 수 있는 새 작업 영역 세션을 명시적으로 시작 됩니다는 `CDaoWorkspace` 개체입니다. 호출한 후 `Create`를 호출할 수 있습니다 [Append](#append) 작업 영역 데이터베이스 엔진의 작업 영역 컬렉션에 추가 하려는 경우.

클래스 개요를 참조 하세요 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 명시적으로 생성 해야 하는 경우에 대 한 자세한를 `CDaoWorkspace` 개체입니다. 열 때 암시적으로 생성 하는 작업 영역을 사용 하는 일반적으로 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체를 열 때 또는 작업 영역을 지정 하지 않고는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 데이터베이스 개체를 지정 하지 않고 개체입니다. 이 방법으로 만든 MFC DAO 개체는 한 번 생성 되 고 다시 사용 되는 DAO의 기본 작업 영역을 사용 합니다.

작업 영역 및 해당 포함 된 개체를 해제 하려면 workspace 개체의 호출 [닫기](#close) 멤버 함수입니다.

##  <a name="close"></a>  CDaoWorkspace::Close

작업 영역 개체를 닫으려면이 멤버 함수를 호출 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

작업 영역 열기 개체 닫기 하는 기본 DAO 개체를 해제 되 고 작업 영역을 사용 하면 작업 영역 컬렉션의 멤버인 경우 컬렉션에서 제거 합니다. 호출 `Close` 이 좋은 프로그래밍 방법입니다.

> [!CAUTION]
>  작업 영역 개체를 닫으면 작업 영역에서 열린 데이터베이스입니다. 이 인해도 닫히기 데이터베이스에서 모든 레코드 집합 열기 및 보류 중인 편집 내용 또는 업데이트 내용이 롤백됩니다. 관련된 정보에 대 한 참조를 [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close)를 [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close), 및 [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) 멤버 함수입니다.

작업 영역 개체; 저장 되지 않습니다. 이러한 참조에 존재 하는 동안에 존재 합니다. 즉, 하는 데이터베이스 엔진 세션이 종료 되 면 작업 영역 및 해당 데이터베이스 컬렉션 지속 되지 않습니다. 다시 만들어야 하 다음 세션에 대 한 작업 영역 및 데이터베이스를 다시 열어 합니다.

관련된 내용은 DAO 도움말의 "Close 메서드가" 항목을 참조 합니다.

##  <a name="committrans"></a>  CDaoWorkspace::CommitTrans

트랜잭션 커밋이 멤버 함수 호출, 편집 하 고 업데이트의 그룹 작업 영역에서 하나 이상의 데이터베이스에 저장 합니다.

```
void CommitTrans();
```

### <a name="remarks"></a>설명

트랜잭션이 구성 된 일련의 데이터베이스의 데이터에 대 한 호출으로 시작 하 고 구조를 변경 [BeginTrans](#begintrans)합니다. 트랜잭션을 완료 하는 경우 하나 커밋하거나 롤백하지 않은 (변경 내용 취소) 사용 하 여 [롤백](#rollback)합니다. 기본적으로 트랜잭션 없이 레코드에 대 한 업데이트 커밋 즉시 됩니다. 호출 `BeginTrans` 호출할 때까지 지연 될 업데이트의 약정 하면 `CommitTrans`합니다.

> [!CAUTION]
>  하나의 작업 영역 내에서 트랜잭션은 항상 작업 영역에 전역 이며 하나의 데이터베이스 또는 레코드 집합에 제한 되지 않습니다. 둘 이상의 데이터베이스 또는 트랜잭션 작업 영역 내 레코드 집합에 대 한 작업을 수행 하는 경우 `CommitTrans` 업데이트를 보류 중인 모든 커밋 및 `Rollback` 해당 데이터베이스 및 레코드 집합에서 모든 작업을 복원 합니다.

데이터베이스 또는 보류 중인 트랜잭션 사용 하 여 작업 영역을 닫으면 트랜잭션이 모두 롤백됩니다.

> [!NOTE]
>  2 단계 커밋 메커니즘이 아닙니다. 하나의 업데이트 커밋에 실패 하면 다른 여전히 커밋됩니다.

##  <a name="compactdatabase"></a>  CDaoWorkspace::CompactDatabase

이 멤버 함수는 지정 된 Microsoft Jet compact를 호출 (합니다. MDB) 데이터베이스입니다.

```
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,
    LPCTSTR lpszDestName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int nOptions = 0);

static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,
    LPCTSTR lpszDestName,
    LPCTSTR lpszLocale,
    int nOptions,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>매개 변수

*lpszSrcName*<br/>
기존 이름을 데이터베이스를 닫힙니다. 수는 전체 경로 및 파일 이름을 같은 "c:\\\MYDB 합니다. MDB "로 설정 합니다. 파일 이름 확장명이 지정 해야 합니다. 네트워크 경로 네트워크에서 일관 된 명명 규칙 (UNC)를 지 원하는 경우 같은 지정할 수도 있습니다 "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB 합니다. MDB "로 설정 합니다. (때문에 경로 문자열에 필요한 이중 백슬래시 "\\" 됩니다는 C++ 문자를 이스케이프 합니다.)

*lpszDestName*<br/>
만들고 있는 압축된 된 데이터베이스의 전체 경로입니다. 사용 하 여 네트워크 경로를 지정할 수도 있습니다 *lpszSrcName*합니다. 사용할 수 없습니다는 *lpszDestName* 와 동일한 데이터베이스 파일을 지정 하는 인수 *lpszSrcName*합니다.

*lpszPassword*<br/>
암호로 보호 된 데이터베이스를 압축 하려고 할 때 사용 되는 암호입니다. 버전을 사용 하는 경우 `CompactDatabase` 암호를 사용 하는 모든 매개 변수를 제공 해야 합니다. 또한 연결 매개 변수 이기 때문에 필요 같이 특별 한 서식,:; PWD = *lpszPassword*합니다. 예를 들어:; PWD = "정상"입니다. (선행 세미콜론은 필수입니다.)

*lpszLocale*<br/>
만들기에 대 한 정렬 순서를 지정 하는 데 사용 하는 문자열 식 *lpszDestName*합니다. 기본값을 그대로 사용 하 여이 인수를 생략 하면 `dbLangGeneral` (아래 참조) 새 데이터베이스의 로캘을 이전 데이터베이스와 동일 합니다. 가능한 값은 다음과 같습니다.

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

*nOptions*<br/>
대상 데이터베이스에 대 한 하나 이상의 옵션을 나타내는 *lpszDestName*합니다. 기본값을 그대로 사용 하 여이 인수를 생략 합니다 *lpszDestName* 동일한 암호화 및와 같은 버전 *lpszSrcName*합니다. 결합할 수 있습니다 합니다 `dbEncrypt` 또는 `dbDecrypt` 비트 OR 연산자를 사용 하 여 버전 옵션 중 하나를 사용 하 여 옵션입니다. 데이터베이스 엔진 버전이 아니라 데이터베이스 형식으로 지정 하는 가능한 값:

- `dbEncrypt` 압축 하는 동안 데이터베이스를 암호화 합니다.

- `dbDecrypt` 압축 하는 동안 데이터베이스를 해독 합니다.

- `dbVersion10` 압축 하는 동안 Microsoft Jet 데이터베이스 엔진 버전 1.0을 사용 하는 데이터베이스를 만듭니다.

- `dbVersion11` 압축 하는 동안 Microsoft Jet 데이터베이스 엔진 버전 1.1을 사용 하는 데이터베이스를 만듭니다.

- `dbVersion20` 압축 하는 동안 Microsoft Jet 데이터베이스 엔진 버전 2.0을 사용 하는 데이터베이스를 만듭니다.

- `dbVersion30` 압축 하는 동안 Microsoft Jet 데이터베이스 엔진 버전 3.0을 사용 하는 데이터베이스를 만듭니다.

사용할 수 있습니다 `dbEncrypt` 또는 `dbDecrypt` 옵션 인수에 압축 하는 대로 데이터베이스를 암호 해독 또는 암호화 여부를 지정 합니다. 암호화 상수를 생략 하는 경우 또는 둘 다를 포함 하는 경우 `dbDecrypt` 하 고 `dbEncrypt`를 *lpszDestName* 와 같은 암호화 해야 *lpszSrcName*합니다. 옵션 인수에 버전 상수 중 하나를 사용 하 여 압축 된 데이터베이스의 데이터 형식 버전을 지정할 수 수 있습니다. 이 상수 데이터 형식의 버전에만 영향을 줍니다 *lpszDestName*합니다. 버전 상수가 하나만 지정할 수 있습니다. 버전 상수를 생략 *lpszDestName* 와 동일한 버전을 갖습니다 *lpszSrcName*합니다. 압축할 수 있습니다 *lpszDestName* 일치 하는 버전에만 또는 나중에 비해 *lpszSrcName*합니다.

> [!CAUTION]
>  데이터베이스 암호화 되지 않은 경우, 직접 데이터베이스를 구성 하는 이진 디스크 파일을 읽는 데 사용자/암호 보안을 구현 하는 경우에 합니다.

### <a name="remarks"></a>설명

데이터베이스의 데이터를 변경 하면 데이터베이스 파일 조각화 될 수 있습니다 및 필요한 것 보다 더 많은 디스크 공간을 사용 합니다. 정기적으로 데이터베이스 파일을 조각 모음에 데이터베이스를 압축 해야 합니다. 압축된 된 데이터베이스는 일반적으로 작습니다. 복사한 데이터베이스를 압축 하는 동안 정렬 순서, 암호화, 또는 데이터 형식의 버전을 변경할 수도 있습니다.

> [!CAUTION]
>  `CompactDatabase` 멤버 함수는 올바르게 변환할 전체 Microsoft Access 데이터베이스 버전 간에 다른 합니다. 데이터 형식에만 변환 됩니다. Microsoft 액세스 정의 개체, 양식 및 보고서와 같은 변환 되지 않습니다. 그러나 데이터가 올바르게 변환 됩니다.

> [!TIP]
>  사용할 수도 있습니다 `CompactDatabase` 데이터베이스 파일을 복사 합니다.

데이터베이스 압축에 대 한 자세한 내용은 항목 DAO 도움말의 "CompactDatabase 메서드"를 참조 하세요.

##  <a name="create"></a>  CDaoWorkspace::Create

새 DAO workspace 개체를 만들고 MFC를 사용 하 여 연결 하려면이 멤버 함수를 호출 `CDaoWorkspace` 개체입니다.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszUserName,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
새 작업 영역 개체의 고유 이름을 지정 하는 최대 14 개의 문자가 포함 된 문자열입니다. 이름을 제공 해야 합니다. 관련된 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*lpszUserName*<br/>
작업 공간의 소유자의 사용자 이름입니다. 요구 사항에 대 한 참조를 *lpszDefaultUser* 매개 변수를 [SetDefaultUser](#setdefaultuser) 멤버 함수입니다. 관련된 내용은 DAO 도움말의 "사용자 이름 속성" 항목을 참조 합니다.

*lpszPassword*<br/>
새 작업 영역 개체에 대 한 암호입니다. 암호는 최대 14 자까지 가능 하며 ASCII 0 (null)를 제외한 모든 문자를 포함할 수 있습니다. 암호는 대소문자를 구분합니다. 관련된 내용은 DAO 도움말에서 "암호 속성이" 항목을 참조 합니다.

### <a name="remarks"></a>설명

전체 생성 프로세스는 다음과 같습니다.

1. 생성 된 [CDaoWorkspace](#cdaoworkspace) 개체입니다.

1. 개체의 호출 `Create` 멤버 함수를 기본 DAO 작업 영역을 만듭니다. 작업 영역 이름을 지정 해야 합니다.

1. 필요에 따라 호출할 [Append](#append) 작업 영역 데이터베이스 엔진의 작업 영역 컬렉션에 추가 하려는 경우. 작업 영역에 추가 하지 않고 작업할 수 있습니다.

이후에 `Create` 호출, 작업 영역 개체가 열린 상태를 사용할 수 있습니다. 호출 하지 마세요 `Open` 후 `Create`합니다. 호출 하지 않으면 `Create` 이미 작업 영역 컬렉션 작업 영역에 있는 경우. `Create` 이미 응용 프로그램에 대 한 초기화 되지 않은 경우 데이터베이스 엔진을 초기화 합니다.

##  <a name="getdatabasecount"></a>  CDaoWorkspace::GetDatabaseCount

Workspace의 데이터베이스 컬렉션에서 DAO 데이터베이스 개체의 수를 검색 하려면이 멤버 함수를 호출, 작업 영역에서 열려 있는 데이터베이스의 수입니다.

```
short GetDatabaseCount();
```

### <a name="return-value"></a>반환 값

작업 영역에서 열려 있는 데이터베이스 수입니다.

### <a name="remarks"></a>설명

`GetDatabaseCount` workspace의 데이터베이스 컬렉션에 정의 된 모든 데이터베이스를 반복 해야 할 경우 유용 합니다. 참조 된 컬렉션의 지정된 된 데이터베이스에 대 한 정보를 얻으려면 [GetDatabaseInfo](#getdatabaseinfo)합니다. 일반적인 사용법은 호출 `GetDatabaseCount` 열려 있는 데이터베이스 개수에 대 한 다음 해당 숫자 루프 인덱스로 반복된 호출에 사용할 `GetDatabaseInfo`합니다.

##  <a name="getdatabaseinfo"></a>  CDaoWorkspace::GetDatabaseInfo

다양 한 종류의 작업 영역 데이터베이스를 열에 대 한 정보를 가져오려면이 함수를 호출 합니다.

```
void GetDatabaseInfo(
    int nIndex,
    CDaoDatabaseInfo& dbinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetDatabaseInfo(
    LPCTSTR lpszName,
    CDaoDatabaseInfo& dbinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스에서 조회에 대 한 작업 영역의 데이터베이스 컬렉션에 있는 데이터베이스 개체의 0부터 시작 하는 인덱스입니다.

*dbinfo*<br/>
에 대 한 참조를 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.

*dwInfoOptions*<br/>
검색할 데이터베이스에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 어떤 문제를 일으킬 있습니다를 반환 하는 함수 함께 나와 있습니다.

- AFX_DAO_PRIMARY_INFO (기본값) 이름, 업데이트 가능한 트랜잭션

- 더하기 AFX_DAO_SECONDARY_INFO 기본 정보: 버전, 정렬 순서, 쿼리 제한 시간

- AFX_DAO_ALL_INFO 기본 및 보조 데이터베이스 정보가 더하기: 연결

*lpszName*<br/>
이름별 조회에 대 한 데이터베이스 개체의 이름입니다. 이름은 최대 14 자까지를 사용 하 여 새 작업 영역 개체의 고유 이름을 지정 하는 문자열입니다.

### <a name="remarks"></a>설명

한 버전의 함수를 사용 하면 인덱스로 데이터베이스를 조회할 수 있습니다. 다른 버전에서는 데이터베이스 이름으로 조회할 수 있습니다.

반환 되는 정보에 대 한 *dbinfo*를 참조 합니다 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 구조입니다. 이 구조에 대 한 설명에서 위에 나열 된 정보 항목에 해당 하는 멤버가 *dwInfoOptions*합니다. 한 수준 정보를 요청으로 모든 이전 수준에 대 한 정보를 얻을 수 있습니다.

##  <a name="getinipath"></a>  CDaoWorkspace::GetIniPath

Windows 레지스트리에서 엔진의 초기화 설정을 Microsoft Jet 데이터베이스의 위치를 가져오려면이 함수를 호출 합니다.

```
static CString PASCAL GetIniPath();
```

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 레지스트리 위치를 포함 합니다.

### <a name="remarks"></a>설명

데이터베이스 엔진에 대 한 설정에 대 한 정보를 가져올 위치를 사용할 수 있습니다. 반환 되는 정보에는 실제로 레지스트리 하위 키의 이름입니다.

관련된 정보에 대 한 "IniPath 속성" 및 "사용자 지정 Windows 레지스트리 설정에 대 한 데이터 액세스" DAO 도움말의 항목을 참조 합니다.

##  <a name="getisolateodbctrans"></a>  CDaoWorkspace::GetIsolateODBCTrans

작업 영역에 대 한 DAO IsolateODBCTrans 속성의 현재 값을 검색할이 멤버 함수를 호출 합니다.

```
BOOL GetIsolateODBCTrans();
```

### <a name="return-value"></a>반환 값

ODBC 트랜잭션 격리; 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

경우에 따라 같은 ODBC 데이터베이스에서 보류 중인 여러 동시 트랜잭션이 하도록 해야 합니다. 이 작업을 수행 하려면 각 트랜잭션에 대 한 별도 작업 영역을 열려면 해야 합니다. 각 작업 영역 데이터베이스에는 자체 ODBC 연결 수 있지만,이 경우 시스템 성능이 저하 염두에 두어야 합니다. 트랜잭션 격리에 일반적으로 필요 하지 않으므로 기본적으로 ODBC 연결 같은 사용자가 연 여러 workspace 개체에서 공유 됩니다.

Microsoft SQL Server와 같은 일부 ODBC 서버에서는 단일 연결에서 동시 트랜잭션을 허용 하지 않습니다. 이러한 데이터베이스에 대해 보류 중인 한 번에 둘 이상의 트랜잭션 해야 할 경우 IsolateODBCTrans 속성을 TRUE로 설정 각 작업 영역에서 열면 즉시 합니다. 이렇게 하면 각 작업 영역에 대 한 별도 ODBC 연결 됩니다.

관련된 내용은 DAO 도움말의 "IsolateODBCTrans Property" 항목을 참조 합니다.

##  <a name="getlogintimeout"></a>  CDaoWorkspace::GetLoginTimeout

작업 영역에 대 한 DAO LoginTimeout 속성의 현재 값을 검색할이 멤버 함수를 호출 합니다.

```
static short PASCAL GetLoginTimeout();
```

### <a name="return-value"></a>반환 값

ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수입니다.

### <a name="remarks"></a>설명

이 값은 ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수를 나타냅니다. LoginTimeout 기본값은 20 초입니다. LoginTimeout을 0으로 설정 하는 경우 시간 제한 없이 발생 하 고 데이터 소스와의 통신 응답 중지 될 수 있습니다.

네트워크 오류로 인해 연결이 실패할 수 있습니다 Microsoft SQL Server와 같은 ODBC 데이터베이스에 로그인 하려는 경우 서버가 실행 중이 아니므로 또는 합니다. 기본값에 대 한 20 초를 위해 대기 중인 연결 하는 대신 데이터베이스 엔진 오류를 생성 하기 전에 대기 하는 시간을 지정할 수 있습니다. 외부 서버 데이터베이스에서 쿼리를 실행 하는 등의 다른 이벤트의 숫자의 일부분으로 암시적으로 발생 서버에 로그인 합니다.

관련된 내용은 DAO 도움말의 "LoginTimeout Property" 항목을 참조 합니다.

##  <a name="getname"></a>  CDaoWorkspace::GetName

DAO 작업 영역 개체 기본 사용자 정의 이름을 가져오려면이 함수를 호출 합니다 `CDaoWorkspace` 개체입니다.

```
CString GetName();
```

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) DAO workspace 개체의 사용자 정의 이름을 포함 합니다.

### <a name="remarks"></a>설명

이름을 이름으로 데이터베이스 엔진의 작업 영역 컬렉션에서 DAO workspace 개체에 액세스 하기 위한 유용 합니다.

관련된 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

##  <a name="getusername"></a>  CDaoWorkspace::GetUserName

작업 영역 소유자의 이름을 가져오려면이 함수를 호출 합니다.

```
CString GetUserName();
```

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) workspace 개체의 소유자를 나타내는입니다.

### <a name="remarks"></a>설명

를 가져오거나 작업 영역 소유자에 대 한 사용 권한을 설정 하려면, 권한을 속성 설정을 검사할 직접 DAO 호출 사용 권한을 결정이 해당 사용자에 게 합니다. 사용 권한으로 작동 하려면 시스템을 해야 합니다. MDA 파일입니다.

DAO 호출 하는 방법에 대 한 정보에 대 한 참조를 직접 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다. 관련된 내용은 DAO 도움말의 "사용자 이름 속성" 항목을 참조 합니다.

##  <a name="getversion"></a>  CDaoWorkspace::GetVersion

사용 중인 Microsoft Jet 데이터베이스 엔진의 버전을 확인 하려면이 멤버 함수를 호출 합니다.

```
static CString PASCAL GetVersion();
```

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체에 연결 된 데이터베이스 엔진의 버전을 나타내는입니다.

### <a name="remarks"></a>설명

반환 된 값 "major.minor"; 버전 번호를 나타냅니다. 예를 들어, "3.0"입니다. 제품 버전 번호 (예: 3.0) 버전 번호 (3), 마침표 및 릴리스 번호 (0)으로 구성 됩니다.

관련된 내용은 DAO 도움말의 "버전 Property" 항목을 참조 합니다.

##  <a name="getworkspacecount"></a>  CDaoWorkspace::GetWorkspaceCount

DAO 데이터베이스 엔진의 작업 영역 컬렉션 작업 영역 개체의 수를 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetWorkspaceCount();
```

### <a name="return-value"></a>반환 값

작업 영역 컬렉션에서 열기 작업의 수입니다.

### <a name="remarks"></a>설명

이 개수 열기 작업 영역 컬렉션에 추가 되지 않는 포함 되지 않습니다. `GetWorkspaceCount` 작업 영역 컬렉션에 정의 된 모든 작업 영역을 반복 해야 할 경우 유용 합니다. 참조 컬렉션에서 지정된 된 작업 영역에 대 한 정보를 얻으려면 [GetWorkspaceInfo](#getworkspaceinfo)합니다. 일반적인 사용법은 호출 `GetWorkspaceCount` 열기 작업 영역에 수에 대 한 다음 사용 하 여 해당 숫자 루프 인덱스에 대 한 반복된 호출 `GetWorkspaceInfo`합니다.

##  <a name="getworkspaceinfo"></a>  CDaoWorkspace::GetWorkspaceInfo

다양 한 유형의 세션에서 열려 있는 작업 영역에 대 한 정보를 가져오려면이 함수를 호출 합니다.

```
void GetWorkspaceInfo(
    int nIndex,
    CDaoWorkspaceInfo& wkspcinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetWorkspaceInfo(
    LPCTSTR lpszName,
    CDaoWorkspaceInfo& wkspcinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스에서 조회에 대 한 작업 영역 컬렉션에서 데이터베이스 개체의 0부터 시작 하는 인덱스입니다.

*wkspcinfo*<br/>
에 대 한 참조를 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.

*dwInfoOptions*<br/>
작업 영역을 검색 하는 방법에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 어떤 문제를 일으킬 있습니다를 반환 하는 함수 함께 나와 있습니다.

- (기본값) AFX_DAO_PRIMARY_INFO 이름

- 더하기 AFX_DAO_SECONDARY_INFO 기본 정보: 사용자 이름

- AFX_DAO_ALL_INFO 기본 및 보조 데이터베이스 정보가 더하기: ODBCTrans 격리

*lpszName*<br/>
이름별 조회에 대 한 작업 영역 개체의 이름입니다. 이름은 최대 14 자까지를 사용 하 여 새 작업 영역 개체의 고유 이름을 지정 하는 문자열입니다.

### <a name="remarks"></a>설명

반환 되는 정보에 대 한 *wkspcinfo*를 참조 합니다 [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) 구조입니다. 이 구조에 대 한 설명에서 위에 나열 된 정보 항목에 해당 하는 멤버가 *dwInfoOptions*합니다. 한 수준 정보를 요청도 이전 수준에 대 한 정보를 얻을 수 있습니다.

##  <a name="idle"></a>  CDaoWorkspace::Idle

호출 `Idle` 집중적인 데이터 처리 때문에 최신 상태가 아닐 수 있는 백그라운드 작업을 수행할 수 있는 기회를 사용 하 여 데이터베이스 엔진을 제공 합니다.

```
static void PASCAL Idle(int nAction = dbFreeLocks);
```

### <a name="parameters"></a>매개 변수

*nAction*<br/>
유휴 처리 하는 동안 수행할 작업입니다. 유효한 작업은 현재 `dbFreeLocks`합니다.

### <a name="remarks"></a>설명

없는 충분 한 백그라운드 처리 시간 레코드 집합에서 모든 레코드를 최신 상태로 유지 하는 다중 사용자, 멀티태스킹 환경에서 더욱 그렇습니다.

> [!NOTE]
>  호출 `Idle` Microsoft Jet 데이터베이스 엔진의 버전 3.0 사용 하 여 만든 데이터베이스를 사용 하 여 필요 하지 않습니다. 사용 하 여 `Idle` 이전 버전을 사용 하 여 만든 데이터베이스에 대해서만 합니다.

일반적으로 읽기 잠금이 해제 되 고 로컬 다이너셋 형식 레코드 집합 개체의 데이터는 마우스 움직임 등 다른 동작이 발생 하는 경우에 업데이트 됩니다. 주기적으로 호출 하는 경우 `Idle`, 백그라운드 처리를 해제 하 여 작업을 처리 하는 시간으로 데이터베이스 엔진에 읽기 잠금이 불필요 한를 제공 합니다. 지정 된 `dbFreeLocks` 상수 인수로 서 모든 읽기 잠금이 해제 될 때까지 처리를 지연 합니다.

이 멤버 함수는 응용 프로그램의 여러 인스턴스 실행 하지 않는 단일 사용자 환경의 필요 하지 않습니다. `Idle` 메모리의 잠금을 해제 하는 디스크에 플러시하는 데이터베이스 엔진이 하므로 멤버 함수를 다중 사용자 환경에서 성능이 향상 됩니다. 트랜잭션의 작업 포함 하 여 읽기 잠금을 해제할 수도 있습니다.

관련된 내용은 DAO 도움말의 "유휴 메서드" 항목을 참조 합니다.

##  <a name="isopen"></a>  CDaoWorkspace::IsOpen

확인 하려면이 멤버 함수를 호출 하는지 여부를 `CDaoWorkspace` 개체가 열려-즉, 여부는 MFC 개체가 초기화 되었는지를 호출 하 여 [엽니다](#open) 호출이 나 [만들기](#create)합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 작업 영역 개체가 열려 있습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

멤버의 모든 열린 상태에 있는 작업 영역의 함수 호출 수 있습니다.

##  <a name="m_pdaoworkspace"></a>  CDaoWorkspace::m_pDAOWorkspace

기본 DAO workspace 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

기본 DAO 개체에 대 한 액세스를 직접 필요한 경우이 데이터 멤버를 사용 합니다. 이 포인터를 통해 DAO 개체의 인터페이스를 호출할 수 있습니다.

DAO 개체에 직접 액세스 하는 방법에 대 한 내용은 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.

##  <a name="open"></a>  CDaoWorkspace::Open

DAO의 기본 작업 영역과 연결 된 작업 영역 개체를 명시적으로 열립니다.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
열려는 DAO workspace 개체의 이름-최대 14 자까지를 사용 하 여 고유 하 게 작업 영역 이름을 지정 하는 문자열입니다. NULL을 명시적으로 기본 작업 영역을 열고 기본값을 그대로 적용 합니다. 명명 요구 사항에 대해서는 *lpszName* 에 대 한 매개 변수 [만들기](#create)합니다. 관련된 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

### <a name="remarks"></a>설명

생성 한 후을 `CDaoWorkspace` 개체를 다음 중 하나를 수행 하려면이 멤버 함수를 호출 합니다.

- 기본 작업 영역을 명시적으로 열어야 합니다. NULL을 전달 *lpszName*합니다.

- 기존 `CDaoWorkspace` 개체를 이름으로 작업 영역 컬렉션의 멤버입니다. 기존 작업 영역 개체에 대 한 유효한 이름을 전달 하세요.

`Open` 열린 상태를 작업 영역 개체를 넣고 이미 응용 프로그램에 대 한 초기화 되지 않은 경우에 데이터베이스 엔진을 초기화 합니다.

하지만 많은 `CDaoWorkspace` 작업 영역이 열린 후에 함수를 호출할 수는 멤버를 생성 한 후 데이터베이스 엔진에서 작동 되는 다음 멤버 함수를 사용할 수는 C++ 개체 를호출하기전에`Open`:

||||
|-|-|-|
|[만들기](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|
|[GetIniPath](#getinipath)|[Idle](#idle)|[SetIniPath](#setinipath)|
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|

##  <a name="repairdatabase"></a>  CDaoWorkspace::RepairDatabase

Microsoft Jet 데이터베이스 엔진에 액세스 하는 손상된 된 데이터베이스를 복구 하는 경우이 멤버 함수를 호출 합니다.

```
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
경로 파일 이름을 기존 Microsoft Jet 엔진에 대 한 데이터베이스 파일입니다. 경로 생략 하면 현재 디렉터리만 검색 됩니다. 네트워크 경로 시스템에서 일관 된 명명 규칙 (UNC)를 지 원하는 경우 같은 지정할 수도 있습니다. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB 합니다. MDB "로 설정 합니다. (때문에 경로 문자열에 필요한 이중 백슬래시 "\\" 됩니다는 C++ 문자를 이스케이프 합니다.)

### <a name="remarks"></a>설명

지정한 데이터베이스를 닫아야 *lpszName* 복구 하기 전에 합니다. 다중 사용자 환경에서 다른 사용자가 사용할 수 없습니다 *lpszName* 이 복구 하는 동안에 열입니다. 하는 경우 *lpszName* 닫혀 있지 않으면 사용할 수 없거나 단독 사용을 위해 오류가 발생 합니다.

이 멤버 함수는 불완전 한 쓰기 작업에서 손상 되었을 가능성이 있는으로 표시 된 데이터베이스를 복구 하려고 합니다. Microsoft Jet 데이터베이스 엔진을 사용 하 여 응용 프로그램 전원 중단 또는 컴퓨터 하드웨어 문제로 인해 예기치 않게 닫힐 경우 발생할 수 있습니다. 호출 및 작업을 완료 하는 경우는 [닫기](../../mfc/reference/cdaodatabase-class.md#close) 이거나 멤버 함수는 일반적인 방법으로 응용 프로그램을 종료, 데이터베이스는 손상 되었을 가능성이 있는으로으로 표시할 수 없습니다.

> [!NOTE]
>  데이터베이스를 복구한 후 것도 사용 하 여 압축 하는 것이 좋습니다 합니다 [CompactDatabase](#compactdatabase) 멤버 함수는 파일을 조각 모음 및 디스크 공간을 복구 합니다.

데이터베이스를 복구 하는 방법에 대 한 자세한 내용은 DAO 도움말의 "것 이었습니다 메서드" 항목을 참조 하세요.

##  <a name="rollback"></a>  CDaoWorkspace::Rollback

현재 트랜잭션을 종료 하 고 트랜잭션이 시작 되기 전에 해당 조건을를 작업 영역에서 모든 데이터베이스를 복원 하려면이 멤버 함수를 호출 합니다.

```
void Rollback();
```

### <a name="remarks"></a>설명

> [!CAUTION]
>  하나의 작업 영역 개체 내에서 트랜잭션은 항상 작업 영역에 전역 이며 하나의 데이터베이스 또는 레코드 집합에 제한 되지 않습니다. 둘 이상의 데이터베이스 또는 트랜잭션 작업 영역 내 레코드 집합에 대 한 작업을 수행 하는 경우 `Rollback` 모든 해당 데이터베이스 및 레코드 집합에 대 한 모든 작업을 복원 합니다.

작업 영역 개체를 저장 하거나 보류 중인 모든 트랜잭션이 롤백 하지 않고 닫으면 트랜잭션은 자동으로 롤백됩니다. 호출 하는 경우 [CommitTrans](#committrans) 하거나 `Rollback` 첫 번째 호출 하지 않고 [BeginTrans](#begintrans), 오류가 발생 합니다.

> [!NOTE]
>  트랜잭션을 시작 하는 경우 데이터베이스 엔진 워크스테이션에서 TEMP 환경 변수로 지정 된 디렉터리에 보관 파일에서 해당 작업을 기록 합니다. 데이터베이스 엔진 MFC throw 하면 트랜잭션 로그 파일을 임시 드라이브에 사용 가능한 저장소 할당량을 하는 경우는 `CDaoException` (DAO 오류 2004). 이 시점에서 호출 하는 경우 `CommitTrans`, 무제한 작업으로 커밋됩니다 하지만 나머지 완료 되지 않은 작업이 손실 되 고 작업을 다시 시작 해야 합니다. 호출 `Rollback` 트랜잭션 로그를 해제 하 고 트랜잭션에서 모든 작업이 롤백됩니다.

##  <a name="setdefaultpassword"></a>  CDaoWorkspace::SetDefaultPassword

데이터베이스 엔진에 특정 암호 없이 작업 영역 개체를 만들 때 사용 하는 기본 암호를 설정 하려면이 멤버 함수를 호출 합니다.

```
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```

### <a name="parameters"></a>매개 변수

*lpszPassword*<br/>
기본 암호입니다. 암호는 최대 14 자까지 가능 하며 ASCII 0 (null)를 제외한 모든 문자를 포함할 수 있습니다. 암호는 대소문자를 구분합니다.

### <a name="remarks"></a>설명

설정 하는 기본 암호는 호출 후 만든 새 작업 영역에 적용 됩니다. 후속 작업 영역을 만들면 필요가 없습니다에서 암호를 지정 하는 [만들기](#create) 호출 합니다.

이 멤버 함수를 사용 합니다.

1. 생성을 `CDaoWorkspace` 개체를 호출 하지 마십시오 있지만 `Create`합니다.

1. 호출 `SetDefaultPassword` 을 원하는 경우 [SetDefaultUser](#setdefaultuser)합니다.

1. 호출 `Create` 이 workspace 개체 또는 이후의 조건은 하지 않고 암호를 지정 합니다.

기본적으로 DefaultUser 속성 "admin"으로 설정 되 고 해야 속성을 빈 문자열 ("").

보안에 대 한 자세한 DAO 도움말의 "권한 속성" 항목을 참조 하세요. 관련된 정보에 대 한 "해야 속성" 및 DAO 도움말의 "DefaultUser Property" 항목을 참조 합니다.

##  <a name="setdefaultuser"></a>  CDaoWorkspace::SetDefaultUser

특정 사용자 이름 없이 작업 영역 개체를 만들 때 데이터베이스 엔진에 사용 되는 기본 사용자 이름을 설정 하려면이 멤버 함수를 호출 합니다.

```
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```

### <a name="parameters"></a>매개 변수

*lpszDefaultUser*<br/>
기본 사용자 이름입니다. 사용자 이름 수 1 ~ 20 자 길이 여야 하며 영문자, 악센트 부호가 있는 문자, 숫자, 공백 및 기호를 제외 하 고 포함: "(따옴표 포함), / (슬래시), \ (백슬래시) \[ \] (대괄호): (콜론), &#124; ( 파이프), \< (작은-기호), > (큰-기호), + (더하기 기호) = (같음 기호); (세미콜론), (쉼표), (물음표) \* (별표)를 앞에 공백 및 제어 문자 (ASCII 00 ASCII 31). 관련된 내용은 DAO 도움말의 "사용자 이름 속성" 항목을 참조 합니다.

### <a name="remarks"></a>설명

설정 하는 기본 사용자 이름은 호출 후 만든 새 작업 영역에 적용 됩니다. 후속 작업 영역을 만든 경우에 사용자 이름을 지정 필요가 없습니다 합니다 [만들기](#create) 호출 합니다.

이 멤버 함수를 사용 합니다.

1. 생성을 `CDaoWorkspace` 개체를 호출 하지 마십시오 있지만 `Create`합니다.

1. 호출 `SetDefaultUser` 을 원하는 경우 [SetDefaultPassword](#setdefaultpassword)합니다.

1. 호출 `Create` 이 workspace 개체 또는 이후의 조건은 없이 사용자 이름을 지정 합니다.

기본적으로 DefaultUser 속성 "admin"으로 설정 되 고 해야 속성을 빈 문자열 ("").

관련된 정보에 대 한 "DefaultUser 속성" 및 DAO 도움말에서 "해야 Property" 항목을 참조 합니다.

##  <a name="setinipath"></a>  CDaoWorkspace::SetIniPath

Microsoft Jet 데이터베이스 엔진에 대 한 Windows 레지스트리 설정의 위치를 지정 하려면이 멤버 함수를 호출 합니다.

```
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```

### <a name="parameters"></a>매개 변수

*lpszRegistrySubkey*<br/>
Microsoft Jet 데이터베이스 엔진 설정 또는 설치할 수 있는 ISAM 데이터베이스에 필요한 매개 변수 위치에 대 한 Windows 레지스트리 하위 키의 이름을 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

호출 `SetIniPath` 특수 한 설정을 지정 해야 하는 경우에 합니다. 자세한 내용은 DAO 도움말의 "IniPath Property" 항목을 참조 하세요.

> [!NOTE]
>  호출 `SetIniPath` 응용 프로그램 설치 중 되지 경우 응용 프로그램을 실행 합니다. `SetIniPath` 모든 작업 영역, 데이터베이스 또는 레코드 집합;을 열기 전에 호출 해야 합니다. 그렇지 않은 경우 MFC는 예외가 throw 됩니다.

사용자가 제공한 레지스트리 설정을 사용 하 여 데이터베이스 엔진을 구성 하려면이 메커니즘을 사용할 수 있습니다. 이 특성의 범위는 응용 프로그램에 제한 되 고 응용 프로그램을 다시 시작 하지 않고 변경할 수 없습니다.

##  <a name="setisolateodbctrans"></a>  CDaoWorkspace::SetIsolateODBCTrans

작업 영역에 대 한 DAO IsolateODBCTrans 속성의 값을 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```

### <a name="parameters"></a>매개 변수

*bIsolateODBCTrans*<br/>
ODBC 트랜잭션 격리를 시작 하려는 경우 TRUE를 전달 합니다. ODBC 트랜잭션 격리를 중지 하려는 경우 FALSE를 전달 합니다.

### <a name="remarks"></a>설명

경우에 따라 같은 ODBC 데이터베이스에서 보류 중인 여러 동시 트랜잭션이 하도록 해야 합니다. 이 작업을 수행 하려면 각 트랜잭션에 대 한 별도 작업 영역을 열려면 해야 합니다. 각 작업 영역 데이터베이스에는 자체 ODBC 연결 수 있지만,이 경우 시스템 성능이 저하 됩니다. 트랜잭션 격리에 일반적으로 필요 하지 않으므로 기본적으로 ODBC 연결 같은 사용자가 연 여러 workspace 개체에서 공유 됩니다.

Microsoft SQL Server와 같은 일부 ODBC 서버에서는 단일 연결에서 동시 트랜잭션을 허용 하지 않습니다. 이러한 데이터베이스에 대해 보류 중인 한 번에 둘 이상의 트랜잭션 해야 할 경우 IsolateODBCTrans 속성을 TRUE로 설정 각 작업 영역에서 열면 즉시 합니다. 이렇게 하면 각 작업 영역에 대 한 별도 ODBC 연결 됩니다.

##  <a name="setlogintimeout"></a>  CDaoWorkspace::SetLoginTimeout

작업 영역에 대 한 DAO LoginTimeout 속성의 값을 설정 하려면이 멤버 함수를 호출 합니다.

```
static void PASCAL SetLoginTimeout(short nSeconds);
```

### <a name="parameters"></a>매개 변수

*nSeconds*<br/>
ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수입니다.

### <a name="remarks"></a>설명

이 값은 ODBC 데이터베이스에 로그인 하려고 할 때 오류가 발생 하기 전에 시간 (초) 수를 나타냅니다. LoginTimeout 기본값은 20 초입니다. LoginTimeout을 0으로 설정 하는 경우 시간 제한 없이 발생 하 고 데이터 소스와의 통신 응답 중지 될 수 있습니다.

네트워크 오류로 인해 연결이 실패할 수 있습니다 Microsoft SQL Server와 같은 ODBC 데이터베이스에 로그인 하려는 경우 서버가 실행 중이 아니므로 또는 합니다. 기본값에 대 한 20 초를 위해 대기 중인 연결 하는 대신 데이터베이스 엔진 오류를 생성 하기 전에 대기 하는 시간을 지정할 수 있습니다. 서버에 로그온 할 외부 서버 데이터베이스에서 쿼리를 실행 하는 등의 다른 이벤트의 숫자의 일부분으로 암시적으로 발생 합니다. 시간 제한 값을 LoginTimeout 속성의 현재 설정에 따라 결정 됩니다.

관련된 내용은 DAO 도움말의 "LoginTimeout Property" 항목을 참조 합니다.

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
