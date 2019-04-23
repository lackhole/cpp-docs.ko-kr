---
title: ComPtr 클래스
ms.date: 10/01/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
- client/Microsoft::WRL::ComPtr::As
- client/Microsoft::WRL::ComPtr::AsIID
- client/Microsoft::WRL::ComPtr::AsWeak
- client/Microsoft::WRL::ComPtr::Attach
- client/Microsoft::WRL::ComPtr::ComPtr
- client/Microsoft::WRL::ComPtr::CopyTo
- client/Microsoft::WRL::ComPtr::Detach
- client/Microsoft::WRL::ComPtr::Get
- client/Microsoft::WRL::ComPtr::GetAddressOf
- client/Microsoft::WRL::ComPtr::InternalAddRef
- client/Microsoft::WRL::ComPtr::InternalRelease
- client/Microsoft::WRL::ComPtr::operator&
- client/Microsoft::WRL::ComPtr::operator->
- client/Microsoft::WRL::ComPtr::operator=
- client/Microsoft::WRL::ComPtr::operator==
- client/Microsoft::WRL::ComPtr::operator!=
- client/Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType
- client/Microsoft::WRL::ComPtr::ptr_
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
- client/Microsoft::WRL::ComPtr::Reset
- client/Microsoft::WRL::ComPtr::Swap
- client/Microsoft::WRL::ComPtr::~ComPtr
helpviewer_keywords:
- Microsoft::WRL::ComPtr class
- Microsoft::WRL::ComPtr::As method
- Microsoft::WRL::ComPtr::AsIID method
- Microsoft::WRL::ComPtr::AsWeak method
- Microsoft::WRL::ComPtr::Attach method
- Microsoft::WRL::ComPtr::ComPtr, constructor
- Microsoft::WRL::ComPtr::CopyTo method
- Microsoft::WRL::ComPtr::Detach method
- Microsoft::WRL::ComPtr::Get method
- Microsoft::WRL::ComPtr::GetAddressOf method
- Microsoft::WRL::ComPtr::InternalAddRef method
- Microsoft::WRL::ComPtr::InternalRelease method
- Microsoft::WRL::ComPtr::operator& operator
- Microsoft::WRL::ComPtr::operator-> operator
- Microsoft::WRL::ComPtr::operator= operator
- Microsoft::WRL::ComPtr::operator== operator
- Microsoft::WRL::ComPtr::operator!= operator
- Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType operator
- Microsoft::WRL::ComPtr::ptr_ data member
- Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf method
- Microsoft::WRL::ComPtr::Reset method
- Microsoft::WRL::ComPtr::Swap method
- Microsoft::WRL::ComPtr::~ComPtr, destructor
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
ms.openlocfilehash: 9e5b2419f070ead17e72b1642f510f74bad8260e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784991"
---
# <a name="comptr-class"></a>ComPtr 클래스

템플릿 매개 변수로 지정된 인터페이스를 나타내는 *스마트 포인터* 형식을 만듭니다. `ComPtr`은 기본 인터페이스 포인터의 참조 개수를 자동으로 관리하여 참조 횟수가 0이 되면 인터페이스를 릴리스합니다.

## <a name="syntax"></a>구문

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
인터페이스는는 `ComPtr` 나타냅니다.

*U*<br/>
클래스를 현재 `ComPtr` 이 friend입니다. 이 매개 변수를 사용하는 템플릿은 보호됩니다.

## <a name="remarks"></a>설명

`ComPtr<>` 기본 인터페이스 포인터를 나타내는 형식을 선언 합니다. 사용 하 여 `ComPtr<>` 변수를 선언 하 고 다음 화살표 멤버 액세스 연산자를 사용 (`->`) 인터페이스 멤버 함수에 액세스할 수 있습니다.

스마트 포인터에 대 한 자세한 내용은 "COM 스마트 포인터" 하위 섹션을 참조 합니다 [COM Coding Practices](/windows/desktop/LearnWin32/com-coding-practices) MSDN 라이브러리의 항목입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름            | 설명
--------------- | ---------------------------------------------------------------
`InterfaceType` | 지정 된 형식에 대 한 동의어는 *T* 템플릿 매개 변수입니다.

