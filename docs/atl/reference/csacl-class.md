---
title: CSacl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
ms.openlocfilehash: f8820be3073c6ffaffdaa9d04a7338ad584d36ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278022"
---
# <a name="csacl-class"></a>CSacl 클래스

이 클래스는 SACL (시스템 액세스 제어 목록) 구조에 대 한 래퍼입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSacl : public CAcl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|생성자입니다.|
|[CSacl::~CSacl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSacl::AddAuditAce](#addauditace)|감사 액세스 제어 항목 (ACE)에 추가 된 `CSacl` 개체입니다.|
|[CSacl::GetAceCount](#getacecount)|액세스 제어 항목 (Ace)의 수를 반환 합니다 `CSacl` 개체입니다.|
|[CSacl::RemoveAce](#removeace)|특정 ACE (액세스 제어 항목)에서 제거 된 `CSacl` 개체입니다.|
|[CSacl::RemoveAllAces](#removeallaces)|에 포함 된 Ace를 모두 제거 된 `CSacl` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CSacl::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

SACL이 도메인 컨트롤러의 보안 이벤트 로그에서 감사 레코드를 생성 하는 액세스 시도의 유형을 지정 하는 액세스 제어 항목 (Ace)를 포함 합니다. 액세스 시도가 발생 하는 도메인 컨트롤러에만, 개체의 복제본을 포함 하는 모든 도메인 컨트롤러에 없는 로그 항목을 생성 하는 SACL note 합니다.

을 설정 하거나 개체의 보안 설명자에서 SACL을 검색 하려면 SE_SECURITY_NAME 권한 액세스 토큰 요청 스레드의에서 활성화 되어야 합니다. 관리자 그룹에이 권한은 기본적으로 부여 하 고 다른 사용자 또는 그룹에 부여할 수 있습니다. 권한을 부여 하지 않으며 모든 필요한: 권한을 적용 하기 위해 보안 액세스 토큰에서 활성화 해야 권한으로 정의 된 작업을 수행 하기 전에 합니다. 모델 권한을 특정 시스템 작업에 대해서만 사용 하도록 설정 되어 더 이상 필요 없는 경우 다음 비활성화를 허용 합니다. 참조 [AtlGetSacl](security-global-functions.md#atlgetsacl) 하 고 [AtlSetSacl](security-global-functions.md#atlsetsacl) SE_SECURITY_NAME 사용의 예입니다.

추가, 제거, 생성 및 삭제의 Ace를 제공 하는 클래스 메서드를 사용 하 여 `SACL` 개체입니다. 참고 항목 [AtlGetSacl](security-global-functions.md#atlgetsacl) 하 고 [AtlSetSacl](security-global-functions.md#atlsetsacl)합니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAcl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="addauditace"></a>  CSacl::AddAuditAce

감사 액세스 제어 항목 (ACE)에 추가 된 `CSacl` 개체입니다.

```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
합니다 [CSid](../../atl/reference/csid-class.md) 개체입니다.

*AccessMask*<br/>
감사할 액세스 권한 마스크를 지정 된 항목에 대 한 `CSid` 개체입니다.

*bSuccess*<br/>
허용 되는 액세스 시도 감사할 수 있는지 여부를 지정 합니다. 이 플래그를 사용 감사; true로 설정 그렇지 않으면 false로 설정 합니다.

*bFailure*<br/>
거부 된 액세스 시도 감사할 수 있는지 여부를 지정 합니다. 이 플래그를 사용 감사; true로 설정 그렇지 않으면 false로 설정 합니다.

*AceFlags*<br/>
ACE 상속을 제어 하는 비트 플래그 집합입니다.

*pObjectType*<br/>
개체 형식입니다.

*pInheritedObjectType*<br/>
상속 된 개체 형식입니다.

### <a name="return-value"></a>반환 값

ACE를 추가할 경우 TRUE를 반환 합니다 `CSacl` FALSE 실패 시 개체입니다.

### <a name="remarks"></a>설명

`CSacl` 보안 이벤트 로그에서 감사 레코드를 생성 하는 액세스 시도의 유형을 지정 하는 액세스 제어 항목 (Ace)을 포함 하는 개체입니다. 이 메서드를 추가 하려면 ACE를 `CSacl` 개체입니다.

참조 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) 에 대 한 설명은에서 설정할 수 있는 다양 한 플래그를 *AceFlags* 매개 변수입니다.

##  <a name="csacl"></a>  CSacl::CSacl

생성자입니다.

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 `ACL` (액세스 제어 목록) 구조입니다.

### <a name="remarks"></a>설명

합니다 `CSacl` 개체가 생성 될 수 필요에 따라 기존 사용 하 여 `ACL` 구조입니다. 이 매개 변수는 임의 액세스 제어 목록 (DACL) 및 시스템 액세스 제어 목록 (SACL) 인지 확인 합니다. DACL이 제공 하는 경우 디버그 빌드에서 어설션을 발생 합니다. 릴리스 빌드에서 DACL에서 모든 항목은 무시 됩니다.

##  <a name="dtor"></a>  CSacl::~CSacl

소멸자입니다.

```
~CSacl() throw();
```

### <a name="remarks"></a>설명

소멸자는 모든 액세스 제어 항목 (Ace)를 포함 하 여 개체에 의해 획득 한 모든 리소스를 해제 합니다.

##  <a name="getacecount"></a>  CSacl::GetAceCount

액세스 제어 항목 (Ace)의 수를 반환 합니다 `CSacl` 개체입니다.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>반환 값

에 포함 된 Ace의 수를 반환 합니다 `CSacl` 개체입니다.

##  <a name="operator_eq"></a>  CSacl::operator =

대입 연산자입니다.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
`ACL` 기존 개체에 할당할 (액세스 제어 목록).

### <a name="return-value"></a>반환 값

업데이트 된 참조를 반환 합니다 `CSacl` 개체입니다. 확인 된 `ACL` 매개 변수는 실제로 시스템 액세스 제어 목록 (SACL)와 임의 액세스 제어 목록 (DACL). 어설션을 발생 하는 디버그 빌드 및 릴리스 빌드는 `ACL` 매개 변수는 무시 합니다.

##  <a name="removeace"></a>  CSacl::RemoveAce

특정 ACE (액세스 제어 항목)에서 제거 된 `CSacl` 개체입니다.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 ACE 항목 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 파생 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)합니다.

##  <a name="removeallaces"></a>  CSacl::RemoveAllAces

에 포함 된 액세스 제어 항목 (Ace)를 모두 제거 된 `CSacl` 개체입니다.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>설명

제거 마다 `ACE` (있는 경우) 구조를 `CSacl` 개체입니다.

## <a name="see-also"></a>참고자료

[CAcl 클래스](../../atl/reference/cacl-class.md)<br/>
[ACLs](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[ACEs](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
