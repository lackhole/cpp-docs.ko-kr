---
title: CTokenPrivileges 클래스
ms.date: 11/04/2016
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 5f8379d20d8c8d525cd645e1d4aa0c751e16f531
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915527"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges 클래스

이 클래스는 `TOKEN_PRIVILEGES` 구조체에 대 한 래퍼입니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CTokenPrivileges
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|생성자입니다.|
|[CTokenPrivileges::~CTokenPrivileges](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CTokenPrivileges::Add](#add)|`CTokenPrivileges` 개체에 하나 이상의 권한을 추가 합니다.|
|[CTokenPrivileges::Delete](#delete)|`CTokenPrivileges` 개체에서 권한을 삭제 합니다.|
|[CTokenPrivileges::DeleteAll](#deleteall)|`CTokenPrivileges` 개체에서 모든 권한을 삭제 합니다.|
|[CTokenPrivileges::GetCount](#getcount)|`CTokenPrivileges` 개체의 권한 항목 수를 반환 합니다.|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|`CTokenPrivileges` 개체에 포함 된 권한의 표시 이름을 검색 합니다.|
|[CTokenPrivileges::GetLength](#getlength)|개체에서 나타내는 `TOKEN_PRIVILEGES` 구조체를 보유 하는 데 필요한 버퍼 크기 (바이트)를 반환 합니다. `CTokenPrivileges`|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|`CTokenPrivileges` 개체에서 luid (로컬 고유 식별자) 및 특성 플래그를 검색 합니다.|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|`CTokenPrivileges` 개체에서 권한 이름과 특성 플래그를 검색 합니다.|
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|`TOKEN_PRIVILEGES` 구조체에 대 한 포인터를 반환 합니다.|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|지정 된 권한 이름과 연결 된 특성을 검색 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CTokenPrivileges:: operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|`TOKEN_PRIVILEGES` 구조체에 대 한 포인터로 값을 캐스팅 합니다.|
|[CTokenPrivileges::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

[액세스 토큰](/windows/desktop/SecAuthZ/access-tokens) 은 프로세스나 스레드의 보안 컨텍스트를 설명 하 고 Windows 시스템에 로그온 한 각 사용자에 게 할당 되는 개체입니다.

액세스 토큰은 각 사용자에 게 부여 된 다양 한 보안 권한을 설명 하는 데 사용 됩니다. 권한은 [LUID](/windows/desktop/api/winnt/ns-winnt-luid)(로컬 고유 식별자) 및 설명자 문자열 이라는 64 비트 숫자로 구성 됩니다.

클래스 `CTokenPrivileges` 는 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) 구조체에 대 한 래퍼로 0 개 이상의 권한을 포함 합니다. 제공 된 클래스 메서드를 사용 하 여 권한을 추가, 삭제 또는 쿼리할 수 있습니다.

Windows의 액세스 제어 모델에 대 한 소개는 Windows SDK [Access Control](/windows/desktop/SecAuthZ/access-control) 를 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:.**

##  <a name="add"></a>  CTokenPrivileges::Add

`CTokenPrivileges` 액세스 토큰 개체에 하나 이상의 권한을 추가 합니다.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>매개 변수

*pszPrivilege*<br/>
WINNT에 정의 된 권한 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. H 헤더 파일입니다.

*bEnable*<br/>
True 이면 권한이 사용 됩니다. False 이면 권한이 사용 되지 않습니다.

*rPrivileges*<br/>
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) 구조체에 대 한 참조입니다. 권한 및 특성은이 구조에서 복사 되 고 `CTokenPrivileges` 개체에 추가 됩니다.

### <a name="return-value"></a>반환 값

이 메서드의 첫 번째 형태는 권한이 성공적으로 추가 된 경우 true를 반환 하 고 그렇지 않으면 false를 반환 합니다.

##  <a name="ctokenprivileges"></a>  CTokenPrivileges::CTokenPrivileges

생성자입니다.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
새 개체에 할당할 개체입니다.`CTokenPrivileges`

*rPrivileges*<br/>
새`CTokenPrivileges` 개체에 할당할 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) 구조체입니다.

### <a name="remarks"></a>설명

필요 `CTokenPrivileges` 에 따라 `TOKEN_PRIVILEGES` 구조체 또는 이전에 정의 `CTokenPrivileges` 된 개체를 사용 하 여 개체를 만들 수 있습니다.

##  <a name="dtor"></a>  CTokenPrivileges::~CTokenPrivileges

소멸자입니다.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당 된 리소스를 모두 해제 합니다.

##  <a name="delete"></a>  CTokenPrivileges::Delete

`CTokenPrivileges` 액세스 토큰 개체에서 권한을 삭제 합니다.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>매개 변수

*pszPrivilege*<br/>
WINNT에 정의 된 권한 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. H 헤더 파일입니다. 예를 들어이 매개 변수는 상수 SE_SECURITY_NAME 또는 해당 문자열 "SeSecurityPrivilege"을 지정할 수 있습니다.

### <a name="return-value"></a>반환 값

권한이 성공적으로 삭제 되었으면 true를 반환 하 고, 그렇지 않으면 false를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 제한 된 토큰을 만들기 위한 도구로 유용 합니다.

##  <a name="deleteall"></a>  CTokenPrivileges::DeleteAll

`CTokenPrivileges` 액세스 토큰 개체에서 모든 권한을 삭제 합니다.

```
void DeleteAll() throw();
```

### <a name="remarks"></a>설명

`CTokenPrivileges` 액세스 토큰 개체에 포함 된 모든 권한을 삭제 합니다.

##  <a name="getdisplaynames"></a>  CTokenPrivileges::GetDisplayNames

`CTokenPrivileges` 액세스 토큰 개체에 포함 된 권한의 표시 이름을 검색 합니다.

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pDisplayNames*<br/>
`CString` 개체의 배열에 대한 포인터입니다. `CNames`는 typedef: `CTokenPrivileges::CAtlArray<CString>`로 정의 됩니다.

### <a name="remarks"></a>설명

매개 변수 `pDisplayNames` 는 `CTokenPrivileges` 개체에 포함 된 권한에 해당 `CString` 하는 표시 이름을 받는 개체의 배열에 대 한 포인터입니다. 이 메서드는 WINNT의 정의 된 권한 섹션에 지정 된 권한에 대 한 표시 이름만 검색 합니다. 넣기.

이 메서드는 표시할 수 있는 이름을 검색 합니다. 예를 들어 특성 이름이 SE_REMOTE_SHUTDOWN_NAME 인 경우 표시할 수 있는 이름은 "원격 시스템에서 강제 종료"입니다. 시스템 이름을 가져오려면 [CTokenPrivileges:: GetNamesAndAttributes](#getnamesandattributes)를 사용 합니다.

##  <a name="getcount"></a>  CTokenPrivileges::GetCount

`CTokenPrivileges` 개체의 권한 항목 수를 반환 합니다.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>반환 값

`CTokenPrivileges` 개체에 포함 된 권한 수를 반환 합니다.

##  <a name="getlength"></a>  CTokenPrivileges::GetLength

`CTokenPrivileges` 개체의 길이를 반환 합니다.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>반환 값

포함 된 모든 권한 항목을 포함 하 여 `TOKEN_PRIVILEGES` `CTokenPrivileges` 개체가 나타내는 구조체를 보유 하는 데 필요한 바이트 수를 반환 합니다.

##  <a name="getluidsandattributes"></a>  CTokenPrivileges::GetLuidsAndAttributes

`CTokenPrivileges` 개체에서 luid (로컬 고유 식별자) 및 특성 플래그를 검색 합니다.

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pPrivileges*<br/>
[LUID](/windows/desktop/api/winnt/ns-winnt-luid) 개체의 배열에 대 한 포인터입니다. `CLUIDArray`는로 `CAtlArray<LUID> CLUIDArray`정의 된 typedef입니다.

*pAttributes*<br/>
DWORD 개체의 배열에 대 한 포인터입니다. 이 매개 변수를 생략 하거나 NULL을 지정 하면 특성이 검색 되지 않습니다. `CAttributes`는로 `CAtlArray <DWORD> CAttributes`정의 된 typedef입니다.

### <a name="remarks"></a>설명

이 메서드는 `CTokenPrivileges` 액세스 토큰 개체에 포함 된 모든 권한을 열거 하 고 개별 luid 및 (선택 사항) 특성 플래그를 배열 개체에 저장 합니다.

##  <a name="getnamesandattributes"></a>  CTokenPrivileges::GetNamesAndAttributes

`CTokenPrivileges` 개체에서 이름 및 특성 플래그를 검색 합니다.

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pNames*<br/>
개체의 `CString` 배열에 대 한 포인터입니다. `CNames`는로 `CAtlArray <CString> CNames`정의 된 typedef입니다.

*pAttributes*<br/>
DWORD 개체의 배열에 대 한 포인터입니다. 이 매개 변수를 생략 하거나 NULL을 지정 하면 특성이 검색 되지 않습니다. `CAttributes`는로 `CAtlArray <DWORD> CAttributes`정의 된 typedef입니다.

### <a name="remarks"></a>설명

이 메서드는 `CTokenPrivileges` 개체에 포함 된 모든 권한을 열거 하 고 이름 및 특성 플래그 (선택 사항)를 배열 개체에 배치 합니다.

이 메서드는 표시할 수 있는 이름이 아니라 특성 이름을 검색 합니다. 예를 들어 특성 이름이 SE_REMOTE_SHUTDOWN_NAME 인 경우 시스템 이름은 "SeRemoteShutdownPrivilege"입니다. 표시할 수 있는 이름을 가져오려면 메서드 [CTokenPrivileges:: GetDisplayNames](#getdisplaynames)를 사용 합니다.

##  <a name="getptoken_privileges"></a>  CTokenPrivileges::GetPTOKEN_PRIVILEGES

`TOKEN_PRIVILEGES` 구조체에 대 한 포인터를 반환 합니다.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>반환 값

[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) 구조체에 대 한 포인터를 반환 합니다.

##  <a name="lookupprivilege"></a>  CTokenPrivileges::LookupPrivilege

지정 된 권한 이름과 연결 된 특성을 검색 합니다.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pszPrivilege*<br/>
WINNT에 정의 된 권한 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. H 헤더 파일입니다. 예를 들어이 매개 변수는 상수 SE_SECURITY_NAME 또는 해당 문자열 "SeSecurityPrivilege"을 지정할 수 있습니다.

*pdwAttributes*<br/>
특성을 받는 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

특성이 성공적으로 검색 되 면 true를 반환 하 고, 그렇지 않으면 false를 반환 합니다.

##  <a name="operator_eq"></a>  CTokenPrivileges::operator =

대입 연산자입니다.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rPrivileges*<br/>
`CTokenPrivileges` 개체에 할당할 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) 구조체입니다.

*rhs*<br/>
개체에 할당할 개체입니다. `CTokenPrivileges`

### <a name="return-value"></a>반환 값

업데이트 `CTokenPrivileges` 된 개체를 반환 합니다.

##  <a name="operator_const_token_privileges__star"></a>CTokenPrivileges:: operator const TOKEN_PRIVILEGES\*

`TOKEN_PRIVILEGES` 구조체에 대 한 포인터로 값을 캐스팅 합니다.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>설명

[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges) 구조체에 대 한 포인터로 값을 캐스팅 합니다.

## <a name="see-also"></a>참고자료

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-token_privileges)<br/>
[LUID](/windows/desktop/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/desktop/api/winnt/ns-winnt-luid_and_attributes)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
