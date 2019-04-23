---
title: SimpleActivationFactory 클래스
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 1831a816d0967c2ca53f941128639ea368c1b727
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785748"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory 클래스

Windows 런타임 또는 클래식 COM 기본 클래스를 만드는 기본적인 메커니즘을 제공합니다.

## <a name="syntax"></a>구문

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>매개 변수

*Base*<br/>
기본 클래스입니다.

## <a name="remarks"></a>설명

기본 클래스 기본 생성자를 제공 해야 합니다.

다음 코드 예제와 SimpleActivationFactory를 사용 하는 방법에 설명 합니다 [ActivatableClassWithFactoryEx](activatableclass-macros.md) 매크로입니다.

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance 메서드](#activateinstance)|지정된 된 인터페이스의 인스턴스를 만듭니다.|
|[SimpleActivationFactory::GetRuntimeClassName 메서드](#getruntimeclassname)|지정한 클래스의 인스턴스는 런타임 클래스 이름을 가져옵니다 합니다 *자료* 클래스 템플릿 매개 변수입니다.|
|[SimpleActivationFactory::GetTrustLevel 메서드](#gettrustlevel)|신뢰 수준에서 지정한 클래스의 인스턴스를 가져옵니다 합니다 *자료* 클래스 템플릿 매개 변수입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

`SimpleActivationFactory`

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="activateinstance"></a>Simpleactivationfactory:: Activateinstance 메서드

지정된 된 인터페이스의 인스턴스를 만듭니다.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>매개 변수

*ppvObject*<br/>
이 작업이 완료 될 때, 지정 된 개체의 인스턴스에 대 한 포인터를 `Base` 클래스 템플릿 매개 변수입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

경우 `__WRL_STRICT__` 가 정의 된 assert 오류가 내보내집니다 클래스 템플릿 매개 변수에서 지정 된 기본 클래스에서 파생 되지 않습니다 [RuntimeClass](runtimeclass-class.md), 또는 WinRt 또는 WinRtClassicComMix를 사용 하 여 구성 되지 않았습니다 [ RuntimeClassType](runtimeclasstype-enumeration.md) 열거형 값입니다.

## <a name="getruntimeclassname"></a>Simpleactivationfactory:: Getruntimeclassname 메서드

런타임 클래스 이름에서 지정한 클래스의 인스턴스를 가져옵니다는 `Base` 클래스 템플릿 매개 변수입니다.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>매개 변수

*runtimeName*<br/>
이 작업이 완료 될 때 런타임 클래스 이름입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

경우 `__WRL_STRICT__` 는 정의 된 assert 오류가 내보내집니다으로 지정 된 클래스를 `Base` 클래스 템플릿 매개 변수에서 파생 되지 않습니다 [RuntimeClass](runtimeclass-class.md), 않거나 WinRt 또는 WinRtClassicComMix 를사용하여구성되지않았습니다[RuntimeClassType](runtimeclasstype-enumeration.md) 열거형 값입니다.

## <a name="gettrustlevel"></a>Simpleactivationfactory:: Gettrustlevel 메서드

신뢰 수준에서 지정한 클래스의 인스턴스를 가져옵니다는 `Base` 클래스 템플릿 매개 변수입니다.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>매개 변수

*trustLvl*<br/>
이 작업이 완료 될 때 현재 클래스 개체의 신뢰 수준입니다.

### <a name="return-value"></a>반환 값

Always S_OK.
