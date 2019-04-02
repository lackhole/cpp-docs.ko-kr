---
title: CriticalSectionTraits 구조체
ms.date: 09/26/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
ms.openlocfilehash: ce904ecbd9a5855c63fd43f07f88c215cef544ae
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785380"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 구조체

전문적으로 다루는 `CriticalSection` 개체는 잘못 된 중요 한 섹션 또는 중요 섹션을 해제 하는 함수를 지원 합니다.

## <a name="syntax"></a>구문

```
struct CriticalSectionTraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름   | 설명
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | `typedef` 임계 영역에 대 한 포인터를 정의 하는 합니다. `Type` 로 정의 된 `typedef CRITICAL_SECTION* Type;`합니다.

### <a name="public-methods"></a>Public 메서드

이름                                                       | 설명
---------------------------------------------------------- | -----------------
[CriticalSectionTraits::GetInvalidValue](#getinvalidvalue) | 전문적으로 다루는 `CriticalSection` 템플릿 서식 파일은 항상 유효한 수 있도록 합니다.
[CriticalSectionTraits::Unlock](#unlock)                   | 특수화는 `CriticalSection` 를 지정 된 임계 영역 개체의 해제 소유권 지원 하므로 템플릿.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CriticalSectionTraits`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>CriticalSectionTraits::GetInvalidValue

전문적으로 다루는 `CriticalSection` 템플릿 서식 파일은 항상 유효한 수 있도록 합니다.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>반환 값

잘못 된 중요 한 섹션에 대 한 포인터를 항상 반환합니다.

### <a name="remarks"></a>설명

합니다 `Type` 한정자로 정의 된 `typedef CRITICAL_SECTION* Type;`합니다.

## <a name="unlock"></a>CriticalSectionTraits::Unlock

특수화는 `CriticalSection` 를 지정 된 임계 영역 개체의 해제 소유권 지원 하므로 템플릿.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
임계 영역 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

합니다 `Type` 한정자로 정의 된 `typedef CRITICAL_SECTION* Type;`합니다.

자세한 내용은 **LeaveCriticalSection 함수** 에 **동기화 함수** Windows API 설명서의 섹션입니다.
