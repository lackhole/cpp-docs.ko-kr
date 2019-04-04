---
title: RuntimeClass 클래스
ms.date: 09/11/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
ms.openlocfilehash: d45fe7c6d794f216da93ffbd95dbb7058d3336f3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785556"
---
# <a name="runtimeclass-class"></a>RuntimeClass 클래스

지정된 된 인터페이스를 상속 하 고 지정 된 Windows 런타임, 클래식 COM 및 약한 참조 지원을 제공 하는 WinRT 또는 COM 클래스를 나타냅니다.

이 클래스의 구현을 제공 하는 클래스 WinRT 및 COM의 상용구 구현을 제공 `QueryInterface`, `AddRef`, `Release` 등 모듈의 참조 횟수를 관리 및 지원에 대 한 클래스 팩터리를 제공 합니다. 활성화할 수 있는 개체입니다.

## <a name="syntax"></a>구문

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>매개 변수

*classFlags*<br/>
선택적 매개 변수입니다. 하나 이상의 조합 [RuntimeClassType](runtimeclasstype-enumeration.md) 열거형 값입니다. `__WRL_CONFIGURATION_LEGACY__` classFlags 프로젝트의 모든 런타임 클래스에 대 한의 기본값을 변경 하려면 매크로 정의할 수 있습니다. 정의 하는 경우에 RuntimeClass 인스턴스는 기본적으로 agile 합니다. 정의 되지 않은 경우 RuntimeClass 인스턴스는 기본적으로 agile입니다. 방지 하려면 모호성 항상 지정 된 `Microsoft::WRL::FtmBase` 에 `TInterfaces` 또는 `RuntimeClassType::InhibitFtmBase`합니다. InhibitFtmBase FtmBase와 개체를 모두 사용 하는 경우 agile 됩니다.

*TInterfaces*<br/>
인터페이스 목록 외 구현 된 개체 `IUnknown`, `IInspectable` 또는 다른 인터페이스에 의해 제어 [RuntimeClassType](runtimeclasstype-enumeration.md)합니다. 다른 클래스에서 특히 파생를 나열할 수 있습니다 `Microsoft::WRL::FtmBase` 개체를 agile 확인을 구현 하면 `IMarshal`합니다.

## <a name="members"></a>멤버

`RuntimeClassInitialize`<br/>
경우에 개체를 초기화 하는 함수는 `MakeAndInitialize` 템플릿 함수는 개체를 만드는 데 사용 됩니다. 초기화에 실패 한 경우 개체가 성공적으로 초기화 된 경우 S_OK 또는 COM 오류 코드를 반환 합니다. COM 오류 코드 반환 값으로 전파 됩니다 `MakeAndInitialize`합니다. 합니다 `RuntimeClassInitialize` 경우에 메서드가 호출 되지 않습니다는 `Make` 템플릿 함수는 개체를 만드는 데 사용 됩니다.

### <a name="public-constructors"></a>Public 생성자

