---
title: SRWLock 클래스
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: 079f1abe652d8c1610a084f5e1158cc5798d61c4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498298"
---
# <a name="srwlock-class"></a>SRWLock 클래스

슬림 판독기/작성기 잠금을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class SRWLock;
```

## <a name="remarks"></a>설명

슬림형 판독기/writer 잠금은 스레드 간 액세스를 개체 또는 리소스에 동기화 하는 데 사용 됩니다. 자세한 내용은 [동기화 함수](/windows/win32/Sync/synchronization-functions)를 참조 하세요.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름                | Description
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Exclusive 모드로 획득 `SRWLock` 된 개체의 동의어입니다.
`SyncLockShared`    | 공유 모드로 획득 `SRWLock` 된 개체의 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

이름                                     | Description
---------------------------------------- | --------------------------------------------------
[SRWLock::SRWLock](#srwlock-constructor) | `SRWLock` 클래스의 새 인스턴스를 초기화합니다.
[SRWLock::~SRWLock](#tilde-srwlock)      | `SRWLock` 클래스의 인스턴스를 초기화 하지 않습니다.

### <a name="public-methods"></a>Public 메서드

이름                                           | Description
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock::LockExclusive](#lockexclusive)       | 단독 모드 `SRWLock` 에서 개체를 가져옵니다.
[SRWLock::LockShared](#lockshared)             | 공유 모드 `SRWLock` 에서 개체를 가져옵니다.
[SRWLock::TryLockExclusive](#trylockexclusive) | 현재 또는 지정 된 `SRWLock` `SRWLock` 개체에 대해 배타 모드로 개체를 가져오려고 시도 합니다.
[SRWLock::TryLockShared](#trylockshared)       | 현재 또는 지정 된 `SRWLock` `SRWLock` 개체에 대해 공유 모드에서 개체를 가져오려고 시도 합니다.

### <a name="protected-data-member"></a>보호 된 데이터 멤버

이름                                      | 설명
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock::SRWLock_](#srwlock-data-member) | 현재 `SRWLock` 개체에 대 한 기본 잠금 변수를 포함 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`SRWLock`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers

## <a name="tilde-srwlock"></a>SRWLock::~SRWLock

`SRWLock` 클래스의 인스턴스를 초기화 하지 않습니다.

```cpp
~SRWLock();
```

## <a name="lockexclusive"></a>SRWLock::LockExclusive

단독 모드 `SRWLock` 에서 개체를 가져옵니다.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
`SRWLock` 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

Exclusive 모드의 개체입니다. `SRWLock`

## <a name="lockshared"></a>SRWLock::LockShared

공유 모드 `SRWLock` 에서 개체를 가져옵니다.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
`SRWLock` 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

공유 모드의 개체입니다. `SRWLock`

## <a name="srwlock-constructor"></a>SRWLock::SRWLock

`SRWLock` 클래스의 새 인스턴스를 초기화합니다.

```cpp
SRWLock();
```

## <a name="srwlock-data-member"></a>SRWLock::SRWLock_

현재 `SRWLock` 개체에 대 한 기본 잠금 변수를 포함 합니다.

```cpp
SRWLOCK SRWLock_;
```

## <a name="trylockexclusive"></a>SRWLock::TryLockExclusive

현재 또는 지정 된 `SRWLock` `SRWLock` 개체에 대해 배타 모드로 개체를 가져오려고 시도 합니다. 호출에 성공 하면 호출 스레드는 잠금의 소유권을 갖습니다.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
`SRWLock` 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 전용 모드 `SRWLock` 의 개체와 호출 스레드가 잠금의 소유권을 갖습니다. 그렇지 않으면 상태가 잘못 된 개체입니다.`SRWLock`

## <a name="trylockshared"></a>SRWLock::TryLockShared

현재 또는 지정 된 `SRWLock` `SRWLock` 개체에 대해 공유 모드에서 개체를 가져오려고 시도 합니다.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
`SRWLock` 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 공유 모드 `SRWLock` 의 개체와 호출 스레드가 잠금의 소유권을 갖습니다. 그렇지 않으면 상태가 잘못 된 개체입니다.`SRWLock`
