---
title: CFirePropNotifyEvent 클래스
ms.date: 11/04/2016
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
ms.openlocfilehash: 493bc00708d031f1bf7a4eb74d56e927a9c3f1dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245493"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent 클래스

이 클래스는 컨트롤 속성 변경에 대 한 컨테이너의 싱크를 알리기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CFirePropNotifyEvent
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(정적) 컨테이너의 싱크를 컨트롤 속성이 변경 되었음을 알립니다.|
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(정적) 컨트롤 속성을 변경 하는 컨테이너의 싱크를에 알립니다.|

## <a name="remarks"></a>설명

`CFirePropNotifyEvent` 에 컨트롤 속성 변경 되었거나 변경 되려고 하는 컨테이너의 싱크를 알리는 두 개의 메서드가 있습니다.

컨트롤을 구현 하는 클래스에서 파생 된 경우 `IPropertyNotifySink`서 `CFirePropNotifyEvent` 메서드를 호출할 때 호출 됩니다 `FireOnRequestEdit` 또는 `FireOnChanged`합니다. 컨트롤 클래스에서 파생 되지 않은 경우 `IPropertyNotifySink`, 이러한 함수를 호출 하는 S_OK를 반환 합니다.

컨트롤을 만드는 방법에 대 한 자세한 내용은 참조는 [ATL 자습서](../../atl/active-template-library-atl-tutorial.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged

모든 알립니다 연결 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) (개체의 모든 연결 지점)에 지정 된 개체 속성 변경 된 인터페이스입니다.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 에 대 한 포인터를 `IUnknown` 알림을 보내는 개체입니다.

*dispID*<br/>
[in] 변경 된 속성의 식별자입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

이 함수는 안전 컨트롤 연결 포인트를 지원 하지 않는 경우에 호출 합니다.

##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit

모든 알립니다 연결 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) (개체의 모든 연결 지점)에 지정 된 개체 속성 변경 되려고 하는 인터페이스입니다.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 에 대 한 포인터를 `IUnknown` 알림을 보내는 개체입니다.

*dispID*<br/>
[in] 변경할 속성의 식별자입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

이 함수는 안전 컨트롤 연결 포인트를 지원 하지 않는 경우에 호출 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
