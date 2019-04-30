---
title: DeferrableEventArgs 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::DeferrableEventArgs
- event/Microsoft::WRL::DeferrableEventArgs::GetDeferral
- event/Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished
helpviewer_keywords:
- Microsoft::WRL::DeferrableEventArgs class
- Microsoft::WRL::DeferrableEventArgs::GetDeferral method
- Microsoft::WRL::DeferrableEventArgs::InvokeAllFinished method
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
ms.openlocfilehash: 4a3786e65873d6837389ad4fa5e7d06a14d66460
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398578"
---
# <a name="deferrableeventargs-class"></a>DeferrableEventArgs 클래스

지연에 대한 이벤트 인수 형식에 사용되는 템플릿 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <typename TEventArgsInterface, typename TEventArgsClass>
class DeferrableEventArgs : public TEventArgsInterface;
```

### <a name="parameters"></a>매개 변수

*TEventArgsInterface*<br/>
지연된 이벤트에 대한 인수를 선언하는 인터페이스 형식입니다.

*TEventArgsClass*<br/>
구현 하는 클래스 *TEventArgsInterface*합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

이름                                                         | 설명
------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------
[DeferrableEventArgs::GetDeferral](#getdeferral)             | 에 대 한 참조를 가져옵니다 합니다 [지연](/uwp/api/windows.foundation.deferral) 지연된 된 이벤트를 나타내는 개체입니다.
[DeferrableEventArgs::InvokeAllFinished](#invokeallfinished) | 지연된 이벤트를 처리하는 모든 처리가 완료되었음을 나타내기 위해 호출됩니다.

## <a name="remarks"></a>설명

이 클래스의 인스턴스는 지연된 이벤트에 대한 이벤트 처리기에 전달됩니다. 템플릿 매개 변수는 특정 형식의 지연된 이벤트에 대한 이벤트 인수 세부 정보를 정의하는 인터페이스 및 해당 인터페이스를 구현하는 클래스를 나타냅니다.

클래스는 지연된 이벤트에 대한 이벤트 처리기에 첫 번째 인수로 표시됩니다. 호출할 수 있습니다 합니다 [GetDeferral](#getdeferral) 메서드를 합니다 [지연](/uwp/api/windows.foundation.deferral) 지연 된 이벤트에 대 한 모든 정보를 가져올 수 있는 개체입니다. 이벤트 처리를 완료한 후 Deferral 개체에 대해 Complete를 호출해야 합니다. 호출 해야 [InvokeAllFinished](#invokeallfinished) 끝에 이벤트 처리기 메서드를 확인 하는 모든 지연 된 이벤트의 완료가 제대로 전달 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** Microsoft::WRL

## <a name="getdeferral"></a>DeferrableEventArgs::GetDeferral

에 대 한 참조를 가져옵니다 합니다 [지연](/uwp/api/windows.foundation.deferral) 지연된 된 이벤트를 나타내는 개체입니다.

```cpp
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)
```

### <a name="parameters"></a>매개 변수

*result*<br/>
참조 하는 포인터를 [지연](/uwp/api/windows.foundation.deferral) 호출이 완료 되 면 개체입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="invokeallfinished"></a>DeferrableEventArgs::InvokeAllFinished

지연된 이벤트를 처리하는 모든 처리가 완료되었음을 나타내기 위해 호출됩니다.

```cpp
void InvokeAllFinished()
```

### <a name="remarks"></a>설명

이벤트 원본 호출한 후이 메서드를 호출 해야 [InvokeAll](eventsource-class.md#invokeall)합니다. 이 메서드를 호출하면 추가 지연이 수행되지 않고, 수행된 지연이 없을 경우 완료 처리기가 강제로 실행됩니다.
