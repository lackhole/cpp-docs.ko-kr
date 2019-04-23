---
title: SyncLockWithStatusT 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT class
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT, constructor
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
ms.openlocfilehash: 1c9c0805834a59d10a559bfc2b6da0f10e2fe160
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785621"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT 클래스

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>매개 변수

*SyncTraits*<br/>
단독으로 사용할 수 있는 형식 또는 리소스의 소유권을 공유 합니다.

## <a name="remarks"></a>설명

단독으로 사용할 수 있는 형식을 나타내는 또는 리소스의 소유권을 공유 합니다.

`SyncLockWithStatusT` 클래스를 구현 하는 데 사용 됩니다 합니다 [뮤텍스](mutex-class.md) 하 고 [세마포](semaphore-class.md) 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                                             | 설명
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT::SyncLockWithStatusT](#synclockwithstatust) | `SyncLockWithStatusT` 클래스의 새 인스턴스를 초기화합니다.

### <a name="protected-constructors"></a>Protected 생성자

이름                                                             | 설명
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT::SyncLockWithStatusT](#synclockwithstatust) | `SyncLockWithStatusT` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

이름                                         | 설명
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT::GetStatus](#getstatus) | 현재 대기 상태를 검색 `SyncLockWithStatusT` 개체입니다.
[SyncLockWithStatusT::IsLocked](#islocked)   | 나타냅니다 여부 현재 `SyncLockWithStatusT` 리소스를 소유 하는 개체입니다. 즉, `SyncLockWithStatusT` 개체가 *잠겨*합니다.

### <a name="protected-data-members"></a>보호된 데이터 멤버

이름                                    | 설명
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT::status_](#status) | 현재를 기준으로 개체에 대 한 잠금 작업이 후 기본 대기 작업의 결과 보관 `SyncLockWithStatusT` 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers::Details

## <a name="getstatus"></a>SyncLockWithStatusT::GetStatus

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>반환 값

기반이 되는 개체에서 대기 작업의 결과 `SyncLockWithStatusT` 와 같은 클래스를 [뮤텍스](mutex-class.md) 또는 [세마포](semaphore-class.md)합니다. 영 (0) 신호를 받은 상태를 반환 하는 대기 작업을 나타냅니다. 그렇지 않은 경우 경과 된 시간 제한 값과 같은 다른 상태가 발생 합니다.

### <a name="remarks"></a>설명

현재 대기 상태를 검색 `SyncLockWithStatusT` 개체입니다.

기본 값을 검색 하는 getstatus () 함수 [status_](#status) 데이터 멤버입니다. 개체에 기반 하는 경우는 `SyncLockWithStatusT` 잠금 작업을 수행 하는 클래스, 개체 먼저 개체를 사용할 수 있을 때까지 대기 합니다. 대기 작업의 결과에 저장 되는 `status_` 데이터 멤버입니다. 가능한 값은 `status_` 데이터 멤버는 대기 작업의 반환 값입니다. 자세한 내용은 참조 반환 값은 `WaitForSingleObjectEx()` MSDN 라이브러리의 함수입니다.

## <a name="islocked"></a>SyncLockWithStatusT::IsLocked

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>설명

나타냅니다 여부 현재 `SyncLockWithStatusT` 리소스를 소유 하는 개체입니다. 즉, `SyncLockWithStatusT` 개체가 *잠겨*합니다.

### <a name="return-value"></a>반환 값

**true** 경우는 `SyncLockWithStatusT` 개체가 고, 그렇지 않으면 잠긴 **false**합니다.

## <a name="status"></a>SyncLockWithStatusT::status_

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
DWORD status_;
```

### <a name="remarks"></a>설명

현재를 기준으로 개체에 대 한 잠금 작업이 후 기본 대기 작업의 결과 보관 `SyncLockWithStatusT` 개체입니다.

## <a name="synclockwithstatust"></a>SyncLockWithStatusT::SyncLockWithStatusT

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>매개 변수

*other*<br/>
다른 rvalue 참조 `SyncLockWithStatusT` 개체입니다.

*sync*<br/>
다른 참조 `SyncLockWithStatusT` 개체입니다.

*status*<br/>
값을 [status_](#status) 의 데이터 멤버는 *다른* 매개 변수 또는 *동기화* 매개 변수입니다.

### <a name="remarks"></a>설명

`SyncLockWithStatusT` 클래스의 새 인스턴스를 초기화합니다.

첫 번째 생성자는 현재 `SyncLockWithStatusT` 개체에서 다른 `SyncLockWithStatusT` 매개 변수에서 지정한 *다른*를 무효화 하는 다른 및 `SyncLockWithStatusT` 개체입니다. 두 번째 생성자는 `protected`, 현재 초기화 `SyncLockWithStatusT` 유효 하지 않은 상태로 개체입니다.
