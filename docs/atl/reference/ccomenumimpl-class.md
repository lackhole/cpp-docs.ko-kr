---
title: CComEnumImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CComEnumImpl
- ATLCOM/ATL::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::Clone
- ATLCOM/ATL::CComEnumImpl::Init
- ATLCOM/ATL::CComEnumImpl::Next
- ATLCOM/ATL::CComEnumImpl::Reset
- ATLCOM/ATL::CComEnumImpl::Skip
- ATLCOM/ATL::CComEnumImpl::m_begin
- ATLCOM/ATL::CComEnumImpl::m_dwFlags
- ATLCOM/ATL::CComEnumImpl::m_end
- ATLCOM/ATL::CComEnumImpl::m_iter
- ATLCOM/ATL::CComEnumImpl::m_spUnk
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
ms.openlocfilehash: ccd083f3bfd9ae694c97e466fcb40b348fec0c27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259863"
---
# <a name="ccomenumimpl-class"></a>CComEnumImpl 클래스

이 클래스는 열거 되 고 있는 항목을 배열에 저장 되어 있는 COM 열거자 인터페이스에 대 한 구현을 제공 합니다.

## <a name="syntax"></a>구문

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>매개 변수

*Base*<br/>
COM 열거자 인터페이스입니다. 참조 [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) 예입니다.

*piid*<br/>
열거자 인터페이스의 인터페이스 ID에 대 한 포인터입니다.

*T*<br/>
열거자 인터페이스에 의해 노출 되는 항목의 형식입니다.

