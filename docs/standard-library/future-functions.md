---
title: '&lt;future&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: 56ae0da7e86e092cee46d24d1a2a27d9d54709e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159511"
---
# <a name="ltfuturegt-functions"></a>&lt;future&gt; 함수

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[swap](#swap)|

## <a name="async"></a>  async

*비동기 공급자*를 나타냅니다.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>매개 변수

*policy*<br/>
[launch](../standard-library/future-enums.md#launch) 값입니다.

### <a name="remarks"></a>설명

약어의 정의:

|||
|-|-|
|*dfn*|호출하는 `decay_copy(forward<Fn>(fn))`의 결과입니다.|
|*dargs*|`decay_copy(forward<ArgsTypes>(args...))` 호출의 결과입니다.|
|*Ty*|`result_of<Fn(ArgTypes...)>::type` 형식|

첫 번째 템플릿 함수는 `async(launch::any, fn, args...)`를 반환합니다.

두 번째 함수는 *연결된 비동기 상태*에 *dfn* 및 *dargs*의 값과 결과를 갖는 `future<Ty>` 개체와, 개별 스레드 실행을 관리하는 스레드 개체를 반환합니다.

`decay<Fn>::type`이 시작 이외의 형식이 아닌 경우 두 번째 함수는 오버로드 확인에 참여하지 않습니다.

C++ 표준 상태 정책 launch::async 인 함수는 새 스레드를 만듭니다. 그러나 Microsoft에서 구현한은 현재 비준수입니다. 경우에 따라 새로 보다는 재생된 스레드를 제공할 수 있는 Windows 스레드 풀에서 해당 스레드를 가져옵니다. 즉 합니다 `launch::async` 정책으로 실제로 구현 `launch::async|launch::deferred`합니다.  ThreadPool 기반 구현의 또 다른 문제는 보장이 없다는 스레드가 완료 될 때 스레드 지역 변수는 소멸 됩니다. 스레드가 재활용 되며 새 호출으로 제공 `async`, 이전 변수는 계속 존재 합니다. 따라서 사용 하 여 스레드 로컬 변수를 사용 하지 않는 권장 `async`합니다.

경우 *정책* 됩니다 `launch::deferred`, 함수가 있는 것으로 연결 된 비동기 상태를 표시를 *지연 된 함수* 반환 합니다. 연결된 비동기 상태가 유효해지기를 기다리는 non-timed 함수의 첫 번째 호출은 `INVOKE(dfn, dargs..., Ty)`를 평가함으로써 지연된 함수를 호출합니다.

어떤 경우에도 `future` 개체의 연결된 비동기 상태는 예외를 throw하거나 정상적으로 반환함으로써 `INVOKE(dfn, dargs..., Ty)`의 계산이 완료될 때까지 *준비*로 설정되지 않습니다. 예외가 throw되거나 계산에서 값이 반환된 경우 연결된 비동기 상태의 결과는 예외입니다.

> [!NOTE]
> `std::async`로 시작하는 작업에 연결된 `future` 또는 마지막 [shared_future](../standard-library/shared-future-class.md)의 경우 작업이 완료되지 않은 경우 소멸자가 차단됩니다. 즉 이 스레드가 `.get()` 또는 `.wait()`를 아직 호출하지 않은 경우 소멸자를 차단하고 작업을 계속 실행합니다. `future`에서 가져온 `std::async`가 로컬 범위 밖으로 이동되는 경우 해당 future를 사용하는 다른 코드는 공유 상태 준비를 위해 소멸자가 차단될 것을 알고 있어야 합니다.

의사 함수 `INVOKE`는 [\<functional>](../standard-library/functional.md)에 정의되어 있습니다.

## <a name="future_category"></a>  future_category

`future` 개체와 연결된 오류의 특징을 결정하는 [error_category](../standard-library/error-category-class.md) 개체에 대한 참조를 반환합니다.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a>  make_error_code

[future](../standard-library/future-class.md) 오류의 특징을 결정하는 [error_category](../standard-library/error-category-class.md) 개체와 함께 [error_code](../standard-library/error-code-class.md)를 만듭니다.

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>매개 변수

*Errno*<br/>
보고된 오류를 식별하는 [future_errc](../standard-library/future-enums.md#future_errc) 값입니다.

### <a name="return-value"></a>반환 값

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a>  make_error_condition

[future](../standard-library/future-class.md) 오류의 특정을 결정하는 [error_category](../standard-library/error-category-class.md) 개체와 함께 [error_condition](../standard-library/error-condition-class.md)을 만듭니다.

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>매개 변수

*Errno*<br/>
보고된 오류를 식별하는 [future_errc](../standard-library/future-enums.md#future_errc) 값입니다.

### <a name="return-value"></a>반환 값

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>  swap

`promise` 개체 하나의 *연결된 비동기 상태*를 다른 개체의 상태와 교환합니다.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>매개 변수

*왼쪽*<br/>
왼쪽 `promise` 개체입니다.

*오른쪽*<br/>
오른쪽 `promise` 개체입니다.

## <a name="see-also"></a>참고자료

[\<future>](../standard-library/future.md)<br/>
