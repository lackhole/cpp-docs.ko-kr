---
title: Module 클래스
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
- module/Microsoft::WRL::Module::Create
- module/Microsoft::WRL::Module::DecrementObjectCount
- module/Microsoft::WRL::Module::GetActivationFactory
- module/Microsoft::WRL::Module::GetClassObject
- module/Microsoft::WRL::Module::GetModule
- module/Microsoft::WRL::Module::GetObjectCount
- module/Microsoft::WRL::Module::IncrementObjectCount
- module/Microsoft::WRL::Module::Module
- module/Microsoft::WRL::Module::objectCount_Data
- module/Microsoft::WRL::Module::RegisterCOMObject
- module/Microsoft::WRL::Module::RegisterObjects
- module/Microsoft::WRL::Module::RegisterWinRTObject
- module/Microsoft::WRL::Module::releaseNotifier_
- module/Microsoft::WRL::Module::Terminate
- module/Microsoft::WRL::Module::~Module
- module/Microsoft::WRL::Module::UnregisterCOMObject
- module/Microsoft::WRL::Module::UnregisterObjects
- module/Microsoft::WRL::Module::UnregisterWinRTObject
helpviewer_keywords:
- Microsoft::WRL::Module class
- Microsoft::WRL::Module::Create method
- Microsoft::WRL::Module::DecrementObjectCount method
- Microsoft::WRL::Module::GetActivationFactory method
- Microsoft::WRL::Module::GetClassObject method
- Microsoft::WRL::Module::GetModule method
- Microsoft::WRL::Module::GetObjectCount method
- Microsoft::WRL::Module::IncrementObjectCount method
- Microsoft::WRL::Module::Module, constructor
- Microsoft::WRL::Module::objectCount_ data member
- Microsoft::WRL::Module::RegisterCOMObject method
- Microsoft::WRL::Module::RegisterObjects method
- Microsoft::WRL::Module::RegisterWinRTObject method
- Microsoft::WRL::Module::releaseNotifier_ data member
- Microsoft::WRL::Module::Terminate method
- Microsoft::WRL::Module::~Module, destructor
- Microsoft::WRL::Module::UnregisterCOMObject method
- Microsoft::WRL::Module::UnregisterObjects method
- Microsoft::WRL::Module::UnregisterWinRTObject method
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
ms.openlocfilehash: db3eb123382ac70f6198d094c5eb3fe44d3bbcd9
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345795"
---
# <a name="module-class"></a>Module 클래스

관련된 개체의 컬렉션을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>매개 변수

*moduleType*<br/>
하나 이상의 조합 [ModuleType](moduletype-enumeration.md) 열거형 값입니다.

## <a name="members"></a>멤버

### <a name="protected-classes"></a>보호 된 클래스

이름                                                                                | 설명
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Module::GenericReleaseNotifier](module-genericreleasenotifier-class.md) | 현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기는 람다, 함수 또는 함수 포인터에 의해 지정됩니다.
[Module::MethodReleaseNotifier](module-methodreleasenotifier-class.md)   | 현재 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다. 이벤트 처리기 개체와 해당 포인터를-a-메서드 멤버 지정 됩니다.
[Module::ReleaseNotifier](module-releasenotifier-class.md)               | 모듈의 마지막 개체가 해제될 때 이벤트 처리기를 호출합니다.

### <a name="public-constructors"></a>Public 생성자

