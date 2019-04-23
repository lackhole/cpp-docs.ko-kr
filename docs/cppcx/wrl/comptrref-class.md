---
title: ComPtrRef 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
- client/Microsoft::WRL::Details::ComPtrRef::operator==
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
- client/Microsoft::WRL::Details::ComPtrRef::operator*
- client/Microsoft::WRL::Details::ComPtrRef::operator T*
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRef class
- Microsoft::WRL::Details::ComPtrRef::ComPtrRef, constructor
- Microsoft::WRL::Details::ComPtrRef::GetAddressOf method
- Microsoft::WRL::Details::ComPtrRef::operator== operator
- Microsoft::WRL::Details::ComPtrRef::operator!= operator
- Microsoft::WRL::Details::ComPtrRef::operator InterfaceType** operator
- Microsoft::WRL::Details::ComPtrRef::operator* operator
- Microsoft::WRL::Details::ComPtrRef::operator T* operator
- Microsoft::WRL::Details::ComPtrRef::operator void** operator
- Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf method
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
ms.openlocfilehash: 281e02d85e70a84530e6980d31669a73091448d5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784839"
---
# <a name="comptrref-class"></a>ComPtrRef 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
A [ComPtr\<T >](comptr-class.md) 형식 또는 형식에서 파생 하 여이 나타내는 인터페이스 뿐만 아니라는 `ComPtr`합니다.

## <a name="remarks"></a>설명

