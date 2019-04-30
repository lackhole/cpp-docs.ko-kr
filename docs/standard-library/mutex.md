---
title: '&lt;mutex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <mutex>
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
ms.openlocfilehash: 4655278e312647f4e69cf48cb772df854260ce57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224079"
---
# <a name="ltmutexgt"></a>&lt;mutex&gt;

`mutex`, `recursive_mutex`, `timed_mutex`, `recursive_timed_mutex` 클래스, `lock_guard`, `unique_lock` 템플릿, 그리고 상호 배제 코드 영역을 정의하는 지원 형식과 함수를 정의하려면 표준 헤더 \<mutex>를 포함합니다.

> [!WARNING]
> Visual Studio 2015에서 시작 하는 C++ 표준 라이브러리 동기화 형식은 Windows 동기화 기본 형식을 기반으로 하 고 더 이상 ConcRT를 사용 하 여 (대상 플랫폼이 Windows XP 인 경우) 제외 합니다. \<mutex>에 정의된 형식은 모든 ConcRT 형식 및 함수와 함께 사용하면 안 됩니다.

## <a name="syntax"></a>구문

```cpp
#include <mutex>
```

## <a name="remarks"></a>설명

> [!NOTE]
> 코드를 사용 하 여 컴파일된 **/clr**,이 헤더가 차단 됩니다.

`mutex` 및 `recursive_mutex` 클래스는 *뮤텍스 형식*입니다. 뮤텍스 형식에는 예외를 throw하지 않는 기본 생성자와 소멸자가 있습니다. 이러한 개체에는 여러 스레드가 동일한 개체를 잠그려고 할 때 상호 배제하는 메서드가 있습니다. 특히, 뮤텍스 형식에는 `lock`, `try_lock` 및 `unlock` 메서드가 포함되어 있습니다.

- 스레드가 뮤텍스의 소유권을 가져올 때까지 `lock` 메서드가 호출 스레드를 차단합니다. 반환 값은 무시됩니다.

- `try_lock` 메서드는 차단하지 않고 뮤텍스에 대한 소유권을 가져오려고 시도합니다. 해당 반환 형식으로 변환할 **bool** 되며 **true** 메서드가 소유권을 가져오면 있지만 고 그렇지 않으면 **false**합니다.

- `unlock` 메서드는 호출 스레드에서 뮤텍스의 소유권을 해제합니다.

뮤텍스 형식을 형식 인수로 사용하여 템플릿 `lock_guard` 및 `unique_lock`을 인스턴스화할 수 있습니다. 템플릿 [condition_variable_any](../standard-library/condition-variable-any-class.md)에서 이러한 형식의 개체를 구성원 대기 함수에 대한 `Lock` 인수로 사용할 수 있습니다.

*시간이 지정된 뮤텍스 형식*은 뮤텍스 형식에 대한 요구 사항을 충족합니다. 또한에 `try_lock_for` 하 고 `try_lock_until` 메서드는 하나의 인수를 사용 하 여 호출할 수 있어야 하 고 변환할 수 있는 형식을 반환 해야 합니다 **bool**합니다. 시간이 지정된 뮤텍스 형식은 추가 인수 모두에 기본값이 있는 경우 이러한 인수를 사용하여 함수를 정의할 수 있습니다.

- `try_lock_for` 메서드는 하나의 인수 즉, `Rel_time`을 사용하여 호출할 수 있어야 합니다. 이 인수의 형식은 [chrono::duration](../standard-library/duration-class.md)의 인스턴스화입니다. 이 메서드에서 뮤텍스의 소유권을 가져오려고 시도하지만 성공 여부에 관계없이 `Rel_time`으로 지정한 시간 이내에 반환합니다. 반환 값으로 변환 **true** 메서드가 소유권을 가져오면 그렇지 않은 경우 반환 값 변환 **false**합니다.

- `try_lock_until` 메서드는 하나의 인수 즉, `Abs_time`을 사용하여 호출할 수 있어야 합니다. 이 인수의 형식은 [chrono::time_point](../standard-library/time-point-class.md)의 인스턴스화입니다. 이 메서드에서 뮤텍스의 소유권을 가져오려고 시도하지만 성공 여부에 관계없이 `Abs_time`으로 지정한 시간 이내에 반환합니다. 반환 값으로 변환 **true** 메서드가 소유권을 가져오면 그렇지 않은 경우 반환 값 변환 **false**합니다.

