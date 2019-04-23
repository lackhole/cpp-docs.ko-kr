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
ms.openlocfilehash: 934d746dafafb39c2ffc3477c59c95914d270196
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772831"
---
# <a name="ctokengroups-class"></a>CTokenGroups 클래스

이 클래스는에 대 한 래퍼를 `TOKEN_GROUPS` 구조입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

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
|[CTokenGroups::Add](#add)|추가 된 `CSid` 또는 기존 `TOKEN_GROUPS` 구조체를 `CTokenGroups` 개체.|
|[CTokenGroups::Delete](#delete)|삭제를 `CSid` 및 해당 관련된 특성을 `CTokenGroups` 개체입니다.|
|[CTokenGroups::DeleteAll](#deleteall)|모든 삭제 `CSid` 개체 및 관련된 특성에서는 `CTokenGroups` 개체입니다.|
|[CTokenGroups::GetCount](#getcount)|개수를 반환 `CSid` 개체와 연결 된 특성에 포함 된를 `CTokenGroups` 개체입니다.|
|[CTokenGroups::GetLength](#getlength)|크기를 반환 합니다 `CTokenGroups` 개체입니다.|
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|에 대 한 포인터를 검색 합니다 `TOKEN_GROUPS` 구조입니다.|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|검색 된 `CSid` 개체와 특성에 속하는 `CTokenGroups` 개체입니다.|
|[CTokenGroups::LookupSid](#lookupsid)|연관 된 특성 검색을 `CSid` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|캐스트를 `CTokenGroups` 개체에 대 한 포인터를 `TOKEN_GROUPS` 구조입니다.|
|[CTokenGroups::operator =](#operator_eq)|대입 연산자입니다.|

## <a name="remarks"></a>설명

[액세스 토큰](/windows/desktop/SecAuthZ/access-tokens) 개체인 프로세스 또는 스레드의 보안 컨텍스트를 설명 하는 Windows 시스템에 로그온 한 각 사용자에 게 할당 됩니다.

`CTokenGroups` 클래스에 대 한 래퍼인 합니다 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) 그룹 보안 식별자 (Sid) 액세스 토큰에 대 한 정보가 포함 된 구조입니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="add"></a>  CTokenGroups::Add

추가 된 `CSid` 또는 기존 `TOKEN_GROUPS` 구조체를 `CTokenGroups` 개체.

```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
A [CSid](../../atl/reference/csid-class.md) 개체입니다.

*dwAttributes*<br/>
특성을 사용 하 여 연결 된 `CSid` 개체입니다.

*rTokenGroups*<br/>
A [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) 구조입니다.

### <a name="remarks"></a>설명

이러한 메서드는 하나 이상의 추가 `CSid` 개체와 연관 된 특성에는 `CTokenGroups` 개체입니다.

##  <a name="ctokengroups"></a>  CTokenGroups::CTokenGroups

생성자입니다.

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
합니다 `CTokenGroups` 개체 또는 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) 생성 하는 구조를 `CTokenGroups` 개체입니다.

### <a name="remarks"></a>설명

합니다 `CTokenGroups` 를 사용 하 여 개체를 만들 수 있습니다를 `TOKEN_GROUPS` 구조 또는 이전에 정의한 `CTokenGroups` 개체입니다.

##  <a name="dtor"></a>  CTokenGroups::~CTokenGroups

소멸자입니다.

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>설명

소멸자는 할당 된 모든 리소스를 해제합니다.

##  <a name="delete"></a>  CTokenGroups::Delete

삭제를 `CSid` 및 해당 관련된 특성을 `CTokenGroups` 개체입니다.

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
합니다 [CSid](../../atl/reference/csid-class.md) 개체는 보안 식별자 (SID) 및 특성을 제거 해야 합니다.

### <a name="return-value"></a>반환 값

경우 true를 반환 합니다 `CSid` 제거 되 면 false이 고, 그렇지 합니다.

##  <a name="deleteall"></a>  CTokenGroups::DeleteAll

모든 삭제 `CSid` 개체 및 관련된 특성에서는 `CTokenGroups` 개체입니다.

```
void DeleteAll() throw();
```

##  <a name="getcount"></a>  CTokenGroups::GetCount

개수를 반환 `CSid` 에 포함 된 개체 `CTokenGroups`합니다.

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>반환 값

개수를 반환 [CSid](../../atl/reference/csid-class.md) 개체와 연관 된 특성에 포함 된를 `CTokenGroups` 개체입니다.

##  <a name="getlength"></a>  CTokenGroups::GetLength

크기를 반환 합니다 `CTokenGroup` 개체입니다.

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>설명

총 크기를 반환 합니다 `CTokenGroup` 개체 (바이트)에서.

##  <a name="getptoken_groups"></a>  CTokenGroups::GetPTOKEN_GROUPS

에 대 한 포인터를 검색 합니다 `TOKEN_GROUPS` 구조입니다.

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 검색 합니다 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) 구조에 속하는 `CTokenGroups` 액세스 토큰 개체입니다.

##  <a name="getsidsandattributes"></a>  CTokenGroups::GetSidsAndAttributes

검색을 `CSid` 개체 및 (선택 사항)에 속한 특성을 `CTokenGroups` 개체입니다.

```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>매개 변수

*pSids*<br/>
배열에 대 한 포인터 [CSid](../../atl/reference/csid-class.md) 개체입니다.

*pAttributes*<br/>
Dword 배열에 대 한 포인터입니다. 이 매개 변수가 생략 하거나 NULL 인 경우에 특성을 검색 하지 됩니다.

### <a name="remarks"></a>설명

이 메서드는 열거의 모든 합니다 `CSid` 에 포함 된 개체는 `CTokenGroups` 개체 및 배열 개체로 서 (선택 사항) 특성 플래그를 배치 합니다.

##  <a name="lookupsid"></a>  CTokenGroups::LookupSid

연관 된 특성 검색을 `CSid` 개체입니다.

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>매개 변수

*rSid*<br/>
합니다 [CSid](../../atl/reference/csid-class.md) 개체입니다.

*pdwAttributes*<br/>
수락할는 DWORD에 대 한 포인터를 `CSid` 개체의 특성입니다. 생략 하거나 NULL 특성 검색 되지 않습니다.

### <a name="return-value"></a>반환 값

경우 true를 반환 합니다 `CSid` , 있으면 false이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

설정 *pdwAttributes* 에 NULL의 존재 여부를 확인 하는 방법을 제공 합니다 `CSid` 특성에 액세스 하지 않고 있습니다. 이 메서드를 액세스 권한 확인에 사용할 해야 note 합니다. 응용 프로그램을 대신 사용 해야 합니다 [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) 메서드.

##  <a name="operator_eq"></a>  CTokenGroups::operator =

대입 연산자입니다.

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>매개 변수

*rhs*<br/>
합니다 `CTokenGroups` 개체 또는 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) 할당할 구조는 `CTokenGroups` 개체입니다.

### <a name="return-value"></a>반환 값

업데이트 된 반환 `CTokenGroups` 개체입니다.

##  <a name="operator_const_token_groups__star"></a>  CTokenGroups::operator const TOKEN_GROUPS *

에 대 한 포인터에 값을 캐스팅 합니다 `TOKEN_GROUPS` 구조입니다.

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>설명

에 대 한 포인터에 값을 캐스팅 합니다 [TOKEN_GROUPS](/windows/desktop/api/winnt/ns-winnt-_token_groups) 구조입니다.

## <a name="see-also"></a>참고자료

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[CSid 클래스](../../atl/reference/csid-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