형식의 개체에 대 한 참조를 나타내는 `ComPtr<T>`합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                               | 설명
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[ComPtrRef::ComPtrRef](#comptrref) | 새 인스턴스를 초기화 합니다 `ComPtrRef` 지정 된 포인터를 클래스 `ComPtrRef` 개체입니다.

### <a name="public-methods"></a>Public 메서드

이름                                                         | 설명
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::GetAddressOf](#getaddressof)                     | 현재이 나타내는 인터페이스에 대 한 포인터의 주소를 검색 `ComPtrRef` 개체입니다.
[ComPtrRef::ReleaseAndGetAddressOf](#releaseandgetaddressof) | 현재 삭제 `ComPtrRef` 개체 및 포인터-에-a-포인터를 반환에서 나타내는 인터페이스를 `ComPtrRef` 개체입니다.

### <a name="public-operators"></a>Public 연산자

이름                                                                     | 설명
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[Comptrref:: Operator InterfaceType * *](#operator-interfacetype-star-star) | 현재 삭제 `ComPtrRef` 개체 및 포인터-에-a-포인터를 반환에서 나타내는 인터페이스를 `ComPtrRef` 개체입니다.
[Comptrref:: Operator T *](#operator-t-star)                               | 값을 반환 합니다 [ptr_](comptrrefbase-class.md#ptr) 현재 ComPtrRef 개체의 데이터 멤버입니다.
[Comptrref:: Operator void * *](#operator-void-star-star)                   | 현재 삭제 `ComPtrRef` 개체에서 나타내는 인터페이스에 대 한 포인터 캐스팅, 합니다 `ComPtrRef` 개체에 대 한 포인터--포인터-을 `void`, cast 포인터를 반환 합니다.
[ComPtrRef::operator*](#operator-star)                                   | 현재이 나타내는 인터페이스에 포인터를 검색 `ComPtrRef` 개체입니다.
[ComPtrRef::operator==](#operator-equality)                              | 두 `ComPtrRef` 개체가 같은지를 나타냅니다.
[ComPtrRef::operator!=](#operator-inequality)                            | 두 `ComPtrRef` 개체가 같지 않은지를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="comptrref"></a>ComPtrRef::ComPtrRef

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>매개 변수

*ptr*<br/>
다른 기본 값 `ComPtrRef` 개체입니다.

### <a name="remarks"></a>설명

새 인스턴스를 초기화 합니다 `ComPtrRef` 지정 된 포인터를 클래스 `ComPtrRef` 개체입니다.

## <a name="getaddressof"></a>ComPtrRef::GetAddressOf

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>반환 값

현재이 나타내는 인터페이스에 대 한 포인터의 주소 `ComPtrRef` 개체입니다.

### <a name="remarks"></a>설명

현재이 나타내는 인터페이스에 대 한 포인터의 주소를 검색 `ComPtrRef` 개체입니다.

## <a name="operator-equality"></a>ComPtrRef::operator==

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>매개 변수

*a*<br/>
`ComPtrRef` 개체에 대한 참조입니다.

*b*<br/>
다른에 대 한 참조가 `ComPtrRef` 개체 또는 무명 형식에 대 한 포인터 (`void*`).

### <a name="return-value"></a>반환 값

첫 번째 연산자 생성 **true** 하는 경우 개체 *는* 개체와 동일한 지 *b*고, 그렇지 않으면 **false**합니다.

두 번째와 세 번째 연산자에서 생성 **true** 하는 경우 개체 *는* 값과 같음 **nullptr**고, 그렇지 않으면 **false**합니다.

네 번째와 다섯 번째 연산자에서 생성 **true** 경우 개체 *는* 개체와 동일한 지 *b*고, 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

두 `ComPtrRef` 개체가 같은지를 나타냅니다.

## <a name="operator-inequality"></a>ComPtrRef::operator!=

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>매개 변수

*a*<br/>
`ComPtrRef` 개체에 대한 참조입니다.

*b*<br/>
다른에 대 한 참조가 `ComPtrRef` 개체 또는 익명 개체에 대 한 포인터 (`void*`).

### <a name="return-value"></a>반환 값

첫 번째 연산자 생성 **true** 하는 경우 개체 *는* 개체와 같지 않은 *b*고, 그렇지 않으면 **false**합니다.

두 번째 및 세 번째 연산자를 생성 **true** 경우 개체 *는* 같지 **nullptr**고, 그렇지 않으면 **false**합니다.

네 번째와 다섯 번째 연산자에서 생성 **true** 하는 경우 개체 *는* 개체와 같지 않은 *b*고, 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

두 `ComPtrRef` 개체가 같지 않은지를 나타냅니다.

## <a name="operator-interfacetype-star-star"></a>Comptrref:: Operator InterfaceType * *

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>설명

현재 삭제 `ComPtrRef` 개체 및 포인터-에-a-포인터를 반환에서 나타내는 인터페이스를 `ComPtrRef` 개체입니다.

## <a name="operator-star"></a>ComPtrRef::operator*

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>반환 값

현재이 나타내는 인터페이스에 대 한 포인터 `ComPtrRef` 개체입니다.

### <a name="remarks"></a>설명

현재이 나타내는 인터페이스에 포인터를 검색 `ComPtrRef` 개체입니다.

## <a name="operator-t-star"></a>Comptrref:: Operator T *

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator T*();
```

### <a name="remarks"></a>설명

값을 반환 합니다 [ptr_](comptrrefbase-class.md#ptr) 현재 데이터 멤버 `ComPtrRef` 개체입니다.

## <a name="operator-void-star-star"></a>Comptrref:: Operator void\*\*

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
operator void**() const;
```

### <a name="remarks"></a>설명

현재 삭제 `ComPtrRef` 개체에서 나타내는 인터페이스에 대 한 포인터 캐스팅, 합니다 `ComPtrRef` 개체에 대 한 포인터--포인터-을 `void`, cast 포인터를 반환 합니다.

## <a name="releaseandgetaddressof"></a>ComPtrRef::ReleaseAndGetAddressOf

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>반환 값

나타내는 인터페이스에 대 한 포인터를 삭제 하 여 `ComPtrRef` 개체입니다.

### <a name="remarks"></a>설명

현재 삭제 `ComPtrRef` 개체 및 포인터-에-a-포인터를 반환에서 나타내는 인터페이스를 `ComPtrRef` 개체입니다.
