---
title: SemaphoreTraits 구조체
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: e7bd2e5d0993c8e4be7223d98ffb1dbec14cbb74
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785580"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits 구조체

일반적인 특성 정의 `Semaphore` 개체입니다.

## <a name="syntax"></a>구문

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

이름                               | 설명
---------------------------------- | --------------------------------------
[SemaphoreTraits::Unlock](#unlock) | 공유 리소스의 릴리스 컨트롤입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>SemaphoreTraits::Unlock

공유 리소스의 릴리스 컨트롤입니다.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
에 대 한 핸들을 `Semaphore` 개체입니다.

### <a name="remarks"></a>설명

잠금 해제 작업이 성공적 이면 `Unlock()` 실패의 원인을 나타내는 오류를 생성 합니다.
