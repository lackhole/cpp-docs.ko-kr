---
title: SRWLockSharedTraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
ms.openlocfilehash: af567fd333854519df4543ad24084e52cda4d96e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784783"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 구조체

일반적인 특징을 설명 합니다 `SRWLock` 공유 잠금 모드의 클래스입니다.

## <a name="syntax"></a>구문

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름   | 설명
------ | --------------------------------------------------------------------------
`Type` | 동의어에 대 한 포인터를 [SRWLOCK](srwlock-class.md) 클래스입니다.

### <a name="public-methods"></a>Public 메서드

이름                                                     | 설명
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLockSharedTraits::GetInvalidValue](#getinvalidvalue) | 검색을 `SRWLockSharedTraits` 항상 유효 하지 않은 개체입니다.
[SRWLockSharedTraits::Unlock](#unlock)                   | 지정 된 한 독점적인 제어권을 해제 `SRWLock` 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SRWLockSharedTraits`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>SRWLockSharedTraits::GetInvalidValue

검색을 `SRWLockSharedTraits` 항상 유효 하지 않은 개체입니다.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>반환 값

에 대 한 핸들을 `SRWLockSharedTraits` 개체입니다.

## <a name="unlock"></a>SRWLockSharedTraits::Unlock

지정 된 한 독점적인 제어권을 해제 `SRWLock` 개체입니다.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>매개 변수

*srwlock*<br/>
에 대 한 핸들을 `SRWLock` 개체입니다.
