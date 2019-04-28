---
title: 보안 식별자 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::Sids::AccountOps
- atlsecurity/ATL::Sids::Admins
- atlsecurity/ATL::Sids::AnonymousLogon
- atlsecurity/ATL::Sids::AuthenticatedUser
- atlsecurity/ATL::Sids::BackupOps
- atlsecurity/ATL::Sids::Batch
- atlsecurity/ATL::Sids::CreatorGroup
- atlsecurity/ATL::Sids::CreatorGroupServer
- atlsecurity/ATL::Sids::CreatorOwner
- atlsecurity/ATL::Sids::CreatorOwnerServer
- atlsecurity/ATL::Sids::Dialup
- atlsecurity/ATL::Sids::Guests
- atlsecurity/ATL::Sids::Interactive
- atlsecurity/ATL::Sids::Local
- atlsecurity/ATL::Sids::Network
- atlsecurity/ATL::Sids::NetworkService
- atlsecurity/ATL::Sids::Null
- atlsecurity/ATL::Sids::PowerUsers
- atlsecurity/ATL::Sids::PrintOps
- atlsecurity/ATL::Sids::Proxy
- atlsecurity/ATL::Sids::RasServers
- atlsecurity/ATL::Sids::Replicator
- atlsecurity/ATL::Sids::RestrictedCode
- atlsecurity/ATL::Sids::Self
- atlsecurity/ATL::Sids::ServerLogon
- atlsecurity/ATL::Sids::Service
- atlsecurity/ATL::Sids::System
- atlsecurity/ATL::Sids::SystemOps
- atlsecurity/ATL::Sids::TerminalServer
- atlsecurity/ATL::Sids::Users
- atlsecurity/ATL::Sids::World
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
ms.openlocfilehash: ab5d743c7c6abf7ee3a849a28916ebd32788ef40
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274947"
---
# <a name="security-identifier-global-functions"></a>보안 식별자 전역 함수

이러한 함수 개체 일반적인 잘 알려진 SID를 반환합니다.

