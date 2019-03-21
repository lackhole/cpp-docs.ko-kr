---
title: Platform::Box 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
ms.openlocfilehash: ca8c9229d0ef5fa654f462282f257b1684984102
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742932"
---
# <a name="platformbox-class"></a>Platform::Box 클래스

`Windows::Foundation::DateTime` 등의 값 형식 또는 `int` 등의 스칼라 형식을 `Platform::Object` 형식에 저장할 수 있습니다. 값 형식을 `Box` 으로 캐스팅할 때 boxing이 암시적으로 발생하므로 일반적으로 `Object^`를 명시적으로 사용할 필요가 없습니다.

### <a name="syntax"></a>구문

```cpp
ref class Box abstract;
```

### <a name="requirements"></a>요구 사항

**헤더:** vccorlib.h

**네임스페이스:** 플랫폼

### <a name="members"></a>멤버

|멤버|설명|
|------------|-----------------|
|[Object^](#ctor) | 지정된 형식의 값을 캡슐화할 수 있는 `Box`를 만듭니다. |
|[연산자 상자&lt;const T&gt;^](#box-const-t) | 
  `const` 값 클래스 `T` 또는 `enum` 클래스 `T`를 `Box<T>`로 boxing 변환할 수 있습니다. |
|[연산자 상자&lt;volatile const T&gt;^](#box-const-volatile-t) | 
  `const volatile` 값 클래스 `T` 또는 `enum` 형식 `T`를 `Box<T>`로 boxing 변환할 수 있습니다. |
|[operator Box&lt;T&gt;^](#box-t) | 값 클래스 `T`를 `Box<T>`로 boxing 변환할 수 있습니다. |
|[연산자 상자&lt;volatile T&gt;^](#box-volatile-t) | 
  `volatile` 값 클래스 `T` 또는 `enum` 형식 `T`를 `Box<T>`로 boxing 변환할 수 있습니다. |
|[Box:: operator T](#t) | 값 클래스 `T` 또는 `enum` 클래스 `T`를 `Box<T>`로 boxing 변환할 수 있습니다. |
|[Value 속성](#value) | 
  `Box` 개체에 캡슐화된 값을 반환합니다. |

## <a name="ctor"></a> Box:: box 생성자

지정된 형식의 값을 캡슐화할 수 있는 `Box`를 만듭니다.

### <a name="syntax"></a>구문

```cpp
Box(T valueArg);
```

### <a name="parameters"></a>매개 변수

*valueArg*<br/>
boxing할 값의 형식입니다(예: `int`, `bool`, `float64`, `DateTime`).

## <a name="box-const-t"></a> Box:: operator 상자가&lt;const T&gt;^ 연산자


  `const` 값 클래스 `T` 또는 `enum` 클래스 `T`를 `Box<T>`로 boxing 변환할 수 있습니다.

### <a name="syntax"></a>구문

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
모든 값 클래스, 값 구조체 또는 열거형 형식입니다. 기본 제공 형식을 포함 합니다 [기본 네임 스페이스](../cppcx/default-namespace.md)합니다.

### <a name="return-value"></a>반환 값

`Platform::Box<T>^` ref 클래스에서 원래 값을 나타내는 상자입니다.

## <a name="box-const-volatile-t"></a> Box:: operator 상자가&lt;volatile const T&gt;^ 연산자


  `const volatile` 값 클래스 `T` 또는 `enum` 형식 `T`를 `Box<T>`로 boxing 변환할 수 있습니다.

### <a name="syntax"></a>구문

```cpp
operator Box<const volatile T>^(const volatile T valueType);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
모든 열거형 형식, 값 클래스 또는 값 구조체입니다. 기본 제공 형식을 포함 합니다 [기본 네임 스페이스](../cppcx/default-namespace.md)합니다.

### <a name="return-value"></a>반환 값

`Platform::Box<T>^` ref 클래스에서 원래 값을 나타내는 상자입니다.

## <a name="box-t"></a> Box:: operator 상자가&lt;T&gt;^ 연산자

값 클래스 `T`를 `Box<T>`로 boxing 변환할 수 있습니다.

### <a name="syntax"></a>구문

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
모든 열거형 형식, 값 클래스 또는 값 구조체입니다. 기본 제공 형식을 포함 합니다 [기본 네임 스페이스](../cppcx/default-namespace.md)합니다.

### <a name="return-value"></a>반환 값

`Platform::Box<T>^` ref 클래스에서 원래 값을 나타내는 상자입니다.

## <a name="box-volatile-t"></a> Box:: operator 상자가&lt;volatile T&gt;^ 연산자


  `volatile` 값 클래스 `T` 또는 `enum` 형식 `T`를 `Box<T>`로 boxing 변환할 수 있습니다.

### <a name="syntax"></a>구문

```cpp
operator Box<volatile T>^(volatile T valueType);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
모든 열거형 형식, 값 클래스 또는 값 구조체입니다. 기본 제공 형식을 포함 합니다 [기본 네임 스페이스](../cppcx/default-namespace.md)합니다.

### <a name="return-value"></a>반환 값

`Platform::Box<T>^` ref 클래스에서 원래 값을 나타내는 상자입니다.

## <a name="t"></a>  Box:: operator T 연산자

값 클래스 `T` 또는 `enum` 클래스 `T`를 `Box<T>`로 boxing 변환할 수 있습니다.

### <a name="syntax"></a>구문

```cpp
operator Box<T>^(T valueType);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
모든 열거형 형식, 값 클래스 또는 값 구조체입니다. 기본 제공 형식을 포함 합니다 [기본 네임 스페이스](../cppcx/default-namespace.md)합니다.

### <a name="return-value"></a>반환 값

`Platform::Box<T>^` ref 클래스에서 원래 값을 나타내는 상자입니다.

## <a name="value"></a> Box:: value 속성


  `Box` 개체에 캡슐화된 값을 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual property T Value{
   T get();
}
```

### <a name="return-value"></a>반환 값

boxing되기 전 형식의 boxed 값을 반환합니다.

## <a name="see-also"></a>참고자료

[Platform 네임 스페이스](../cppcx/platform-namespace-c-cx.md)<br/>
[Boxing](../cppcx/boxing-c-cx.md)
