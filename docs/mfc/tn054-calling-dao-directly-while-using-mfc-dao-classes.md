---
title: 'TN054: MFC DAO 클래스를 사용 하면서 직접 DAO 호출'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.dao
helpviewer_keywords:
- MFC, DAO and
- passwords [MFC], calling DAO
- security [MFC], DAO
- DAO (Data Access Objects), calling directly
- DAO (Data Access Objects), security
- security [MFC]
- TN054
- DAO (Data Access Objects), and MFC
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
ms.openlocfilehash: 938381f55b598911b69bb25bf7af576dfdfb2e4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399657"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: MFC DAO 클래스를 사용 하면서 직접 DAO 호출

> [!NOTE]
> 시각적 개체 C++ 환경 및 마법사 지원 하지 않습니다 DAO (하지만 DAO 클래스에 포함 되어 있으며 계속 사용할 수 있습니다). 사용 하는 것이 좋습니다 [OLE DB Templates](../data/oledb/ole-db-templates.md) 하거나 [ODBC 및 MFC](../data/odbc/odbc-and-mfc.md) 새 프로젝트에 대 한 합니다. DAO 기존 응용 프로그램 유지 관리에 사용 해야 합니다.

MFC DAO 데이터베이스 클래스를 사용할 때 DAO를 직접 사용 하는 데 필요한 한 상황이 있을 수 있습니다. 일반적으로이 경우 되지 않지만 MFC는 MFC 클래스를 직접 DAO 호출으로 결합 하는 경우 만드는 대 한 직접 DAO 호출 간단한를 용이 하 게 몇 가지 도우미 메커니즘을 제공 합니다. 직접 DAO 만드는 DAO MFC 관리 되는 개체의 메서드를 호출 하는 코드 몇 줄만 요구 해야 합니다. 만들기 및 DAO 개체를 사용 해야 하는 경우 *하지* MFC에서 관리 해야 실제로 호출 하 여 좀 더 많은 작업을 수행 `Release` 개체에 있습니다. 이 기술 노트에 직접 DAO 호출 하려는 경우, MFC 도우미를 하는 데 수행할 수 있는 작업 및 DAO OLE 인터페이스를 사용 하는 방법을 설명 합니다. 마지막으로,이 DAO 보안 기능에 대 한 직접 DAO 호출 하는 방법을 보여 주는 몇 가지 샘플 함수를 제공 합니다.

## <a name="when-to-make-direct-dao-calls"></a>직접 DAO 호출을 수행 하는 경우

컬렉션을 새로 고칠 수 해야 하는 경우 직접 DAO 호출에 대 한 가장 일반적인 상황에서 발생 하거나 MFC에서 래핑되지 기능을 구현 하는 경우. MFC에 의해 노출 되지 않는 가장 중요 한 기능에는 보안입니다. 보안 기능을 구현 하려는 경우에 DAO 사용자 및 그룹 개체를 직접 사용 하는 것이 해야 합니다. 보안 외에도 기능이 몇 가지 다른 DAO MFC에서 지원 되지 않습니다. 여기에 레코드 집합 복제 및 데이터베이스 복제 기능 뿐만 아니라 DAO로 몇 가지 추가 기능이 포함 됩니다.

## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>DAO MFC의 구현에 대 한 간략 한 개요

DAO 사소한 부분에 걱정할 필요가 없습니다 있도록 다양 한 세부 정보를 처리 하 여 쉽게 사용 하는 DAO 하면 MFC의 줄 바꿈 합니다. OLE, 생성 및 관리 DAO 개체 (특히: 컬렉션 개체)를 검사 하 고 강력한 형식의 간단한 인터페이스를 제공 하는 오류를 초기화 하는 여기에 (없습니다 **VARIANT** 또는 `BSTR` 인수)입니다. 직접 DAO 호출 하 고 이러한 기능을 활용할 수 있습니다. 코드 해야 모든 호출이 `Release` 직접 DAO에서 생성 된 모든 개체에 대 한 호출 및 *하지* MFC에서 내부적으로 사용할 수 있는 인터페이스 포인터를 수정 합니다. 예를 들어 수정 하지 마십시오 합니다 *m_pDAORecordset* 개방적이 고 소속 `CDaoRecordset` 잘 모르는 경우 개체 *모든* 내부 결과입니다. 그러나 사용할 수 있습니다 합니다 *m_pDAORecordset* 필드 컬렉션을 가져옵니다에 직접 DAO 호출 하는 인터페이스입니다. 이 경우에 *m_pDAORecordset* 멤버는 수정할 수 없습니다. 호출 하기만 하면 `Release` 개체 작업이 완료 되 면 필드 컬렉션 개체에서.