> [!IMPORTANT]
>  다음 표에 나열 된 함수를 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[Sids::AccountOps](#accountops)|DOMAIN_ALIAS_RID_ACCOUNT_OPS SID를 반환합니다.|
|[Sids::Admins](#admins)|DOMAIN_ALIAS_RID_ADMINS SID를 반환합니다.|
|[Sids::AnonymousLogon](#anonymouslogon)|SECURITY_ANONYMOUS_LOGON_RID SID를 반환합니다.|
|[Sids::AuthenticatedUser](#authenticateduser)|SECURITY_AUTHENTICATED_USER_RID SID를 반환합니다.|
|[Sids::BackupOps](#backupops)|DOMAIN_ALIAS_RID_BACKUP_OPS SID를 반환합니다.|
|[Sids::Batch](#batch)|SECURITY_BATCH_RID SID를 반환합니다.|
|[Sids::CreatorGroup](#creatorgroup)|SECURITY_CREATOR_GROUP_RID SID를 반환합니다.|
|[Sids::CreatorGroupServer](#creatorgroupserver)|SECURITY_CREATOR_GROUP_SERVER_RID SID를 반환합니다.|
|[Sids::CreatorOwner](#creatorowner)|SECURITY_CREATOR_OWNER_RID SID를 반환합니다.|
|[Sids::CreatorOwnerServer](#creatorownerserver)|SECURITY_CREATOR_OWNER_SERVER_RID SID를 반환합니다.|
|[Sids::Dialup](#dialup)|SECURITY_DIALUP_RID SID를 반환합니다.|
|[Sids::Guests](#guests)|DOMAIN_ALIAS_RID_GUESTS SID를 반환합니다.|
|[Sids::Interactive](#interactive)|SECURITY_INTERACTIVE_RID SID를 반환합니다.|
|[Sids::Local](#local)|SECURITY_LOCAL_RID SID를 반환합니다.|
|[Sids::Network](#network)|SECURITY_NETWORK_RID SID를 반환합니다.|
|[Sids::NetworkService](#networkservice)|SECURITY_NETWORK_SERVICE_RID SID를 반환합니다.|
|[Sids::Null](#null)|SECURITY_NULL_RID SID를 반환합니다.|
|[Sids::PreW2KAccess](#prew2kaccess)|DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID를 반환합니다.|
|[Sids::PowerUsers](#powerusers)|DOMAIN_ALIAS_RID_POWER_USERS SID를 반환합니다.|
|[Sids::PrintOps](#printops)|DOMAIN_ALIAS_RID_PRINT_OPS SID를 반환합니다.|
|[Sids::Proxy](#proxy)|SECURITY_PROXY_RID SID를 반환합니다.|
|[Sids::RasServers](#rasservers)|DOMAIN_ALIAS_RID_RAS_SERVERS SID를 반환합니다.|
|[Sids::Replicator](#replicator)|DOMAIN_ALIAS_RID_REPLICATOR SID를 반환합니다.|
|[Sids::RestrictedCode](#restrictedcode)|SECURITY_RESTRICTED_CODE_RID SID를 반환합니다.|
|[Sids::Self](#self)|SECURITY_PRINCIPAL_SELF_RID SID를 반환합니다.|
|[Sids::ServerLogon](#serverlogon)|SECURITY_SERVER_LOGON_RID SID를 반환합니다.|
|[Sids::Service](#service)|SECURITY_SERVICE_RID SID를 반환합니다.|
|[Sids::System](#system)|SECURITY_LOCAL_SYSTEM_RID SID를 반환합니다.|
|[Sids::SystemOps](#systemops)|DOMAIN_ALIAS_RID_SYSTEM_OPS SID를 반환합니다.|
|[Sids::TerminalServer](#terminalserver)|SECURITY_TERMINAL_SERVER_RID SID를 반환합니다.|
|[Sids::Users](#users)|DOMAIN_ALIAS_RID_USERS SID를 반환합니다.|
|[Sids::World](#world)|SECURITY_WORLD_RID SID를 반환합니다.|

### <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="accountops"></a>  Sids::AccountOps

DOMAIN_ALIAS_RID_ACCOUNT_OPS SID를 반환합니다.

```
CSid AccountOps() throw(...);
```

##  <a name="admins"></a>  Sids::Admins

DOMAIN_ALIAS_RID_ADMINS SID를 반환합니다.

```
CSid Admins() throw(...);
```

##  <a name="anonymouslogon"></a>  Sids::AnonymousLogon

SECURITY_ANONYMOUS_LOGON_RID SID를 반환합니다.

```
CSid AnonymousLogon() throw(...);
```

##  <a name="authenticateduser"></a>  Sids::AuthenticatedUser

SECURITY_AUTHENTICATED_USER_RID SID를 반환합니다.

```
CSid AuthenticatedUser() throw(...);
```

##  <a name="backupops"></a>  Sids::BackupOps

DOMAIN_ALIAS_RID_BACKUP_OPS SID를 반환합니다.

```
CSid BackupOps() throw(...);
```

##  <a name="batch"></a>  Sids::Batch

SECURITY_BATCH_RID SID를 반환합니다.

```
CSid Batch() throw(...);
```

##  <a name="creatorgroup"></a>  Sids::CreatorGroup

SECURITY_CREATOR_GROUP_RID SID를 반환합니다.

```
CSid CreatorGroup() throw(...);
```

##  <a name="creatorgroupserver"></a>  Sids::CreatorGroupServer

SECURITY_CREATOR_GROUP_SERVER_RID SID를 반환합니다.

```
CSid CreatorGroupServer() throw(...);
```

##  <a name="creatorowner"></a>  Sids::CreatorOwner

SECURITY_CREATOR_OWNER_RID SID를 반환합니다.

```
CSid CreatorOwner() throw(...);
```

##  <a name="creatorownerserver"></a>  Sids::CreatorOwnerServer

SECURITY_CREATOR_OWNER_SERVER_RID SID를 반환합니다.

```
CSid CreatorOwnerServer() throw(...);
```

##  <a name="dialup"></a>  Sids::Dialup

SECURITY_DIALUP_RID SID를 반환합니다.

```
CSid Dialup() throw(...);
```

##  <a name="guests"></a>  Sids::Guests

DOMAIN_ALIAS_RID_GUESTS SID를 반환합니다.

```
CSid Guests() throw(...);
```

##  <a name="interactive"></a>  Sids::Interactive

SECURITY_INTERACTIVE_RID SID를 반환합니다.

```
CSid Interactive() throw(...);
```

##  <a name="local"></a>  Sids::Local

SECURITY_LOCAL_RID SID를 반환합니다.

```
CSid Local() throw(...);
```

##  <a name="network"></a>  Sids::Network

SECURITY_NETWORK_RID SID를 반환합니다.

```
CSid Network() throw(...);
```

##  <a name="networkservice"></a>  Sids::NetworkService

SECURITY_NETWORK_SERVICE_RID SID를 반환합니다.

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>설명

NetworkService CPerfMon 보안 개체를 읽는 NT AUTHORITY\NetworkService 사용자를 사용 하도록 설정 하려면 사용 합니다. NetworkService는 DLL Windows XP Home Edition, Windows XP Professional, Windows Server 2003 및 큰 운영 체제에서 NetworkService 계정으로 로그인을 사용 하면 ATLServer 코드에는 SecurityAttribute를 추가 합니다.

사용자 지정 로그 카운터 Perfmon mmc에서 ATLServer CPerfMon 클래스를 사용 하 여 생성 되 면 실시간 보기에서 올바르게 표시 되도록 하지만 로그 파일을 보는 카운터 나타나지 않을 수 있습니다. CPerfMon 사용자 지정 성능 카운터 (smlogsvc.exe) "성능 로그 및 경고" 서비스 아래 Windows XP Home Edition, Windows XP Professional, windows Server 2003 이상 운영 체제를 실행 하는 데 필요한 권한이 없는 합니다. 이 서비스는 "NT AUTHORITY\NetworkService" 계정으로 실행 됩니다.

##  <a name="null"></a>  Sids::Null

SECURITY_NULL_RID SID를 반환합니다.

```
CSid Null() throw(...);
```

##  <a name="prew2kaccess"></a>  Sids::PreW2KAccess

DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID를 반환합니다.

```
CSid PreW2KAccess() throw(...);
```

##  <a name="powerusers"></a>  Sids::PowerUsers

DOMAIN_ALIAS_RID_POWER_USERS SID를 반환합니다.

```
CSid PowerUsers() throw(...);
```

##  <a name="printops"></a>  Sids::PrintOps

DOMAIN_ALIAS_RID_PRINT_OPS SID를 반환합니다.

```
CSid PrintOps() throw(...);
```

##  <a name="proxy"></a>  Sids::Proxy

SECURITY_PROXY_RID SID를 반환합니다.

```
CSid Proxy() throw(...);
```

##  <a name="rasservers"></a>  Sids::RasServers

DOMAIN_ALIAS_RID_RAS_SERVERS SID를 반환합니다.

```
CSid RasServers() throw(...);
```

##  <a name="replicator"></a>  Sids::Replicator

DOMAIN_ALIAS_RID_REPLICATOR SID를 반환합니다.

```
CSid Replicator() throw(...);
```

##  <a name="restrictedcode"></a>  Sids::RestrictedCode

SECURITY_RESTRICTED_CODE_RID SID를 반환합니다.

```
CSid RestrictedCode() throw(...);
```

##  <a name="self"></a>  Sids::Self

SECURITY_PRINCIPAL_SELF_RID SID를 반환합니다.

```
CSid Self() throw(...);
```

##  <a name="serverlogon"></a>  Sids::ServerLogon

SECURITY_SERVER_LOGON_RID SID를 반환합니다.

```
CSid ServerLogon() throw(...);
```

##  <a name="service"></a>  Sids::Service

SECURITY_SERVICE_RID SID를 반환합니다.

```
CSid Service() throw(...);
```

##  <a name="system"></a>  Sids::System

SECURITY_LOCAL_SYSTEM_RID SID를 반환합니다.

```
CSid System() throw(...);
```

##  <a name="systemops"></a>  Sids::SystemOps

DOMAIN_ALIAS_RID_SYSTEM_OPS SID를 반환합니다.

```
CSid SystemOps() throw(...);
```

##  <a name="terminalserver"></a>  Sids::TerminalServer

SECURITY_TERMINAL_SERVER_RID SID를 반환합니다.

```
CSid TerminalServer() throw(...);
```

##  <a name="users"></a>  Sids::Users

DOMAIN_ALIAS_RID_USERS SID를 반환합니다.

```
CSid Users() throw(...);
```

##  <a name="world"></a>  Sids::World

SECURITY_WORLD_RID SID를 반환합니다.

```
CSid World() throw(...);
```

## <a name="see-also"></a>참고자료

[함수](../../atl/reference/atl-functions.md)
