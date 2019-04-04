---
title: CSecurityDesc 클래스
ms.date: 11/04/2016
f1_keywords:
- CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::CSecurityDesc
- ATLSECURITY/ATL::CSecurityDesc::FromString
- ATLSECURITY/ATL::CSecurityDesc::GetControl
- ATLSECURITY/ATL::CSecurityDesc::GetDacl
- ATLSECURITY/ATL::CSecurityDesc::GetGroup
- ATLSECURITY/ATL::CSecurityDesc::GetOwner
- ATLSECURITY/ATL::CSecurityDesc::GetPSECURITY_DESCRIPTOR
- ATLSECURITY/ATL::CSecurityDesc::GetSacl
- ATLSECURITY/ATL::CSecurityDesc::IsDaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsDaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsDaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsDaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsGroupDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsOwnerDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclAutoInherited
- ATLSECURITY/ATL::CSecurityDesc::IsSaclDefaulted
- ATLSECURITY/ATL::CSecurityDesc::IsSaclPresent
- ATLSECURITY/ATL::CSecurityDesc::IsSaclProtected
- ATLSECURITY/ATL::CSecurityDesc::IsSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::MakeAbsolute
- ATLSECURITY/ATL::CSecurityDesc::MakeSelfRelative
- ATLSECURITY/ATL::CSecurityDesc::SetControl
- ATLSECURITY/ATL::CSecurityDesc::SetDacl
- ATLSECURITY/ATL::CSecurityDesc::SetGroup
- ATLSECURITY/ATL::CSecurityDesc::SetOwner
- ATLSECURITY/ATL::CSecurityDesc::SetSacl
- ATLSECURITY/ATL::CSecurityDesc::ToString
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
ms.openlocfilehash: aadaa64a936aee867766dfc0f7a6e190c9691ca6
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778028"
---
# <a name="csecuritydesc-class"></a>CSecurityDesc 클래스