뮤텍스 형식은 *잠금 가능 형식*이라고도 합니다. 구성원 함수 `try_lock`을 제공하지 않는 경우 *기본 잠금 형식*입니다. 시간이 지정된 뮤텍스 형식은 *시간이 지정된 잠금 가능 형식*이라고도 합니다.

### <a name="classes"></a>클래스

|이름|설명|
|----------|-----------------|
|[lock_guard 클래스](../standard-library/lock-guard-class.md)|소멸자가 `mutex`의 잠금을 해제하는 개체를 만들기 위해 인스턴스화할 수 있는 템플릿을 나타냅니다.|
|[mutex 클래스(C++ 표준 라이브러리)](../standard-library/mutex-class-stl.md)|뮤텍스 형식을 나타냅니다. 이 형식의 개체를 사용하면 프로그램 내에서 상호 배제를 강제로 수행할 수 있습니다.|
|[recursive_mutex 클래스](../standard-library/recursive-mutex-class.md)|뮤텍스 형식을 나타냅니다. `mutex` 클래스와 달리 이미 잠겨 있는 개체에 대한 잠금 메서드 호출 동작이 잘 정의되어 있습니다.|
|[recursive_timed_mutex 클래스](../standard-library/recursive-timed-mutex-class.md)|시간이 지정된 뮤텍스 형식을 나타냅니다. 이러한 형식의 개체를 사용하면 프로그램 내에서 시간이 제한된 차단이 있는 상호 배제를 강제로 수행할 수 있습니다. `timed_mutex` 형식의 개체와 달리 `recursive_timed_mutex` 개체에 대한 잠금 메서드 호출의 효과가 잘 정의되어 있습니다.|
|[timed_mutex 클래스](../standard-library/timed-mutex-class.md)|시간이 지정된 뮤텍스 형식을 나타냅니다. 이러한 형식의 개체를 사용하면 프로그램 내에서 시간이 제한된 차단이 있는 상호 배제를 강제로 수행할 수 있습니다.|
|[unique_lock 클래스](../standard-library/unique-lock-class.md)|`mutex`의 잠금 및 잠금 해제를 관리하는 개체를 만들기 위해 인스턴스화할 수 있는 템플릿을 나타냅니다.|

### <a name="functions"></a>함수

|이름|설명|
|----------|-----------------|
|[call_once](../standard-library/mutex-functions.md#call_once)|지정된 호출 가능 개체를 실행 중 정확하게 한 번 호출할 수 있는 메커니즘을 제공합니다.|
|[lock](../standard-library/mutex-functions.md#lock)|교착 상태가 발생하지 않고 모든 인수를 잠그려고 시도합니다.|

### <a name="structs"></a>Structs

|이름|설명|
|----------|-----------------|
|[adopt_lock_t 구조체](../standard-library/adopt-lock-t-structure.md)|`adopt_lock`을 정의하는 데 사용되는 형식을 나타냅니다.|
|[defer_lock_t 구조체](../standard-library/defer-lock-t-structure.md)|`unique_lock`의 오버로드된 생성자 중 하나를 선택하는 데 사용되는 `defer_lock` 개체를 정의하는 형식을 나타냅니다.|
|[once_flag 구조체](../standard-library/once-flag-structure.md)|나타냅니다는 **구조체** 템플릿 함수를 사용 하 여 사용 되는 `call_once` 해당 초기화 되도록 코드는 한 번만 호출, 다중 스레드 방식의 실행 하는 경우에 합니다.|
|[try_to_lock_t 구조체](../standard-library/try-to-lock-t-structure.md)|나타냅니다를 **구조체** 정의 하는 `try_to_lock` 개체의 오버 로드 된 생성자 중 하나를 선택 하는 데 사용 되 고 `unique_lock`입니다.|

### <a name="variables"></a>변수

|이름|설명|
|----------|-----------------|
|[adopt_lock](../standard-library/mutex-functions.md#adopt_lock)|생성자에게 전달 중인 뮤텍스 개체가 잠겨 있음을 나타내기 위해 `lock_guard` 및 `unique_lock`의 생성자에 전달할 수 있는 개체를 나타냅니다.|
|[defer_lock](../standard-library/mutex-functions.md#defer_lock)|생성자가 전달 중인 뮤텍스 개체를 잠그면 안 됨을 나타내기 위해 `unique_lock`의 생성자에 전달할 수 있는 개체를 나타냅니다.|
|[try_to_lock](../standard-library/mutex-functions.md#try_to_lock)|생성자가 차단 없이 전달 중인 `mutex`의 잠금을 해제하려고 하면 안 됨을 나타내기 위해 `unique_lock`의 생성자에 전달할 수 있는 개체를 나타냅니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
