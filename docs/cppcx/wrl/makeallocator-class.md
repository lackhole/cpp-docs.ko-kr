---
title: MakeAllocator 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
- implements/Microsoft::WRL::Details::MakeAllocator::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
helpviewer_keywords:
- Microsoft::WRL::Details::MakeAllocator class
- Microsoft::WRL::Details::MakeAllocator::Allocate method
- Microsoft::WRL::Details::MakeAllocator::Detach method
- Microsoft::WRL::Details::MakeAllocator::MakeAllocator, constructor
- Microsoft::WRL::Details::MakeAllocator::~MakeAllocator, destructor
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
ms.openlocfilehash: 805f0c09b0490d8cec1a0be96dcb1fc99a051371
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784762"
---
# <a name="makeallocator-class"></a>MakeAllocator 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<
    typename T,
    bool hasWeakReferenceSupport =
          !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,
                        T)
>
class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식 이름.

*hasWeakReferenceSupport*<br/>
**true** ; 약한 참조를 지 원하는 개체에 대 한 메모리를 할당 하려면 **false** 약한 참조를 지원 하지 않는 개체에 대 한 메모리를 할당할 수 있습니다.

## <a name="remarks"></a>설명

약한 참조 지원을 유무는 활성화 가능한 클래스에 대 한 메모리를 할당합니다.

재정의 `MakeAllocator` 사용자 정의 메모리 할당 모델을 구현 하는 클래스입니다.

`MakeAllocator` 개체를 생성 하는 동안 throw 하는 경우 메모리 누수를 방지 하려면 일반적으로 사용 됩니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                                  | 설명
----------------------------------------------------- | ----------------------------------------------------------------
[MakeAllocator::MakeAllocator](#makeallocator)        | `MakeAllocator` 클래스의 새 인스턴스를 초기화합니다.
[MakeAllocator::~MakeAllocator](#tilde-makeallocator) | 현재 인스턴스를 초기화 해제는 `MakeAllocator` 클래스입니다.

### <a name="public-methods"></a>Public 메서드

이름                                 | 설명
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[MakeAllocator::Allocate](#allocate) | 메모리를 할당 하 고 현재 연결 `MakeAllocator` 개체입니다.
[MakeAllocator::Detach](#detach)     | 의해 할당 된 메모리를 분리 합니다 [할당](#allocate) 메서드에서 현재 `MakeAllocator` 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`MakeAllocator`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="allocate"></a>MakeAllocator::Allocate

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>반환 값

성공 하면 할당된 된 메모리;에 대 한 포인터 그렇지 않으면 `nullptr`합니다.

### <a name="remarks"></a>설명

메모리를 할당 하 고 현재 연결 `MakeAllocator` 개체입니다.

할당된 된 메모리의 크기는 현재 지정 된 형식의 크기 `MakeAllocator` 템플릿 매개 변수입니다.

개발자만 재정의 해야 하는 `Allocate()` 서로 다른 메모리 할당 모델을 구현 하는 방법입니다.

## <a name="detach"></a>MakeAllocator::Detach

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>설명

의해 할당 된 메모리를 분리 합니다 [할당](#allocate) 메서드에서 현재 `MakeAllocator` 개체입니다.

호출 하는 경우 `Detach()`에서 제공한 메모리를 삭제 하는 일을 담당 하는 `Allocate` 메서드.

## <a name="makeallocator"></a>MakeAllocator::MakeAllocator

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
MakeAllocator();
```

### <a name="remarks"></a>설명

`MakeAllocator` 클래스의 새 인스턴스를 초기화합니다.

## <a name="tilde-makeallocator"></a>MakeAllocator::~MakeAllocator

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>설명

현재 인스턴스를 초기화 해제는 `MakeAllocator` 클래스입니다.

이 소멸자는 또한 필요한 경우 할당된 된 기본 메모리를 삭제 합니다.