## <a name="description-of-helpers-to-make-dao-calls-easier"></a>DAO 있도록 도우미 설명은 쉽게 호출

DAO를 쉽게 호출할 수 있도록 하는 도우미는 MFC DAO 데이터베이스 클래스에서 내부적으로 사용 되는 동일한 도우미입니다. 이러한 도우미 예상 되는 오류를 확인 하 고 필요한 경우 적절 한 예외를 throw 디버그 출력을 기록 하는 직접 DAO 호출을 수행할 때 반환 코드를 확인 하는 데 사용 됩니다. 두 개의 기본 도우미 함수 및 이러한 두 도우미 중 하나에 매핑되는 4 개의 매크로가 있습니다. 가장 하는 코드를 단순히 읽을 수 있습니다. 참조 **DAO_CHECK**를 **DAO_CHECK_ERROR**합니다 **DAO_CHECK_MEM**, 및 **DAO_TRACE** AFXDAO에서. 매크로 확인 하 고 볼 H **AfxDaoCheck** 하 고 **AfxDaoTrace** DAOCORE에서. CPP 합니다.

## <a name="using-the-dao-ole-interfaces"></a>DAO OLE 인터페이스를 사용 하 여

DAO 개체 계층의 각 개체에 대 한 OLE 인터페이스 DBDAOINT 헤더 파일에 정의 됩니다. Visual Studio.NET 2003\VC7\include \Program Files\Microsoft 디렉터리에 있는 H 이러한 인터페이스는 전체 DAO 계층을 조작할 수 있는 메서드를 제공 합니다.

조작 해야 DAO 인터페이스의 메서드 중 대부분을 `BSTR` 개체 (길이 접두사가 문자열 OLE 자동화에 사용). 합니다 `BSTR` 일반적으로 개체 내에서 캡슐화 되는 **VARIANT** 데이터 형식입니다. MFC 클래스 `COleVariant` 에서 상속 되는 **VARIANT** 데이터 형식입니다. 여부 ANSI 또는 유니코드에 대 한 프로젝트를 빌드할를 따라 DAO 인터페이스 돌아갑니다 ANSI 또는 유니코드 `BSTR`s입니다. 가져옵니다 확인 하는 과정의 DAO 인터페이스에 대 한 두 매크로 V_BSTR 및 V_BSTRT에 유용 합니다.는 `BSTR` 예상 된 유형이 있습니다.

V_BSTR 추출 합니다 *bstrVal* 의 멤버는 `COleVariant`합니다. 콘텐츠를 전달 해야 하는 경우에 일반적으로이 매크로는 `COleVariant` DAO 인터페이스의 메서드에 있습니다. 다음 코드는 선언과 V_BSTR 매크로 활용 하는 DAO DAOUser 인터페이스의 두 가지 방법에 대 한 실제 사용을 보여 줍니다.

```cpp
COleVariant varOldName;
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

// Code to assign pUser to a valid value omitted
DAOUser *pUser = NULL;

// These method declarations were taken from DBDAOINT.H
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;

DAO_CHECK(pUser->get_Name(&V_BSTR (&varOldName)));
DAO_CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```

합니다 `VT_BSTRT` 에 지정 된 인수를 `COleVariant` 위의 생성자는 ANSI 되도록 보장 `BSTR` 에 `COleVariant` 는 ANSI 버전의 응용 프로그램 및 유니코드를 작성 하는 경우 `BSTR` 의 유니코드 버전에 대 한 응용 프로그램입니다. DAO에 필요한 것입니다.

