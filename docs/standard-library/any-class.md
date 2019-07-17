---
title: 모든 클래스
ms.date: 04/04/2019
f1_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
helpviewer_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
ms.openlocfilehash: 050276da665ab6ed3eb53d9e65bfea06b88bcbea
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268755"
---
# <a name="any-class"></a>모든 클래스

모든 개체 클래스의 상태 라는 이거나 생성자 요구 사항을 충족 하는 모든 형식의 인스턴스 값이 없는 경우는 저장소입니다.

저장 된 인스턴스가 포함 된 값을 이라고 합니다. 두 상태 중 둘 값 없음 또는 둘 다 값 및 포함 된 값이 동일한 경우 같습니다.

## <a name="syntax"></a>구문

```cpp
class any
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[any](#any)|`any` 형식의 개체를 생성합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[emplace](#emplace)|모든 값을 설정합니다.|
|[has_value](#has_value)|반환 **true** 값이 있는 경우.|
|[reset](#reset)|Any를 다시 설정합니다.|
|[swap](#swap)|두 개의 교환 개체입니다.|
|[type](#type)|모든 형식을 반환합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator=](#op_eq)|모든 다른 복사본을 사용 하 여 하나를 바꿉니다.|

## <a name="any"></a> 모든

`any` 형식의 개체를 생성합니다. 소멸자가 포함 됩니다.

```cpp
constexpr any() noexcept;
any(const any& other);
any(any&& other) noexcept;
template <class T>
    any(T&& value);
template <class T, class... Args>
    explicit any(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    explicit any(in_place_type_t<T>, initializer_list<U>, Args&&...);

~any();
```

## <a name="emplace"></a> emplace

모든 값을 설정합니다.

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a> has_value

반환 **true** 값이 있는 경우.

```cpp
bool has_value() const noexcept;
```

## <a name="op_eq"></a> 연산자 =

모든 다른 복사본을 사용 하 여 하나를 바꿉니다.

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
모든 복사 되는 하나입니다.

## <a name="reset"></a> 다시 설정

Any를 다시 설정합니다.

```cpp
void reset() noexcept;
```

## <a name="swap"></a> 교환

두 개의 교환 개체입니다.

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a> 형식

모든 형식을 반환합니다.

```cpp
const type_info& type() const noexcept;
```
