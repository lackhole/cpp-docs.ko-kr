---
title: 데이터베이스 매크로 및 전역
ms.date: 11/04/2016
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
ms.openlocfilehash: 47a1bb434801c24ab8eee048d9ef8f93793101cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323192"
---
# <a name="database-macros-and-globals"></a>데이터베이스 매크로 및 전역

매크로 및 전역 변수 아래에 나열 된 ODBC 기반 데이터베이스 응용 프로그램에 적용 됩니다. DAO 기반 응용 프로그램을 사용 하 여 사용 되지 않습니다.

MFC 4.2에서 매크로 하기 전에 `AFX_SQL_ASYNC` 및 `AFX_SQL_SYNC` 지정한 비동기 작업 생성 시간을 다른 프로세스 수입니다. MFC ODBC 클래스에는 동기 작업만 사용 되므로 변경 이러한 매크로의 구현은 MFC 4.2를 사용 하 여 시작 합니다. 매크로 `AFX_ODBC_CALL` MFC 4.2를 합니다.

### <a name="database-macros"></a>데이터베이스 매크로

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|반환 하는 ODBC API 함수 호출 `SQL_STILL_EXECUTING`합니다. `AFX_ODBC_CALL` 반복적으로 함수를 호출할 때까지 더 이상 반환 `SQL_STILL_EXECUTING`합니다.|
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|반환 하지 않는 ODBC API 함수 호출 `SQL_STILL_EXECUTING`합니다.|