*복사*<br/>
동종 [복사 정책 클래스](../../atl/atl-copy-policy-classes.md)합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|생성자입니다.|
|[CComEnumImpl::~CComEnumImpl](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComEnumImpl::Clone](#clone)|구현의 합니다 **복제** 열거형 인터페이스 메서드.|
|[CComEnumImpl::Init](#init)|열거자를 초기화합니다.|
|[CComEnumImpl::Next](#next)|구현의 **다음**합니다.|
|[CComEnumImpl::Reset](#reset)|구현의 **재설정**합니다.|
|[CComEnumImpl::Skip](#skip)|구현의 **Skip**합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComEnumImpl::m_begin](#m_begin)|배열의 첫 번째 항목에 대 한 포인터입니다.|
|[CComEnumImpl::m_dwFlags](#m_dwflags)|통해 전달 되는 플래그를 복사 `Init`합니다.|
|[CComEnumImpl::m_end](#m_end)|배열의 마지막 항목 바로 다음 위치에 대 한 포인터입니다.|
|[CComEnumImpl::m_iter](#m_iter)|배열에 현재 항목에 대 한 포인터입니다.|
|[CComEnumImpl::m_spUnk](#m_spunk)|`IUnknown` 열거 되는 컬렉션을 제공 하는 개체의 포인터입니다.|

## <a name="remarks"></a>설명

참조 [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) 메서드 구현의 예입니다. `CComEnumImpl` 열거 되 고 있는 항목을 배열에 저장 되어 있는 COM 열거자 인터페이스에 대 한 구현을 제공 합니다. 이 클래스는 비슷합니다는 `IEnumOnSTLImpl` 열거자 인터페이스의 구현을 제공 하는 클래스를 기반으로 C++ 표준 라이브러리 컨테이너입니다.

> [!NOTE]
>  간의 추가 차이점에 대 한 내용은 `CComEnumImpl` 하 고 `IEnumOnSTLImpl`를 참조 하세요 [CComEnumImpl::Init](#init)합니다.

일반적으로 *되지* 이 인터페이스 구현에서 파생 하 여 사용자 지정 열거자 클래스를 만들어야 합니다. 배열을 기반으로 하는 ATL 제공한 열거자를 사용 하려는 경우 것이 더 일반적의 인스턴스를 만드는 [CComEnum](../../atl/reference/ccomenum-class.md)합니다.

그러나 (예를 들어 하나 열거자 인터페이스 외에 인터페이스를 노출 하는) 사용자 지정 열거자를 제공 해야 수행 하는 경우이 클래스에서 파생할 수 있습니다. 이런 경우 가능성이 재정의 해야 합니다 [CComEnumImpl::Clone](#clone) 고유한 구현을 제공 하는 방법입니다.

자세한 내용은 [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComEnumImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="ccomenumimpl"></a>  CComEnumImpl::CComEnumImpl

생성자입니다.

```
CComEnumImpl();
```

##  <a name="dtor"></a>  CComEnumImpl::~CComEnumImpl

소멸자입니다.

```
~CComEnumImpl();
```

##  <a name="init"></a>  CComEnumImpl::Init

모든 클라이언트에 다시 열거자 인터페이스에 대 한 포인터를 전달 하기 전에이 메서드를 호출 해야 합니다.

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>매개 변수

*begin*<br/>
열거할 항목을 포함 하는 배열의 첫 번째 요소에 대 한 포인터입니다.

*end*<br/>
열거할 항목을 포함 하는 배열의 마지막 요소 바로 다음 위치에 대 한 포인터입니다.

*pUnk*<br/>
[in] `IUnknown` 유지 해야 하는 활성 열거자의 수명 동안 개체의 포인터입니다. 이러한 개체가 없는 경우 NULL을 전달 합니다.

*flags*<br/>
열거자 배열의 소유권을 갖거나 복사본을 확인 해야 여부를 지정 하는 플래그입니다. 가능한 값에 대 한 설명은 다음과 같습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

이 메서드를 한 번만 호출-를 사용 하 여 차례로 버리는 것 열거자를 초기화 합니다.

다른 개체에 저장 된 배열의 항목에 대 한 포인터를 전달 하면 (및 데이터를 복사 하는 열거자를 묻지) 하는 경우 사용할 수 있습니다 합니다 *pUnk* 매개 변수를 개체 및 포함 된 배열 열거자는 동안 사용할 수 있는지 확인 합니다. 해당 해야합니다. 열거자는 단순히 활성화 상태로 유지 하려면 개체에서 COM 참조를 보유 합니다. COM 참조를 열거자 소멸 될 때에 자동으로 해제 됩니다.

합니다 *플래그* 매개 변수를 사용 하면 열거자가 전달 된 배열 요소를 처리 해야 하는 방법을 지정할 수 있습니다. *플래그* 의 값 중 하나를 수행할 수는 `CComEnumFlags` 아래에 표시 된 열거형:

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy` 열거자가 배열의 수명 제어 되지 의미 합니다. 정적 또는 식별 되는 개체 배열 됩니다이 예에서 *pUnk* 가 더 이상 필요 없는 경우 배열을 해제 하는 일을 담당 합니다.

`AtlFlagTakeOwnership` 배열의 소멸 열거자에서 제어할 수 있음을 의미 합니다. 이 경우 배열 할당 되어야 합니다 동적으로 사용 하 여 **새**합니다. 열거자는 해당 소멸자에서 배열을 삭제 됩니다. 일반적으로 NULL에 대 한 전달 *pUnk*하지만 어떤 이유로 열거자의 소멸 알려야 하는 경우에 여전히 유효한 포인터를 전달할 수 있습니다.

`AtlFlagCopy` 새 배열에 전달 된 배열에 복사 하 여 만들어야 함을 의미 `Init`합니다. 새 배열의 수명은 열거자에서 제어할 수 있습니다. 열거자는 해당 소멸자에서 배열을 삭제 됩니다. 일반적으로 NULL에 대 한 전달 *pUnk*하지만 어떤 이유로 열거자의 소멸 알려야 하는 경우에 여전히 유효한 포인터를 전달할 수 있습니다.

> [!NOTE]
>  형식으로 배열 요소를 지정 하는이 메서드의 프로토타입을 `T`여기서 `T` 클래스 템플릿 매개 변수로 정의 되었습니다. COM 인터페이스 메서드를 사용 하 여 노출 되는 동일한 유형 [CComEnumImpl::Next](#next)합니다. 이 여기에 함축 된는 달리 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md),이 클래스는 다른 저장소를 지원 하지 않으며 데이터 형식을 노출 합니다. 배열에서 요소의 데이터 형식과 COM 인터페이스를 통해 노출 된 데이터 형식으로 동일 해야 합니다.

##  <a name="clone"></a>  CComEnumImpl::Clone

이 방법의 구현을 제공 합니다 **클론** 형식의 개체를 만들어 메서드 `CComEnum`, 같은 배열 및 현재 개체에서 사용 하는 반복기를 사용 하 여 초기화 하 고 새로 만든에서 인터페이스를 반환 개체입니다.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>매개 변수

*ppEnum*<br/>
[out] 현재 열거자에서 복제는 새로 만든된 개체에서 열거자 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

복제 된 열거자 하지 확인 자신의 원래 열거자가 사용 되는 데이터의 복사본 (또는 소유권 가져오기). 필요한 경우 복제 열거자 상태로 유지 합니다 원래 열거자 (COM 참조를 사용 하 여)으로 필요한 데이터에 사용할 수 있는 인지 확인 합니다.

##  <a name="m_spunk"></a>  CComEnumImpl::m_spUnk

이 스마트 포인터에 전달 된 개체에 대 한 참조를 유지 관리 [CComEnumImpl::Init](#init), 열거자의 수명 동안 활성 상태로 그대로 확인 합니다.

```
CComPtr<IUnknown> m_spUnk;
```

##  <a name="m_begin"></a>  CComEnumImpl::m_begin

열거할 항목을 포함 하는 배열의 마지막 요소 바로 다음 위치에 대 한 포인터입니다.

```
T* m_begin;
```

##  <a name="m_end"></a>  CComEnumImpl::m_end

열거할 항목을 포함 하는 배열의 첫 번째 요소에 대 한 포인터입니다.

```
T* m_end;
```

##  <a name="m_iter"></a>  CComEnumImpl::m_iter

현재 항목을 열거할 수를 포함 하는 배열 요소의 포인터입니다.

```
T* m_iter;
```

##  <a name="m_dwflags"></a>  CComEnumImpl::m_dwFlags

플래그에 전달 [CComEnumImpl::Init](#init)합니다.

```
DWORD m_dwFlags;
```

##  <a name="next"></a>  CComEnumImpl::Next

이 메서드는 구현을 제공 합니다 **다음** 메서드.

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>매개 변수

*celt*<br/>
[in] 요청 하는 요소의 수입니다.

*rgelt*<br/>
[out] 배열 요소를 사용 하 여 채울 수입니다.

*pceltFetched*<br/>
[out] 에 실제로 반환 된 요소 수가 *rgelt*합니다. 수 미만 *celt* 개 보다 적으면 *celt* 요소 목록에 유지 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="reset"></a>  CComEnumImpl::Reset

이 메서드는 구현을 제공 합니다 **재설정** 메서드.

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="skip"></a>  CComEnumImpl::Skip

이 메서드는 구현을 제공 합니다 **Skip** 메서드.

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>매개 변수

*celt*<br/>
[in] 건너뛸 요소 수입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

E_INVALIDARG를 반환 *celt* 이 0 이면 보다 작으면 S_FALSE를 반환 합니다. *celt* 요소가 반환 됩니다 그렇지 않은 경우는 S_OK를 반환 합니다.

## <a name="see-also"></a>참고자료

[IEnumOnSTLImpl 클래스](../../atl/reference/ienumonstlimpl-class.md)<br/>
[CComEnum 클래스](../../atl/reference/ccomenum-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
