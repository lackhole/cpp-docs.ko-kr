---
title: CAccessToken 클래스
ms.date: 11/04/2016
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
ms.openlocfilehash: ce5c29c2399fd47bdb1ad0135257b41617094aa9
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503375"
---
# <a name="caccesstoken-class"></a>CAccessToken 클래스

이 클래스는 액세스 토큰에 대 한 래퍼입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAccessToken
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAccessToken::~CAccessToken](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAccessToken::Attach](#attach)|지정 된 액세스 토큰 핸들의 소유권을이 메서드를 호출 합니다.|
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|지정 된 SID에서 사용 되는지 여부를 확인 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|새 가장 액세스 토큰을 생성 하도록이 메서드를 호출 합니다.|
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|새 기본 토큰을 생성 하도록이 메서드를 호출 합니다.|
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|가 나타내는 사용자의 보안 컨텍스트에서 실행 되는 새 프로세스를 만들려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|새로 만들려면이 메서드를 호출 제한 `CAccessToken` 개체입니다.|
|[CAccessToken::Detach](#detach)|액세스 토큰의 소유권을 취소 하려면이 메서드를 호출 합니다.|
|[CAccessToken::DisablePrivilege](#disableprivilege)|권한 사용 하지 않도록 설정 하려면이 메서드는 `CAccessToken` 개체입니다.|
|[CAccessToken::DisablePrivileges](#disableprivileges)|하나 이상의 권한을 사용 하지 않도록 설정 하려면이 메서드는 `CAccessToken` 개체입니다.|
|[CAccessToken::EnablePrivilege](#enableprivilege)|권한 사용 하도록 설정 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::EnablePrivileges](#enableprivileges)|하나 이상의 권한을 사용 하도록 설정 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|반환 하려면이 메서드를 호출 합니다 `CAccessToken` 개체의 기본 DACL입니다.|
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|이 메서드를 호출 합니다 `CAccessToken` 개체를 현재 스레드에 적용에 대 한 액세스 토큰입니다.|
|[CAccessToken::GetGroups](#getgroups)|반환 하려면이 메서드를 호출 합니다 `CAccessToken` 개체의 토큰 그룹입니다.|
|[CAccessToken::GetHandle](#gethandle)|액세스 토큰에 대 한 핸들을 검색 하려면이 메서드를 호출 합니다.|
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|액세스 토큰 가장 수준을 활용 하려면이 메서드를 호출 합니다.|
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|연결 된 로그온 세션 ID를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetLogonSid](#getlogonsid)|연결 된 로그온 SID를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetOwner](#getowner)|연결 된 소유자를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|연결 된 기본 그룹을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetPrivileges](#getprivileges)|연결 된 권한을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetProcessToken](#getprocesstoken)|지정된 프로세스의 액세스 토큰을 사용해서 `CAccessToken`을 초기화하려면 이 메서드를 호출합니다.|
|[CAccessToken::GetProfile](#getprofile)|연결 된 사용자 프로필을 가리키는 핸들을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetSource](#getsource)|소스를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetStatistics](#getstatistics)|연관 된 정보를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|연결 된 터미널 서비스 세션 ID를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetThreadToken](#getthreadtoken)|초기화 하려면이 메서드를 호출 합니다 `CAccessToken` 지정된 된 스레드의에서 토큰을 사용 하 여 합니다.|
|[CAccessToken::GetTokenId](#gettokenid)|연결 된 토큰 ID를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetType](#gettype)|토큰 형식을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::GetUser](#getuser)|연결 된 사용자를 식별 하려면이 메서드는 `CAccessToken` 개체입니다.|
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|연결 된 사용자 프로필을 가리키는 핸들을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::Impersonate](#impersonate)|가장을 할당 하려면이 메서드를 호출 `CAccessToken` 스레드로 합니다.|
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|호출 스레드가 로그온 한 사용자의 보안 컨텍스트를 가장할 수 있도록이 메서드를 호출 합니다.|
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|테스트 하려면이 메서드를 호출 합니다 `CAccessToken` 개체 제한 Sid 목록을 포함 합니다.|
|[CAccessToken::LoadUserProfile](#loaduserprofile)|연결 된 사용자 프로필을 로드 하려면이 메서드는 `CAccessToken` 개체입니다.|
|[CAccessToken::LogonUser](#logonuser)|지정된 된 자격 증명을 사용 하 여 연결 된 사용자에 대 한 로그온 세션을 만들려면이 메서드를 호출 합니다.|
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|초기화 하도록 클라이언트에서 호출을 처리 하는 COM 서버 내에서이 메서드를 호출 합니다 `CAccessToken` COM 클라이언트에서 액세스 토큰입니다.|
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|명명된 된 파이프 초기화를 통해 수행 요청 서버 내에서이 메서드를 호출 합니다 `CAccessToken` 클라이언트에서 액세스 토큰입니다.|
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|초기화는 RPC 클라이언트에서 호출을 처리 하는 서버 내에서이 메서드를 호출 합니다 `CAccessToken` 클라이언트에서 액세스 토큰입니다.|
|[CAccessToken::OpenThreadToken](#openthreadtoken)|가장 수준을 설정 하 고 다음을 초기화 하려면이 메서드는 `CAccessToken` 지정된 된 스레드의에서 토큰을 사용 하 여 합니다.|
|[CAccessToken::PrivilegeCheck](#privilegecheck)|지정된 된 권한 집합에 사용 되는지 여부를 확인 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::Revert](#revert)|가장 토큰을 사용 하는 스레드를 중지 하려면이 메서드를 호출 합니다.|
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|기본값을 설정 하려면이 메서드를 호출의 DACL을 `CAccessToken` 개체입니다.|
|[CAccessToken::SetOwner](#setowner)|소유자를 설정 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|주 그룹을 설정 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.|

## <a name="remarks"></a>설명

[액세스 토큰](/windows/desktop/SecAuthZ/access-tokens) 개체인 프로세스 또는 스레드의 보안 컨텍스트를 설명 하는 Windows 시스템에 로그온 한 각 사용자에 게 할당 됩니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="attach"></a>  CAccessToken::Attach

지정 된 액세스 토큰 핸들의 소유권을이 메서드를 호출 합니다.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>매개 변수

*hToken*<br/>
액세스 토큰 핸들입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 어설션 오류가 발생 하는 경우는 `CAccessToken` 개체에 이미 액세스 토큰의 소유권입니다.

##  <a name="dtor"></a>  CAccessToken::~CAccessToken

소멸자입니다.

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="checktokenmembership"></a>  CAccessToken::CheckTokenMembership

지정 된 SID에서 사용 되는지 여부를 확인 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
에 대 한 참조를 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.

*pbIsMember*<br/>
검사의 결과 수신 하는 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

`CheckTokenMembership` 메서드는 사용자 및 그룹 Sid 액세스 토큰의 SID가 있는지 확인 합니다. SID가 있고 SE_GROUP_ENABLED 특성이 있으면 *pbIsMember* 가 FALSE로 설정 되어에 고 그렇지 않으면 TRUE를 설정 합니다.

디버그 빌드에서 어설션 오류가 발생 하는 경우 *pbIsMember* 유효한 포인터가 아닙니다.

> [!NOTE]
>  `CAccessToken` 하면 가장 토큰과 주 토큰 하지 개체 여야 합니다.

##  <a name="createimpersonationtoken"></a>  CAccessToken::CreateImpersonationToken

가장 액세스 토큰을 생성 하도록이 메서드를 호출 합니다.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pImp*<br/>
새 포인터 `CAccessToken` 개체입니다.

*sil*<br/>
지정 된 [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) 열거 새 토큰 가장 수준을 제공 하는 형식.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

`CreateImpersonationToken` 호출 [DuplicateToken](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) 새 가장 토큰을 만들어야 합니다.

##  <a name="createprimarytoken"></a>  CAccessToken::CreatePrimaryToken

새 기본 토큰을 생성 하도록이 메서드를 호출 합니다.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pPri*<br/>
새 포인터 `CAccessToken` 개체입니다.

*dwDesiredAccess*<br/>
새 토큰에 대 한 요청 된 액세스 권한을 지정합니다. 기본값인 MAXIMUM_ALLOWED, 호출자가 사용할 수 있는 모든 액세스 권한을 요청 합니다. 참조 [액세스 권한 및 액세스 마스크](/windows/desktop/SecAuthZ/access-rights-and-access-masks) 자세한 on 액세스 권한에 대 한 합니다.

*pTokenAttributes*<br/>
에 대 한 포인터를 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 새 토큰의 보안 설명자를 지정 하 고 자식 프로세스 토큰을 상속할 수 있는지 여부를 결정 하는 구조입니다. 하는 경우 *pTokenAttributes* 가 NULL이 고, 토큰에는 기본 보안 설명자를 가져옵니다 핸들을 상속할 수 없습니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

`CreatePrimaryToken` 호출 [DuplicateTokenEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) 새 기본 토큰을 만들어야 합니다.

##  <a name="createprocessasuser"></a>  CAccessToken::CreateProcessAsUser

가 나타내는 사용자의 보안 컨텍스트에서 실행 되는 새 프로세스를 만들려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*pApplicationName*<br/>
모듈에서 실행 하도록 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 매개 변수는 NULL 일 수 없습니다.

*pCommandLine*<br/>
실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*pProcessInformation*<br/>
에 대 한 포인터를 [PROCESS_INFORMATION](/windows/desktop/api/processthreadsapi/ns-processthreadsapi-_process_information) 새 프로세스에 대 한 식별 정보를 수신 하는 구조입니다.

*pStartupInfo*<br/>
에 대 한 포인터를 [STARTUPINFO](/windows/desktop/api/processthreadsapi/ns-processthreadsapi-_startupinfoa) 새 프로세스의 주 창 표시 방법을 지정 하는 구조입니다.

*dwCreationFlags*<br/>
우선 순위 클래스 및 프로세스의 생성을 제어 하는 추가 플래그를 지정 합니다. Win32 함수를 참조 하세요 [createprocessasuser가](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessasusera) 플래그의 목록은 합니다.

*bLoadProfile*<br/>
사용자의 프로필을 사용 하 여 로드 되 고 TRUE 인 경우 [LoadUserProfile](/windows/desktop/api/userenv/nf-userenv-loaduserprofilea)합니다.

*pProcessAttributes*<br/>
에 대 한 포인터를 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 새 프로세스에 대 한 보안 설명자를 지정 하 고 자식 프로세스가 반환된 된 핸들을 상속할 수 있는지 여부를 결정 하는 구조입니다. 하는 경우 *pProcessAttributes* 가 NULL이 고, 프로세스는 기본 보안 설명자를 가져옵니다 핸들을 상속할 수 없습니다.

*pThreadAttributes*<br/>
에 대 한 포인터를 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 새 스레드에 대 한 보안 설명자를 지정 하 고 자식 프로세스가 반환된 된 핸들을 상속할 수 있는지 여부를 결정 하는 구조입니다. 하는 경우 *pThreadAttributes* 가 NULL이 고, 스레드는 기본 보안 설명자를 가져옵니다 핸들을 상속할 수 없습니다.

*bInherit*<br/>
새 프로세스가 호출 프로세스에서 핸들을 상속 되는지 여부를 나타냅니다. TRUE 이면 호출 프로세스에 상속할 수 있는 열린 핸들 각 새 프로세스에 의해 상속 됩니다. 상속 된 핸들에는 원래 핸들으로 동일한 값 및 액세스 권한이 있습니다.

*pCurrentDirectory*<br/>
새 프로세스에 대 한 디렉터리와 현재 드라이브를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 문자열에는 드라이브 문자를 포함 하는 전체 경로 여야 합니다. 이 매개 변수가 NULL 인 경우 새 프로세스 호출 프로세스와 같은 현재 드라이브 및 디렉터리 포함 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

`CreateProcessAsUser` 사용 하는 `CreateProcessAsUser` 나타내는 사용자의 보안 컨텍스트에서 실행 하는 새 프로세스를 만들려는 Win32 함수는 `CAccessToken` 개체입니다. 에 대 한 설명을 참조는 [createprocessasuser가](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessasusera) 대 한 전체 설명은 필요한 매개 변수는 함수입니다.

이 메서드가 성공 하려면에 대 한는 `CAccessToken` 개체 (아닌 경우 제한 된 토큰) AssignPrimaryToken 가져야 및 IncreaseQuota 권한.

##  <a name="createrestrictedtoken"></a>  CAccessToken::CreateRestrictedToken

새로 만들려면이 메서드를 호출 제한 `CAccessToken` 개체입니다.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pRestrictedToken*<br/>
신규 제한 `CAccessToken` 개체입니다.

*SidsToDisable*<br/>
`CTokenGroups` 거부 전용 Sid를 지정 하는 개체입니다.

*SidsToRestrict*<br/>
`CTokenGroups` 제한 Sid를 지정 하는 개체입니다.

*PrivilegesToDelete*<br/>
`CTokenPrivileges` 제한 된 토큰에서 삭제 하는 권한을 지정 하는 개체입니다. 기본값은 빈 개체를 만듭니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

`CreateRestrictedToken` 사용 하는 [CreateRestrictedToken](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) Win32 함수를 만들기 위한 `CAccessToken` 개체를 제한 합니다.

> [!IMPORTANT]
>  사용 하는 경우 `CreateRestrictedToken`, 다음을 확인: 기존 토큰이 유효한 (및 사용자가 입력 없습니다) 및 *SidsToDisable* 하 고 *PrivilegesToDelete* 모두 유효한 (및 사용자가 입력 없습니다). 메서드가 FALSE를 반환 하는 경우 기능을 거부 합니다.

##  <a name="detach"></a>  CAccessToken::Detach

액세스 토큰의 소유권을 취소 하려면이 메서드를 호출 합니다.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>반환 값

에 대 한 핸들을 반환 합니다 `CAccessToken` 는 분리 되었습니다.

### <a name="remarks"></a>설명

이 메서드가 취소는 `CAccessToken`의 액세스 토큰의 소유권입니다.

##  <a name="disableprivilege"></a>  CAccessToken::DisablePrivilege

권한 사용 하지 않도록 설정 하려면이 메서드는 `CAccessToken` 개체입니다.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*pszPrivilege*<br/>
사용 권한을 사용 하지 않도록 설정 하려면 포함 하는 문자열에 대 한 포인터를 `CAccessToken` 개체입니다.

*pPreviousState*<br/>
에 대 한 포인터를 `CTokenPrivileges` 권한의 이전 상태를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="disableprivileges"></a>  CAccessToken::DisablePrivileges

하나 이상의 권한을 사용 하지 않도록 설정 하려면이 메서드는 `CAccessToken` 개체입니다.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*rPrivileges*<br/>
사용 하지 않도록 설정 하는 권한을 포함 하는 문자열의 배열에 대 한 포인터를 `CAccessToken` 개체입니다.

*pPreviousState*<br/>
에 대 한 포인터를 `CTokenPrivileges` 권한의 이전 상태를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="enableprivilege"></a>  CAccessToken::EnablePrivilege

권한 사용 하도록 설정 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*pszPrivilege*<br/>
사용할 수 있도록 권한을 포함 하는 문자열에 대 한 포인터를 `CAccessToken` 개체입니다.

*pPreviousState*<br/>
에 대 한 포인터를 `CTokenPrivileges` 권한의 이전 상태를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="enableprivileges"></a>  CAccessToken::EnablePrivileges

하나 이상의 권한을 사용 하도록 설정 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*rPrivileges*<br/>
사용 하도록 설정 하는 권한을 포함 하는 문자열의 배열에 대 한 포인터를 `CAccessToken` 개체입니다.

*pPreviousState*<br/>
에 대 한 포인터를 `CTokenPrivileges` 권한의 이전 상태를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="getdefaultdacl"></a>  CAccessToken::GetDefaultDacl

반환 하려면이 메서드를 호출 합니다 `CAccessToken` 개체의 기본 DACL입니다.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pDacl*<br/>
에 대 한 포인터를 [CDacl 클래스](../../atl/reference/cdacl-class.md) 수신 하는 개체는 `CAccessToken` 개체의 기본 DACL입니다.

### <a name="return-value"></a>반환 값

기본 DACL 되었으면이 고, FALSE 복구 그렇지 않은 경우 TRUE를 반환 합니다.

##  <a name="geteffectivetoken"></a>  CAccessToken::GetEffectiveToken

이 메서드를 호출 합니다 `CAccessToken` 개체를 현재 스레드에 적용에 대 한 액세스 토큰입니다.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="getgroups"></a>  CAccessToken::GetGroups

반환 하려면이 메서드를 호출 합니다 `CAccessToken` 개체의 토큰 그룹입니다.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pGroups*<br/>
에 대 한 포인터를 [CTokenGroups 클래스](../../atl/reference/ctokengroups-class.md) 그룹 정보를 수신 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="gethandle"></a>  CAccessToken::GetHandle

액세스 토큰에 대 한 핸들을 검색 하려면이 메서드를 호출 합니다.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>반환 값

에 대 한 핸들을 반환 합니다 `CAccessToken` 개체의 액세스 토큰입니다.

##  <a name="getimpersonationlevel"></a>  CAccessToken::GetImpersonationLevel

액세스 토큰 가장 수준을 활용 하려면이 메서드를 호출 합니다.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pImpersonationLevel*<br/>
에 대 한 포인터를 [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) 가장 수준 정보를 수신 하는 열거형입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="getlogonsessionid"></a>  CAccessToken::GetLogonSessionId

연결 된 로그온 세션 ID를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pluid*<br/>
에 대 한 포인터를 [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) 는 로그온 세션 id입니다. 수신할 됩니다

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 어설션 오류가 발생 하는 경우 *pluid* 잘못 된 값입니다.

##  <a name="getlogonsid"></a>  CAccessToken::GetLogonSid

연결 된 로그온 SID를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSid*<br/>
에 대 한 포인터를 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 어설션 오류가 발생 하는 경우 *pSid* 잘못 된 값입니다.

##  <a name="getowner"></a>  CAccessToken::GetOwner

연결 된 소유자를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSid*<br/>
에 대 한 포인터를 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

소유자는이 액세스 토큰이 적용 되는 동안 생성 된 모든 개체에는 기본적으로 설정 됩니다.

##  <a name="getprimarygroup"></a>  CAccessToken::GetPrimaryGroup

연결 된 기본 그룹을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSid*<br/>
에 대 한 포인터를 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

그룹은이 액세스 토큰이 적용 되는 동안 생성 된 모든 개체에는 기본적으로 설정 됩니다.

##  <a name="getprivileges"></a>  CAccessToken::GetPrivileges

연결 된 권한을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pPrivileges*<br/>
에 대 한 포인터를 [CTokenPrivileges 클래스](../../atl/reference/ctokenprivileges-class.md) 권한을 수신 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="getprocesstoken"></a>  CAccessToken::GetProcessToken

지정된 프로세스의 액세스 토큰을 사용해서 `CAccessToken`을 초기화하려면 이 메서드를 호출합니다.

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*hProcess*<br/>
액세스 토큰이 열린 프로세스에 대한 핸들입니다. 기본값은 NULL 사용 하는 경우 현재 프로세스가 사용 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

호출 된 [OpenProcessToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-openprocesstoken) Win32 함수입니다.

##  <a name="getprofile"></a>  CAccessToken::GetProfile

연결 된 사용자 프로필을 가리키는 핸들을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>반환 값

프로필이 없는 경우 NULL을 사용자 프로필을 가리키는 핸들을 반환 합니다.

##  <a name="getsource"></a>  CAccessToken::GetSource

소스를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSource*<br/>
에 대 한 포인터를 [TOKEN_SOURCE](/windows/desktop/api/winnt/ns-winnt-_token_source) 구조입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="getstatistics"></a>  CAccessToken::GetStatistics

연관 된 정보를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pStatistics*<br/>
에 대 한 포인터를 [TOKEN_STATISTICS](/windows/desktop/api/winnt/ns-winnt-_token_statistics) 구조입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="getterminalservicessessionid"></a>  CAccessToken::GetTerminalServicesSessionId

연결 된 터미널 서비스 세션 ID를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pdwSessionId*<br/>
터미널 서비스 세션 id입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="getthreadtoken"></a>  CAccessToken::GetThreadToken

초기화 하려면이 메서드를 호출 합니다 `CAccessToken` 지정된 된 스레드의에서 토큰을 사용 하 여 합니다.

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*hThread*<br/>
해당 액세스 토큰이 열린 스레드로 처리 합니다.

*bOpenAsSelf*<br/>
액세스 검사 스레드 호출의 보안 컨텍스트에 대 한 수를 여부를 나타내는 `GetThreadToken` 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.

이 매개 변수가 FALSE 인 경우 액세스 검사가 호출 스레드에 대 한 보안 컨텍스트를 사용 하 여 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우 다음 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 TRUE 인 경우 프로세스의 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="gettokenid"></a>  CAccessToken::GetTokenId

연결 된 토큰 ID를 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pluid*<br/>
에 대 한 포인터를 [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) 는 수신할 토큰 id입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="gettype"></a>  CAccessToken::GetType

토큰 형식을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pType*<br/>
주소를 [TOKEN_TYPE](/windows/desktop/api/winnt/ne-winnt-_token_type) 변수 성공 하면 수신 하는 토큰의 형식입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

TOKEN_TYPE 열거형 형식의 기본 토큰을 가장 토큰을 구분 하는 값을 포함 합니다.

##  <a name="getuser"></a>  CAccessToken::GetUser

연결 된 사용자를 식별 하려면이 메서드는 `CAccessToken` 개체입니다.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSid*<br/>
에 대 한 포인터를 [CSid 클래스](../../atl/reference/csid-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

##  <a name="hkeycurrentuser"></a>  CAccessToken::HKeyCurrentUser

연결 된 사용자 프로필을 가리키는 핸들을 가져오려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>반환 값

프로필이 없는 경우 NULL을 사용자 프로필을 가리키는 핸들을 반환 합니다.

##  <a name="impersonate"></a>  CAccessToken::Impersonate

가장을 할당 하려면이 메서드를 호출 `CAccessToken` 스레드로 합니다.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*hThread*<br/>
가장 토큰을 할당 하는 스레드를 처리 합니다. 이 핸들 TOKEN_IMPERSONATE 액세스 권한이 있는 열려 있어야 합니다. 하는 경우 *hThread* 가 null 인 경우 메서드를 호출 하면 스레드의 가장 토큰을 사용 하 여 중지 합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 어설션 오류가 발생 하는 경우 `CAccessToken` 토큰에 대 한 유효한 포인터는 없습니다.

합니다 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 가장된 액세스 토큰을 자동으로 되돌리는 데 사용할 수 있습니다.

##  <a name="impersonateloggedonuser"></a>  CAccessToken::ImpersonateLoggedOnUser

호출 스레드가 로그온 한 사용자의 보안 컨텍스트를 가장할 수 있도록이 메서드를 호출 합니다.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

> [!IMPORTANT]
>  어떤 이유로 든 실패 하면 가장 함수를 호출 하는 경우 클라이언트를 가장할 수 없습니다 하 고 클라이언트 요청이 호출이 이루어진 프로세스의 보안 컨텍스트에서 수행 됩니다. 높은 권한이 있는 계정으로 프로세스가 실행 중인 경우 관리 그룹의 멤버인 사용자 작업을 수행 하는 일을 할 수 있습니다 자신이 그렇지 않은 경우 허용 되지 것입니다. 따라서이 함수에 대 한 반환 값에 확인 항상 되어야 합니다.

##  <a name="istokenrestricted"></a>  CAccessToken::IsTokenRestricted

테스트 하려면이 메서드를 호출 합니다 `CAccessToken` 개체 제한 Sid 목록을 포함 합니다.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>반환 값

개체 제한 sid가 없는 경우 Sid가 FALSE를 제한 하는 목록을 포함 하는 경우 또는 메서드가 실패 하는 경우 TRUE를 반환 합니다.

##  <a name="loaduserprofile"></a>  CAccessToken::LoadUserProfile

연결 된 사용자 프로필을 로드 하려면이 메서드는 `CAccessToken` 개체입니다.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 어설션 오류가 발생 하는 경우는 `CAccessToken` 유효한 토큰을 포함 하지 않거나 사용자가 이미 프로 파일링 하는 경우 존재 합니다.

##  <a name="logonuser"></a>  CAccessToken::LogonUser

지정된 된 자격 증명을 사용 하 여 연결 된 사용자에 대 한 로그온 세션을 만들려면이 메서드를 호출 합니다.

```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```

### <a name="parameters"></a>매개 변수

*pszUserName*<br/>
사용자 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 에 로그온 사용자 계정의 이름입니다.

*pszDomain*<br/>
도메인 또는 계정 데이터베이스를 포함 하는 서버의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터를 *pszUserName* 계정.

*pszPassword*<br/>
지정 된 사용자 계정에 대 한 일반 텍스트 암호를 지정 하는 null로 끝나는 문자열에 대 한 포인터 *pszUserName*합니다.

*dwLogonType*<br/>
수행할 로그온 작업 유형을 지정 합니다. 참조 [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) 대 한 자세한 내용은 합니다.

*dwLogonProvider*<br/>
로그온 공급자를 지정합니다. 참조 [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) 대 한 자세한 내용은 합니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

와 연결 된 로그온에서 토큰 발생 액세스는 `CAccessToken`합니다. 이 메서드가 성공 하려면에 대 한는 `CAccessToken` 개체 소유자는 기본 신뢰할 수 있는 컴퓨터의 일부로 식별 SE_TCB_NAME 권한이 보유 해야 합니다. 참조 [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) 필요한 권한에 대 한 자세한 내용은 합니다.

##  <a name="opencomclienttoken"></a>  CAccessToken::OpenCOMClientToken

초기화 하도록 클라이언트에서 호출을 처리 하는 COM 서버 내에서이 메서드를 호출 합니다 `CAccessToken` COM 클라이언트에서 액세스 토큰입니다.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*bImpersonate*<br/>
TRUE 이면 현재 스레드는이 호출이 성공적으로 완료 되 면 호출 하는 COM 클라이언트를 가장 합니다. FALSE 인 경우 액세스 토큰을 열 수는 있지만 스레드가 가장 토큰을는이 호출이 완료 될 때.

*bOpenAsSelf*<br/>
액세스 검사 스레드 호출의 보안 컨텍스트에 대 한 수를 여부를 나타내는 합니다 [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.

이 매개 변수가 FALSE 인 경우 액세스 검사가 호출 스레드에 대 한 보안 컨텍스트를 사용 하 여 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우 다음 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 TRUE 인 경우 프로세스의 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

합니다 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 설정 하 여 생성 하는 가장된 액세스 토큰을 자동으로 되돌리려면 사용할 수는 *bImpersonate* 플래그가 TRUE로 합니다.

##  <a name="opennamedpipeclienttoken"></a>  CAccessToken::OpenNamedPipeClientToken

명명된 된 파이프 초기화를 통해 수행 요청 서버 내에서이 메서드를 호출 합니다 `CAccessToken` 클라이언트에서 액세스 토큰입니다.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*hPipe*<br/>
명명된 된 파이프에 대 한 핸들입니다.

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*bImpersonate*<br/>
TRUE 이면 현재 스레드는이 호출이 성공적으로 완료 되 면 호출 파이프 클라이언트를 가장 합니다. FALSE 인 경우 액세스 토큰을 열 수는 있지만 스레드가 가장 토큰을는이 호출이 완료 될 때.

*bOpenAsSelf*<br/>
액세스 검사 스레드 호출의 보안 컨텍스트에 대 한 수를 여부를 나타내는 합니다 [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.

이 매개 변수가 FALSE 인 경우 액세스 검사가 호출 스레드에 대 한 보안 컨텍스트를 사용 하 여 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우 다음 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 TRUE 인 경우 프로세스의 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

합니다 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 설정 하 여 생성 하는 가장된 액세스 토큰을 자동으로 되돌리려면 사용할 수는 *bImpersonate* 플래그가 TRUE로 합니다.

##  <a name="openrpcclienttoken"></a>  CAccessToken::OpenRPCClientToken

초기화는 RPC 클라이언트에서 호출을 처리 하는 서버 내에서이 메서드를 호출 합니다 `CAccessToken` 클라이언트에서 액세스 토큰입니다.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>매개 변수

*BindingHandle*<br/>
클라이언트에 대 한 바인딩을 나타내는 서버 바인딩 핸들입니다.

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*bImpersonate*<br/>
TRUE 이면 현재 스레드는이 호출이 성공적으로 완료 되 면 호출 RPC 클라이언트를 가장 합니다. FALSE 인 경우 액세스 토큰을 열 수는 있지만 스레드가 가장 토큰을는이 호출이 완료 될 때.

*bOpenAsSelf*<br/>
액세스 검사 스레드 호출의 보안 컨텍스트에 대 한 수를 여부를 나타내는 합니다 [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.

이 매개 변수가 FALSE 인 경우 액세스 검사가 호출 스레드에 대 한 보안 컨텍스트를 사용 하 여 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우 다음 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 TRUE 인 경우 프로세스의 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

합니다 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 설정 하 여 생성 하는 가장된 액세스 토큰을 자동으로 되돌리려면 사용할 수는 *bImpersonate* 플래그가 TRUE로 합니다.

##  <a name="openthreadtoken"></a>  CAccessToken::OpenThreadToken

가장 수준을 설정 하 고 다음을 초기화 하려면이 메서드는 `CAccessToken` 지정된 된 스레드의에서 토큰을 사용 하 여 합니다.

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>매개 변수

*dwDesiredAccess*<br/>
액세스 토큰에 대해 요청된 액세스 형식을 지정하는 액세스 마스크를 지정합니다. 이러한 요청된 액세스 형식은 토큰의 DACL과 비교하여 액세스가 허용 또는 거부되는 경우를 확인합니다.

*bImpersonate*<br/>
True 이면이 메서드가 완료 된 후 스레드가 요청 된 가장 수준에 남게 됩니다. False 인 경우, 스레드가 가장 수준으로 되돌아갑니다.

*bOpenAsSelf*<br/>
액세스 검사 스레드 호출의 보안 컨텍스트에 대 한 수를 여부를 나타내는 합니다 [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) 메서드 또는 호출 스레드에 대 한 프로세스의 보안 컨텍스트에 대 한 합니다.

이 매개 변수가 FALSE 인 경우 액세스 검사가 호출 스레드에 대 한 보안 컨텍스트를 사용 하 여 수행 됩니다. 스레드는 클라이언트를 가장 하는 경우 다음 보안 컨텍스트는 클라이언트 프로세스의 수 있습니다. 이 매개 변수가 TRUE 인 경우 프로세스의 보안 컨텍스트를 사용 하 여 호출 스레드에 대 한 액세스 검사가 됩니다.

*sil*<br/>
지정 된 [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) 열거 토큰 가장 수준을 제공 하는 형식.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

`OpenThreadToken` 비슷합니다 [CAccessToken::GetThreadToken](#getthreadtoken)를 초기화 하기 전에 가장 수준으로 설정 합니다는 `CAccessToken` 스레드의 액세스 토큰에서.

합니다 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md) 설정 하 여 생성 하는 가장된 액세스 토큰을 자동으로 되돌리려면 사용할 수는 *bImpersonate* 플래그가 TRUE로 합니다.

##  <a name="privilegecheck"></a>  CAccessToken::PrivilegeCheck

지정된 된 권한 집합에 사용 되는지 여부를 확인 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>매개 변수

*RequiredPrivileges*<br/>
에 대 한 포인터를 [PRIVILEGE_SET](/windows/desktop/api/winnt/ns-winnt-_privilege_set) 구조입니다.

*pbResult*<br/>
메서드는 지정 된 권한 중 일부 또는 모두에 사용 되는지 여부를 나타내는 설정 값에 대 한 포인터를 `CAccessToken` 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

때 `PrivilegeCheck` 반환 합니다 `Attributes` 의 각 멤버 [LUID_AND_ATTRIBUTES](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes) 구조는 해당 권한을 사용 하도록 설정 하는 경우 SE_PRIVILEGE_USED_FOR_ACCESS로 설정 됩니다. 이 메서드를 호출 합니다 [PrivilegeCheck](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-privilegecheck) Win32 함수입니다.

##  <a name="revert"></a>  CAccessToken::Revert

가장 토큰을 사용 하 여 스레드를 중지 하려면이 메서드를 호출 합니다.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>매개 변수

*hThread*<br/>
가장에서 되돌리려면 스레드로 처리 합니다. 하는 경우 *hThread* 가 NULL 이면 현재 스레드에 것으로 간주 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

가장 토큰으로 자동으로 수행할 수는 [CAutoRevertImpersonation 클래스](../../atl/reference/cautorevertimpersonation-class.md)합니다.

##  <a name="setdefaultdacl"></a>  CAccessToken::SetDefaultDacl

기본값을 설정 하려면이 메서드를 호출의 DACL을 `CAccessToken` 개체입니다.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>매개 변수

*rDacl*<br/>
새 기본값 [CDacl 클래스](../../atl/reference/cdacl-class.md) 정보입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

기본 DACL은이 액세스 토큰을 사용 하 여 실제로 새 개체를 만들 때 기본적으로 사용 되는 DACL입니다.

##  <a name="setowner"></a>  CAccessToken::SetOwner

소유자를 설정 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
합니다 [CSid 클래스](../../atl/reference/csid-class.md) 소유자 정보를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

소유자는이 액세스 토큰이 적용 되는 동안 생성 된 새 개체에 사용 되는 기본 소유자가입니다.

##  <a name="setprimarygroup"></a>  CAccessToken::SetPrimaryGroup

주 그룹을 설정 하려면이 메서드를 호출 합니다 `CAccessToken` 개체입니다.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
합니다 [CSid 클래스](../../atl/reference/csid-class.md) 주 그룹 정보를 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

기본 그룹에는이 액세스 토큰이 적용 되는 동안 생성 된 새 개체에 대 한 기본 그룹이입니다.

## <a name="see-also"></a>참고자료

[ATLSecurity 샘플](../../overview/visual-cpp-samples.md)<br/>
[액세스 토큰](/windows/desktop/SecAuthZ/access-tokens)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