### <a name="database-globals"></a>데이터베이스 전역

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|MFC에 동적으로 연결 된 기본 MFC DLL에 대 한 데이터베이스 지원을 추가 합니다.|
|[AfxGetHENV](#afxgethenv)|MFC에서 사용 중인 ODBC 환경 핸들을 검색합니다. 직접 ODBC 호출에서이 핸들을 사용할 수 있습니다.|

## <a name="afxdbinitmodule"></a> AfxDbInitModule

MFC에 동적으로 연결 된 기본 MFC DLL에서 MFC 데이터베이스 (또는 DAO) 지원, 기본 MFC DLL의에이 함수에 대 한 호출 추가 `CWinApp::InitInstance` MFC를 초기화 하는 함수에 DLL 데이터베이스입니다.

### <a name="syntax"></a>구문

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>설명

이 호출은 기본 클래스를 호출 하기 전에 나 서 DLL MFC 데이터베이스에 액세스 하는 코드를 추가 해야 합니다. MFC DLL 데이터베이스가 MFC 확장 DLL; MFC 확장 DLL에 유선 가져오려면 하려면에서를 `CDynLinkLibrary` 체인을 생성 하도록 해야 합니다는 `CDynLinkLibrary` 은 사용 하는 모든 모듈의 컨텍스트에서 개체입니다. `AfxDbInitModule` 만듭니다는 `CDynLinkLibrary` 에 유선 가져옵니다 있도록 기본 MFC DLL의 컨텍스트에서 개체를 `CDynLinkLibrary` 기본 MFC DLL의 체인 개체입니다.

### <a name="requirements"></a>요구 사항

**헤더:** \<afxdll_.h >

##  <a name="afx_odbc_call"></a>  AFX_ODBC_CALL

이 매크로 사용 하 여 반환할 수 있는 모든 ODBC API 함수를 호출 `SQL_STILL_EXECUTING`합니다.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>매개 변수

*SQLFunc*<br/>
ODBC API 함수입니다. ODBC API 함수에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="remarks"></a>설명

`AFX_ODBC_CALL` 반복적으로 함수를 호출 될 때까지 더 이상 반환 `SQL_STILL_EXECUTING`합니다.

호출 하기 전에 `AFX_ODBC_CALL`, 변수를 선언 해야 `nRetCode`, RETCODE 형식의 합니다.

MFC ODBC 클래스 지금 사용 하 여 동기적 처리만는 note 합니다. 비동기 작업을 수행 하려면 ODBC API 함수를 호출 해야 `SQLSetConnectOption`합니다. 자세한 내용은 "비동기적으로 함수 실행" Windows SDK의 항목을 참조 합니다.

### <a name="example"></a>예제

이 예제에서는 `AFX_ODBC_CALL` 를 호출 하는 `SQLColumns` 테이블에서 명명 된 열 목록을 반환 하는 ODBC API 함수를 `strTableName`입니다. 선언을 확인 하십시오 `nRetCode` 및 레코드 집합 데이터 멤버 함수에 매개 변수를 전달 하려면 사용 합니다. 또한 예제에 사용 하 여 호출의 결과 확인 `Check`, 클래스의 멤버 함수 `CRecordset`합니다. 변수의 `prs` 에 대 한 포인터를 `CRecordset` 개체를 다른 곳에서 선언 합니다.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

##  <a name="afx_sql_async"></a>  AFX_SQL_ASYNC

이 매크로의 구현은 MFC 4.2에서 변경되었습니다.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>매개 변수

*prs*<br/>
`CRecordset` 개체 또는 `CDatabase` 개체에 대한 포인터입니다. MFC 4.2부터는 이 매개 변수 값이 무시됩니다.

*SQLFunc*<br/>
ODBC API 함수입니다. ODBC API 함수에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="remarks"></a>설명

`AFX_SQL_ASYNC` 매크로 호출 하기만 하면 [AFX_ODBC_CALL](#afx_odbc_call) 무시 합니다 *pr* 매개 변수입니다. MFC 4.2 이전 버전에서, `AFX_SQL_ASYNC`는 `SQL_STILL_EXECUTING`를 반환할 수 있는 ODBC API 함수를 호출하기 위해 사용되었습니다. ODBC API 함수가 `SQL_STILL_EXECUTING`을 반환한 경우, `AFX_SQL_ASYNC`가 `prs->OnWaitForDataSource`를 호출합니다.

> [!NOTE]
>  MFC ODBC 클래스에는 이제 동기적 처리만 사용됩니다. 비동기 작업을 수행 하려면 ODBC API 함수를 호출 해야 `SQLSetConnectOption`합니다. 자세한 내용은 "비동기적으로 함수 실행" Windows SDK의 항목을 참조 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdb.h

##  <a name="afx_sql_sync"></a>  AFX_SQL_SYNC

합니다 `AFX_SQL_SYNC` 매크로 함수를 호출 하기만 하면 `SQLFunc`합니다.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>매개 변수

*SQLFunc*<br/>
ODBC API 함수입니다. 이러한 함수에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="remarks"></a>설명

이 매크로 사용 하 여 반환 하지 것입니다는 ODBC API 함수 호출 `SQL_STILL_EXECUTING`합니다.

호출 하기 전에 `AFX_SQL_SYNC`에 변수를 선언 해야 `nRetCode`, RETCODE 형식의 합니다. 값을 확인할 수 있습니다 `nRetCode` 매크로 호출 후 합니다.

구현의 `AFX_SQL_SYNC` MFC 4.2에서 변경 합니다. 서버 상태를 확인 하는 더 이상 필요 하므로 `AFX_SQL_SYNC` 값을 할당 `nRetCode`합니다. 예를 들어, 호출을 수행 하는 대신

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

할당을 만들 수 있습니다.

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdb.h

##  <a name="afxgethenv"></a>  AfxGetHENV

직접 ODBC 호출에서 반환된 된 핸들을 사용할 수 있지만 핸들을 종료 하거나 핸들을 여전히 유효 하 고 사용할 수 있는 모든 기존 가정 않아야 `CDatabase`-또는 `CRecordset`-파생된 개체가 제거 합니다.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>반환 값

MFC에서 사용 중인 ODBC 환경 핸들입니다. 일 수 있습니다 `SQL_HENV_NULL` 없으면 없습니다 [CDatabase](../../mfc/reference/cdatabase-class.md) 개체 및 0 [CRecordset](../../mfc/reference/crecordset-class.md) 사용 중인 개체입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdb.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
