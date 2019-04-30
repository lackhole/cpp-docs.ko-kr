---
title: CComDynamicUnkArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: 39f137f199db1d7519801c19375baea6cd08db93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259484"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray 클래스

이 클래스의 배열을 저장 `IUnknown` 포인터입니다.

## <a name="syntax"></a>구문

```
class CComDynamicUnkArray
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|생성자입니다. 컬렉션 값을 NULL 및 컬렉션 크기를 0으로 초기화합니다.|
|[CComDynamicUnkArray::~CComDynamicUnkArray](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComDynamicUnkArray::Add](#add)|이 메서드를 추가 하는 `IUnknown` 배열에 대 한 포인터입니다.|
|[CComDynamicUnkArray::begin](#begin)|첫 번째 포인터를 반환 합니다. `IUnknown` 컬렉션에 대 한 포인터입니다.|
|[CComDynamicUnkArray::clear](#clear)|배열을 비웁니다.|
|[CComDynamicUnkArray::end](#end)|마지막으로 이전 하나에 대 한 포인터를 반환 `IUnknown` 컬렉션에 대 한 포인터입니다.|
|[CComDynamicUnkArray::GetAt](#getat)|지정된 된 인덱스에 요소를 검색 합니다.|
|[CComDynamicUnkArray::GetCookie](#getcookie)|연결 된 쿠키를 가져오려면이 메서드를 호출 하는 지정 된 `IUnknown` 포인터입니다.|
|[CComDynamicUnkArray::GetSize](#getsize)|배열의 길이 반환합니다.|
|[CComDynamicUnkArray::GetUnknown](#getunknown)|이 메서드를 호출 합니다 `IUnknown` 지정 된 쿠키를 사용 하 여 연결 된 포인터입니다.|
|[CComDynamicUnkArray::Remove](#remove)|제거 하려면이 메서드는 `IUnknown` 배열에서 포인터입니다.|

## <a name="remarks"></a>설명

`CComDynamicUnkArray` 동적으로 할당 된 배열을 보유 `IUnknown` 포인터 각 인터페이스에 대 한 연결 지점입니다. `CComDynamicUnkArray` 매개 변수로 사용할 수는 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 템플릿 클래스입니다.

합니다 `CComDynamicUnkArray` 메서드 [시작](#begin) 하 고 [끝](#end) (예: 이벤트가 발생 하는 경우) 모든 연결 지점을 통해 루프를 사용할 수 있습니다.

참조 [개체에 추가 연결 지점을](../../atl/adding-connection-points-to-an-object.md) 연결 생성을 자동화 하는 방법은 프록시를 가리킵니다.

> [!NOTE]
> **참고** 클래스 `CComDynamicUnkArray` 에서 사용 되는 **클래스 추가** 연결점에 있는 컨트롤을 만들 때 마법사. 연결 지점의 수를 수동으로 지정 하려는 경우 해당 참조를 변경 `CComDynamicUnkArray` 하 `CComUnkArray<` *n* `>`여기서 *n* 연결점 수 필수.

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="add"></a>  CComDynamicUnkArray::Add

이 메서드를 추가 하는 `IUnknown` 배열에 대 한 포인터입니다.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
`IUnknown` 배열에 추가에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

새로 추가 된 포인터와 연결 된 쿠키를 반환 합니다.

##  <a name="begin"></a>  CComDynamicUnkArray::begin

컬렉션의 시작 부분에 대 한 포인터를 반환 합니다. `IUnknown` 인터페이스 포인터입니다.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터는 `IUnknown` 인터페이스 포인터입니다.

### <a name="remarks"></a>설명

컬렉션에 로컬로 저장 하는 인터페이스에 대 한 포인터 `IUnknown`합니다. 각 캐스팅 `IUnknown` 실제 인터페이스 형식으로 인터페이스를 통해 호출 합니다. 먼저 인터페이스를 쿼리할 필요가 없습니다.

사용 하기 전에 `IUnknown` 인터페이스를 확인 해야 하 고 NULL이 아닙니다.

##  <a name="clear"></a>  CComDynamicUnkArray::clear

배열을 비웁니다.

```
void clear();
```

##  <a name="ccomdynamicunkarray"></a>  CComDynamicUnkArray::CComDynamicUnkArray

생성자입니다.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>설명

컬렉션 크기를 0으로 설정 하 고 NULL 값을 초기화 합니다. 소멸자는 필요한 경우 컬렉션을 해제 합니다.

##  <a name="dtor"></a>  CComDynamicUnkArray::~CComDynamicUnkArray

소멸자입니다.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>설명

클래스 생성자에 의해 할당 된 리소스를 해제 합니다.

##  <a name="end"></a>  CComDynamicUnkArray::end

마지막으로 이전 하나에 대 한 포인터를 반환 `IUnknown` 컬렉션에 대 한 포인터입니다.

```
IUnknown**
    end();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터는 `IUnknown` 인터페이스 포인터입니다.

##  <a name="getat"></a>  CComDynamicUnkArray::GetAt

지정된 된 인덱스에 요소를 검색 합니다.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
검색할 요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 인터페이스입니다.

##  <a name="getcookie"></a>  CComDynamicUnkArray::GetCookie

연결 된 쿠키를 가져오려면이 메서드를 호출 하는 지정 된 `IUnknown` 포인터입니다.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>매개 변수

*ppFind*<br/>
`IUnknown` 포인터 관련된 쿠키를 필수입니다.

### <a name="return-value"></a>반환 값

연결 된 쿠키를 반환 합니다 `IUnknown` 포인터 또는 일치 하는 경우 0이 `IUnknown` 포인터를 찾을 수 합니다.

### <a name="remarks"></a>설명

동일한 인스턴스가 둘 이상 있으면 `IUnknown` 포인터를이 함수에 대 한 첫 번째 쿠키를 반환 합니다.

##  <a name="getsize"></a>  CComDynamicUnkArray::GetSize

배열의 길이 반환합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>반환 값

배열의 길이입니다.

##  <a name="getunknown"></a>  CComDynamicUnkArray::GetUnknown

이 메서드를 호출 합니다 `IUnknown` 지정 된 쿠키를 사용 하 여 연결 된 포인터입니다.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>매개 변수

*dwCookie*<br/>
쿠키는 연결 된 `IUnknown` 포인터가 필요 합니다.

### <a name="return-value"></a>반환 값

반환 된 `IUnknown` 포인터나 없는 일치 하는 쿠키를 찾을 수 없으면 NULL입니다.

##  <a name="remove"></a>  CComDynamicUnkArray::Remove

제거 하려면이 메서드는 `IUnknown` 배열에서 포인터입니다.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>매개 변수

*dwCookie*<br/>
참조 하는 쿠키를 `IUnknown` 배열에서 제거할 수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

포인터는 제거 하는 경우 TRUE를 반환합니다 그렇지 않으면 FALSE입니다.

## <a name="see-also"></a>참고자료

[CComUnkArray 클래스](../../atl/reference/ccomunkarray-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
