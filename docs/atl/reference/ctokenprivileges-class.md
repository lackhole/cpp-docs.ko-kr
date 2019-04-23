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
ms.openlocfilehash: 8bca3e1d45d0a85d1d4ceac4ffdf7b11091020f6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769318"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges 클래스

이 클래스는에 대 한 래퍼를 `TOKEN_PRIVILEGES` 구조입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

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

|이름|설명|
|----------|-----------------|
|[CTokenPrivileges::Add](#add)|하나 이상의 권한을 추가 `CTokenPrivileges` 개체입니다.|
|[CTokenPrivileges::Delete](#delete)|권한 삭제를 `CTokenPrivileges` 개체입니다.|
|[CTokenPrivileges::DeleteAll](#deleteall)|모든 권한을 삭제는 `CTokenPrivileges` 개체입니다.|
|[CTokenPrivileges::GetCount](#getcount)|권한 항목의 수를 반환 합니다 `CTokenPrivileges` 개체입니다.|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|검색에 포함 된 권한 이름을 표시 합니다 `CTokenPrivileges` 개체입니다.|
|[CTokenPrivileges::GetLength](#getlength)|보유 하는 데 필요한 바이트의 버퍼 크기를 반환 합니다 `TOKEN_PRIVILEGES` 구조를 나타내는 `CTokenPrivileges` 개체입니다.|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|Locally unique identifier (Luid) 및 특성 플래그에서 검색 된 `CTokenPrivileges` 개체입니다.|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|권한 이름 및 특성 플래그를 검색 합니다 `CTokenPrivileges` 개체입니다.|
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|에 대 한 포인터를 반환 합니다 `TOKEN_PRIVILEGES` 구조입니다.|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|지정 된 권한 이름과 연관 된 특성을 검색 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CTokenPrivileges::operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|에 대 한 포인터에 값을 캐스팅 합니다 `TOKEN_PRIVILEGES` 구조입니다.|
|[CTokenPrivileges::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

[액세스 토큰](/windows/desktop/SecAuthZ/access-tokens) 개체인 프로세스 또는 스레드의 보안 컨텍스트를 설명 하는 Windows 시스템에 로그온 한 각 사용자에 게 할당 됩니다.

액세스 토큰은 각 사용자에 게 부여 된 다양 한 보안 권한을 설명 하기 위해 사용 됩니다. 고유한 로컬 식별자 라고 하는 64 비트 숫자의 권한으로 구성 됩니다 ( [LUID](/windows/desktop/api/winnt/ns-winnt-_luid)) 및 설명자 문자열입니다.

합니다 `CTokenPrivileges` 클래스에 대 한 래퍼인 합니다 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) 구조체이 고 0 또는 더 많은 권한이 포함 되어 있습니다. 제공 된 클래스 메서드를 사용 하 여 쿼리 또는 삭제 권한은 추가할 수 있습니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="add"></a>  CTokenPrivileges::Add

하나 이상의 권한을 추가 `CTokenPrivileges` 액세스 토큰 개체입니다.

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>매개 변수

*pszPrivilege*<br/>
WINNT에 정의 된 대로, 권한의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. H 헤더 파일입니다.

*bEnable*<br/>
True 이면 권한이 사용 됩니다. False 이면 권한은 사용할 수 없습니다.

*rPrivileges*<br/>
에 대 한 참조를 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) 구조입니다. 권한 및 특성은이 구조에서 복사 하 고 추가 `CTokenPrivileges` 개체입니다.

### <a name="return-value"></a>반환 값

이 메서드의 첫 번째 폼 권한을 성공적으로 추가 되 면 false이 고, 그렇지 경우 true를 반환 합니다.

##  <a name="ctokenprivileges"></a>  CTokenPrivileges::CTokenPrivileges

생성자입니다.

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
`CTokenPrivileges` 새 개체에 할당 하는 개체입니다.

*rPrivileges*<br/>
합니다 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) 구조에 새 할당할 `CTokenPrivileges` 개체입니다.

### <a name="remarks"></a>설명

합니다 `CTokenPrivileges` 를 사용 하 여 개체를 만들 수 있습니다를 `TOKEN_PRIVILEGES` 구조 또는 이전에 정의한 `CTokenPrivileges` 개체입니다.

##  <a name="dtor"></a>  CTokenPrivileges::~CTokenPrivileges

소멸자입니다.

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당 된 모든 리소스를 해제합니다.

##  <a name="delete"></a>  CTokenPrivileges::Delete

권한 삭제를 `CTokenPrivileges` 액세스 토큰 개체입니다.

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>매개 변수

*pszPrivilege*<br/>
WINNT에 정의 된 대로, 권한의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. H 헤더 파일입니다. 이 매개 변수를 상수 SE_SECURITY_NAME, 또는 해당 문자열을 "SeSecurityPrivilege." 지정할 수는 예를 들어,

### <a name="return-value"></a>반환 값

권한을 삭제 했습니다.이 고, false가 그렇지 않은 경우 true를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 제한 된 토큰을 만들기 위한 도구로 유용 합니다.

##  <a name="deleteall"></a>  CTokenPrivileges::DeleteAll

모든 권한을 삭제는 `CTokenPrivileges` 액세스 토큰 개체입니다.

```
void DeleteAll() throw();
```

### <a name="remarks"></a>설명

에 포함 된 모든 권한을 삭제는 `CTokenPrivileges` 액세스 토큰 개체입니다.

##  <a name="getdisplaynames"></a>  CTokenPrivileges::GetDisplayNames

검색에 포함 된 권한 이름을 표시 합니다 `CTokenPrivileges` 액세스 토큰 개체입니다.

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pDisplayNames*<br/>
`CString` 개체의 배열에 대한 포인터입니다. `CNames` typedef로 정의 됩니다. `CTokenPrivileges::CAtlArray<CString>`합니다.

### <a name="remarks"></a>설명

매개 변수 `pDisplayNames` 배열에 대 한 포인터가 `CString` 에 포함 된 권한으로 해당 표시 이름을 수신 하는 개체는 `CTokenPrivileges` 개체입니다. 이 메서드는 WINNT의 권한 정의 섹션에 지정 된 권한 표시 이름만 검색 합니다. 8.

이 메서드를 표시할 수 있는 이름을 검색 합니다: 예를 들어, 특성 이름 SE_REMOTE_SHUTDOWN_NAME 인 경우 표시할 수 있는 이름은 "원격 시스템에서 강제 종료 합니다." 시스템 이름을 가져오려면 [CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)합니다.

##  <a name="getcount"></a>  CTokenPrivileges::GetCount

권한 항목의 수를 반환 합니다 `CTokenPrivileges` 개체입니다.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>반환 값

에 포함 된 권한 수를 반환 합니다 `CTokenPrivileges` 개체입니다.

##  <a name="getlength"></a>  CTokenPrivileges::GetLength

길이 반환 합니다 `CTokenPrivileges` 개체입니다.

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>반환 값

보유 하는 데 필요한 바이트 수를 반환 합니다는 `TOKEN_PRIVILEGES` 구조를 나타내는 `CTokenPrivileges` 개체에 포함 된 권한 항목을 모두 포함 합니다.

##  <a name="getluidsandattributes"></a>  CTokenPrivileges::GetLuidsAndAttributes

Locally unique identifier (Luid) 및 특성 플래그에서 검색 된 `CTokenPrivileges` 개체입니다.

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pPrivileges*<br/>
배열에 대 한 포인터 [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) 개체입니다. `CLUIDArray` 로 정의 된 typedef `CAtlArray<LUID> CLUIDArray`합니다.

*pAttributes*<br/>
DWORD 개체의 배열에 대 한 포인터입니다. 이 매개 변수가 생략 하거나 NULL 인 경우에 특성을 검색 하지 됩니다. `CAttributes` 로 정의 된 typedef `CAtlArray <DWORD> CAttributes`합니다.

### <a name="remarks"></a>설명

이 메서드는 모두에 포함 된 권한의 열거를 `CTokenPrivileges` 토큰 개체를 액세스 하 고 개별 Luid 및 (선택 사항) 특성 플래그 배열 개체를 배치 합니다.

##  <a name="getnamesandattributes"></a>  CTokenPrivileges::GetNamesAndAttributes

이름 및 특성 플래그를 검색 합니다 `CTokenPrivileges` 개체입니다.

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pNames*<br/>
배열에 대 한 포인터 `CString` 개체입니다. `CNames` 로 정의 된 typedef `CAtlArray <CString> CNames`합니다.

*pAttributes*<br/>
DWORD 개체의 배열에 대 한 포인터입니다. 이 매개 변수가 생략 하거나 NULL 인 경우에 특성을 검색 하지 됩니다. `CAttributes` 로 정의 된 typedef `CAtlArray <DWORD> CAttributes`합니다.

### <a name="remarks"></a>설명

이 메서드는 모두에 포함 된 권한의 열거를 `CTokenPrivileges` 개체, 배열 개체를 이름 및 특성 플래그 (옵션)를 배치 합니다.

이 메서드를 표시할 수 있는 이름 대신 특성 이름을 검색 합니다: 예를 들어 특성 이름은 SE_REMOTE_SHUTDOWN_NAME 시스템 이름이 "SeRemoteShutdownPrivilege." 메서드를 사용 하 여 표시할 수 있는 이름을 가져오려면 [CTokenPrivileges::GetDisplayNames](#getdisplaynames)합니다.

##  <a name="getptoken_privileges"></a>  CTokenPrivileges::GetPTOKEN_PRIVILEGES

에 대 한 포인터를 반환 합니다 `TOKEN_PRIVILEGES` 구조입니다.

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 반환 합니다 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) 구조입니다.

##  <a name="lookupprivilege"></a>  CTokenPrivileges::LookupPrivilege

지정 된 권한 이름과 연관 된 특성을 검색 합니다.

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pszPrivilege*<br/>
WINNT에 정의 된 대로, 권한의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. H 헤더 파일입니다. 이 매개 변수를 상수 SE_SECURITY_NAME, 또는 해당 문자열을 "SeSecurityPrivilege." 지정할 수는 예를 들어,

*pdwAttributes*<br/>
특성을 수신 하는 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

그렇지 않으면 특성은 false를 성공적으로 검색 하는 경우 true를 반환 합니다.

##  <a name="operator_eq"></a>  CTokenPrivileges::operator =

대입 연산자입니다.

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rPrivileges*<br/>
합니다 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) 할당할 구조는 `CTokenPrivileges` 개체입니다.

*rhs*<br/>
`CTokenPrivileges` 개체에 할당할 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CTokenPrivileges` 개체입니다.

##  <a name="operator_const_token_privileges__star"></a>  CTokenPrivileges::operator const TOKEN_PRIVILEGES \*

에 대 한 포인터에 값을 캐스팅 합니다 `TOKEN_PRIVILEGES` 구조입니다.

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>설명

에 대 한 포인터에 값을 캐스팅 합니다 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges) 구조입니다.

## <a name="see-also"></a>참고자료

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)<br/>
[LUID](/windows/desktop/api/winnt/ns-winnt-_luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
