---
title: CSid 클래스
ms.date: 03/27/2019
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
ms.openlocfilehash: ed19ed3cdeb77612e20d826480ab73b9361366e9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496446"
---
# <a name="csid-class"></a>CSid 클래스

이 클래스는 `SID` (보안 식별자) 구조체에 대 한 래퍼입니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSid
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|Description|
|----------|-----------------|
|[CSid::CSidArray](#csidarray)|`CSid` 개체의 배열입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSid::CSid](#csid)|생성자입니다.|
|[CSid::~CSid](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CSid::AccountName](#accountname)|`CSid` 개체와 연결 된 계정의 이름을 반환 합니다.|
|[CSid::Domain](#domain)|`CSid` 개체와 연결 된 도메인의 이름을 반환 합니다.|
|[CSid::EqualPrefix](#equalprefix)|같음을 `SID` 위한 테스트 (보안 식별자) 접두사입니다.|
|[CSid::GetLength](#getlength)|`CSid` 개체의 길이를 반환 합니다.|
|[CSid::GetPSID](#getpsid)|`SID` 구조체에 대 한 포인터를 반환 합니다.|
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|`SID_IDENTIFIER_AUTHORITY` 구조체에 대 한 포인터를 반환 합니다.|
|[CSid::GetSubAuthority](#getsubauthority)|`SID` 구조에서 지정 된 subauthority를 반환 합니다.|
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|하위 기관 수를 반환 합니다.|
|[CSid::IsValid](#isvalid)|개체의 `CSid` 유효성을 테스트 합니다.|
|[CSid::LoadAccount](#loadaccount)|계정 이름과 `CSid` 도메인 또는 기존 `SID` 구조를 지정 하 여 개체를 업데이트 합니다.|
|[CSid::Sid](#sid)|ID 문자열을 반환 합니다.|
|[CSid::SidNameUse](#sidnameuse)|`CSid` 개체의 상태에 대 한 설명을 반환 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator =](#operator_eq)|대입 연산자입니다.|
|[operator const SID *](#operator_const_sid__star)|개체를 `CSid` `SID` 구조체에 대 한 포인터로 캐스팅 합니다.|

### <a name="global-operators"></a>전역 연산자

|||
|-|-|
|[operator ==](#operator_eq_eq)|두 보안 설명자 개체가 같은지 테스트 합니다.|
|[operator !=](#operator_neq)|두 보안 설명자 개체가 같지 않은지 테스트 합니다.|
|[연산자\<](#operator_lt)|두 보안 설명자 개체의 상대 값을 비교 합니다.|
|[연산자 >](#operator_gt)|두 보안 설명자 개체의 상대 값을 비교 합니다.|
|[operator \<=](#operator_lt__eq)|두 보안 설명자 개체의 상대 값을 비교 합니다.|
|[operator >=](#operator_gt__eq)|두 보안 설명자 개체의 상대 값을 비교 합니다.|

## <a name="remarks"></a>설명

`SID` 구조는 사용자 또는 그룹을 고유 하 게 식별 하는 데 사용 되는 가변 길이 구조입니다.

응용 프로그램은 `SID` 구조를 직접 수정 하면 안 되며 대신이 래퍼 클래스에서 제공 되는 메서드를 사용 해야 합니다. 참고 항목을 [AtlGetOwnerSid](security-global-functions.md#atlgetownersid), [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid), [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid), 및  [AtlSetOwnerSid](security-global-functions.md#atlsetownersid)을 참조 하세요.

Windows의 액세스 제어 모델에 대 한 소개는 Windows SDK [Access Control](/windows/win32/SecAuthZ/access-control) 를 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:.**

##  <a name="accountname"></a>  CSid::AccountName

`CSid` 개체와 연결 된 계정의 이름을 반환 합니다.

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>반환 값

계정 이름을 가리키는 LPCTSTR를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 지정 `SID` 된 (보안 식별자)의 이름을 찾으려고 시도 합니다. 자세한 내용은 [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)를 참조 하세요.

의 계정 이름을 `SID` 찾을 수 없는 경우 빈 문자열을 `AccountName` 반환 합니다. 네트워크 시간 제한으로 인해이 메서드에서 이름을 찾을 수 없는 경우이 문제가 발생할 수 있습니다. 로그인 세션을 식별 `SID` 하는와 같이 해당 계정 이름이 없는 보안 식별자에도 발생 합니다.

##  <a name="csid"></a>  CSid::CSid

생성자입니다.

```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 `CSid` 개체 또는 `SID` (보안 식별자) 구조입니다.

*IdentifierAuthority*<br/>
권한입니다.

*nSubAuthorityCount*<br/>
Subauthority 수입니다.

*pszAccountName*<br/>
계정 이름입니다.

*pszSystem*<br/>
시스템 이름입니다. 이 문자열은 원격 컴퓨터의 이름일 수 있습니다. 이 문자열이 NULL 이면 로컬 시스템이 대신 사용 됩니다.

*pSid*<br/>
`SID` 구조체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

생성자는 `CSid` 개체를 초기화 하거나, 내부 데이터 멤버를 *sidtypeinvalid*로 설정 하거나, 기존 `CSid` `SID`또는 기존 계정에서 설정을 복사 합니다.

초기화가 실패 하면 생성자는이 [클래스](../../atl/reference/catlexception-class.md)를 throw 합니다.

##  <a name="dtor"></a>  CSid::~CSid

소멸자입니다.

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>설명

소멸자는 개체에서 획득 한 모든 리소스를 해제 합니다.

##  <a name="csidarray"></a>  CSid::CSidArray

[CSid](../../atl/reference/csid-class.md) 개체의 배열입니다.

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>설명

이 typedef는 ACL (액세스 제어 목록)에서 보안 식별자를 검색 하는 데 사용할 수 있는 배열 형식을 지정 합니다. [Cacl:: GetAclEntries](../../atl/reference/cacl-class.md#getaclentries)를 참조 하세요.

##  <a name="domain"></a>  CSid::Domain

`CSid` 개체와 연결 된 도메인의 이름을 반환 합니다.

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>반환 값

도메인을 `LPCTSTR` 가리키는를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 지정 `SID` 된 (보안 식별자)의 이름을 찾으려고 시도 합니다. 자세한 내용은 [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)를 참조 하세요.

의 계정 이름을 `SID` `Domain` 찾을 수 없는 경우는 도메인을 빈 문자열로 반환 합니다. 네트워크 시간 제한으로 인해이 메서드에서 이름을 찾을 수 없는 경우이 문제가 발생할 수 있습니다. 로그인 세션을 식별 `SID` 하는와 같이 해당 계정 이름이 없는 보안 식별자에도 발생 합니다.

##  <a name="equalprefix"></a>  CSid::EqualPrefix

같음을 `SID` 위한 테스트 (보안 식별자) 접두사입니다.

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
비교할 (보안 식별자) 구조체 또는 `CSid` 개체입니다. `SID`

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 하 고 실패 하면 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

자세한 내용은 Windows SDK의 [EqualPrefixSid](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) 를 참조 하세요.

##  <a name="getlength"></a>  CSid::GetLength

`CSid` 개체의 길이를 반환 합니다.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>반환 값

`CSid` 개체의 길이 (바이트)를 반환 합니다.

### <a name="remarks"></a>설명

`CSid` 구조체가 유효 하지 않으면 반환 값이 정의 되지 않습니다. 를 호출 `GetLength`하기 전에 [CSid:: IsValid](#isvalid) 멤버 함수를 사용 하 여 `CSid` 가 유효한 지 확인 합니다.

> [!NOTE]
>  디버그 빌드에서 함수는 `CSid` 개체가 유효 하지 않은 경우 어설션을 발생 시킵니다.

##  <a name="getpsid"></a>  CSid::GetPSID

(보안 식별자) 구조체 `SID` 에 대 한 포인터를 반환 합니다.

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>반환 값

`CSid` 개체의 내부 `SID` 구조에 대 한 주소를 반환 합니다.

##  <a name="getpsid_identifier_authority"></a>  CSid::GetPSID_IDENTIFIER_AUTHORITY

`SID_IDENTIFIER_AUTHORITY` 구조체에 대 한 포인터를 반환 합니다.

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 `SID_IDENTIFIER_AUTHORITY` 구조체의 주소를 반환 합니다. 실패 하면 반환 값이 정의 되지 않습니다. `CSid` 개체가 유효 하지 않으면 오류가 발생할 수 있습니다 .이 경우 [CSid:: IsValid](#isvalid) 메서드는 FALSE를 반환 합니다. 함수 `GetLastError` 를 호출 하 여 확장 오류 정보를 확인할 수 있습니다.

> [!NOTE]
>  디버그 빌드에서 함수는 `CSid` 개체가 유효 하지 않은 경우 어설션을 발생 시킵니다.

##  <a name="getsubauthority"></a>  CSid::GetSubAuthority

지정 된 subauthority `SID` (보안 식별자) 구조를 반환 합니다.

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>매개 변수

*nSubAuthority*<br/>
Subauthority입니다.

### <a name="return-value"></a>반환 값

*Nsubauthority* 에서 참조 하는 subauthority를 반환 합니다. Subauthority 값은 RID (상대 식별자)입니다.

### <a name="remarks"></a>설명

*Nsubauthority* 매개 변수는 메서드가 반환 하는 subauthority 배열 요소를 식별 하는 인덱스 값을 지정 합니다. 메서드는이 값에 대해 유효성 검사 테스트를 수행 하지 않습니다. 응용 프로그램은 [CSid:: GetSubAuthorityCount](#getsubauthoritycount) 를 호출 하 여 허용 되는 값 범위를 검색할 수 있습니다.

> [!NOTE]
>  디버그 빌드에서 함수는 `CSid` 개체가 유효 하지 않은 경우 어설션을 발생 시킵니다.

##  <a name="getsubauthoritycount"></a>  CSid::GetSubAuthorityCount

하위 기관 수를 반환 합니다.

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 하위 기관 수입니다.

메서드가 실패 하면 반환 값은 정의 되지 않습니다. `CSid` 개체가 잘못 된 경우 메서드가 실패 합니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.

> [!NOTE]
>  디버그 빌드에서 함수는 `CSid` 개체가 유효 하지 않은 경우 어설션을 발생 시킵니다.

##  <a name="isvalid"></a>  CSid::IsValid

개체의 `CSid` 유효성을 테스트 합니다.

```
bool IsValid() const throw();
```

### <a name="return-value"></a>반환 값

`CSid` 개체가 유효 하면 TRUE를 반환 하 고 그렇지 않으면 FALSE를 반환 합니다. 이 메서드에 대 한 확장 오류 정보는 없습니다. 을 호출 `GetLastError`하지 마세요.

### <a name="remarks"></a>설명

메서드 `IsValid` 는 수정 번호가 `CSid` 알려진 범위 내에 있고 하위 기관의 수가 최대값 보다 적은지 확인 하 여 개체의 유효성을 검사 합니다.

##  <a name="loadaccount"></a>  CSid::LoadAccount

계정 이름과 `CSid` 도메인 또는 기존 SID (보안 식별자) 구조를 지정 하 여 개체를 업데이트 합니다.

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>매개 변수

*pszAccountName*<br/>
계정 이름입니다.

*pszSystem*<br/>
시스템 이름입니다. 이 문자열은 원격 컴퓨터의 이름일 수 있습니다. 이 문자열이 NULL 이면 로컬 시스템이 대신 사용 됩니다.

*pSid*<br/>
[SID](/windows/win32/api/winnt/ns-winnt-sid) 구조에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 하 고 실패 하면 FALSE를 반환 합니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.

### <a name="remarks"></a>설명

`LoadAccount`지정 된 이름에 대 한 보안 식별자를 찾으려고 시도 합니다. 자세한 내용은 [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw) 를 참조 하세요.

##  <a name="operator_eq"></a>  CSid::operator =

대입 연산자입니다.

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
개체에`CSid` 할당할 `CSid` (보안식별자)또는입니다.`SID`

### <a name="return-value"></a>반환 값

업데이트 `CSid` 된 개체에 대 한 참조를 반환 합니다.

##  <a name="operator_eq_eq"></a>  CSid::operator ==

두 보안 설명자 개체가 같은지 테스트 합니다.

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
= = 연산자의 왼쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

*rhs*<br/>
= = 연산자의 오른쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

### <a name="return-value"></a>반환 값

보안 설명자가 동일 하면 TRUE이 고, 그렇지 않으면 FALSE입니다.

##  <a name="operator_neq"></a>  CSid::operator !=

두 보안 설명자 개체가 같지 않은지 테스트 합니다.

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
! = 연산자의 왼쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

*rhs*<br/>
! = 연산자의 오른쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

### <a name="return-value"></a>반환 값

보안 설명자가 같지 않으면 TRUE이 고, 그렇지 않으면 FALSE입니다.

##  <a name="operator_lt"></a>  CSid::operator &lt;

두 보안 설명자 개체의 상대 값을 비교 합니다.

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
! = 연산자의 왼쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

*rhs*<br/>
! = 연산자의 오른쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

### <a name="return-value"></a>반환 값

*Lhs* 가 *rhs*보다 작은 경우 TRUE이 고, 그렇지 않으면 FALSE입니다.

##  <a name="operator_lt__eq"></a>  CSid::operator &lt;=

두 보안 설명자 개체의 상대 값을 비교 합니다.

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
! = 연산자의 왼쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

*rhs*<br/>
! = 연산자의 오른쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

### <a name="return-value"></a>반환 값

*Lhs* 가 *rhs*보다 작거나 같으면 TRUE이 고, 그렇지 않으면 FALSE입니다.

##  <a name="operator_gt"></a>  CSid::operator &gt;

두 보안 설명자 개체의 상대 값을 비교 합니다.

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
! = 연산자의 왼쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

*rhs*<br/>
! = 연산자의 오른쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

### <a name="return-value"></a>반환 값

*Lhs* 가 *RHS*보다 크면 TRUE이 고, 그렇지 않으면 FALSE입니다.

##  <a name="operator_gt__eq"></a>  CSid::operator &gt;=

두 보안 설명자 개체의 상대 값을 비교 합니다.

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
! = 연산자의 왼쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

*rhs*<br/>
! = 연산자의 오른쪽에 `CSid` 표시 되는 (보안식별자)또는입니다.`SID`

### <a name="return-value"></a>반환 값

*Lhs* 가 *rhs*보다 크거나 같으면 TRUE이 고, 그렇지 않으면 FALSE입니다.

##  <a name="operator_const_sid__star"></a>  CSid::operator const SID \*

개체를 `CSid` `SID` (보안 식별자) 구조체에 대 한 포인터로 캐스팅 합니다.

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>설명

`SID` 구조체의 주소를 반환 합니다.

##  <a name="sid"></a>  CSid::Sid

`SID` (보안 식별자) 구조체를 문자열로 반환 합니다.

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>반환 값

`SID` 구조를 표시, 저장 또는 전송에 적합 한 형식으로 문자열로 반환 합니다. [Convertsidtostringsid](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw)와 동일 합니다.

##  <a name="sidnameuse"></a>  CSid::SidNameUse

`CSid` 개체의 상태에 대 한 설명을 반환 합니다.

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>반환 값

`CSid` 개체의 상태를 설명 하는 값을 저장 하는 데이터 멤버의 값을 반환 합니다.

|값|Description|
|-----------|-----------------|
|SidTypeUser|사용자 `SID` (보안 식별자)를 나타냅니다.|
|SidTypeGroup|그룹 `SID`을 나타냅니다.|
|SidTypeDomain|도메인 `SID`을 나타냅니다.|
|SidTypeAlias|별칭 `SID`을 나타냅니다.|
|SidTypeWellKnownGroup|잘 알려진 `SID` 그룹의를 나타냅니다.|
|SidTypeDeletedAccount|삭제 된 `SID` 계정에 대 한를 나타냅니다.|
|SidTypeInvalid|가 잘못 `SID`되었음을 나타냅니다.|
|SidTypeUnknown|알 수 없는 `SID` 형식을 나타냅니다.|
|SidTypeComputer|컴퓨터의 `SID` 를 나타냅니다.|

### <a name="remarks"></a>설명

`SidNameUse`를 호출하여 해당 상태를 반환하기 전에 [CSid::loadaccount](#loadaccount)를 호출하여 `CSid` 개체를 업데이트합니다. `SidNameUse`는 또는 `LookupAccountName` `LookupAccountSid`를 호출 하 여 개체의 상태를 변경 하지 않고 현재 상태만 반환 합니다.

## <a name="see-also"></a>참고자료

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)<br/>
[연산자](../../atl/reference/atl-operators.md)
