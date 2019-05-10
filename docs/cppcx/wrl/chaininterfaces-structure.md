---
title: ChainInterfaces 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
- implements/Microsoft::WRL::ChainInterfaces::IidCount
- implements/Microsoft::WRL::ChainInterfaces::Verify
helpviewer_keywords:
- Microsoft::WRL::ChainInterfaces structure
- Microsoft::WRL::ChainInterfaces::CanCastTo method
- Microsoft::WRL::ChainInterfaces::CastToUnknown method
- Microsoft::WRL::ChainInterfaces::FillArrayWithIid method
- Microsoft::WRL::ChainInterfaces::IidCount constant
- Microsoft::WRL::ChainInterfaces::Verify method
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
ms.openlocfilehash: 9fd315f017d3dcc9823054ea99e845ec99bc4192
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398747"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces 구조체

인터페이스 ID 집합에 적용할 수 있는 확인 및 초기화 함수를 지정합니다.

## <a name="syntax"></a>구문

```cpp
template <
    typename I0,
    typename I1,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct ChainInterfaces : I0;

template <
    typename DerivedType,
    typename BaseType,
    bool hasImplements,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8,
    typename I9
>
struct ChainInterfaces<
    MixIn<
        DerivedType,
        BaseType,
        hasImplements
    >, I1, I2, I3, I4, I5, I6, I7, I8, I9
>;
```

### <a name="parameters"></a>매개 변수

*I0*<br/>
(필수) 인터페이스 ID 0입니다.

*I1*<br/>
(필수) 인터페이스 ID 1입니다.

*I2*<br/>
(선택 사항) 인터페이스 ID 2입니다.

*I3*<br/>
(선택 사항) 인터페이스 ID 3입니다.

*I4*<br/>
(선택 사항) ID 4 인터페이스입니다.

*I5*<br/>
(선택 사항) 인터페이스 ID 5입니다.

*I6*<br/>
(선택 사항) 인터페이스 ID 6입니다.

*I7*<br/>
(선택 사항) 인터페이스 ID 7입니다.

*I8*<br/>
(선택 사항) 인터페이스 ID 8입니다.

*I9*<br/>
(선택 사항) 인터페이스 ID 9입니다.

*DerivedType*<br/>
파생된 형식입니다.

*BaseType*<br/>
파생 형식이 기본 형식입니다.

*hasImplements*<br/>
경우에 해당 하는 부울 값 **true**를 사용할 수 없습니다는 [MixIn](mixin-structure.md) 에서 파생 되지 않은 클래스를 사용 하 여 구조를 [구현](implements-structure.md) 갖는 합니다.

## <a name="members"></a>멤버

### <a name="protected-methods"></a>Protected 메서드

이름                                                   | 설명
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ChainInterfaces::CanCastTo](#cancastto)               | 지정 된 인터페이스 ID 각 여 정의 된 특수화로 캐스팅 될 수 있는지 여부를 나타냅니다는 `ChainInterface` 템플릿 매개 변수입니다.
[ChainInterfaces::CastToUnknown](#casttounknown)       | 정의한 형식의 인터페이스 포인터를 캐스팅 합니다 *I0* 포인터에 대 한 템플릿 매개 변수 `IUnknown`합니다.
[ChainInterfaces::FillArrayWithIid](#fillarraywithiid) | 인터페이스 ID가 정의한 저장소 합니다 *I0* 인터페이스 Id의 지정된 된 배열에 지정된 된 위치에 템플릿 매개 변수입니다.
[ChainInterfaces::Verify](#verify)                     | 템플릿 매개 변수에서 정의 된 각 인터페이스가 확인 *I0* 를 통해 *I9* 에서 상속 `IUnknown` 및/또는 `IInspectable`를 올바르고 *I0* 에서 상속 *I1* 를 통해 *I9*합니다.

### <a name="protected-constants"></a>보호 된 상수

이름                                   | 설명
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[ChainInterfaces::IidCount](#iidcount) | 템플릿 매개 변수에서 지정한 인터페이스에 포함 된 인터페이스 Id의 총 *I0* 를 통해 *I9*합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`I0`

`ChainInterfaces`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="cancastto"></a>ChainInterfaces::CanCastTo

각 기본이 아닌 템플릿 매개 변수를 정의한 특수화에 지정 된 인터페이스 ID 캐스팅 될 수 있는지 여부를 나타냅니다.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID입니다.

*ppv*<br/>
성공적으로 캐스팅 된 마지막 인터페이스 ID에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

**true 이면** 모든 캐스트 작업이 성공 하면이 고, 그렇지 **false**합니다.

## <a name="casttounknown"></a>ChainInterfaces::CastToUnknown

정의한 형식의 인터페이스 포인터를 캐스팅 합니다 *I0* 포인터에 대 한 템플릿 매개 변수 `IUnknown`합니다.

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터 `IUnknown`합니다.

## <a name="fillarraywithiid"></a>ChainInterfaces::FillArrayWithIid

인터페이스 ID가 정의한 저장소 합니다 *I0* 인터페이스 Id의 지정된 된 배열에 지정된 된 위치에 템플릿 매개 변수입니다.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>매개 변수

*index*<br/>
에 인덱스 값에 대 한 포인터를 *iid* 배열입니다.

*iids*<br/>
인터페이스 Id의 배열입니다.

## <a name="iidcount"></a>ChainInterfaces::IidCount

템플릿 매개 변수에서 지정한 인터페이스에 포함 된 인터페이스 Id의 총 *I0* 를 통해 *I9*합니다.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>반환 값

인터페이스 ID의 총 개수입니다.

### <a name="remarks"></a>설명

템플릿 매개 변수 *I0* 하 고 *I1* 필요 및 매개 변수 *I2* 를 통해 *I9* 는 선택 사항입니다. 각 인터페이스의 IID 수는 일반적으로 1입니다.

## <a name="verify"></a>ChainInterfaces::Verify

템플릿 매개 변수에서 정의 된 각 인터페이스가 확인 *I0* 를 통해 *I9* 에서 상속 `IUnknown` 및/또는 `IInspectable`를 올바르고 *I0* 에서 상속 *I1* 를 통해 *I9*합니다.

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>설명

확인 작업이 실패하는 경우 `static_assert`에서 실패를 설명하는 오류 메시지를 내보냅니다.

템플릿 매개 변수 *I0* 하 고 *I1* 필요 및 매개 변수 *I2* 를 통해 *I9* 는 선택 사항입니다.