이 클래스는에 대 한 래퍼를 `SECURITY_DESCRIPTOR` 구조입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSecurityDesc
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|생성자입니다.|
|[CSecurityDesc::~CSecurityDesc](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSecurityDesc::FromString](#fromstring)|유효한, 기능 보안 설명자를 문자열 형식 보안 설명자를 변환합니다.|
|[CSecurityDesc::GetControl](#getcontrol)|검색 보안 설명자에서 정보를 제어합니다.|
|[CSecurityDesc::GetDacl](#getdacl)|보안 설명자에서 임의 액세스 제어 목록 (DACL) 정보를 검색합니다.|
|[CSecurityDesc::GetGroup](#getgroup)|보안 설명자에서 주 그룹 정보를 검색합니다.|
|[CSecurityDesc::GetOwner](#getowner)|보안 설명자에서 소유자 정보를 검색합니다.|
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|에 대 한 포인터를 반환 합니다 `SECURITY_DESCRIPTOR` 구조입니다.|
|[CSecurityDesc::GetSacl](#getsacl)|보안 설명자에서 시스템 액세스 제어 목록 (SACL) 정보를 검색합니다.|
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|DACL 자동 전파를 지원 하도록 구성 된 경우를 결정 합니다.|
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|보안 설명자를 기본 DACL로 구성 된 경우를 결정 합니다.|
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|보안 설명자 DACL을 포함 하는 경우를 결정 합니다.|
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|DACL 수정을 방지 하도록 구성 된 경우를 결정 합니다.|
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|보안 설명자의 그룹 SID (보안 식별자) 기본적으로 설정 되었는지 여부를 결정 합니다.|
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|보안 설명자의 소유자 SID 기본적으로 설정 되었는지 여부를 결정 합니다.|
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|SACL 자동 전파를 지원 하도록 구성 된 경우를 결정 합니다.|
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|보안 설명자의 SACL 기본값을 사용 하 여 구성 된 경우를 결정 합니다.|
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|보안 설명자 SACL을 포함 하는 경우를 결정 합니다.|
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|SACL 수정을 방지 하도록 구성 된 경우를 결정 합니다.|
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|보안 설명자를 자기 상대적 형식 인지 여부를 결정 합니다.|
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|보안 설명자를 절대 형식으로 변환 하려면이 메서드를 호출 합니다.|
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|보안 설명자를 자기 상대적 형식으로 변환 하려면이 메서드를 호출 합니다.|
|[CSecurityDesc::SetControl](#setcontrol)|보안 설명자의 제어 비트를 설정합니다.|
|[CSecurityDesc::SetDacl](#setdacl)|DACL에 정보를 설정합니다. 보안 설명자에서 DACL 이미 있으면 대체 됩니다.|
|[CSecurityDesc::SetGroup](#setgroup)|이미 있는 모든 주 그룹 정보를 대체 하는 절대 형식 보안 설명자의 주 그룹 정보를 설정 합니다.|
|[CSecurityDesc::SetOwner](#setowner)|이미 있는 모든 소유자 정보를 대체 하는 절대 형식 보안 설명자의 소유자 정보를 설정 합니다.|
|[CSecurityDesc::SetSacl](#setsacl)|SACL에 정보를 설정합니다. 보안 설명자에서 SACL 이미 있으면 대체 됩니다.|
|[CSecurityDesc::ToString](#tostring)|보안 설명자 문자열 형식으로 변환합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CSecurityDesc::operator const SECURITY_DESCRIPTOR *](#operator_const_security_descriptor__star)|에 대 한 포인터를 반환 합니다 `SECURITY_DESCRIPTOR` 구조입니다.|
|[CSecurityDesc::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

`SECURITY_DESCRIPTOR` 구조 개체에 연결 된 보안 정보를 포함 합니다. 응용 프로그램 개체의 보안 상태를 쿼리를이 구조를 사용 합니다. 참고 항목 [AtlGetSecurityDescriptor](security-global-functions.md#atlgetsecuritydescriptor)합니다.

응용 프로그램을 수정 하지 않아야 합니다 `SECURITY_DESCRIPTOR` 구조를 직접 및 대신 클래스 메서드를 사용 해야 제공 합니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="csecuritydesc"></a>  CSecurityDesc::CSecurityDesc

생성자입니다.

```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
합니다 `CSecurityDesc` 개체 또는 `SECURITY_DESCRIPTOR` 구조에 새 할당할 `CSecurityDesc` 개체입니다.

### <a name="remarks"></a>설명

합니다 `CSecurityDesc` 를 사용 하 여 개체를 만들 수 있습니다를 `SECURITY_DESCRIPTOR` 구조 또는 이전에 정의한 `CSecurityDesc` 개체입니다.

##  <a name="dtor"></a>  CSecurityDesc::~CSecurityDesc

소멸자입니다.

```
virtual ~CSecurityDesc() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당 된 모든 리소스를 해제합니다.

##  <a name="fromstring"></a>  CSecurityDesc::FromString

유효한, 기능 보안 설명자를 문자열 형식 보안 설명자를 변환합니다.

```
bool FromString(LPCTSTR pstr) throw(...);
```

### <a name="parameters"></a>매개 변수

*pstr*<br/>
포함 된 null로 끝나는 문자열에 대 한 포인터를 [문자열 형식 보안 설명자](/windows/desktop/SecAuthZ/security-descriptor-string-format) 변환할 수 있습니다.

### <a name="return-value"></a>반환 값

성공 시 true를 반환 합니다. 실패 시 예외를 throw 합니다.

### <a name="remarks"></a>설명

문자열을 사용 하 여 만들 수 있습니다 [CSecurityDesc::ToString](#tostring)합니다. 보안 설명자를 문자열로 변환 쉽게 저장 하 고 전송 합니다.

이 메서드를 호출 [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora)합니다.

##  <a name="getcontrol"></a>  CSecurityDesc::GetControl

검색 보안 설명자에서 정보를 제어합니다.

```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```

### <a name="parameters"></a>매개 변수

*psdc*<br/>
에 대 한 포인터를 `SECURITY_DESCRIPTOR_CONTROL` 보안 설명자의 제어 정보를 수신 하는 구조입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 false 실패 한 경우 true를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [GetSecurityDescriptorControl](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-getsecuritydescriptorcontrol)합니다.

##  <a name="getdacl"></a>  CSecurityDesc::GetDacl

보안 설명자에서 임의 액세스 제어 목록 (DACL) 정보를 검색합니다.

```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pDacl*<br/>
에 대 한 포인터는 `CDacl` 보안 설명자의 DACL의 복사본을 저장 하는 구조입니다. 메서드를 설정 하는 임의의 ACL이 있으면 *pDacl* 보안 설명자의 임의 ACL의 주소입니다. 임의 ACL을 존재 하지 않는 경우 값이 없는 저장 됩니다.

*pbPresent*<br/>
지정 된 보안 설명자는 임의 ACL의 존재를 나타내는 값에 대 한 포인터입니다. 이 매개 변수가 설정 된 보안 설명자는 임의 ACL이 있으면 true입니다. 보안 설명자는 임의 ACL이 없는 경우이 매개 변수를 false로 설정 됩니다.

*pbDefaulted*<br/>
플래그에 대 한 포인터에서 SE_DACL_DEFAULTED 플래그의 값으로 설정 된 `SECURITY_DESCRIPTOR_CONTROL` 보안 설명자에 대 한 임의의 ACL이 있으면 구조체입니다. 임의 ACL 기본 메커니즘을;에서 검색 된이 플래그가 true 인 경우 false 이면 임의 ACL 사용자가 명시적으로 지정 되었습니다.

### <a name="return-value"></a>반환 값

메서드가 성공 false 실패 한 경우 true를 반환 합니다.

##  <a name="getgroup"></a>  CSecurityDesc::GetGroup

보안 설명자에서 주 그룹 정보를 검색합니다.

```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSid*<br/>
에 대 한 포인터를 [CSid](../../atl/reference/csid-class.md) (보안 식별자)는 CDacl에 저장 된 그룹의 복사본을 받는입니다.

*pbDefaulted*<br/>
플래그에 대 한 포인터에서 SE_GROUP_DEFAULTED 플래그의 값으로 설정 된 `SECURITY_DESCRIPTOR_CONTROL` 메서드는 반환 될 때 구조체입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 false 실패 한 경우 true를 반환 합니다.

##  <a name="getowner"></a>  CSecurityDesc::GetOwner

보안 설명자에서 소유자 정보를 검색합니다.

```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSid*<br/>
에 대 한 포인터를 [CSid](../../atl/reference/csid-class.md) (보안 식별자)는 CDacl에 저장 된 그룹의 복사본을 받는입니다.

*pbDefaulted*<br/>
플래그에 대 한 포인터에서 SE_OWNER_DEFAULTED 플래그의 값으로 설정 된 `SECURITY_DESCRIPTOR_CONTROL` 메서드는 반환 될 때 구조체입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 false 실패 한 경우 true를 반환 합니다.

##  <a name="getpsecurity_descriptor"></a>  CSecurityDesc::GetPSECURITY_DESCRIPTOR

에 대 한 포인터를 반환 합니다 `SECURITY_DESCRIPTOR` 구조입니다.

```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 합니다 [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) 구조입니다.

##  <a name="getsacl"></a>  CSecurityDesc::GetSacl

보안 설명자에서 시스템 액세스 제어 목록 (SACL) 정보를 검색합니다.

```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSacl*<br/>
에 대 한 포인터는 `CSacl` 보안 설명자의 SACL의 복사본을 저장 하는 구조입니다. 메서드를 설정 하는 시스템 ACL을 볼 수 있으면 *pSacl* 보안 설명자의 시스템 ACL의 주소입니다. 시스템 ACL을 존재 하지 않는 경우 값이 없는 저장 됩니다.

*pbPresent*<br/>
지정 된 보안 설명자에는 시스템 ACL의 존재를 나타내는 설정 하는 메서드 플래그에 대 한 포인터입니다. 이 매개 변수가 설정 된 보안 설명자는 시스템 ACL이 있으면 true입니다. 보안 설명자는 시스템 ACL이 없는 경우이 매개 변수를 false로 설정 됩니다.

*pbDefaulted*<br/>
플래그에 대 한 포인터에서 SE_SACL_DEFAULTED 플래그의 값으로 설정 된 `SECURITY_DESCRIPTOR_CONTROL` 보안 설명자에 대 한 시스템 ACL 있으면 구조체입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 false 실패 한 경우 true를 반환 합니다.

##  <a name="isdaclautoinherited"></a>  CSecurityDesc::IsDaclAutoInherited

임의 액세스 제어 목록 (DACL) 자동 전파를 지원 하도록 구성 된 경우를 결정 합니다.

```
bool IsDaclAutoInherited() const throw();
```

### <a name="return-value"></a>반환 값

보안 설명자를 기존 자식 개체가 상속 가능한 액세스 제어 항목 (Ace)의 자동 전파를 지원 하도록 설정 되어 있는 DACL을 포함 하는 경우 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

시스템 개체 및 기존 자식 개체에 대 한 자동 상속 알고리즘을 수행 하는 경우이 비트를 설정 합니다.

##  <a name="isdacldefaulted"></a>  CSecurityDesc::IsDaclDefaulted

보안 설명자를 기본 임의 액세스 제어 목록 (DACL)를 사용 하 여 구성 된 경우를 결정 합니다.

```
bool IsDaclDefaulted() const throw();
```

### <a name="return-value"></a>반환 값

보안 설명자에 기본 DACL, false이 고, 그렇지 경우 true를 반환 합니다.

### <a name="remarks"></a>설명

이 플래그는 시스템 액세스 제어 항목 (ACE) 상속과 관련 하 여 DACL을 처리 하는 방법으로 발생할 수 있습니다. 예를 들어 개체의 작성자는 DACL을 지정 하지 않으면 개체는 작성자의 액세스 토큰에서 기본 DACL을 받습니다. SE_DACL_PRESENT 플래그를 설정 하지 않으면 시스템에서이 플래그를 무시 합니다.

이 플래그 개체의 DACL을 최종 계산 방법을 결정 하는 데 사용 되 고 보안 개체의 보안 설명자 컨트롤에 물리적으로 저장 되지 않습니다.

이 플래그를 설정 하려면 사용 합니다 [csecuritydesc:: Setdacl](#setdacl) 메서드.

##  <a name="isdaclpresent"></a>  CSecurityDesc::IsDaclPresent

보안 설명자는 임의 액세스 제어 목록 (DACL)를 포함 하는 경우를 결정 합니다.

```
bool IsDaclPresent() const throw();
```

### <a name="return-value"></a>반환 값

보안 설명자 false 값이 들어 DACL, 그렇지 않으면 true를 반환 합니다.

### <a name="remarks"></a>설명

이 플래그를 설정 하지 않으면,이 플래그가 설정 되 고 DACL에는 NULL 인 보안 설명자는 모든 사용자에 게 전체 액세스를 허용 합니다.

이 플래그는 보안 설명자는 보안 개체와 연결 될 때까지 호출자가 지정 된 보안 정보를 저장 하기에 사용 됩니다. 보안 설명자는 보안 개체와 연결 되 고 나면 SE_DACL_PRESENT 플래그는 항상 보안 설명자 컨트롤에 설정 됩니다.

이 플래그를 설정 하려면 사용 합니다 [csecuritydesc:: Setdacl](#setdacl) 메서드.

##  <a name="isdaclprotected"></a>  CSecurityDesc::IsDaclProtected

임의 액세스 제어 목록 (DACL) 수정을 방지 하도록 구성 된 경우를 결정 합니다.

```
bool IsDaclProtected() const throw();
```

### <a name="return-value"></a>반환 값

DACL의 보안 설명자 상속 가능한 액세스 제어 항목 (Ace)에 의해 수정 되지 않도록 방지 하기 위해 구성 된 경우 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정 하려면 사용 합니다 [csecuritydesc:: Setdacl](#setdacl) 메서드.

이 메서드는 상속 가능한 Ace의 자동 전파를 지원합니다.

##  <a name="isgroupdefaulted"></a>  CSecurityDesc::IsGroupDefaulted

보안 설명자의 그룹 SID (보안 식별자) 기본적으로 설정 되었는지 여부를 결정 합니다.

```
bool IsGroupDefaulted() const throw();
```

### <a name="return-value"></a>반환 값

보안 설명자의 원래 공급자 대신 기본 메커니즘을 제공 된 보안 설명자의 경우 true를 반환 합니다 그룹 SID입니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정 하려면 사용 합니다 [csecuritydesc:: Setgroup](#setgroup) 메서드.

##  <a name="isownerdefaulted"></a>  CSecurityDesc::IsOwnerDefaulted

보안 설명자의 소유자 보안 식별자 (SID) 기본적으로 설정 되었는지 여부를 결정 합니다.

```
bool IsOwnerDefaulted() const throw();
```

### <a name="return-value"></a>반환 값

보안 설명자의 원래 공급자 대신 기본 메커니즘을 보안 설명자의 소유자 SID를 제공 하는 경우 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정 하려면 사용 합니다 [csecuritydesc:: Setowner](#setowner) 메서드.

##  <a name="issaclautoinherited"></a>  CSecurityDesc::IsSaclAutoInherited

시스템 액세스 제어 목록 (SACL) 자동 전파를 지원 하도록 구성 된 경우를 결정 합니다.

```
bool IsSaclAutoInherited() const throw();
```

### <a name="return-value"></a>반환 값

보안 설명자에 기존 자식 개체가 상속 가능한 액세스 제어 항목 (Ace)의 자동 전파를 지원 하도록 설정 된 SACL 포함 된 경우 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

시스템 개체 및 기존 자식 개체에 대 한 자동 상속 알고리즘을 수행 하는 경우이 비트를 설정 합니다.

##  <a name="issacldefaulted"></a>  CSecurityDesc::IsSaclDefaulted

보안 설명자는 기본 시스템 액세스 제어 목록 (SACL)를 사용 하 여 구성 된 경우를 결정 합니다.

```
bool IsSaclDefaulted() const throw();
```

### <a name="return-value"></a>반환 값

보안 설명자에 기본 SACL false이 고, 그렇지 경우 true를 반환 합니다.

### <a name="remarks"></a>설명

이 플래그는 시스템 액세스 제어 항목 (ACE) 상속에 대해 SACL을 처리 하는 방법으로 발생할 수 있습니다. SE_SACL_PRESENT 플래그를 설정 하지 않으면 시스템에서이 플래그를 무시 합니다.

이 플래그를 설정 하려면 사용 합니다 [csecuritydesc:: Setsacl](#setsacl) 메서드.

##  <a name="issaclpresent"></a>  CSecurityDesc::IsSaclPresent

보안 설명자는 시스템 액세스 제어 목록 (SACL)를 포함 하는 경우를 결정 합니다.

```
bool IsSaclPresent() const throw();
```

### <a name="return-value"></a>반환 값

보안 설명자 false가 포함 된 SACL 그렇지 않은 경우 true를 반환 합니다.

### <a name="remarks"></a>설명

이 플래그를 설정 하려면 사용 합니다 [csecuritydesc:: Setsacl](#setsacl) 메서드.

##  <a name="issaclprotected"></a>  CSecurityDesc::IsSaclProtected

시스템 액세스 제어 목록 (SACL) 수정을 방지 하도록 구성 된 경우를 결정 합니다.

```
bool IsSaclProtected() const throw();
```

### <a name="return-value"></a>반환 값

SACL 상속 가능한 액세스 제어 항목 (Ace)에 의해 수정 되지 않도록 보안 설명자를 방지 하기 위해 구성 된 경우 true를 반환 합니다. 그렇지 않으면 false를 반환합니다.

### <a name="remarks"></a>설명

이 플래그를 설정 하려면 사용 합니다 [csecuritydesc:: Setsacl](#setsacl) 메서드.

이 메서드는 상속 가능한 Ace의 자동 전파를 지원합니다.

##  <a name="isselfrelative"></a>  CSecurityDesc::IsSelfRelative

보안 설명자를 자기 상대적 형식 인지 여부를 결정 합니다.

```
bool IsSelfRelative() const throw();
```

### <a name="return-value"></a>반환 값

연속 된 메모리 블록에 있는 모든 보안 정보를 사용 하 여 상대적 형식의 보안 설명자가 true를 반환 합니다. 절대적 형식의 보안 설명자가 false를 반환 합니다. 자세한 내용은 [Absolute 및 Self-Relative 보안 설명자](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors)합니다.

##  <a name="makeabsolute"></a>  CSecurityDesc::MakeAbsolute

보안 설명자를 절대 형식으로 변환 하려면이 메서드를 호출 합니다.

```
bool MakeAbsolute() throw(...);
```

### <a name="return-value"></a>반환 값

메서드가 성공 false 그렇지 않으면 true를 반환 합니다.

### <a name="remarks"></a>설명

절대적 형식의 보안 설명자를 포함 하는 대신 정보 자체를 포함 하는 정보에 대 한 포인터입니다. 상대적 형식의 보안 설명자를 인접 한 메모리 블록의 정보를 포함합니다. 상대적 보안 설명자를에서 `SECURITY_DESCRIPTOR` 구조에는 항상 정보를 시작 하지만 보안 설명자의 또 다른 구성 요소는 순서에 관계 없이 구조를 따를 수 있습니다. 메모리 주소를 사용 하는 대신 상대적 보안 설명자의 구성 요소는 보안 설명자의 시작 부분에서 오프셋으로 식별 됩니다. 이 형식은 보안 설명자를 디스크에 저장 하거나 통신 프로토콜을 통해 전송 해야 하는 경우에 유용 합니다. 자세한 내용은 [Absolute 및 Self-Relative 보안 설명자](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors)합니다.

##  <a name="makeselfrelative"></a>  CSecurityDesc::MakeSelfRelative

보안 설명자를 자기 상대적 형식으로 변환 하려면이 메서드를 호출 합니다.

```
bool MakeSelfRelative() throw(...);
```

### <a name="return-value"></a>반환 값

메서드가 성공 false 그렇지 않으면 true를 반환 합니다.

### <a name="remarks"></a>설명

절대적 형식의 보안 설명자 정보 자체를 포함 하는 것이 아니라에 포함 된 정보에 대 한 포인터를 포함 합니다. 상대적 형식의 보안 설명자를 인접 한 메모리 블록의 정보를 포함합니다. 상대적 보안 설명자를에서 `SECURITY_DESCRIPTOR` 구조에는 항상 정보를 시작 하지만 보안 설명자의 또 다른 구성 요소는 순서에 관계 없이 구조를 따를 수 있습니다. 메모리 주소를 사용 하는 대신 보안 설명자의 구성 요소는 보안 설명자의 시작 부분에서 오프셋으로 식별 됩니다. 이 형식은 보안 설명자를 디스크에 저장 하거나 통신 프로토콜을 통해 전송 해야 하는 경우에 유용 합니다. 자세한 내용은 [Absolute 및 Self-Relative 보안 설명자](/windows/desktop/SecAuthZ/absolute-and-self-relative-security-descriptors)합니다.

##  <a name="operator_eq"></a>  CSecurityDesc::operator =

대입 연산자입니다.

```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
합니다 `SECURITY_DESCRIPTOR` 구조 또는 `CSecurityDesc` 할당할 개체는 `CSecurityDesc` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CSecurityDesc` 개체입니다.

##  <a name="operator_const_security_descriptor__star"></a>  CSecurityDesc::operator const SECURITY_DESCRIPTOR *

에 대 한 포인터에 값을 캐스팅 합니다 `SECURITY_DESCRIPTOR` 구조입니다.

```
operator const SECURITY_DESCRIPTOR *() const throw();
```

##  <a name="setcontrol"></a>  CSecurityDesc::SetControl

보안 설명자의 제어 비트를 설정합니다.

```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest,
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```

### <a name="parameters"></a>매개 변수

*ControlBitsOfInterest*<br/>
설정 제어 비트를 나타내는 SECURITY_DESCRIPTOR_CONTROL 마스크입니다. 설정할 수 있는 플래그 목록은 참조 하세요 [SetSecurityDescriptorControl](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)합니다.

*ControlBitsToSet*<br/>
지정 된 컨트롤 비트에 대 한 새 값을 나타내는 SECURITY_DESCRIPTOR_CONTROL 마스크를 *ControlBitsOfInterest* 마스크입니다. 이 매개 변수에 대해 나열 된 플래그의 조합 수를 *ControlBitsOfInterest* 매개 변수입니다.

### <a name="return-value"></a>반환 값

성공하면 true를 반환하고, 실패하면 false를 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 호출 [SetSecurityDescriptorControl](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-setsecuritydescriptorcontrol)합니다.

##  <a name="setdacl"></a>  CSecurityDesc::SetDacl

임의 액세스 제어 목록 (DACL) 정보를 설정합니다. 보안 설명자에서 DACL 이미 있으면 대체 됩니다.

```
inline void SetDacl(
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*Dacl*<br/>
에 대 한 참조를 `CDacl` 보안 설명자의 DACL을 지정 하는 개체입니다. 이 매개 변수가 NULL이 아니어야 합니다. 보안 설명자에는 NULL DACL을 설정 하려면 메서드의 첫 번째 형태는 것 *bPresent* false로 설정 합니다.

*bPresent*<br/>
보안 설명자의 DACL의 유무를 나타내는 플래그를 지정 합니다. 이 매개 변수가 true 인 경우 메서드 SE_DACL_PRESENT 플래그를 설정 합니다 `SECURITY_DESCRIPTOR_CONTROL` 구조체의 값을 사용 하는 *Dacl* 및 *bDefaulted* 매개 변수. 메서드를 지우고 SE_DACL_PRESENT 플래그를 false 인 경우와 *bDefaulted* 무시 됩니다.

*bDefaulted*<br/>
DACL의 소스를 나타내는 플래그를 지정 합니다. 이 플래그가 true 인 경우 몇 가지 기본 메커니즘을 통해 검색 된 DACL입니다. False 인 경우 사용자가 DACL은 명시적으로 지정 된 했습니다. SE_DACL_DEFAULTED 플래그의에이 값을 저장 하는 메서드는 `SECURITY_DESCRIPTOR_CONTROL` 구조입니다. 이 매개 변수를 지정 하지 않으면 SE_DACL_DEFAULTED 플래그를 지웁니다.

### <a name="return-value"></a>반환 값

성공하면 true를 반환하고, 실패하면 false를 반환합니다.

### <a name="remarks"></a>설명

빈와 존재 하지 않는 DACL 간의 중요 한 차이점이 있습니다. DACL을 비어 있는 경우 액세스 제어 엔트리가 및 액세스 권한이 없습니다. 권한이 명시적으로 부여 합니다. 결과적으로, 개체에 대 한 액세스는 암시적으로 거부 됩니다. 개체 없음 DACL에 있는 경우에 보호 되지 않음 개체에 할당 되 고 모든 액세스 요청은 허용 다른 한편으로.

##  <a name="setgroup"></a>  CSecurityDesc::SetGroup

이미 있는 모든 주 그룹 정보를 대체 하는 절대 형식 보안 설명자의 주 그룹 정보를 설정 합니다.

```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*Sid*<br/>
에 대 한 참조를 [CSid](../../atl/reference/csid-class.md) 보안 설명자의 새 기본 그룹에 대 한 개체입니다. 이 매개 변수가 NULL이 아니어야 합니다. 보안 설명자 DACL 또는 SACL에 없는 것으로 표시할 수 있지만 그룹 및 소유자는 이러한도 있어야 합니다 (즉, 특별 한 의미가 있는 기본 제공 SID) NULL SID 됩니다.

*bDefaulted*<br/>
기본 그룹 정보는 기본 메커니즘에서 파생 된 여부를 나타냅니다. 경우이 값은 true, 기본 정보에 SE_GROUP_DEFAULTED 플래그로이 값을 저장 하는 메서드는 `SECURITY_DESCRIPTOR_CONTROL` 구조입니다. 이 매개 변수가 0 이면 SE_GROUP_DEFAULTED 플래그가 지워집니다.

### <a name="return-value"></a>반환 값

성공하면 true를 반환하고, 실패하면 false를 반환합니다.

##  <a name="setowner"></a>  CSecurityDesc::SetOwner

절대 형식 보안 설명자의 소유자 정보를 설정합니다. 이미 있는 모든 소유자 정보를 대체합니다.

```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*Sid*<br/>
합니다 [CSid](../../atl/reference/csid-class.md) 보안 설명자의 새 기본 소유자에 대 한 개체입니다. 이 매개 변수가 NULL이 아니어야 합니다.

*bDefaulted*<br/>
소유자 정보는 기본 메커니즘에서 파생 되었는지 여부를 나타냅니다. 이 값이 true 인 경우 기본 정보입니다. SE_OWNER_DEFAULTED 플래그로이 값을 저장 하는 메서드는 `SECURITY_DESCRIPTOR_CONTROL` 구조입니다. 이 매개 변수가 0 이면 SE_OWNER_DEFAULTED 플래그가 지워집니다.

### <a name="return-value"></a>반환 값

성공하면 true를 반환하고, 실패하면 false를 반환합니다.

##  <a name="setsacl"></a>  CSecurityDesc::SetSacl

시스템 액세스 제어 목록 (SACL)에서 정보를 설정합니다. 보안 설명자에서 SACL 이미 있으면 대체 됩니다.

```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*Sacl*<br/>
에 대 한 포인터는 `CSacl` 보안 설명자의 SACL을 지정 하는 개체입니다. 이 매개 변수는 NULL이 아니어야 하며 CSacl 개체 여야 합니다. Dacl을 달리 차이가 없습니다 NULL 및 빈는 SACL SACL 개체 액세스 권한, 감사만 정보를 지정 하지 않으면으로 합니다.

*bDefaulted*<br/>
SACL의 소스를 나타내는 플래그를 지정 합니다. 이 플래그가 true 이면 SACL 몇 가지 기본 메커니즘을 통해 검색 된 합니다. False 인 경우 사용자가 SACL은 명시적으로 지정 된 했습니다. SE_SACL_DEFAULTED 플래그의에이 값을 저장 하는 메서드는 `SECURITY_DESCRIPTOR_CONTROL` 구조입니다. 이 매개 변수를 지정 하지 않으면 SE_SACL_DEFAULTED 플래그를 지웁니다.

### <a name="return-value"></a>반환 값

성공하면 true를 반환하고, 실패하면 false를 반환합니다.

##  <a name="tostring"></a>  CSecurityDesc::ToString

보안 설명자 문자열 형식으로 변환합니다.

```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pstr*<br/>
수신 하는 null로 끝나는 문자열에 대 한 포인터를 [문자열 형식 보안 설명자](/windows/desktop/SecAuthZ/security-descriptor-string-format)합니다.

*si*<br/>
출력 문자열에 포함 하는 보안 설명자의 구성 요소를 표시 하기 위해 SECURITY_INFORMATION 비트 플래그의 조합을 지정 합니다.

### <a name="return-value"></a>반환 값

성공하면 true를 반환하고, 실패하면 false를 반환합니다.

### <a name="remarks"></a>설명

문자열 형식에서 보안 설명자를 보다 쉽게 저장 하거나 이동할 수 있습니다 전송 합니다. 사용 된 `CSecurityDesc::FromString` 문자열을 다시 보안 설명자를 변환 하는 방법입니다.

합니다 *si* 매개 변수는 다음 SECURITY_INFORMATION 플래그를 포함할 수 있습니다.

|값|의미|
|-----------|-------------|
|OWNER_SECURITY_INFORMATION|소유자를 포함 합니다.|
|GROUP_SECURITY_INFORMATION|기본 그룹을 포함 합니다.|
|DACL_SECURITY_INFORMATION|DACL을 포함 합니다.|
|SACL_SECURITY_INFORMATION|SACL을 포함 합니다.|

DACL은 NULL SE_DACL_PRESENT 컨트롤 비트가 입력된 보안 설명자에 설정 되 고 메서드가 실패 합니다.

DACL가 NULL이 고 SE_DACL_PRESENT 컨트롤 비트가 입력된 보안 설명자에 설정 되지 않으면, 경우의 결과 보안 설명자 문자열 d: 구성 요소가 없습니다. 참조 [보안 설명자 문자열 형식을](/windows/desktop/SecAuthZ/security-descriptor-string-format) 대 한 자세한 내용은 합니다.

이 메서드를 호출 [ConvertStringSecurityDescriptorToSecurityDescriptor](/windows/desktop/api/sddl/nf-sddl-convertstringsecuritydescriptortosecuritydescriptora)합니다.

## <a name="see-also"></a>참고자료

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
