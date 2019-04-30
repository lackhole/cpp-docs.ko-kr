---
title: InterfaceTraits 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
- implements/Microsoft::WRL::Details::InterfaceTraits::IidCount
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::InterfaceTraits structure
- Microsoft::WRL::Details::InterfaceTraits::CanCastTo method
- Microsoft::WRL::Details::InterfaceTraits::CastToBase method
- Microsoft::WRL::Details::InterfaceTraits::CastToUnknown method
- Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid method
- Microsoft::WRL::Details::InterfaceTraits::IidCount constant
- Microsoft::WRL::Details::InterfaceTraits::Verify method
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
ms.openlocfilehash: e8222ccaca9572331412b90e696829568eedcf8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386059"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<typename I0>
struct __declspec(novtable) InterfaceTraits;

template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<
    CloakedIid<CloakedType>
>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>매개 변수

*I0*<br/>
인터페이스의 이름입니다.

*CloakedType*<br/>
에 대 한 `RuntimeClass`, `Implements` 고 `ChainInterfaces`, 목록의 수 없는 인터페이스는 인터페이스 Id를 지원 합니다.

## <a name="remarks"></a>설명

인터페이스의 공통 특성을 구현 합니다.

두 번째 템플릿은 감추어진된 인터페이스에 대 한 특수화입니다. 세 번째 템플릿은 Nil 매개 변수에 대 한 특수화입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름   | 설명
------ | ------------------------------------------
`Base` | 동의어는 *I0* 템플릿 매개 변수입니다.

### <a name="public-methods"></a>Public 메서드

이름                                                   | 설명
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[InterfaceTraits::CanCastTo](#cancastto)               | 지정된 된 포인터에 대 한 포인터로 캐스팅 될 수 있는지 여부를 나타내는 `Base`합니다.
[InterfaceTraits::CastToBase](#casttobase)             | 지정된 된 포인터에 대 한 포인터를 캐스팅 `Base`합니다.
[InterfaceTraits::CastToUnknown](#casttounknown)       | 지정된 된 포인터에 대 한 포인터를 캐스팅 `IUnknown`합니다.
[InterfaceTraits::FillArrayWithIid](#fillarraywithiid) | 인터페이스 ID를 할당 `Base` 인덱스 인수에 의해 지정 된 배열 요소에 있습니다.
[InterfaceTraits::Verify](#verify)                     | 확인 `Base` 제대로 파생 됩니다.

### <a name="public-constants"></a>공용 상수

이름                                   | 설명
-------------------------------------- | ---------------------------------------------------------------------------------------
[InterfaceTraits::IidCount](#iidcount) | 인터페이스는 현재 연결 된 Id의 수가 포함 `InterfaceTraits` 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`InterfaceTraits`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="cancastto"></a>InterfaceTraits::CanCastTo

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>매개 변수

*ptr*<br/>
이름 형식에 대 한 포인터입니다.

*riid*<br/>
인터페이스 ID의 `Base`합니다.

*ppv*<br/>
이 작업에 성공 하면 *ppv* 로 지정 된 인터페이스를 가리키는 `Base`합니다. 그렇지 않으면 *ppv* 로 설정 된 `nullptr`합니다.

### <a name="return-value"></a>반환 값

**true** 이 작업이 완료 되 고 *ptr* 포인터로 캐스팅 됩니다 `Base`이 고, 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

지정된 된 포인터에 대 한 포인터로 캐스팅 될 수 있는지 여부를 나타내는 `Base`합니다.

에 대 한 자세한 내용은 `Base`를 참조 합니다 [공용 Typedefs](#public-typedefs) 섹션입니다.

## <a name="casttobase"></a>InterfaceTraits::CastToBase

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
매개 변수의 유형을 *ptr*합니다.

*ptr*<br/>
형식에 대 한 포인터 *T*합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터 `Base`합니다.

### <a name="remarks"></a>설명

지정된 된 포인터에 대 한 포인터를 캐스팅 `Base`합니다.

에 대 한 자세한 내용은 `Base`를 참조 합니다 [공용 Typedefs](#public-typedefs) 섹션입니다.

## <a name="casttounknown"></a>InterfaceTraits::CastToUnknown

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
매개 변수의 유형을 *ptr*합니다.

*ptr*<br/>
입력에 대 한 포인터 *T*합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 IUnknown는 `Base` 파생 됩니다.

### <a name="remarks"></a>설명

지정된 된 포인터에 대 한 포인터를 캐스팅 `IUnknown`합니다.

에 대 한 자세한 내용은 `Base`를 참조 합니다 [공용 Typedefs](#public-typedefs) 섹션입니다.

## <a name="fillarraywithiid"></a>InterfaceTraits::FillArrayWithIid

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
0부터 시작 인덱스 값이 포함 된 필드에 대 한 포인터입니다.

*iids*<br/>
인터페이스 Id의 배열입니다.

### <a name="remarks"></a>설명

인터페이스 ID를 할당 `Base` 인덱스 인수에 의해 지정 된 배열 요소에 있습니다.

이 API의 이름, 달리 하나만 배열 요소가 수정 되; 전체 배열 되지 않습니다.

에 대 한 자세한 내용은 `Base`를 참조 합니다 [공용 Typedefs](#public-typedefs) 섹션입니다.

## <a name="iidcount"></a>InterfaceTraits::IidCount

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>설명

인터페이스는 현재 연결 된 Id의 수가 포함 `InterfaceTraits` 개체입니다.

## <a name="verify"></a>InterfaceTraits::Verify

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>설명

확인 `Base` 제대로 파생 됩니다.

에 대 한 자세한 내용은 `Base`를 참조 합니다 [공용 Typedefs](#public-typedefs) 섹션입니다.
