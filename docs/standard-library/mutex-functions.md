---
title: '&lt;mutex&gt; 함수 및 변수'
ms.date: 11/04/2016
f1_keywords:
- mutex/std::adopt_lock
- mutex/std::call_once
- mutex/std::defer_lock
- mutex/std::lock
- mutex/std::try_to_lock
ms.assetid: 78ab3c8b-c7db-4226-ac93-e2e78ff8b964
helpviewer_keywords:
- std::adopt_lock [C++]
- std::call_once [C++]
- std::defer_lock [C++]
- std::lock [C++]
- std::try_to_lock [C++]
ms.openlocfilehash: b375aec0bee4183563b8cd55e4e8a27f79e7cd3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326328"
---
# <a name="ltmutexgt-functions-and-variables"></a>&lt;mutex&gt; 함수 및 변수

||||
|-|-|-|
|[adopt_lock](#adopt_lock)|[call_once](#call_once)|[defer_lock](#defer_lock)|
|[lock](#lock)|[try_to_lock](#try_to_lock)|

## <a name="adopt_lock"></a>  adopt_lock 변수

생성자에게 전달 중인 뮤텍스 개체가 잠겨 있음을 나타내기 위해 [lock_guard](../standard-library/lock-guard-class.md) 및 [unique_lock](../standard-library/unique-lock-class.md)의 생성자에 전달할 수 있는 개체를 나타냅니다.

```cpp
const adopt_lock_t adopt_lock;
```

## <a name="call_once"></a>  call_once

지정된 호출 가능 개체를 실행 중 정확하게 한 번 호출할 수 있는 메커니즘을 제공합니다.

```cpp
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```

### <a name="parameters"></a>매개 변수

*플래그*<br/>
호출 가능 개체가 한 번만 호출되도록 하는 [once_flag](../standard-library/once-flag-structure.md) 개체입니다.

*F*<br/>
호출 가능 개체입니다.

*A*<br/>
인수 목록입니다.

### <a name="remarks"></a>설명

하는 경우 *플래그* 유효 하지 않은 throw를 [system_error](../standard-library/system-error-class.md) 오류 코드가 있는 `invalid_argument`합니다. 템플릿 함수는 사용이 고, 그렇지 해당 *플래그* 인수를 호출 하는 것 `F(A...)` 성공적으로 정확히 한 번 횟수에 관계 없이 템플릿 함수를 호출 합니다. 예외가 throw되어 `F(A...)`가 종료되면 호출은 실패한 것입니다.

## <a name="defer_lock"></a>  defer_lock 변수

[unique_lock](../standard-library/unique-lock-class.md)을 위해 생성자에 전달할 수 있는 개체를 나타냅니다. 이 변수는 생성자가 역시 생성자로 전달되는 뮤텍스 개체를 잠그면 안 됨을 나타냅니다.

```cpp
const defer_lock_t defer_lock;
```

## <a name="lock"></a>  lock

교착 상태가 발생하지 않고 모든 인수를 잠그려고 시도합니다.

```cpp
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```

### <a name="remarks"></a>설명

템플릿 함수에 대한 인수는 *뮤텍스 형식*이어야 합니다. 단, `try_lock` 호출에서는 예외를 throw할 수 있습니다.

함수는 `lock`, `try_lock`, `unlock` 호출에 의한 교착 상태 없이 모든 인수를 잠급니다. `lock` 또는 `try_lock` 호출에서 예외가 throw되면 함수는 예외를 다시 throw하기 전에 정상적으로 잠긴 모든 뮤텍스 개체에 대해 `unlock`을 호출합니다.

## <a name="try_to_lock"></a>  try_to_lock 변수

생성자가 차단 없이 역시 생성자로 전달되는 `mutex`의 잠금 해제를 시도해야 함을 나타내기 위해 [unique_lock](../standard-library/unique-lock-class.md)의 생성자에 전달할 수 있는 개체를 나타냅니다.

```cpp
const try_to_lock_t try_to_lock;
```

## <a name="see-also"></a>참고자료

[\<mutex>](../standard-library/mutex.md)<br/>
