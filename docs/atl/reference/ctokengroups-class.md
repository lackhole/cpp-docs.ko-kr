---
title: CTokenGroups 클래스
ms.date: 11/04/2016
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: 4e5d06ca01201bf415afedbe6f6e5bca096f68fa
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915587"
---
# <a name="ctokengroups-class"></a>CTokenGroups 클래스

이 클래스는 `TOKEN_GROUPS` 구조체에 대 한 래퍼입니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CTokenGroups
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CTokenGroups::CTokenGroups](#ctokengroups)|생성자입니다.|
|[CTokenGroups::~CTokenGroups](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CTokenGroups::Add](#add)|개체에`CTokenGroups` 또는 기존 `TOKEN_GROUPS` 구조체를 추가 합니다. `CSid`|
|[CTokenGroups::Delete](#delete)|개체에서 및 관련 특성을 `CSid` 삭제 합니다. `CTokenGroups`|
|[CTokenGroups::DeleteAll](#deleteall)|개체에서 모든 `CSid` 개체 및 관련 특성을 삭제 합니다. `CTokenGroups`|
|[CTokenGroups::GetCount](#getcount)|개체에 포함 된 `CSid` 개체 및 관련 특성의 수를 반환 합니다. `CTokenGroups`|
|[CTokenGroups::GetLength](#getlength)|`CTokenGroups` 개체의 크기를 반환 합니다.|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|`TOKEN_GROUPS` 구조체에 대 한 포인터를 검색 합니다.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|개체에 속하는 개체 및 특성을 검색 합니다. `CSid` `CTokenGroups`|
|[CTokenGroups::LookupSid](#lookupsid)|`CSid` 개체와 연결 된 특성을 검색 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|Description|
|----------|-----------------|
|[CTokenGroups:: operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|개체를 `CTokenGroups` `TOKEN_GROUPS` 구조체에 대 한 포인터로 캐스팅 합니다.|
|[CTokenGroups::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

[액세스 토큰](/windows/desktop/SecAuthZ/access-tokens) 은 프로세스나 스레드의 보안 컨텍스트를 설명 하 고 Windows 시스템에 로그온 한 각 사용자에 게 할당 되는 개체입니다.

클래스 `CTokenGroups` 는 액세스 토큰의 그룹 sid (보안 식별자)에 대 한 정보를 포함 하는 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) 구조체에 대 한 래퍼입니다.

Windows의 액세스 제어 모델에 대 한 소개는 Windows SDK [Access Control](/windows/desktop/SecAuthZ/access-control) 를 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:.**

##  <a name="add"></a>  CTokenGroups::Add

개체에`CTokenGroups` 또는 기존 `TOKEN_GROUPS` 구조체를 추가 합니다. `CSid`

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md) 개체입니다.

*dwAttributes*<br/>
`CSid` 개체에 연결할 특성입니다.

*rTokenGroups*<br/>
[TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) 구조체입니다.

### <a name="remarks"></a>설명

이러한 메서드는 `CTokenGroups` 개체와 개체 `CSid` 에 연결 된 특성을 하나 이상 추가 합니다.

##  <a name="ctokengroups"></a>  CTokenGroups::CTokenGroups

생성자입니다.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
`CTokenGroups` 개체를 생성 하는 데 사용할 `CTokenGroups`개체 또는 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) 구조체입니다.

### <a name="remarks"></a>설명

필요 `CTokenGroups` 에 따라 `TOKEN_GROUPS` 구조체 또는 이전에 정의 `CTokenGroups` 된 개체를 사용 하 여 개체를 만들 수 있습니다.

##  <a name="dtor"></a>  CTokenGroups::~CTokenGroups

소멸자입니다.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당 된 리소스를 모두 해제 합니다.

##  <a name="delete"></a>  CTokenGroups::Delete

개체에서 및 관련 특성을 `CSid` 삭제 합니다. `CTokenGroups`

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
SID (보안 식별자) 및 특성을 제거할 [CSid](../../atl/reference/csid-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

`CSid` 이 제거 되 면 true를 반환 하 고, 그렇지 않으면 false를 반환 합니다.

##  <a name="deleteall"></a>  CTokenGroups::DeleteAll

개체에서 모든 `CSid` 개체 및 관련 특성을 삭제 합니다. `CTokenGroups`

```
void DeleteAll() throw();
```

##  <a name="getcount"></a>  CTokenGroups::GetCount

`CSid` 에`CTokenGroups`포함 된 개체 수를 반환 합니다.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>반환 값

`CTokenGroups` 개체에 포함 된 [CSid](../../atl/reference/csid-class.md) 개체 및 관련 특성의 수를 반환 합니다.

##  <a name="getlength"></a>  CTokenGroups::GetLength

`CTokenGroup` 개체의 크기를 반환 합니다.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>설명

`CTokenGroup` 개체의 총 크기 (바이트)를 반환 합니다.

##  <a name="getptoken_groups"></a>  CTokenGroups::GetPTOKEN_GROUPS

`TOKEN_GROUPS` 구조체에 대 한 포인터를 검색 합니다.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>반환 값

`CTokenGroups` 액세스 토큰 개체에 속하는 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) 구조체에 대 한 포인터를 검색 합니다.

##  <a name="getsidsandattributes"></a>  CTokenGroups::GetSidsAndAttributes

개체를 검색 하 고 선택적으로 `CTokenGroups` 개체에 속한 특성을 검색 합니다. `CSid`

```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSids*<br/>
[CSid](../../atl/reference/csid-class.md) 개체의 배열에 대 한 포인터입니다.

*pAttributes*<br/>
Dword 배열에 대 한 포인터입니다. 이 매개 변수를 생략 하거나 NULL을 지정 하면 특성이 검색 되지 않습니다.

### <a name="remarks"></a>설명

이 메서드는 `CTokenGroups` 개체에 포함 된 `CSid` 모든 개체를 열거 하 고 배열 개체에 특성 플래그를 추가 합니다 (선택 사항).

##  <a name="lookupsid"></a>  CTokenGroups::LookupSid

`CSid` 개체와 연결 된 특성을 검색 합니다.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md) 개체입니다.

*pdwAttributes*<br/>
`CSid` 개체의 특성을 허용 하는 DWORD에 대 한 포인터입니다. 생략 하거나 NULL 인 경우에는 특성이 검색 되지 않습니다.

### <a name="return-value"></a>반환 값

`CSid` 이 있으면 true를 반환 하 고, 그렇지 않으면 false를 반환 합니다.

### <a name="remarks"></a>설명

*Pdwattributes* 를 NULL로 설정 하면 특성에 액세스 `CSid` 하지 않고의 존재를 확인 하는 방법을 제공 합니다. 이 메서드는 액세스 권한을 확인 하는 데 사용 하면 안 됩니다. 응용 프로그램에서 [CAccessToken:: CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) 메서드를 대신 사용 해야 합니다.

##  <a name="operator_eq"></a>  CTokenGroups::operator =

대입 연산자입니다.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
`CTokenGroups` 개체에 할당할 `CTokenGroups`개체 또는 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) 구조체입니다.

### <a name="return-value"></a>반환 값

업데이트 `CTokenGroups` 된 개체를 반환 합니다.

##  <a name="operator_const_token_groups__star"></a>CTokenGroups:: operator const TOKEN_GROUPS *

`TOKEN_GROUPS` 구조체에 대 한 포인터로 값을 캐스팅 합니다.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>설명

[TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-token_groups) 구조체에 대 한 포인터로 값을 캐스팅 합니다.

## <a name="see-also"></a>참고자료

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[CSid 클래스](../../atl/reference/csid-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
