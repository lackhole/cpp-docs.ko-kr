---
title: CAcl 클래스
ms.date: 11/04/2016
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
ms.openlocfilehash: 05d9d5fe9cc344be3f903f247f34003056404c9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247653"
---
# <a name="cacl-class"></a>CAcl 클래스

이 클래스에 대 한 래퍼인는 `ACL` (액세스 제어 목록) 구조입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CAcl
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CAcl::CAccessMaskArray](#caccessmaskarray)|배열 ACCESS_MASKs입니다.|
|[CAcl::CAceFlagArray](#caceflagarray)|바이트 배열입니다.|
|[CAcl::CAceTypeArray](#cacetypearray)|바이트 배열입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAcl::CAcl](#cacl)|생성자입니다.|
|[CAcl::~CAcl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAcl::GetAceCount](#getacecount)|항목 (ACE) 개체 액세스 제어의 수를 반환합니다.|
|[CAcl::GetAclEntries](#getaclentries)|액세스 제어 목록 (ACL) 항목을 검색 합니다 `CAcl` 개체입니다.|
|[CAcl::GetAclEntry](#getaclentry)|모든 항목에 대 한 정보를 검색 한 `CAcl` 개체입니다.|
|[CAcl::GetLength](#getlength)|ACL의 길이 반환 합니다.|
|[CAcl::GetPACL](#getpacl)|패키지 (ACL에 대 한 포인터)를 반환합니다.|
|[CAcl::IsEmpty](#isempty)|테스트는 `CAcl` 항목에 대 한 개체입니다.|
|[CAcl::IsNull](#isnull)|상태를 반환 합니다 `CAcl` 개체입니다.|
|[CAcl::RemoveAce](#removeace)|특정 ACE (액세스 제어 항목)에서 제거 된 `CAcl` 개체입니다.|
|[CAcl::RemoveAces](#removeaces)|모든 Ace (액세스 제어 항목)를 제거 합니다 `CAcl` 에 적용 되는 지정 `CSid`합니다.|
|[CAcl::SetEmpty](#setempty)|표시 된 `CAcl` 빈 개체입니다.|
|[CAcl::SetNull](#setnull)|표시 된 `CAcl` NULL 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAcl::operator const ACL *](#operator_const_acl__star)|캐스트를 `CAcl` 개체는 `ACL` 구조입니다.|
|[CAcl::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

`ACL` 구조는 ACL (액세스 제어 목록)의 헤더입니다. ACL에는 0 개 이상의 순차적 목록이 포함 되어 있습니다. [Ace](/windows/desktop/SecAuthZ/access-control-entries) (액세스 제어 항목). 0에서 ACL의 개별 ace가 매겨집니다 *n-1*, 여기서 *n* ACL에서 ace입니다. ACL을 편집할 때 응용 프로그램 액세스 제어 항목 (ACE) ACL 내에서 해당 항목이 있는 인덱스 여 참조 합니다.

두 가지가 ACL:

- 임의

- 시스템

임의 ACL 개체의 소유자에 의해 제어 됩니다 또는 모든 사용자 개체에 대 한 WRITE_DAC 액세스를 부여 합니다. 개체에 대 한 액세스 특정 사용자 및 그룹 있습니다 지정 합니다. 예를 들어 파일의 소유자는 사용자 및 그룹을 파일에 액세스할 수 없습니다. 컨트롤에 임의 ACL을 사용할 수 있습니다.

개체는 시스템을 시스템 관리자가 제어 하는 ACL의 형태로 연결 된 시스템 수준 보안 정보를 가질 수도 있습니다. 시스템 ACL을 시스템 관리자에 개체에 액세스 하려는 모든 시도 감사할 수 있습니다.

자세한 내용은 참조 하세요.는 [ACL](/windows/desktop/SecAuthZ/access-control-lists) Windows SDK에 설명 합니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="caccessmaskarray"></a>  CAcl::CAccessMaskArray

ACCESS_MASK 개체의 배열입니다.

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>설명

이 형식 정의 사용 권한이 액세스 제어 항목 (Ace)에 저장 하는 배열 형식을 지정 합니다.

##  <a name="caceflagarray"></a>  CAcl::CAceFlagArray

바이트 배열입니다.

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>설명

이 형식 정의 액세스 제어 항목 (ACE) 형식별 제어 플래그를 정의 하는 데 배열 형식을 지정 합니다. 참조 된 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) 가능한 플래그의 전체 목록을 정의 합니다.

##  <a name="cacetypearray"></a>  CAcl::CAceTypeArray

바이트 배열입니다.

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>설명

액세스 제어 항목 (ACE) 개체 ACCESS_ALLOWED_ACE_TYPE ACCESS_DENIED_ACE_TYPE 등의 특성을 정의 하는 데 배열 형식을 지정 하는이 형식 정의입니다. 참조 된 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) 가능한 형식의 전체 목록을 정의 합니다.

##  <a name="cacl"></a>  CAcl::CAcl

생성자입니다.

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
기존 `CAcl` 개체입니다.

### <a name="remarks"></a>설명

합니다 `CAcl` 개체가 생성 될 수 필요에 따라 기존 사용 하 여 `CAcl` 개체입니다.

##  <a name="dtor"></a>  CAcl::~CAcl

소멸자입니다.

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>설명

소멸자는 개체에서 획득 한 모든 리소스를 해제 합니다.

##  <a name="getacecount"></a>  CAcl::GetAceCount

항목 (ACE) 개체 액세스 제어의 수를 반환합니다.

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>반환 값

ACE 항목 수를 반환 합니다 `CAcl` 개체입니다.

##  <a name="getaclentries"></a>  CAcl::GetAclEntries

액세스 제어 목록 (ACL) 항목을 검색 합니다 `CAcl` 개체입니다.

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSids*<br/>
배열에 대 한 포인터 [CSid](../../atl/reference/csid-class.md) 개체입니다.

*pAccessMasks*<br/>
액세스 마스크입니다.

*pAceTypes*<br/>
액세스 제어 항목 (ACE) 형식입니다.

*pAceFlags*<br/>
ACE는 플래그입니다.

### <a name="remarks"></a>설명

이 메서드 입력에 포함 된 모든 ACE 개체의 세부 정보를 사용 하 여 배열 매개 변수는 `CAcl` 개체입니다. 특정 배열에 대 한 세부 정보 필요 하지 않은 경우 NULL을 사용 합니다.

각 배열의 내용을 해당 서로 즉, 첫 번째 요소를 `CAccessMaskArray` 첫 번째 요소에 해당 하는 배열은 `CSidArray` 배열 및 등입니다.

참조 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) ACE 형식 및 플래그에 대 한 자세한 내용은 합니다.

##  <a name="getaclentry"></a>  CAcl::GetAclEntry

모든 액세스 제어 목록 (ACL)에 항목에 대 한 정보를 검색합니다.

```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 ACL 항목 인덱스입니다.

*pSid*<br/>
합니다 [CSid](../../atl/reference/csid-class.md) ACL 항목이 적용 되는 개체입니다.

*pMask*<br/>
액세스를 부여 하거나 거부할 권한을 지정 하는 마스크입니다.

*pType*<br/>
ACE 형식입니다.

*pFlags*<br/>
ACE는 플래그입니다.

*pObjectType*<br/>
개체 형식입니다. ACE는 개체 ACE 없는 경우 또는 ACE에 개체 형식을 지정 하지 않으면이 GUID_NULL에 설정 됩니다.

*pInheritedObjectType*<br/>
상속 된 개체 형식입니다. ACE는 개체 ACE 없는 경우 또는 ACE의 상속 된 개체 형식을 지정 하지 않으면이 GUID_NULL에 설정 됩니다.

### <a name="remarks"></a>설명

이 메서드는 모든 개별 ACE는 보다 자세한 정보를 제공 하는 방법에 대 한 정보를 검색 [CAcl::GetAclEntries](#getaclentries) 단독으로 사용할 수 있도록 합니다.

참조 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) ACE 형식 및 플래그에 대 한 자세한 내용은 합니다.

##  <a name="getlength"></a>  CAcl::GetLength

액세스 제어 목록 (ACL)의 길이 반환 합니다.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>반환 값

필요한 길이 포함 하는 데 필요한 바이트 단위로 반환 합니다 `ACL` 구조입니다.

##  <a name="getpacl"></a>  CAcl::GetPACL

액세스 제어 목록 (ACL)에 대 한 포인터를 반환합니다.

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 합니다 `ACL` 구조입니다.

##  <a name="isempty"></a>  CAcl::IsEmpty

테스트는 `CAcl` 항목에 대 한 개체입니다.

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>설명

경우 TRUE를 반환 합니다 `CAcl` 개체가 NULL 이며에 항목이 없습니다. 경우 FALSE를 반환 합니다 `CAcl` 개체가 NULL 이거나 이거나 하나 이상의 항목이 포함 되어 있습니다.

##  <a name="isnull"></a>  CAcl::IsNull

상태를 반환 합니다 `CAcl` 개체입니다.

```
bool IsNull() const throw();
```

### <a name="return-value"></a>반환 값

TRUE를 반환 합니다 `CAcl` 개체가 NULL이 FALSE이 고, 그렇지 합니다.

##  <a name="operator_const_acl__star"></a>  CAcl::operator const ACL *

캐스트를 `CAcl` 개체는 `ACL` (액세스 제어 목록) 구조입니다.

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>설명

주소를 반환 합니다 `ACL` 구조입니다.

##  <a name="operator_eq"></a>  CAcl::operator =

대입 연산자입니다.

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
`CAcl` 기존 개체에 할당 합니다.

### <a name="return-value"></a>반환 값

업데이트 된 참조를 반환 합니다 `CAcl` 개체입니다.

##  <a name="removeace"></a>  CAcl::RemoveAce

특정 ACE (액세스 제어 항목)에서 제거 된 `CAcl` 개체입니다.

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
제거할 ACE 항목 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 파생 [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)합니다.

##  <a name="removeaces"></a>  CAcl::RemoveAces

Alls Ace (액세스 제어 항목)에서 제거 합니다 `CAcl` 에 적용 되는 지정 된 `CSid`합니다.

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
`CSid` 개체에 대한 참조입니다.

##  <a name="setempty"></a>  CAcl::SetEmpty

표시 된 `CAcl` 빈 개체입니다.

```
void SetEmpty() throw();
```

### <a name="remarks"></a>설명

`CAcl` 비어 있는 것으로 또는 NULL로 설정할 수 있습니다: 두 상태에는 서로 다릅니다.

##  <a name="setnull"></a>  CAcl::SetNull

표시 된 `CAcl` NULL 개체입니다.

```
void SetNull() throw();
```

### <a name="remarks"></a>설명

`CAcl` 비어 있는 것으로 또는 NULL로 설정할 수 있습니다: 두 상태에는 서로 다릅니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
