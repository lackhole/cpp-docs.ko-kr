---
title: IEnumOnSTLImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
ms.openlocfilehash: 8ff29522351b542d0b674bc173040d4468d00f1c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275271"
---
# <a name="ienumonstlimpl-class"></a>IEnumOnSTLImpl 클래스

이 클래스 정의 기반으로 하는 열거자 인터페이스는 C++ 표준 라이브러리 컬렉션입니다.

## <a name="syntax"></a>구문

```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```

#### <a name="parameters"></a>매개 변수

*Base*<br/>
COM 열거자입니다. 참조 [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) 예입니다.

*piid*<br/>
열거자 인터페이스의 인터페이스 ID에 대 한 포인터입니다.

*T*<br/>
열거자 인터페이스에 의해 노출 되는 항목의 형식입니다.

*복사*<br/>
A [복사 정책 클래스](../../atl/atl-copy-policy-classes.md)합니다.

*CollType*<br/>
C++ 표준 라이브러리 컨테이너 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IEnumOnSTLImpl::Clone](#clone)|구현의 **복제**합니다.|
|[IEnumOnSTLImpl::Init](#init)|열거자를 초기화합니다.|
|[IEnumOnSTLImpl::Next](#next)|구현의 **다음**합니다.|
|[IEnumOnSTLImpl::Reset](#reset)|구현의 **재설정**합니다.|
|[IEnumOnSTLImpl::Skip](#skip)|구현의 **Skip**합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[IEnumOnSTLImpl::m_iter](#m_iter)|컬렉션에서 열거자의 현재 위치를 나타내는 반복기입니다.|
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|에 대 한 포인터를 C++ 항목을 열거할 수를 보유 하는 표준 라이브러리 컨테이너입니다.|
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|`IUnknown` 컬렉션을 제공 하는 개체의 포인터입니다.|

## <a name="remarks"></a>설명

`IEnumOnSTLImpl` 열거 되 고 있는 항목에 저장 되어 있는 COM 열거자 인터페이스에 대 한 구현을 제공 된 C++ 호환 표준 라이브러리 컨테이너입니다. 이 클래스는 비슷합니다는 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) 열거자 인터페이스에 대 한 구현을 제공 하는 클래스 배열을 기반으로 합니다.

> [!NOTE]
>  참조 [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) 간의 추가 차이점에 대 한 자세한 내용은 `CComEnumImpl` 고 `IEnumOnSTLImpl`입니다.

일반적으로 *되지* 이 인터페이스 구현에서 파생 하 여 사용자 지정 열거자 클래스를 만들어야 합니다. ATL 제공한 열거자에 따라 사용 하려는 경우는 C++ 의 인스턴스를 만드는 일반적인 것이 표준 라이브러리 컨테이너 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), 에서파생하여열거자를반환하는컬렉션클래스를만들려면[ ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)합니다.

그러나 (예를 들어 하나 열거자 인터페이스 외에 인터페이스를 노출 하는) 사용자 지정 열거자를 제공 해야 수행 하는 경우이 클래스에서 파생할 수 있습니다. 이런에서 것을 재정의 해야 합니다 [복제](#clone) 고유한 구현을 제공 하는 방법입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`IEnumOnSTLImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="init"></a>  IEnumOnSTLImpl::Init

열거자를 초기화합니다.

```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```

### <a name="parameters"></a>매개 변수

*pUnkForRelease*<br/>
[in] `IUnknown` 유지 해야 하는 활성 열거자의 수명 동안 개체의 포인터입니다. 이러한 개체가 없는 경우 NULL을 전달 합니다.

*collection*<br/>
에 대 한 참조는 C++ 항목을 열거할 수를 보유 하는 표준 라이브러리 컨테이너입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

전달 하는 경우 `Init` 다른 개체에 저장 된 컬렉션에 대 한 참조를 사용할 수는 *pUnkForRelease* 매개 변수를 보유 하는 컬렉션 및 개체를 사용할 수 있는지에 대 한 열거자가 필요할 만큼 합니다.

모든 클라이언트에 다시 열거자 인터페이스에 대 한 포인터를 전달 하기 전에이 메서드를 호출 해야 합니다.

##  <a name="clone"></a>  IEnumOnSTLImpl::Clone

이 방법의 구현을 제공 합니다 **복제** 형식의 개체를 만들어 메서드 `CComEnumOnSTL`, 동일한 컬렉션 및 현재 개체에서 사용 하는 반복기를 사용 하 여 초기화 하 고 인터페이스를 반환 합니다 새로 만든된 개체입니다.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>매개 변수

*ppEnum*<br/>
[out] 현재 열거자에서 복제는 새로 만든된 개체에서 열거자 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="m_spunk"></a>  IEnumOnSTLImpl::m_spUnk

`IUnknown` 컬렉션을 제공 하는 개체의 포인터입니다.

```
CComPtr<IUnknown> m_spUnk;
```

### <a name="remarks"></a>설명

이 스마트 포인터에 전달 된 개체에 대 한 참조를 유지 관리 [IEnumOnSTLImpl::Init](#init), 열거자의 수명 동안 활성 상태로 그대로 확인 합니다.

##  <a name="m_pcollection"></a>  IEnumOnSTLImpl::m_pcollection

이 멤버의 열거자 인터페이스 구현의 주행 데이터를 제공 하는 컬렉션을 가리킵니다.

```
CollType* m_pcollection;
```

### <a name="remarks"></a>설명

이 멤버를 호출 하 여 인스턴스화될 [IEnumOnSTLImpl::Init](#init)합니다.

##  <a name="m_iter"></a>  IEnumOnSTLImpl::m_iter

이 멤버는 컬렉션 내의 현재 위치를 표시 하 고 후속 요소를 이동 하는 데 사용 하는 반복기를 보유 합니다.

```
CollType::iterator m_iter;
```

##  <a name="next"></a>  IEnumOnSTLImpl::Next

이 메서드는 구현을 제공 합니다 **다음** 메서드.

```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```

### <a name="parameters"></a>매개 변수

*celt*<br/>
[in] 요청 하는 요소의 수입니다.

*rgelt*<br/>
[out] 요소로 채워질 배열입니다.

*pceltFetched*<br/>
[out] 에 실제로 반환 된 요소 수가 *rgelt*합니다. 일 수 있습니다 보다 작은 *celt* 개 보다 적으면 *celt* 요소 목록에 남아 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="reset"></a>  IEnumOnSTLImpl::Reset

이 메서드는 구현을 제공 합니다 **재설정** 메서드.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="skip"></a>  IEnumOnSTLImpl::Skip

이 메서드는 구현을 제공 합니다 **Skip** 메서드.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>매개 변수

*celt*<br/>
[in] 건너뛸 요소 수입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
