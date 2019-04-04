---
title: ImplementsHelper 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
ms.openlocfilehash: 250a59152e9b41eb48c453caaa696fdc8ca3d3b4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785653"
---
# <a name="implementshelper-structure"></a>ImplementsHelper 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>매개 변수

*RuntimeClassFlagsT*<br/>
플래그 중 하나 이상 지정 하는 필드 [RuntimeClassType](runtimeclasstype-enumeration.md) 열거자입니다.

*ILst*<br/>
목록 인터페이스 Id입니다.

*IsDelegateToClass*<br/>
지정 **true** 하는 경우 현재 인스턴스의 `Implements` 첫 번째 인터페이스 ID의 기본 클래스인 *ILst*고, 그렇지 않으면 **false**합니다.

## <a name="remarks"></a>설명

구현에 유용한 합니다 [구현](implements-structure.md) 구조입니다.

이 템플릿은 인터페이스의 목록을 트래버스하 고 사용 하도록 설정 하는 데 필요한 정보 및 기본 클래스로 추가 `QueryInterface`합니다.

## <a name="members"></a>멤버

### <a name="protected-methods"></a>Protected 메서드

이름                                                    | 설명
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[ImplementsHelper::CanCastTo](#cancastto)               | 지정 된 인터페이스 id와 같습니다. 포인터를 가져옵니다.
[ImplementsHelper::CastToUnknown](#casttounknown)       | 기본 포인터를 가져옵니다 `IUnknown` 현재 인터페이스 `Implements` 구조입니다.
[ImplementsHelper::FillArrayWithIid](#fillarraywithiid) | 현재 0 번째 템플릿 매개 변수로 지정 된 배열 요소에 지정 된 인터페이스 ID를 삽입 합니다.
[ImplementsHelper::IidCount](#iidcount)                 | 현재에서 구현 된 인터페이스 Id의 수가 포함 `Implements` 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ImplementsHelper`

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL::Details

## <a name="cancastto"></a>ImplementsHelper::CanCastTo

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);

HRESULT CanCastTo(
   _In_ const IID &iid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
인터페이스 ID에 대 한 참조

*ppv*<br/>
인터페이스에 대 한 포인터를 지정 하 여이 작업에 성공한 경우 *riid* 하거나 *iid*합니다.

*iid*<br/>
인터페이스 ID에 대 한 참조

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

지정 된 인터페이스 id와 같습니다. 포인터를 가져옵니다.

## <a name="casttounknown"></a>ImplementsHelper::CastToUnknown

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>반환 값

기본 포인터 `IUnknown` 인터페이스입니다.

### <a name="remarks"></a>설명

기본 포인터를 가져옵니다 `IUnknown` 현재 인터페이스 `Implements` 구조입니다.

## <a name="fillarraywithiid"></a>ImplementsHelper::FillArrayWithIid

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>매개 변수

*index*<br/>
이 작업에 대 한 시작 배열 요소를 나타내는 0부터 시작 인덱스입니다. 이 작업이 완료 되 면 *인덱스* 1 씩 증가 합니다.

*iids*<br/>
Iid 형식의 배열입니다.

### <a name="remarks"></a>설명

현재 0 번째 템플릿 매개 변수로 지정 된 배열 요소에 지정 된 인터페이스 ID를 삽입 합니다.

## <a name="iidcount"></a>ImplementsHelper::IidCount

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>설명

현재에서 구현 된 인터페이스 Id의 수가 포함 `Implements` 개체입니다.
