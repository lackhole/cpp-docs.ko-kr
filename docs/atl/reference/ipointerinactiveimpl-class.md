---
title: IPointerInactiveImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: d7d9f048fceb3a569b024d7fe2b87f30a828b68e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274830"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl 클래스

이 클래스는 구현 `IUnknown` 하며 [IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) 인터페이스 메서드.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IPointerInactiveImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|개체에 대해 현재 활성화 정책을 검색합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|마우스 포인터 이동이 통해 개체를 나타내는 개체 마우스 이벤트를 발생 시킬 수에 알립니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|비활성 개체에 대 한 마우스 포인터를 설정합니다. ATL 구현 E_NOTIMPL을 반환합니다.|

## <a name="remarks"></a>설명

비활성 개체는 즉 로드 하거나 실행 하기만 하면 됩니다. 현재 개체와 달리 비활성 개체는 Windows 마우스 및 키보드 메시지를 받을 수 없습니다. 따라서 비활성 개체 리소스를 적게 사용 되며 일반적으로 더 효율적입니다.

합니다 [IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) 인터페이스 최소 수준의 비활성을 유지 하면서 마우스 상호 작용을 지원 하기 위해 개체를 사용 합니다. 이 기능은 컨트롤에 대 한 특히 유용합니다.

클래스 `IPointerInactiveImpl` 구현 된 `IPointerInactive` 단순히 E_NOTIMPL을 반환 하 여 메서드. 그러나 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="getactivationpolicy"></a>  IPointerInactiveImpl::GetActivationPolicy

개체에 대해 현재 활성화 정책을 검색합니다.

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IPointerInactive::GetActivationPolicy](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) Windows SDK에에서 있습니다.

##  <a name="oninactivemousemove"></a>  IPointerInactiveImpl::OnInactiveMouseMove

마우스 포인터 이동이 통해 개체를 나타내는 개체 마우스 이벤트를 발생 시킬 수에 알립니다.

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IPointerInactive::OnInactiveMouseMove](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) Windows SDK에에서 있습니다.

##  <a name="oninactivesetcursor"></a>  IPointerInactiveImpl::OnInactiveSetCursor

비활성 개체에 대 한 마우스 포인터를 설정합니다.

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IPointerInactive::OnInactiveSetCursor](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