ANSI 또는 유니코드 다른 매크로 V_BSTRT, 추출 *bstrVal* 소속 `COleVariant` 빌드 (ANSI 또는 유니코드) 형식에 따라 합니다. 다음 코드를 추출 하는 방법에 설명 합니다 `BSTR` 에서 값을 `COleVariant` 에 `CString`:

```cpp
COleVariant varName(_T("MyName"), VT_BSTRT);
CString str = V_BSTRT(&varName);
```

다른 방법에 저장 되는 다른 형식을 함께 V_BSTRT 매크로 `COleVariant`, DAOVIEW 샘플에 설명 되어 있습니다. 특히이 변환에서 수행 된 `CCrack::strVARIANT` 메서드. 이 메서드를 돕고 가능한 경우 변환의 값을 `COleVariant` 의 인스턴스로 `CString`합니다.

## <a name="simple-example-of-a-direct-call-to-dao"></a>직접 DAO 호출의 간단한 예

기본 DAO 컬렉션 개체를 새로 고치는 데 필요한 경우 상황이 발생할 수 있습니다. 일반적으로 필요한 안이 이지만 간단한 프로시저를 해야 하는 경우. 새로 고쳐져 야 컬렉션 필요할 경우의 예에는 새 테이블 정의 만드는 여러 사용자를 사용 하 여 다중 사용자 환경에서 작동 하는 경우입니다. 이 경우 tabledefs 컬렉션 부실 해질 수 있습니다. 컬렉션을 새로 고치려면 하면 호출 된 `Refresh` 오류에 대 한 특정 컬렉션 개체의 메서드:

```cpp
DAO_CHECK(pMyDaoDatabase->m_pDAOTableDefs->Refresh());
```

현재 모든 DAO 컬렉션 개체 인터페이스는 MFC DAO 데이터베이스 클래스로 변경의 문서화 되지 않은 구현 세부 정보를 참고 합니다.

## <a name="using-dao-directly-for-dao-security-features"></a>DAO 보안 기능에 대 한 직접 DAO를 사용 하 여

MFC DAO 데이터베이스 클래스에서 DAO 보안 기능을 래핑하지 마십시오. DAO 일부 DAO 보안 기능을 사용 하는 인터페이스의 메서드를 호출 해야 합니다. 다음 함수는 시스템 데이터베이스를 설정 하 고 사용자의 암호를 변경 합니다. 이 함수는 세 가지 다른 함수를 정의 된 이후에 호출 합니다.

```cpp
void ChangeUserPassword()
{
    // Specify path to the Microsoft Access *// system database
    CString strSystemDB =
        _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

    // Set system database before MFC initilizes DAO
    // NOTE: An MFC module uses only one instance
    // of a DAO database engine object. If you have
    // called a DAO object in your application prior
    // to calling the function below, you must call
    // AfxDaoTerm to destroy the existing database
    // engine object. Otherwise, the database engine
    // object already in use will be reused, and setting
    // a system datbase will have no effect.
    //
    // If you have used a DAO object prior to calling
    // this function it is important that DAO be
    // terminated with AfxDaoTerm since an MFC
    // module only gets one copy of the database engine
    // and that engine will be reused if it hasn't been
    // terminated. In other words, if you do not call
    // AfxDaoTerm and there is currently a database
    // initialized, setting the system database will
    // have no effect.
    SetSystemDB(strSystemDB);

    // User name and password manually added
    // by using Microsoft Access
    CString strUserName = _T("NewUser");
    CString strOldPassword = _T("Password");
    CString strNewPassword = _T("NewPassword");

    // Set default user so that MFC will be able
    // to log in by default using the user name and
    // password from the system database
    SetDefaultUser(strUserName, strOldPassword);

    // Change the password. You should be able to
    // call this function from anywhere in your
    // MFC application
    ChangePassword(strUserName, strOldPassword, strNewPassword);

    // ...
}
```

다음 네 개의 예에서는 설명 하는 방법.

- 시스템 DAO 데이터베이스 설정 (합니다. MDW 파일)입니다.

