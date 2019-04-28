---
title: CDacl 클래스
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 1beac6106b825c775012b85ccd01226c3dfab795
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258964"
---
# <a name="cdacl-class"></a>CDacl 클래스

이 클래스는 DACL (임의 액세스 제어 목록) 구조에 대 한 래퍼입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CDacl : public CAcl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|생성자입니다.|
|[CDacl::~CDacl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|허용 되는 ACE (액세스 제어 항목)에 추가 된 `CDacl` 개체입니다.|
|[CDacl::AddDeniedAce](#adddeniedace)|추가 하도록 거부 ACE를 `CDacl` 개체입니다.|
|[CDacl::GetAceCount](#getacecount)|Ace (액세스 제어 항목)의 수를 반환 합니다 `CDacl` 개체입니다.|
|[CDacl::RemoveAce](#removeace)|특정 ACE (액세스 제어 항목)에서 제거 된 `CDacl` 개체입니다.|
|[CDacl::RemoveAllAces](#removeallaces)|에 포함 된 Ace를 모두 제거 된 `CDacl` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CDacl::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

개체의 보안 설명자에서 DACL을 포함할 수 있습니다. DACL에는 0 개 이상의 Ace (액세스 제어 항목) 사용자 및 그룹 개체에 액세스할 수 있는 사용자를 식별 하는 포함 되어 있습니다. DACL이 비어 있으면 (즉, 포함 된 0 개 Ace) 암시적으로 액세스할 수 있도록 액세스 권한 없음, 명시적으로 부여 합니다. 그러나 개체의 보안 설명자에서 DACL이 없는 경우 개체를 보호 되지 않으며 everyone에 대 한 전체 액세스.

개체의 DACL에서 검색할 개체의 소유자 이거나 있어야 READ_CONTROL 개체에 대 한 액세스 권한이 있습니다. 개체의 DACL을 변경 하려면 개체에 대 한 WRITE_DAC 액세스를 해야 합니다.

만들기, 추가, 제거 및 삭제의 Ace를 제공 하는 클래스 메서드를 사용 하 여 `CDacl` 개체입니다. 참고 항목 [AtlGetDacl](security-global-functions.md#atlgetdacl) 하 고 [AtlSetDacl](security-global-functions.md#atlsetdacl)합니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="addallowedace"></a>  CDacl::AddAllowedAce

허용 되는 ACE (액세스 제어 항목)에 추가 된 `CDacl` 개체입니다.

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
A [CSid](../../atl/reference/csid-class.md) 개체입니다.

*AccessMask*<br/>
허용 액세스 권한 마스크를 지정 된에 대 한 `CSid` 개체입니다.

*AceFlags*<br/>
ACE 상속을 제어 하는 비트 플래그 집합입니다.

*pObjectType*<br/>
개체 형식입니다.

*pInheritedObjectType*<br/>
상속 된 개체 형식입니다.

### <a name="return-value"></a>반환 값

ACE를 추가할 경우 TRUE를 반환 합니다 `CDacl` FALSE 실패 시 개체입니다.

### <a name="remarks"></a>설명

`CDacl` 0 개 이상의 Ace (액세스 제어 항목) 사용자 및 그룹 개체에 액세스할 수 있는 사용자를 식별 하는 개체에 포함 되어 있습니다. 이 메서드는 추가에 대 한 액세스를 허용 하는 ACE를 `CDacl` 개체입니다.

참조 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) 에 대 한 설명은에서 설정할 수 있는 다양 한 플래그를 `AceFlags` 매개 변수입니다.

##  <a name="adddeniedace"></a>  CDacl::AddDeniedAce

에 거부 ACE (액세스 제어 항목)를 추가 합니다 `CDacl` 개체입니다.

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
`CSid` 개체입니다.

*AccessMask*<br/>
거부 될 액세스 권한 마스크를 지정 된 항목에 대 한 `CSid` 개체입니다.

*AceFlags*<br/>
ACE 상속을 제어 하는 비트 플래그 집합입니다. 기본값은 메서드의 첫 번째 형태는 0입니다.

*pObjectType*<br/>
개체 형식입니다.

*pInheritedObjectType*<br/>
상속 된 개체 형식입니다.

### <a name="return-value"></a>반환 값

ACE를 추가할 경우 TRUE를 반환 합니다 `CDacl` FALSE 실패 시 개체입니다.

### <a name="remarks"></a>설명

`CDacl` 0 개 이상의 Ace (액세스 제어 항목) 사용자 및 그룹 개체에 액세스할 수 있는 사용자를 식별 하는 개체에 포함 되어 있습니다. 이 메서드는 추가 액세스를 거부 하는 ACE를 `CDacl` 개체입니다.

참조 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) 에 대 한 설명은에서 설정할 수 있는 다양 한 플래그를 `AceFlags` 매개 변수입니다.

##  <a name="cdacl"></a>  CDacl::CDacl

생성자입니다.

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 `ACL` (액세스 제어 목록) 구조입니다.

### <a name="remarks"></a>설명

합니다 `CDacl` 개체가 생성 될 수 필요에 따라 기존 사용 하 여 `ACL` 구조입니다. DACL (임의 액세스 제어 목록)만 유의 해야 하 고는 SACL (시스템 액세스 제어 목록)이이 매개 변수로 전달 해야 합니다. 디버그 빌드에서 SACL을 전달 하면 어설션이 발생 합니다. 릴리스 빌드에서 SACL을 전달 하면 Ace (액세스 제어 항목) acl 무시 되 고 오류가 발생 하지 것입니다.

##  <a name="dtor"></a>  CDacl::~CDacl

소멸자입니다.

```
~CDacl () throw();
```

### <a name="remarks"></a>설명

사용 하 여 모든 Ace (액세스 제어 항목)를 포함 하 여 개체에 의해 획득 한 리소스를 해제 하는 소멸자 [CDacl::RemoveAllAces](#removeallaces)합니다.

##  <a name="getacecount"></a>  CDacl::GetAceCount

Ace (액세스 제어 항목)의 수를 반환 합니다 `CDacl` 개체입니다.

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>반환 값

에 포함 된 Ace의 수를 반환 합니다 `CDacl` 개체입니다.

##  <a name="operator_eq"></a>  CDacl::operator =

대입 연산자입니다.

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 개체에 할당할 ACL (액세스 제어 목록).

### <a name="return-value"></a>반환 값

업데이트 된 참조를 반환 합니다 `CDacl` 개체입니다.

### <a name="remarks"></a>설명

이 함수는 DACL (임의 액세스 제어 목록)만 전달 해야 합니다. SACL (시스템 액세스 제어 목록)를 전달 합니다.이 함수에이 어설션이 디버그 빌드에서 하지만 릴리스 빌드에 없음 오류가 발생 합니다.

##  <a name="removeace"></a>  CDacl::RemoveAce

특정 ACE (액세스 제어 항목)에서 제거 된 `CDacl` 개체입니다.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 ACE 항목 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 파생 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)합니다.

##  <a name="removeallaces"></a>  CDacl::RemoveAllAces

에 포함 된 Ace (액세스 제어 항목)를 모두 제거 된 `CDacl` 개체입니다.

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>설명

제거 마다 `ACE` (액세스 제어 항목) 구조 (있는 경우)에 `CDacl` 개체입니다.

## <a name="see-also"></a>참고자료

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[CAcl 클래스](../../atl/reference/cacl-class.md)<br/>
[ACLs](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[ACEs](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
