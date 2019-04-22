---
title: Semaphore 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
ms.openlocfilehash: 10357bb1cd46a33a8d4090c1ccc30050584d1816
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785669"
---
# <a name="semaphore-class"></a>Semaphore 클래스

제한된 사용자 수를 지원할 수 있는 공유 리소스를 제어하는 동기화 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

이름       | 설명
---------- | ------------------------------------------------------
`SyncLock` | 동기 잠금을 지 원하는 클래스에 대 한 동의어입니다.

### <a name="public-constructors"></a>Public 생성자

이름                               | 설명
---------------------------------- | ----------------------------------------------------
[Semaphore::Semaphore](#semaphore) | `Semaphore` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

이름                     | 설명
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Semaphore::Lock](#lock) | 현재 개체 또는 지정된 된 핸들과 연결 된 개체가 될 때까지 대기한 신호를 받은 상태 이거나 지정한 시간 제한 간격이 경과 합니다.

### <a name="public-operators"></a>Public 연산자

이름                                     | 설명
---------------------------------------- | ---------------------------------------------------------------------------------------
[Semaphore::operator=](#operator-assign) | 지정 된 핸들을 이동 하는 `Semaphore` 개체를 현재 `Semaphore` 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Semaphore`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers

## <a name="lock"></a>Semaphore::Lock

현재 개체를 때까지 대기 또는 `Semaphore` 개체와 연결 된 지정된 된 핸들에 신호를 받은 상태 이거나 지정한 시간 제한 간격이 경과 합니다.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>매개 변수

*milliseconds*<br/>
제한 시간 간격(밀리초)입니다. 기본값은 INFINITE으로, 무제한 대기합니다.

*h*<br/>
에 대 한 핸들을 `Semaphore` 개체입니다.

### <a name="return-value"></a>반환 값

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`입니다.

## <a name="operator-assign"></a>Semaphore::operator=

지정 된 핸들을 이동 하는 `Semaphore` 개체를 현재 `Semaphore` 개체입니다.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
대 한 Rvalue 참조는 `Semaphore` 개체입니다.

### <a name="return-value"></a>반환 값

현재에 대 한 참조 `Semaphore` 개체입니다.

## <a name="semaphore"></a>Semaphore::Semaphore

`Semaphore` 클래스의 새 인스턴스를 초기화합니다.

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>매개 변수

*h*<br/>
핸들 또는 rvalue 참조에는 `Semaphore` 개체입니다.