### <a name="public-constructors"></a>Public 생성자

이름                             | 설명
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr::ComPtr](#comptr)        | `ComPtr` 클래스의 새 인스턴스를 초기화합니다. 오버로드는 기본, 복사, 이동 및 변환 생성자를 제공합니다.
[ComPtr::~ComPtr](#tilde-comptr) | 인스턴스를 초기화 취소 `ComPtr`합니다.

### <a name="public-methods"></a>Public 메서드

이름                                                      | 설명
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr::As](#as)                                         | 반환 된 `ComPtr` 지정 된 템플릿 매개 변수로 식별 된 인터페이스를 나타내는 개체입니다.
[ComPtr::AsIID](#asiid)                                   | 반환 된 `ComPtr` 지정 된 인터페이스 ID로 식별 된 인터페이스를 나타내는 개체
[ComPtr::AsWeak](#asweak)                                 | 현재 개체에 대한 약한 참조를 검색합니다.
[ComPtr::Attach](#attach)                                 | 이 연결 `ComPtr` 현재 템플릿 형식 매개 변수에 의해 지정 된 인터페이스 형식을 사용 하 여 합니다.
[ComPtr::CopyTo](#copyto)                                 | 현재 또는 지정 된 인터페이스와 관련 된 복사 `ComPtr` 지정 된 출력 포인터에 대 한 합니다.
[ComPtr::Detach](#detach)                                 | 이 연결을 끊습니다 `ComPtr` 나타내는 인터페이스입니다.
[ComPtr::Get](#get)                                       | 이 사용 하 여 연결 된 인터페이스에 대 한 포인터를 검색 `ComPtr`합니다.
[ComPtr::GetAddressOf](#getaddressof)                     | 주소를 검색 합니다 [ptr_](#ptr) 이 나타내는 인터페이스에 대 한 포인터를 포함 하는 데이터 멤버 `ComPtr`합니다.
[ComPtr::ReleaseAndGetAddressOf](#releaseandgetaddressof) | 와 연결 된 인터페이스를 해제 `ComPtr` 다음의 주소를 검색 합니다 [ptr_](#ptr) 출시 된 인터페이스에 대 한 포인터를 포함 하는 데이터 멤버입니다.
[ComPtr::Reset](#reset)                                   | 이 사용 하 여 연결 된 인터페이스 포인터에 대 한 모든 참조가 해제 `ComPtr`합니다.
[ComPtr::Swap](#swap)                                     | 현재 관리 되는 인터페이스를 교환 `ComPtr` 지정 된 관리 인터페이스를 사용 하 여 `ComPtr`입니다.

### <a name="protected-methods"></a>Protected 메서드

이름                                        | 설명
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr::InternalAddRef](#internaladdref)   | 와 연결 된 인터페이스의 참조 횟수를 증가 시킵니다 `ComPtr`합니다.
[ComPtr::InternalRelease](#internalrelease) | 연결 된이 인터페이스에서 COM 릴리스 작업을 수행 `ComPtr`합니다.

### <a name="public-operators"></a>Public 연산자

이름                                                                                           | 설명
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr::operator&](#operator-ampersand)                                                       | 현재 주소를 검색 `ComPtr`합니다.
[ComPtr::operator->](#operator-arrow)                                                          | 현재 템플릿 매개 변수에 지정된 형식에 대한 포인터를 검색합니다.
[ComPtr::operator=](#operator-assign)                                                          | 현재 값을 할당 `ComPtr`합니다.
[ComPtr::operator==](#operator-equality)                                                       | 두 `ComPtr` 개체가 같은지를 나타냅니다.
[ComPtr::operator!=](#operator-inequality)                                                     | 두 `ComPtr` 개체가 같지 않은지를 나타냅니다.
[Comptr:: Operator Microsoft::WRL::Details::BoolType](#operator-microsoft-wrl-details-booltype) | 나타냅니다 여부는 `ComPtr` 인터페이스의 개체 수명을 관리 합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

이름                 | 설명
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::ptr_](#ptr) | 와 연결 되 고 관리 하는 인터페이스에 대 한 포인터가 포함 `ComPtr`합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ComPtr`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** Microsoft::WRL

## <a name="tilde-comptr"></a>ComPtr::~ComPtr

인스턴스를 초기화 취소 `ComPtr`합니다.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>ComPtr::As

반환 된 `ComPtr` 지정 된 템플릿 매개 변수로 식별 된 인터페이스를 나타내는 개체입니다.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* p
) const;

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> p
) const;
```

### <a name="parameters"></a>매개 변수

*U*<br/>
인터페이스를 매개 변수로 표시할 *p*합니다.

*p*<br/>
A `ComPtr` 매개 변수로 지정 된 인터페이스를 나타내는 개체 *U*합니다. 매개 변수 *p* 현재 참조 하지 않아야 `ComPtr` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 템플릿은 코드에서 사용해야 하는 폼입니다. 두 번째 템플릿은 [자동](../../cpp/auto-cpp.md) 형식 추론 키워드와 같은 C++ 언어 기능을 지원하는 내부 도우미 특수화입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="asiid"></a>ComPtr::AsIID

반환 된 `ComPtr` 지정 된 인터페이스 ID로 식별 된 인터페이스를 나타내는 개체

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*p*<br/>
개체에 있는 경우 해당 ID가 인터페이스 *riid*,으로 지정한 인터페이스에 대 한 이중 간접 포인터는 *riid* 매개 변수가 고, 그렇지 않으면에 대 한 포인터 `IUnknown`합니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="asweak"></a>ComPtr::AsWeak

현재 개체에 대한 약한 참조를 검색합니다.

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>매개 변수

*pWeakRef*<br/>
이 작업이 완료 될 때 약한 참조 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="attach"></a>ComPtr::Attach

이 연결 `ComPtr` 현재 템플릿 형식 매개 변수에 의해 지정 된 인터페이스 형식을 사용 하 여 합니다.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>매개 변수

*other*<br/>
인터페이스 형식입니다.

## <a name="comptr"></a>ComPtr::ComPtr

`ComPtr` 클래스의 새 인스턴스를 초기화합니다. 오버로드는 기본, 복사, 이동 및 변환 생성자를 제공합니다.

```cpp
WRL_NOTHROW ComPtr();
WRL_NOTHROW ComPtr(
   decltype(__nullptr)
);
template<class U>
WRL_NOTHROW ComPtr(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr(
   const ComPtr& other
);
template<class U>
WRL_NOTHROW ComPtr(
   const ComPtr<U> &other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
```

### <a name="parameters"></a>매개 변수

*U*<br/>
형식의 합니다 *다른* 매개 변수입니다.

*other*<br/>
형식의 개체 *U*합니다.

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

첫 번째 생성자는 기본 생성자는 암시적 빈 개체를 만듭니다. 두 번째 생성자는 지정 [__nullptr](../../extensions/nullptr-cpp-component-extensions.md), 빈 개체를 명시적으로 만듭니다.

세 번째 생성자는 포인터에 의해 지정 된 개체에서 개체를 만듭니다.

네 번째와 다섯 번째 생성자는 복사 생성자입니다. 현재 형식으로 변환할 경우 다섯 번째 생성자는 개체를 복사 합니다.

여섯 번째와 일곱 번째 생성자는 이동 생성자입니다. 현재 형식으로 변환할 경우 일곱 번째 생성자는 개체를 이동 합니다.

## <a name="copyto"></a>ComPtr::CopyTo

현재 또는 지정 된 인터페이스와 관련 된 복사 `ComPtr` 지정 된 포인터에 대 한 합니다.

```cpp
HRESULT CopyTo(
   _Deref_out_ InterfaceType** ptr
);

HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ void** ptr
) const;

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
) const;
```

### <a name="parameters"></a>매개 변수

*U*<br/>
형식 이름.

*ptr*<br/>
이 작업이 완료 될 때 요청된 된 인터페이스에 대 한 포인터입니다.

*riid*<br/>
인터페이스 ID입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않은 경우 이유를 나타내는 HRESULT 암시적 `QueryInterface` 작업이 실패 했습니다.

### <a name="remarks"></a>설명

와 연결 된 인터페이스에 대 한 포인터의 복사본을 반환 하는 첫 번째 함수 `ComPtr`합니다. 이 함수는 항상 S_OK를 반환합니다.

수행 하는 두 번째 함수는 `QueryInterface` 와 연결 된 인터페이스에 대 한 작업 `ComPtr` 으로 지정한 인터페이스에 대 한 합니다 *riid* 매개 변수입니다.

수행 하는 세 번째 함수는 `QueryInterface` 와 연결 된 인터페이스에 대 한 작업 `ComPtr` 의 기본 인터페이스에 대 한 합니다 *U* 매개 변수.

## <a name="detach"></a>ComPtr::Detach

이 연결을 끊습니다 `ComPtr` 나타내는 인터페이스에서 개체입니다.

```cpp
T* Detach();
```

### <a name="return-value"></a>반환 값

이 나타내는 인터페이스에 대 한 포인터 `ComPtr` 개체입니다.

## <a name="get"></a>ComPtr::Get

이 사용 하 여 연결 된 인터페이스에 대 한 포인터를 검색 `ComPtr`합니다.

```cpp
T* Get() const;
```

### <a name="return-value"></a>반환 값

이 사용 하 여 연결 된 인터페이스에 대 한 포인터 `ComPtr`합니다.

## <a name="getaddressof"></a>ComPtr::GetAddressOf

주소를 검색 합니다 [ptr_](#ptr) 이 나타내는 인터페이스에 대 한 포인터를 포함 하는 데이터 멤버 `ComPtr`합니다.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>반환 값

변수의 주소입니다.

## <a name="internaladdref"></a>ComPtr::InternalAddRef

와 연결 된 인터페이스의 참조 횟수를 증가 시킵니다 `ComPtr`합니다.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>설명

이 메서드는 보호 됩니다.

## <a name="internalrelease"></a>ComPtr::InternalRelease

연결 된이 인터페이스에서 COM 릴리스 작업을 수행 `ComPtr`합니다.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>설명

이 메서드는 보호 됩니다.

## <a name="operator-ampersand"></a>ComPtr::operator&amp;

와 연결 된 인터페이스를 해제 `ComPtr` 개체를 다음의 주소를 검색 합니다 `ComPtr` 개체입니다.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>반환 값

현재에 대 한 약한 참조 `ComPtr`합니다.

### <a name="remarks"></a>설명

이 방법은에서 다릅니다 [comptr:: Getaddressof](#getaddressof) 는이 메서드는 인터페이스 포인터에 대 한 참조를 해제 합니다. 사용 하 여 `ComPtr::GetAddressOf` 인터페이스 포인터의 주소가 필요 하지만 해당 인터페이스를 해제 하지 않으려는 경우.

## <a name="operator-arrow"></a>ComPtr::operator-&gt;

현재 템플릿 매개 변수에 지정된 형식에 대한 포인터를 검색합니다.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>반환 값

현재 템플릿 형식 이름으로 지정 된 형식에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 도우미 함수 STDMETHOD 매크로 사용 하 여 발생 하는 불필요 한 오버 헤드를 제거 합니다. 이 기능을 사용 하면 `IUnknown` 형식을 `private` 대신 `virtual`합니다.

## <a name="operator-assign"></a>ComPtr::operator=

현재 값을 할당 `ComPtr`합니다.

```cpp
WRL_NOTHROW ComPtr& operator=(
   decltype(__nullptr)
);
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ T *other
);
template <typename U>
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr& operator=(
   const ComPtr &other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   const ComPtr<U>& other
);
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr<U>&& other
);
```

### <a name="parameters"></a>매개 변수

*U*<br/>
클래스입니다.

*other*<br/>
포인터, 참조 또는 rvalue 참조 형식 또는 다른 `ComPtr`합니다.

### <a name="return-value"></a>반환 값

현재에 대 한 참조 `ComPtr`합니다.

### <a name="remarks"></a>설명

이 연산자의 첫 번째 버전은 현재 빈 값을 할당 `ComPtr`합니다.

두 번째 버전에서는 할당에 대 한 인터페이스 포인터 없는 경우 현재 동일 `ComPtr` 인터페이스 포인터를 두 번째 인터페이스 포인터를 현재에 할당 된 `ComPtr`합니다.

세 번째 버전에서는 할당에 대 한 인터페이스 포인터는 현재 할당 된 `ComPtr`합니다.

할당 값의 인터페이스 포인터를 현재 경우 네 번째 버전에서는 `ComPtr` 인터페이스 포인터를 두 번째 인터페이스 포인터를 현재에 할당 된 `ComPtr`합니다.

다섯 번째 버전이 복사 연산자입니다. 에 대 한 참조를 `ComPtr` 현재 할당 된 `ComPtr`합니다.

여섯 번째 버전은 이동 의미 체계;를 사용 하는 복사 연산자 rvalue 참조를 `ComPtr` 캐스팅 하 고 다음 현재 할당 된 모든 형식의 정적인 경우 `ComPtr`합니다.

일곱 번째 버전은 이동 의미 체계;를 사용 하는 복사 연산자 rvalue 참조를 `ComPtr` 형식의 *U* 정적 캐스팅 한 다음 이며 현재 할당 된 `ComPtr`합니다.

## <a name="operator-equality"></a>ComPtr::operator==

두 `ComPtr` 개체가 같은지를 나타냅니다.

```cpp
bool operator==(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator==(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>매개 변수

*a*<br/>
`ComPtr` 개체에 대한 참조입니다.

*b*<br/>
다른 참조 `ComPtr` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 연산자 생성 `true` 하는 경우 개체 *는* 개체와 동일한 지 *b*고, 그렇지 않으면 `false`합니다.

두 번째 및 세 번째 연산자를 생성 `true` 경우 개체 *는* 값과 같음 `nullptr`이 고, 그렇지 않으면 `false`합니다.

## <a name="operator-inequality"></a>ComPtr::operator!=

두 `ComPtr` 개체가 같지 않은지를 나타냅니다.

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>매개 변수

*a*<br/>
`ComPtr` 개체에 대한 참조입니다.

*b*<br/>
다른 참조 `ComPtr` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 연산자 생성 `true` 하는 경우 개체 *는* 개체와 같지 않은 *b*고, 그렇지 않으면 `false`합니다.

두 번째 및 세 번째 연산자에서 생성 `true` 경우 개체 *는* 같지 `nullptr`이 고, 그렇지 않으면 `false`합니다.

## <a name="operator-microsoft-wrl-details-booltype"></a>ComPtr::operator Microsoft::WRL::Details::BoolType

나타냅니다 여부는 `ComPtr` 인터페이스의 개체 수명을 관리 합니다.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>반환 값

인터페이스와 연결 된 경우 `ComPtr`의 주소를 [boolstruct:: Member](boolstruct-structure.md#member) 데이터 멤버가 고, 그렇지 않으면 `nullptr`합니다.

## <a name="ptr"></a>ComPtr::ptr_

와 연결 되 고 관리 하는 인터페이스에 대 한 포인터가 포함 `ComPtr`합니다.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>설명

`ptr_` 내부, 보호 된 데이터 멤버가입니다.

## <a name="releaseandgetaddressof"></a>ComPtr::ReleaseAndGetAddressOf

와 연결 된 인터페이스를 해제 `ComPtr` 다음의 주소를 검색 합니다 [ptr_](#ptr) 출시 된 인터페이스에 대 한 포인터를 포함 하는 데이터 멤버입니다.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>반환 값

주소를 [ptr_](#ptr) 이 데이터 멤버 `ComPtr`합니다.

## <a name="reset"></a>ComPtr::Reset

이 사용 하 여 연결 된 인터페이스 포인터에 대 한 모든 참조가 해제 `ComPtr`합니다.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>반환 값

해제된 참조 수입니다(있는 경우).

## <a name="swap"></a>ComPtr::Swap

현재 관리 되는 인터페이스를 교환 `ComPtr` 지정 된 관리 인터페이스를 사용 하 여 `ComPtr`입니다.

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>매개 변수

*r*<br/>
`ComPtr`