| 이름                                               | 설명                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass::RuntimeClass](#runtimeclass)        | 현재 인스턴스를 초기화 합니다 `RuntimeClass` 클래스입니다.   |
| [RuntimeClass::~RuntimeClass](#tilde-runtimeclass) | 현재 인스턴스를 초기화 해제는 `RuntimeClass` 클래스입니다. |

### <a name="public-methods"></a>Public 메서드

| 이름                                                      | 설명                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass::AddRef](#addref)                           | 현재 참조 횟수를 증가 시킵니다 `RuntimeClass` 개체입니다.                              |
| [RuntimeClass::DecrementReference](#decrementreference)   | 현재 참조 횟수를 감소 `RuntimeClass` 개체입니다.                              |
| [RuntimeClass::GetIids](#getiids)                         | 인터페이스는 현재 구현 하는 Id를 포함할 수 있는 배열을 가져옵니다 `RuntimeClass` 개체입니다. |
| [RuntimeClass::GetRuntimeClassName](#getruntimeclassname) | 현재 런타임 클래스 이름을 가져옵니다 `RuntimeClass` 개체입니다.                                  |
| [RuntimeClass::GetTrustLevel](#gettrustlevel)             | 현재 신뢰 수준을 가져옵니다 `RuntimeClass` 개체입니다.                                         |
| [RuntimeClass::GetWeakReference](#getweakreference)       | 현재에 대 한 약한 참조 개체에 대 한 포인터를 가져옵니다 `RuntimeClass` 개체입니다.                 |
| [RuntimeClass::InternalAddRef](#internaladdref)           | 현재 참조 횟수를 증가 시킵니다 `RuntimeClass` 개체입니다.                               |
| [RuntimeClass::QueryInterface](#queryinterface)           | 지정 된 인터페이스 ID에 대 한 포인터를 검색합니다.                                                 |
| [RuntimeClass::Release](#release)                         | 현재 COM 릴리스 작업을 수행 `RuntimeClass` 개체입니다.                             |

## <a name="inheritance-hierarchy"></a>상속 계층 구조

구현 세부 정보입니다.

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="tilde-runtimeclass"></a>RuntimeClass::~RuntimeClass

현재 인스턴스를 초기화 해제는 `RuntimeClass` 클래스입니다.

```cpp
virtual ~RuntimeClass();
```

## <a name="addref"></a>RuntimeClass::AddRef

현재 참조 횟수를 증가 시킵니다 `RuntimeClass` 개체입니다.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="decrementreference"></a>RuntimeClass::DecrementReference

현재 참조 횟수를 감소 `RuntimeClass` 개체입니다.

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="getiids"></a>RuntimeClass::GetIids

인터페이스는 현재 구현 하는 Id를 포함할 수 있는 배열을 가져옵니다 `RuntimeClass` 개체입니다.

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>매개 변수

*iidCount*<br/>
이 작업이 완료 되 면 배열에 있는 요소의 총 *iid*합니다.

*iids*<br/>
이 작업이 완료될 때 인터페이스 ID 배열에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 E_OUTOFMEMORY입니다.

## <a name="getruntimeclassname"></a>RuntimeClass::GetRuntimeClassName

현재 런타임 클래스 이름을 가져옵니다 `RuntimeClass` 개체입니다.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>매개 변수

*runtimeName*<br/>
이 작업이 완료 될 때 런타임 클래스 이름입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

어설션 오류가 발생 하는 경우에 내보내집니다 `__WRL_STRICT__` 또는 `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` 정의 되어 있지 않습니다.

## <a name="gettrustlevel"></a>RuntimeClass::GetTrustLevel

현재 신뢰 수준을 가져옵니다 `RuntimeClass` 개체입니다.

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>매개 변수

*trustLvl*<br/>
이 작업이 완료 되 면, 현재 신뢰 수준 `RuntimeClass` 개체입니다.

### <a name="return-value"></a>반환 값

Always S_OK.

### <a name="remarks"></a>설명

어설션 오류가 발생 하는 경우에 내보내집니다 `__WRL_STRICT__` 또는 `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` 정의 되어 있지 않습니다.

## <a name="getweakreference"></a>RuntimeClass::GetWeakReference

현재에 대 한 약한 참조 개체에 대 한 포인터를 가져옵니다 `RuntimeClass` 개체입니다.

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>매개 변수

*weakReference*<br/>
이 작업이 완료 될 때 약한 참조 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

Always S_OK.

## <a name="internaladdref"></a>RuntimeClass::InternalAddRef

현재 참조 횟수를 증가 시킵니다 `RuntimeClass` 개체입니다.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>반환 값

결과 참조 수입니다.

## <a name="queryinterface"></a>RuntimeClass::QueryInterface

지정 된 인터페이스 ID에 대 한 포인터를 검색합니다.

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppvObject*<br/>
완료 될 때이 opereation으로 지정한 인터페이스에 대 한 포인터를 *riid* 매개 변수입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="release"></a>RuntimeClass::Release

현재 COM 릴리스 작업을 수행 `RuntimeClass` 개체입니다.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

참조 횟수가 0 인 경우는 `RuntimeClass` 개체가 삭제 됩니다.

## <a name="runtimeclass"></a>RuntimeClass::RuntimeClass

현재 인스턴스를 초기화 합니다 `RuntimeClass` 클래스입니다.

```cpp
RuntimeClass();
```
