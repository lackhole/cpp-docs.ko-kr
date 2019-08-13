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
ms.openlocfilehash: b75dc4110b785f0ab1f55ba5c31df7d3fc6fbd37
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915751"
---
# <a name="csacl-class"></a>CSacl 클래스

이 클래스는 SACL (시스템 액세스 제어 목록) 구조체에 대 한 래퍼입니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSacl : public CAcl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|생성자입니다.|
|[CSacl::~CSacl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSacl::AddAuditAce](#addauditace)|`CSacl` 개체에 감사 ACE (액세스 제어 항목)를 추가 합니다.|
|[CSacl::GetAceCount](#getacecount)|`CSacl` 개체의 ace (액세스 제어 항목) 수를 반환 합니다.|
|[CSacl::RemoveAce](#removeace)|`CSacl` 개체에서 특정 ACE (액세스 제어 항목)를 제거 합니다.|
|[CSacl::RemoveAllAces](#removeallaces)|`CSacl` 개체에 포함 된 모든 ace를 제거 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|Description|
|----------|-----------------|
|[CSacl::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

SACL에는 도메인 컨트롤러의 보안 이벤트 로그에 감사 레코드를 생성 하는 액세스 시도 유형을 지정 하는 Ace (액세스 제어 항목)가 포함 되어 있습니다. SACL은 개체의 복제본을 포함 하는 모든 도메인 컨트롤러가 아니라 액세스 시도가 발생 한 도메인 컨트롤러에 대해서만 로그 항목을 생성 합니다.

개체의 보안 설명자에서 SACL을 설정 하거나 검색 하려면 요청 하는 스레드의 액세스 토큰에서 SE_SECURITY_NAME 권한을 사용 하도록 설정 해야 합니다. Administrators 그룹에는 기본적으로이 권한이 부여 되 고 다른 사용자 또는 그룹에 게 부여할 수 있습니다. 권한 부여가 필요한 것은 아닙니다. 권한으로 정의 된 작업을 수행할 수 있기 전에 보안 액세스 토큰에서 권한을 사용 하도록 설정 해야 적용 됩니다. 모델에서는 특정 시스템 작업에 대해서만 권한을 사용할 수 있으며, 더 이상 필요 하지 않은 경우 사용 하지 않도록 설정할 수 있습니다. SE_SECURITY_NAME 사용에 대 한 예제는 [getsacl](security-global-functions.md#atlgetsacl) 및 [atlsetsacl](security-global-functions.md#atlsetsacl) 을 참조 하세요.

제공 된 클래스 메서드를 사용 하 여 `SACL` 개체에서 ace를 추가, 제거, 생성 및 삭제 합니다. 참고 항목 [getsacl](security-global-functions.md#atlgetsacl) 및 [atlsetsacl](security-global-functions.md#atlsetsacl)

Windows의 액세스 제어 모델에 대 한 소개는 Windows SDK [Access Control](/windows/desktop/SecAuthZ/access-control) 를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAcl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>요구 사항

**헤더:.**

##  <a name="addauditace"></a>  CSacl::AddAuditAce

`CSacl` 개체에 감사 ACE (액세스 제어 항목)를 추가 합니다.

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
[CSid](../../atl/reference/csid-class.md) 개체입니다.

*AccessMask*<br/>
지정 `CSid` 된 개체에 대해 감사할 액세스 권한의 마스크를 지정 합니다.

*bSuccess*<br/>
허용 되는 액세스 시도의 감사 여부를 지정 합니다. 감사를 사용 하려면이 플래그를 true로 설정 합니다. 그렇지 않으면 false로 설정 합니다.

*bFailure*<br/>
거부 된 액세스 시도의 감사 여부를 지정 합니다. 감사를 사용 하려면이 플래그를 true로 설정 합니다. 그렇지 않으면 false로 설정 합니다.

*AceFlags*<br/>
ACE 상속을 제어 하는 비트 플래그 집합입니다.

*pObjectType*<br/>
개체 형식입니다.

*pInheritedObjectType*<br/>
상속 된 개체 유형입니다.

### <a name="return-value"></a>반환 값

ACE가 `CSacl` 개체에 추가 되 면 TRUE를 반환 하 고, 실패 하면 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

개체 `CSacl` 에는 보안 이벤트 로그에서 감사 레코드를 생성 하는 액세스 시도 유형을 지정 하는 ace (액세스 제어 항목)가 포함 되어 있습니다. 이 메서드는 이러한 ACE를 `CSacl` 개체에 추가 합니다.

*AceFlags* 매개 변수에 설정할 수 있는 다양 한 플래그에 대 한 설명은 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-ace_header) 를 참조 하세요.

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

필요 `CSacl` 에 따라 기존 `ACL` 구조를 사용 하 여 개체를 만들 수 있습니다. 이 매개 변수가 DACL (임의 액세스 제어 목록)이 아닌 SACL (시스템 액세스 제어 목록) 인지 확인 합니다. 디버그 빌드에서 DACL이 제공 되 면 어설션이 발생 합니다. 릴리스 빌드에서 DACL의 모든 항목은 무시 됩니다.

##  <a name="dtor"></a>  CSacl::~CSacl

소멸자입니다.

```
~CSacl() throw();
```

### <a name="remarks"></a>설명

소멸자는 모든 Ace (액세스 제어 항목)를 포함 하 여 개체에서 획득 한 모든 리소스를 해제 합니다.

##  <a name="getacecount"></a>  CSacl::GetAceCount

`CSacl` 개체의 ace (액세스 제어 항목) 수를 반환 합니다.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>반환 값

`CSacl` 개체에 포함 된 ace의 수를 반환 합니다.

##  <a name="operator_eq"></a>  CSacl::operator =

대입 연산자입니다.

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 개체에 할당할 (액세스제어목록)입니다.`ACL`

### <a name="return-value"></a>반환 값

업데이트 `CSacl` 된 개체에 대 한 참조를 반환 합니다. `ACL` 매개 변수가 실제로 SACL (시스템 액세스 제어 목록)이 아닌지 확인 하 고 DACL (임의 액세스 제어 목록)이 아닌지 확인 합니다. 디버그 빌드에서 어설션이 발생 하 고 릴리스 빌드에서 `ACL` 매개 변수가 무시 됩니다.

##  <a name="removeace"></a>  CSacl::RemoveAce

`CSacl` 개체에서 특정 ACE (액세스 제어 항목)를 제거 합니다.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 ACE 항목의 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat)에서 파생 됩니다.

##  <a name="removeallaces"></a>  CSacl::RemoveAllAces

`CSacl` 개체에 포함 된 모든 ace (액세스 제어 항목)를 제거 합니다.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>설명

개체에서 모든 `ACE` 구조체 (있는 경우)를 제거 합니다. `CSacl`

## <a name="see-also"></a>참고자료

[CAcl 클래스](../../atl/reference/cacl-class.md)<br/>
[ACLs](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[에이스](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