이름                             | 설명
-------------------------------- | -----------------------------------------------------------
[Module::~Module](#tilde-module) | 현재 인스턴스를 초기화 해제는 `Module` 클래스입니다.

### <a name="protected-constructors"></a>Protected 생성자

이름                      | 설명
------------------------- | ---------------------------------------------------
[Module::Module](#module) | `Module` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

이름                                                    | 설명
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Module::Create](#create)                               | 모듈의 인스턴스를 만듭니다.
[Module::DecrementObjectCount](#decrementobjectcount)   | 모듈에서 추적하는 개체 수를 줄입니다.
[Module::GetActivationFactory](#getactivationfactory)   | 모듈에 대한 활성화 팩터리를 가져옵니다.
[Module::GetClassObject](#getclassobject)               | 클래스 팩터리의 캐시를 검색합니다.
[Module::GetModule](#getmodule)                         | 모듈의 인스턴스를 만듭니다.
[Module::GetObjectCount](#getobjectcount)               | 이 모듈에서 관리되는 개체 수를 가져옵니다.
[Module::IncrementObjectCount](#incrementobjectcount)   | 모듈에서 추적하는 개체 수를 늘립니다.
[Module::RegisterCOMObject](#registercomobject)         | 다른 응용 프로그램이 COM 개체에 연결할 수 있도록 이 개체를 하나 이상 등록합니다.
[Module::RegisterObjects](#registerobjects)             | 다른 응용 프로그램에 연결할 수 있도록 COM 또는 Windows 런타임 개체를 등록 합니다.
[Module::RegisterWinRTObject](#registerwinrtobject)     | 다른 응용 프로그램에 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 합니다.
[Module::Terminate](#terminate)                         | 모듈에 의해 인스턴스화되는 모든 팩터리가 종료됩니다.
[Module::UnregisterCOMObject](#unregistercomobject)     | 다른 응용 프로그램에서 COM 개체에 연결할 수 없도록 하나 이상의 COM 개체의 등록을 취소합니다.
[Module::UnregisterObjects](#unregisterobjects)         | 다른 응용 프로그램에서 지정된 모듈의 개체에 연결할 수 없도록 이 개체의 등록을 취소합니다.
[Module::UnregisterWinRTObject](#unregisterwinrtobject) | 다른 응용 프로그램과 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 취소 합니다.

### <a name="protected-methods"></a>Protected 메서드

이름                      | 설명
------------------------- | --------------------------------
[Module::Create](#create) | 모듈의 인스턴스를 만듭니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

이름                                         | 설명
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Module::objectCount_](#objectcount)         | 얼마나 많은 클래스가 사용 하 여 만든 추적 합니다는 [있도록](make-function.md) 함수입니다.
[Module::releaseNotifier_](#releasenotifier) | 에 대 한 포인터를 보유 한 `ReleaseNotifier` 개체입니다.

### <a name="macros"></a>매크로

이름 | 설명-----| --- [ActivatableClass](activatableclass-macros.md) |  지정된 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다. 이 매크로 기본 팩터리 및 그룹 ID 매개 변수를 지정합니다.
[ActivatableClassWithFactory](activatableclass-macros.md) | 지정된 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다. 이 매크로 사용 하면 특정 factory 매개 변수를 지정할 수 있습니다.
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | 지정된 된 클래스의 인스턴스를 만들 수 있는 팩터리를 포함 하는 내부 캐시를 채웁니다. 이 매크로 사용 하면 특정 팩터리 및 그룹 ID 매개 변수를 지정할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="tilde-module"></a>Module::~Module

현재 인스턴스를 초기화 해제는 `Module` 클래스입니다.

```cpp
virtual ~Module();
```

## <a name="create"></a>Module::Create

모듈의 인스턴스를 만듭니다.

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
모듈 유형입니다.

*callback*<br/>
모듈의 마지막 인스턴스 개체가 해제 될 때 호출 됩니다.

*object*<br/>
합니다 *개체* 하 고 *메서드* 조합 하 여 매개 변수를 사용 합니다. 요소 마지막 인스턴스 개체 모듈의 마지막 인스턴스 개체가 해제 될 때입니다.

*method*<br/>
합니다 *개체* 하 고 *메서드* 조합 하 여 매개 변수를 사용 합니다. 모듈의 마지막 인스턴스 개체가 해제 될 때 마지막 인스턴스 개체의 메서드를 가리킵니다.

### <a name="return-value"></a>반환 값

모듈에 대 한 참조입니다.

## <a name="decrementobjectcount"></a>Module::DecrementObjectCount

모듈에서 추적하는 개체 수를 줄입니다.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>반환 값

감소 작업 전 수입니다.

## <a name="getactivationfactory"></a>Module::GetActivationFactory

모듈에 대한 활성화 팩터리를 가져옵니다.

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>매개 변수

*pActivatibleClassId*<br/>
런타임 클래스의 IID입니다.

*ppIFactory*<br/>
지정된 런타임 클래스에 대한 IActivationFactory입니다.

*serverName*<br/>
현재 모듈의 클래스 팩터리 하위 집합 이름입니다. 에 사용 되는 서버 이름을 지정 합니다 [ActivatableClassWithFactoryEx](activatableclass-macros.md) 매크로 지정 하거나 `nullptr` 기본 서버 이름을 가져올 수 합니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 GetActivationFactory에서 반환된 HRESULT입니다.

## <a name="getclassobject"></a>Module::GetClassObject

클래스 팩터리의 캐시를 가져옵니다.

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
클래스 ID입니다.

*riid*<br/>
요청하는 인터페이스 ID입니다.

*ppv*<br/>
반환된 개체에 대한 포인터입니다.

*serverName*<br/>
`ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx` 또는 `ActivatableClass` 매크로에 지정된 서버 이름 또는 기본 서버 이름을 가져오는 `nullptr`입니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

Windows 런타임이 아닌 COM에만이 메서드를 사용 합니다. 이 메서드는만 노출 `IClassFactory` 메서드.

## <a name="getmodule"></a>Module::GetModule

모듈의 인스턴스를 만듭니다.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>반환 값

모듈에 대한 참조입니다.

## <a name="getobjectcount"></a>Module::GetObjectCount

이 모듈에서 관리되는 개체 수를 가져옵니다.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>반환 값

이 모듈에서 관리되는 현재 개체 수입니다.

## <a name="incrementobjectcount"></a>Module::IncrementObjectCount

모듈에서 추적하는 개체 수를 늘립니다.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>반환 값

증가 연산 전 수입니다.

## <a name="module"></a>Module::Module

`Module` 클래스의 새 인스턴스를 초기화합니다.

```cpp
Module();
```

### <a name="remarks"></a>설명

이 생성자가 보호되고 `new` 키워드로 호출할 수 없습니다. 대신, 호출 [module:: getmodule](#getmodule) 하거나 [module:: create](#create)합니다.

## <a name="objectcount"></a>Module::objectCount_

얼마나 많은 클래스가 사용 하 여 만든 추적 합니다는 [있도록](make-function.md) 함수입니다.

```cpp
volatile long objectCount_;
```

## <a name="registercomobject"></a>Module::RegisterCOMObject

다른 응용 프로그램이 COM 개체에 연결할 수 있도록 이 개체를 하나 이상 등록합니다.

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);
```

### <a name="parameters"></a>매개 변수

*serverName*<br/>
서버의 정규화된 이름입니다.

*clsids*<br/>
등록할 CLSID의 배열입니다.

*factories*<br/>
가용성을 게시하고 있는 클래스 개체의 IUnknown 인터페이스 배열입니다.

*cookies*<br/>
작업이 완료되면 등록된 클래스 개체를 식별하는 값에 대한 포인터 배열입니다. 이러한 값은 나중에 등록을 해지하는 데 사용됩니다.

*count*<br/>
등록할 CLSID 수입니다.

### <a name="return-value"></a>반환 값

성공할 경우 S_OK이고, 그렇지 않으면 작업에 실패한 이유를 나타내는 CO_E_OBJISREG와 같은 HRESULT가 발생합니다.

### <a name="remarks"></a>설명

COM 개체는 CLSCTX 열거형의 CLSCTX_LOCAL_SERVER 열거자를 사용하여 등록됩니다.

현재는 결합 하 여 등록된 된 개체에는 연결 유형을 지정 *comflag* 템플릿 매개 변수 및 REGCLS 열거형의 열거자입니다.

## <a name="registerobjects"></a>Module::RegisterObjects

다른 응용 프로그램에 연결할 수 있도록 COM 또는 Windows 런타임 개체를 등록 합니다.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>매개 변수

*module*<br/>
COM 또는 Windows 런타임 개체의 배열입니다.

*serverName*<br/>
개체를 생성한 서버의 이름입니다.

### <a name="return-value"></a>반환 값

성공 시 S_OK이고, 그렇지 않으면 작업이 실패한 이유를 나타내는 HRESULT입니다.

## <a name="registerwinrtobject"></a>Module::RegisterWinRTObject

다른 응용 프로그램에 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 합니다.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>매개 변수

*serverName*<br/>
이 작업으로 영향을 받는 개체의 하위 집합을 지정하는 이름입니다.

*activatableClassIds*<br/>
등록할 활성화 가능한 CLSID 배열입니다.

*cookie*<br/>
등록된 클래스 개체를 식별하는 값입니다. 이 값은 나중에 등록을 해지할 때 사용됩니다.

*count*<br/>
등록할 개체의 수입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고 그렇지 않으면 작업에 실패한 이유를 나타내는 CO_E_OBJISREG와 같은 HRESULT 오류가 발생합니다.

## <a name="releasenotifier"></a>Module::releaseNotifier_

에 대 한 포인터를 보유 한 `ReleaseNotifier` 개체입니다.

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="terminate"></a>Module::Terminate

모듈에 의해 인스턴스화되는 모든 팩터리가 종료됩니다.

```cpp
void Terminate();
```

### <a name="remarks"></a>설명

캐시에서 팩터리를 해제합니다.

## <a name="unregistercomobject"></a>Module::UnregisterCOMObject

다른 응용 프로그램에서 COM 개체에 연결할 수 없도록 하나 이상의 COM 개체의 등록을 취소합니다.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>매개 변수

*serverName*<br/>
(사용되지 않음)

*cookies*<br/>
등록 취소한 클래스 개체를 식별하는 값에 대한 포인터 배열입니다. 배열에서 만든 합니다 [RegisterCOMObject](#registercomobject) 메서드.

*count*<br/>
등록 취소할 클래스 수입니다.

### <a name="return-value"></a>반환 값

이 작업에 성공하면 S_OK이고, 그렇지 않으면 작업에 실패한 이유를 나타내는 HRESULT 오류가 발생합니다.

## <a name="unregisterobjects"></a>Module::UnregisterObjects

다른 응용 프로그램에서 지정된 모듈의 개체에 연결할 수 없도록 이 개체의 등록을 취소합니다.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>매개 변수

*module*<br/>
모듈에 대한 포인터입니다.

*serverName*<br/>
이 작업으로 영향을 받는 개체의 하위 집합을 지정하는 정규화 이름입니다.

### <a name="return-value"></a>반환 값

이 작업에 성공하면 S_OK이고, 그렇지 않으면 이 작업에 실패한 이유를 나타내는 HRESULT 오류가 발생합니다.

## <a name="unregisterwinrtobject"></a>Module::UnregisterWinRTObject

다른 응용 프로그램과 연결할 수 있도록 하나 이상의 Windows 런타임 개체를 등록 취소 합니다.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>매개 변수

*cookie*<br/>
등록이 해지된 클래스 개체를 식별하는 값에 대한 포인터입니다.
