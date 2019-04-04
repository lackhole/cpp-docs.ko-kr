---
title: InvokeHelper 구조체
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
ms.openlocfilehash: 3fcba210d4018d22487d234b437acfee3634cec6
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785161"
---
# <a name="invokehelper-structure"></a>InvokeHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>매개 변수

*TDelegateInterface*<br/>
대리자 인터페이스 형식입니다.

*TCallback*<br/>
이벤트 처리기 함수의 형식입니다.

*argCount*<br/>
인수 개수는 `InvokeHelper` 특수화 합니다.

## <a name="remarks"></a>설명

구현을 제공 합니다 `Invoke()` 메서드 인수 형식 및 지정 된 수에 따라 합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름     | 설명
-------- | -----------------------------------------------------------------------------
`Traits` | 각 이벤트 처리기 인수 형식을 정의 하는 클래스의 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

이름                                        | 설명
------------------------------------------- | -------------------------------------------------------
[InvokeHelper::InvokeHelper](#invokehelper) | `InvokeHelper` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

이름                            | 설명
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper::Invoke](#invoke) | 지정 된 인수 개수를 포함 하는 시그니처를 가진 이벤트 처리기를 호출 합니다.

### <a name="public-data-members"></a>공용 데이터 멤버

이름                                 | 설명
------------------------------------ | ----------------------------------------------------------
[InvokeHelper::callback_](#callback) | 이벤트가 발생할 때 호출할 이벤트 처리기를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`InvokeHelper`

## <a name="requirements"></a>요구 사항

**헤더:** event.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="callback"></a>InvokeHelper::callback_

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>설명

이벤트가 발생할 때 호출할 이벤트 처리기를 나타냅니다.

`TCallback` 템플릿 매개 변수는 이벤트 처리기의 유형을 지정 합니다.

## <a name="invoke"></a>InvokeHelper::Invoke

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>매개 변수

*arg1*<br/>
인수 1입니다.

*arg2*<br/>
인수 2입니다.

*arg3*<br/>
인수 3입니다.

*arg4*<br/>
인수 4입니다.

*arg5*<br/>
5 인수입니다.

*arg6*<br/>
인수 6입니다.

*arg7*<br/>
7 인수입니다.

*arg8*<br/>
8 인수입니다.

*arg9*<br/>
9 인수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 오류를 설명 하는 HRESULT입니다.

### <a name="remarks"></a>설명

지정 된 인수 개수를 포함 하는 시그니처를 가진 이벤트 처리기를 호출 합니다.

## <a name="invokehelper"></a>InvokeHelper::InvokeHelper

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>매개 변수

*callback*<br/>
이벤트 처리기입니다.

### <a name="remarks"></a>설명

`InvokeHelper` 클래스의 새 인스턴스를 초기화합니다.

`TCallback` 템플릿 매개 변수는 이벤트 처리기의 유형을 지정 합니다.
