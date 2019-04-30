---
title: CriticalSection 클래스
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::cs_
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::IsValid
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::CriticalSection class
- Microsoft::WRL::Wrappers::CriticalSection::cs_ data member
- Microsoft::WRL::Wrappers::CriticalSection::IsValid method
- Microsoft::WRL::Wrappers::CriticalSection::Lock method
- Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection, destructor
- Microsoft::WRL::Wrappers::CriticalSection::CriticalSection, constructor
- Microsoft::WRL::Wrappers::CriticalSection::TryLock method
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
ms.openlocfilehash: dd34206741ba8fee8b283e22b6e8eefb3b3efb0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398591"
---
# <a name="criticalsection-class"></a>CriticalSection 클래스

임계 영역 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class CriticalSection;
```

## <a name="members"></a>멤버

### <a name="constructor"></a>생성자

이름                                                        | 설명
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[CriticalSection::CriticalSection](#criticalsection)        | 뮤텍스 개체와 유사하지만 단일 프로세스의 스레드에만 사용할 수 있는 동기화 개체를 초기화합니다.
[CriticalSection::~CriticalSection](#tilde-criticalsection) | 초기화를 취소 하 고 현재 소멸 `CriticalSection` 개체입니다.

### <a name="public-methods"></a>Public 메서드

이름                                 | 설명
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[CriticalSection::IsValid](#isvalid) | 현재 임계 영역이 유효한지 여부를 나타냅니다.
[CriticalSection::Lock](#lock)       | 지정된 임계 영역 개체의 소유권을 기다립니다. 함수가 호출 스레드가 소유권을 부여받는 시기를 반환합니다.
[CriticalSection::TryLock](#trylock) | 임계 영역을 차단 하지 않고 입력 하려고 합니다. 호출이 성공 하면 호출 스레드가 중요 섹션의 소유권을 갖습니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

이름                        | 설명
--------------------------- | ----------------------------------------
[CriticalSection::cs_](#cs) | 임계 영역 데이터 멤버를 선언합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CriticalSection`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers

## <a name="tilde-criticalsection"></a>CriticalSection::~CriticalSection

초기화를 취소 하 고 현재 소멸 `CriticalSection` 개체입니다.

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsection"></a>CriticalSection::CriticalSection

뮤텍스 개체와 유사하지만 단일 프로세스의 스레드에만 사용할 수 있는 동기화 개체를 초기화합니다.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>매개 변수

*spincount*<br/>
임계 영역 개체의 스핀 수입니다. 기본값은 0입니다.

### <a name="remarks"></a>설명

임계 영역 및 스핀 수에 대 한 자세한 내용은 참조는 `InitializeCriticalSectionAndSpinCount` 함수는 `Synchronization` Windows API 설명서의 섹션입니다.

## <a name="cs"></a>CriticalSection::cs_

임계 영역 데이터 멤버를 선언합니다.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>설명

이 데이터 멤버가 보호됩니다.

## <a name="isvalid"></a>CriticalSection::IsValid

현재 임계 영역이 유효한지 여부를 나타냅니다.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>반환 값

기본적으로 항상 반환 **true**합니다.

## <a name="lock"></a>CriticalSection::Lock

지정된 임계 영역 개체의 소유권을 기다립니다. 함수가 호출 스레드가 소유권을 부여받는 시기를 반환합니다.

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
사용자가 지정한 임계 영역 개체입니다.

### <a name="return-value"></a>반환 값

현재 임계 영역의 잠금을 해제하는 데 사용할 수 있는 잠금 개체입니다.

### <a name="remarks"></a>설명

첫 번째 `Lock` 함수는 현재 임계 영역 개체에 영향을 미칩니다. 두 번째 `Lock` 함수는 사용자가 지정한 임계 영역에 영향을 미칩니다.

## <a name="trylock"></a>CriticalSection::TryLock

임계 영역을 차단 하지 않고 입력 하려고 합니다. 호출이 성공 하면 호출 스레드가 중요 섹션의 소유권을 갖습니다.

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>매개 변수

*cs*<br/>
사용자가 지정한 임계 영역 개체입니다.

### <a name="return-value"></a>반환 값

중요 섹션은 성공적으로 입력 한 경우 0이 아닌 값 또는 현재 스레드에 이미 중요 섹션을 소유 합니다. 다른 스레드가 중요 섹션을 이미 소유 하는 경우 0입니다.

### <a name="remarks"></a>설명

첫 번째 `TryLock` 함수는 현재 임계 영역 개체에 영향을 미칩니다. 두 번째 `TryLock` 함수는 사용자가 지정한 임계 영역에 영향을 미칩니다.
