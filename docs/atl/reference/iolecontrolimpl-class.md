---
title: IOleControlImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
ms.openlocfilehash: 50119d21b041f37f03ca416a9a56ca9e29ae3344
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276798"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl 클래스

이 클래스의 기본 구현을 제공 합니다 `IOleControl` 인터페이스와 구현 `IUnknown`합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IOleControlImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IOleControlImpl::FreezeEvents](#freezeevents)|컨테이너를 무시 하거나 컨트롤에서 이벤트를 수신 여부를 나타냅니다.|
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|컨트롤의 키보드 동작에 대 한 정보를 채웁니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|컨테이너의 앰비언트 속성 중 하나 이상이 변경 된 컨트롤에 알립니다. ATL 구현은 S_OK를 반환 합니다.|
|[IOleControlImpl::OnMnemonic](#onmnemonic)|사용자가 지정 된 키를 눌렀음을 컨트롤에 알립니다. ATL 구현 E_NOTIMPL을 반환합니다.|

## <a name="remarks"></a>설명

클래스 `IOleControlImpl` 의 기본 구현을 제공 합니다 [IOleControl](/windows/desktop/api/ocidl/nn-ocidl-iolecontrol) 인터페이스와 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents

ATL의 구현에서는 `FreezeEvents` control 클래스의 증가 `m_nFreezeEvents` 데이터 멤버 경우 `bFreeze` TRUE 이며 감소 `m_nFreezeEvents` 경우 `bFreeze` 은 FALSE입니다.

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>설명

`FreezeEvents` S_OK를 반환합니다.

참조 [IOleControl::FreezeEvents](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-freezeevents) Windows SDK에에서 있습니다.

##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo

컨트롤의 키보드 동작에 대 한 정보를 채웁니다.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>설명

참조 [IOleControl:GetControlInfo](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) Windows SDK에에서 있습니다.

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange

컨테이너의 앰비언트 속성 중 하나 이상이 변경 된 컨트롤에 알립니다.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

참조 [IOleControl::OnAmbientPropertyChange](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) Windows SDK에에서 있습니다.

##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic

사용자가 지정 된 키를 눌렀음을 컨트롤에 알립니다.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IOleControl::OnMnemonic](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[IOleObjectImpl 클래스](../../atl/reference/ioleobjectimpl-class.md)<br/>
[ActiveX 컨트롤 인터페이스](/windows/desktop/com/activex-controls-interfaces)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
