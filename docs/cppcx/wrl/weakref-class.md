---
title: WeakRef 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
ms.openlocfilehash: 9616fcffac0b92d5ac6d96cfe5f4119f3a3b180f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785508"
---
# <a name="weakref-class"></a>WeakRef 클래스

클래식 COM이 아닌 Windows 런타임에서만 사용할 수 있는 *약한 참조* 를 나타냅니다. 약한 참조는 액세스할 수 있거나 액세스할 수 없는 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class WeakRef : public ComPtr<IWeakReference>;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[WeakRef::WeakRef 생성자](#weakref)|`WeakRef` 클래스의 새 인스턴스를 초기화합니다.|
|[WeakRef::~WeakRef 소멸자](#tilde-weakref)|현재 인스턴스를 초기화 해제는 `WeakRef` 클래스입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[WeakRef::As 메서드](#as)|지정 된 `ComPtr` 포인터 매개 변수를 지정된 된 인터페이스를 나타냅니다.|
|[WeakRef::AsIID 메서드](#asiid)|지정 된 `ComPtr` 포인터 매개 변수를 나타내는 지정 된 인터페이스 id입니다.|
|[WeakRef::CopyTo 메서드](#copyto)|사용 가능한 경우 지정된 포인터 변수에 인터페이스에 대한 포인터를 할당합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[WeakRef::operator& 연산자](#operator-ampersand-operator)|반환 된 `ComPtrRef` 현재를 나타내는 개체 `WeakRef` 개체입니다.|

## <a name="remarks"></a>설명

A `WeakRef` 개체를 유지 관리를 *강한 참조*, 개체와 관련이 있으며 올바르지 않거나 잘못 된 일 수 있습니다. 호출 된 `As()` 또는 `AsIID()` 대 한 강한 참조 하는 방법입니다. 강력한 참조가 유효한 경우 연결된 개체에 액세스할 수 있습니다. 강력한 참조가 올바르지 않은 경우(`nullptr`) 연결된 개체에 액세스할 수 없습니다.

`WeakRef` 개체는 일반적으로 외부 스레드나 응용 프로그램에서 제어 하는 개체를 나타내는 데 사용 됩니다. 예를 들어, 생성 된 `WeakRef` 파일 개체에 대 한 참조에서 개체입니다. 파일이 열려 있는 동안 강력한 참조는 유효합니다. 그러나 파일이 닫히면 강력한 참조는 유효하지 않게 됩니다.

Windows 10 SDK에서는 [As](#as), [AsIID](#asiid) 및 [CopyTo](#copyto) 메서드의 동작 변경이 있습니다. 이전에 이러한 방법 중 하나를 호출한 후 확인할 수 있습니다 합니다 `WeakRef` 에 대 한 `nullptr` 경우 강력한 참조를 성공적으로 가져왔는지, 다음 코드 에서처럼 확인 하려면:

```cpp
WeakRef wr;
strongComptrRef.AsWeak(&wr);

// Now suppose that the object strongComPtrRef points to no longer exists
// and the following code tries to get a strong ref from the weak ref:
ComPtr<ISomeInterface> strongRef;
HRESULT hr = wr.As(&strongRef);

// This check won't work with the Windows 10 SDK version of the library.
// Check the input pointer instead.
if(wr == nullptr)
{
    wprintf(L"Couldn’t get strong ref!");
}
```

위의 코드는 Windows 10 SDK(이상)를 사용하는 경우 작동하지 않습니다. 대신에 전달 된 포인터를 확인할 `nullptr`합니다.

```cpp
if (strongRef == nullptr)
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ComPtr`

`WeakRef`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** Microsoft::WRL

## <a name="tilde-weakref"></a>WeakRef:: ~ WeakRef 소멸자

현재 인스턴스를 초기화 해제는 `WeakRef` 클래스입니다.

```cpp
~WeakRef();
```

## <a name="as"></a>Weakref:: As 메서드

지정 된 `ComPtr` 포인터 매개 변수를 지정된 된 인터페이스를 나타냅니다.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* ptr
);

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr
);
```

### <a name="parameters"></a>매개 변수

*U*<br/>
인터페이스 ID입니다.

*ptr*<br/>
이 작업이 완료 되 면 매개 변수를 나타내는 개체 *U*합니다.

### <a name="return-value"></a>반환 값

- 이 작업이 성공 하면 s_ok이 고 이유를 나타내는 HRESULT 그렇지 않으면 작업이 실패 하 고 *ptr* 로 설정 된 `nullptr`합니다.

- 하지만 현재가이 작업이 성공 하면 s_ok이 고, `WeakRef` 개체는 이미 해제 되었습니다. 매개 변수 *ptr* 로 설정 된 `nullptr`합니다.

- 하지만 현재가이 작업이 성공 하면 S_OK `WeakRef` 개체 매개 변수에서 파생 되지 않은 *U*합니다. 매개 변수 *ptr* 로 설정 된 `nullptr`합니다.

### <a name="remarks"></a>설명

오류가 발생 하는 경우에 내보내집니다 매개 변수 *U* 됩니다 `IWeakReference`에서 파생 되지 않은 또는 `IInspectable`합니다.

첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿은 [자동](../../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.

Windows 10 SDK 부터는이 메서드는 설정 되지 합니다 `WeakRef` 인스턴스를 `nullptr` 약한 참조를 가져올 수 없는 경우는 피할 수 확인 하는 오류 검사 코드를 `WeakRef` 에 대 한 `nullptr`합니다. 대신 확인 합니다 *ptr* 에 대 한 `nullptr`합니다.

## <a name="asiid"></a>Weakref:: Asiid 메서드

지정 된 `ComPtr` 포인터 매개 변수를 나타내는 지정 된 인터페이스 id입니다.

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ptr*<br/>
이 작업이 완료 되 면 매개 변수를 나타내는 개체 *riid*합니다.

### <a name="return-value"></a>반환 값

- 이 작업이 성공 하면 s_ok이 고 이유를 나타내는 HRESULT 그렇지 않으면 작업이 실패 하 고 *ptr* 로 설정 된 `nullptr`합니다.

- 하지만 현재가이 작업이 성공 하면 s_ok이 고, `WeakRef` 개체는 이미 해제 되었습니다. 매개 변수 *ptr* 로 설정 된 `nullptr`합니다.

- 하지만 현재가이 작업이 성공 하면 S_OK `WeakRef` 개체 매개 변수에서 파생 되지 않은 *riid*합니다. 매개 변수 *ptr* 로 설정 된 `nullptr`합니다. 자세한 내용은 설명 부분을 참조하세요.

### <a name="remarks"></a>설명

오류가 발생 하는 경우에 내보내집니다 매개 변수 *riid* 에서 파생 되지 않은 `IInspectable`합니다. 이 오류는 반환 값을 대체합니다.

첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿(여기에 표시되지 않지만 헤더 파일에서 선언됨)은 [자동](../../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.

Windows 10 SDK 부터는이 메서드는 설정 되지 합니다 `WeakRef` 인스턴스를 `nullptr` 약한 참조를 가져올 수 없는 경우는 피할 수 확인 하는 오류 검사 코드를 `WeakRef` 에 대 한 `nullptr`합니다. 대신 확인 합니다 *ptr* 에 대 한 `nullptr`합니다.

## <a name="copyto"></a>Weakref:: Copyto 메서드

사용 가능한 경우 지정된 포인터 변수에 인터페이스에 대한 포인터를 할당합니다.

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>매개 변수

*U*<br/>
포인터는 `IInspectable` 인터페이스입니다. 오류가 발생 하는 경우에 내보내집니다 *U* 에서 파생 되지 않은 `IInspectable`합니다.

*riid*<br/>
인터페이스 ID입니다. 오류가 발생 하는 경우에 내보내집니다 *riid* 에서 파생 되지 않은 `IWeakReference`합니다.

*ptr*<br/>
에 대 한 이중 간접 포인터 `IInspectable` 또는 `IWeakReference`합니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 실패를 설명하는 HRESULT가 발생합니다. 자세한 내용은 **설명**을 참조하세요.

### <a name="remarks"></a>설명

반환 값 S_OK는 이 작업이 성공했음을 의미하지만 약한 참조가 강한 참조로 확인되었는지를 나타내지 않습니다. S_OK가 반환 되 면 해당 매개 변수를 테스트 *p* 는 강력한 참조 매개 변수, 즉 *p* 같지 `nullptr`합니다.

Windows 10 SDK 부터는이 메서드는 설정 하지 않습니다는 `WeakRef` 인스턴스를 `nullptr` 약한 참조를 가져올 수 없는 경우는 피할 수 오류 검사 코드를 검사 하는 `WeakRef` 에 대 한 `nullptr`합니다. 대신 확인 합니다 *ptr* 에 대 한 `nullptr`합니다.

## <a name="operator-ampersand-operator"></a>WeakRef::operator&amp; 연산자

반환 된 `ComPtrRef` 현재를 나타내는 개체 `WeakRef` 개체입니다.

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>반환 값

A `ComPtrRef` 현재 나타내는 `WeakRef` 개체입니다.

### <a name="remarks"></a>설명

코드에서 사용할 고려 하지 않은 한 내부 도우미 연산자입니다.

## <a name="weakref"></a>Weakref:: Weakref 생성자

`WeakRef` 클래스의 새 인스턴스를 초기화합니다.

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>매개 변수

*ptr*<br/>
포인터, 참조 또는 현재 초기화 하는 기존 개체에 대 한 rvalue 참조 `WeakRef` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 빈 `WeakRef` 개체입니다. 두 번째 생성자는 초기화를 `WeakRef` 개체에 대 한 포인터를 `IWeakReference` 인터페이스입니다. 세 번째 생성자는 초기화를 `WeakRef` 개체에 대 한 참조를 `ComPtr<IWeakReference>` 개체입니다. 네 번째와 다섯 번째 생성자 초기화를 `WeakRef` 간에 개체 `WeakRef` 개체입니다.
