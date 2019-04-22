---
title: SyncLockT 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::sync_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockT class
- Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockT::sync_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT, constructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT, destructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock method
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
ms.openlocfilehash: d27e6ba8601d0e822113bf3a4a65269c89437271
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785612"
---
# <a name="synclockt-class"></a>SyncLockT 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>매개 변수

*SyncTraits*<br/>
리소스의 소유권을 가져올 수 있는 형식입니다.

## <a name="remarks"></a>설명

단독으로 사용할 수 있는 형식을 나타내는 또는 리소스의 소유권을 공유 합니다.

합니다 `SyncLockT` 클래스가 사용 되며, 예를 들어 구현할 수 있도록 합니다 [SRWLock](srwlock-class.md) 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                      | 설명
----------------------------------------- | ----------------------------------------------------
[SyncLockT::SyncLockT](#synclockt)        | `SyncLockT` 클래스의 새 인스턴스를 초기화합니다.
[SyncLockT::~SyncLockT](#tilde-synclockt) | 인스턴스를 초기화 해제는 `SyncLockT` 클래스입니다.

### <a name="protected-constructors"></a>Protected 생성자

이름                               | 설명
---------------------------------- | ----------------------------------------------------
[SyncLockT::SyncLockT](#synclockt) | `SyncLockT` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

이름                             | 설명
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[SyncLockT::IsLocked](#islocked) | 나타냅니다 여부 현재 `SyncLockT` 리소스를 소유 하는 개체입니다. 즉, `SyncLockT` 개체가 *잠겨*합니다.
[SyncLockT::Unlock](#unlock)     | 현재 보유 한 리소스의 제어권을 해제 `SyncLockT` 개체에 있는 경우.

### <a name="protected-data-members"></a>보호된 데이터 멤버

이름                      | 설명
------------------------- | -------------------------------------------------------------------
[SyncLockT::sync_](#sync) | 표시 되는 기본 리소스를 보유 합니다 `SyncLockT` 클래스입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SyncLockT`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::Details

## <a name="tilde-synclockt"></a>SyncLockT::~SyncLockT

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>설명

인스턴스를 초기화 해제는 `SyncLockT` 클래스입니다.

이 소멸자에는 또한 현재 잠금 해제 `SyncLockT` 인스턴스.

## <a name="islocked"></a>SyncLockT::IsLocked

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>반환 값

**true** 경우는 `SyncLockT` 개체가 고, 그렇지 않으면 잠긴 **false**합니다.

### <a name="remarks"></a>설명

나타냅니다 여부 현재 `SyncLockT` 리소스를 소유 하는 개체입니다. 즉, `SyncLockT` 개체가 *잠겨*합니다.

## <a name="sync"></a>SyncLockT::sync_

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>설명

표시 되는 기본 리소스를 보유 합니다 `SyncLockT` 클래스입니다.

## <a name="synclockt"></a>SyncLockT::SyncLockT

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>매개 변수

*other*<br/>
다른 rvalue 참조 `SyncLockT` 개체입니다.

*sync*<br/>
다른 참조 `SyncLockWithStatusT` 개체입니다.

### <a name="remarks"></a>설명

`SyncLockT` 클래스의 새 인스턴스를 초기화합니다.

첫 번째 생성자는 현재 `SyncLockT` 간에 개체 `SyncLockT` 매개 변수로 지정 된 개체 *다른*를 무효화 하는 다른 및 `SyncLockT` 개체입니다. 두 번째 생성자는 `protected`, 현재 초기화 `SyncLockT` 유효 하지 않은 상태로 개체입니다.

## <a name="unlock"></a>SyncLockT::Unlock

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
void Unlock();
```

### <a name="remarks"></a>설명

현재 보유 한 리소스의 제어권을 해제 `SyncLockT` 개체에 있는 경우.