- 기본 사용자 이름 및 암호를 설정 합니다.

- 사용자의 암호를 변경 합니다.

- 암호를 변경를 합니다. MDB 파일입니다.

### <a name="setting-the-system-database"></a>시스템 데이터베이스를 설정합니다.

다음은 응용 프로그램에서 사용 될 시스템 데이터베이스를 설정 하는 샘플 함수입니다. 모든 다른 DAO를 호출 하기 전에이 함수를 호출 해야 합니다.

```cpp
// Set the system database that the
// DAO database engine will use

void SetSystemDB(CString& strSystemMDB)
{
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

    // Initialize DAO for MFC
    AfxDaoInit();
    DAODBEngine* pDBEngine = AfxDaoGetEngine();

    ASSERT(pDBEngine != NULL);

    // Call put_SystemDB method to set the *// system database for DAO engine
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));
}
```

### <a name="setting-the-default-user-and-password"></a>기본 사용자 이름 및 암호를 설정합니다.

기본 사용자 및 시스템 데이터베이스에 대 한 암호를 설정 하려면 다음 함수를 사용 합니다.

```cpp
void SetDefaultUser(CString& strUserName,
    CString& strPassword)
{
    COleVariant varUserName(strUserName, VT_BSTRT);
    COleVariant varPassword(strPassword, VT_BSTRT);

    DAODBEngine* pDBEngine = AfxDaoGetEngine();
    ASSERT(pDBEngine != NULL);

    // Set default user:
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

    // Set default password:
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));
}
```

### <a name="changing-a-users-password"></a>사용자의 암호를 변경합니다.

사용자의 암호를 변경 하려면 다음 함수를 사용 합니다.

```cpp
void ChangePassword(CString &strUserName,
    CString &strOldPassword,
    CString &strNewPassword)
{
    // Create (open) a workspace
    CDaoWorkspace wsp;
    CString strWspName = _T("Temp Workspace");

    wsp.Create(strWspName, strUserName, strOldPassword);
    wsp.Append();

    // Determine how many objects there are *// in the Users collection
    short nUserCount;
    short nCurrentUser;
    DAOUser *pUser = NULL;
    DAOUsers *pUsers = NULL;

    // Side-effect is implicit OLE AddRef()
    // on DAOUser object:
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

    // Side-effect is implicit OLE AddRef()
    // on DAOUsers object
    DAO_CHECK(pUsers->getcount(&nUserCount));

    // Traverse through the list of users
    // and change password for the userid
    // used to create/open the workspace
    for(nCurrentUser = 0; nCurrentUser <nUserCount; nCurrentUser++)
    {
        COleVariant varIndex(nCurrentUser, VT_I2);
        COleVariant varName;

        // Retrieve information for user nCurrentUser
        DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

        // Retrieve name for user nCurrentUser
        DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

        CString strTemp = V_BSTRT(&varName);

        // If there is a match, change the password
        if (strTemp == strUserName)
        {
            COleVariant varOldPwd(strOldPassword, VT_BSTRT);
            COleVariant varNewPwd(strNewPassword, VT_BSTRT);

            DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd),
                V_BSTR(&varNewPwd)));

            TRACE("\t Password is changed\n");
        }
    }
    // Clean up: decrement the usage count
    // on the OLE objects
    pUser->Release();
    pUsers->Release();
    wsp.Close();
}
```

### <a name="changing-the-password-of-an-mdb-file"></a>암호를 변경 하는 합니다. MDB 파일

암호를 변경 하는 합니다. MDB 파일에서 다음 함수를 사용 합니다.

```cpp
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)
{
    CDaoDatabase db;
    CString strConnect(_T(";pwd="));

    // the database must be opened as exclusive
    // to set a password
    db.Open(pDB, TRUE, FALSE, strConnect + pszOldPassword);

    COleVariant NewPassword(pszNewPassword, VT_BSTRT),
                OldPassword(pszOldPassword, VT_BSTRT);

    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword),
        V_BSTR(&NewPassword)));

    db.Close();
}
```

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
