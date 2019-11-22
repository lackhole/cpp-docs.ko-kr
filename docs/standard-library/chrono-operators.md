---
title: '&lt;chrono&gt; 연산자'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 398e2429c38cffb454c7b510aa5ab44fbe4cfef6
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244886"
---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt; 연산자

## <a name="operator-"></a> 연산자-

[duration](../standard-library/duration-class.md) 및 [time_point](../standard-library/time-point-class.md) 개체의 빼기 또는 부정 연산자입니다.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator-(
       const duration<Rep1, Period1>& Left,
       cconst duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type
   operator-(
       const time_point<Clock, Duration1>& Time,
       const duration<Rep2, Period2>& Dur);

template <class Clock, class Duration1, class Duration2>
constexpr typename common_type<Duration1, Duration2>::type
   operator-(
       const time_point<Clock, Duration1>& Left,
       const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `duration` 또는 `time_point` 개체입니다.

*오른쪽*\
오른쪽 `duration` 또는 `time_point` 개체입니다.

*시간*\
`time_point` 개체입니다.

*기간*\
`duration` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 함수는 간격 길이가 두 인수의 시간 간격 간 차이인 `duration` 개체를 반환합니다.

두 번째 함수를 반환 합니다는 `time_point` 시간으로 표현 되는 시간 간격의 부정 만큼 치환 된 시점을 나타내는 개체 *Dur*를 지정 된 시점에서 *Time*.

세 번째 함수를 반환 합니다는 `duration` 사이의 시간 간격을 나타내는 개체 *Left* 하 고 *Right*합니다.

## <a name="op_neq"></a> operator!=

[duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체에 대한 같지 않음 연산자입니다.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `duration` 또는 `time_point` 개체입니다.

*오른쪽*\
오른쪽 `duration` 또는 `time_point` 개체입니다.

### <a name="return-value"></a>반환 값

각 함수는 `!(Left == Right)`를 반환합니다.

## <a name="op_star"></a> 연산자 *

[duration](../standard-library/chrono-operators.md#op_star) 개체에 대한 곱하기 연산자입니다.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator*(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Mult);

template <class Rep1, class Rep2, class Period2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2>
   operator*(
       const Rep1& Mult,
       const duration<Rep2,
       Period2>& Dur);
```

### <a name="parameters"></a>매개 변수

*기간*\
`duration` 개체입니다.

*Mult*\
정수 값입니다.

### <a name="return-value"></a>반환 값

각 함수가 반환 하는 `duration` 개체는 간격 길이가 *Mult* 의 길이로 곱해지고 *Dur*합니다.

`is_convertible<Rep2, common_type<Rep1, Rep2>>`가 *true*가 아닌 한 첫 번째 함수는 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.

`is_convertible<Rep1, common_type<Rep1, Rep2>>`가 *true*가 아닌 한 두 번째 함수는 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.

## <a name="op_div"></a> 연산자 /

[duration](../standard-library/chrono-operators.md#op_star) 개체에 대한 나누기 연산자입니다.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator/(
     const duration<Rep1, Period1>& Dur,
     const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<Rep1, Rep2>::type
   operator/(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>매개 변수

*기간*\
`duration` 개체입니다.

*div*\
정수 값입니다.

*왼쪽*\
왼쪽 `duration` 개체입니다.

*오른쪽*\
오른쪽 `duration` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 연산자 개체를 반환 합니다 시간 간격이 길이가 길이의 *Dur* 값으로 나눈 *Div*합니다.

두 번째 연산자의 간격 길이 비율을 반환 합니다. *왼쪽* 하 고 *오른쪽*합니다.

`is_convertible<Rep2, common_type<Rep1, Rep2>>`가 *true*이고 `Rep2`가 `duration`의 인스턴스화가 아닌 경우 외에는 첫 번째 연산자가 오버로드 확인에 참여하지 않습니다. 자세한 내용은 [<type_traits>](../standard-library/type-traits.md)를 참조하세요.

## <a name="op_add"></a> operator +

[duration](../standard-library/duration-class.md) 및 [time_point](../standard-library/time-point-class.md) 개체를 추가합니다.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator+(
      const duration<Rep1, Period1>& Left,
      const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,
      const duration<Rep2, Period2>& Dur);

template <class Rep1, class Period1, class Clock, class Duration2>
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,
      const time_point<Clock, Duration2>& Time);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `duration` 또는 `time_point` 개체입니다.

*오른쪽*\
오른쪽 `duration` 또는 `time_point` 개체입니다.

*시간*\
`time_point` 개체입니다.

*기간*\
`duration` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 함수는 `duration` 간격의 합계와 동일한 시간 간격을 가진 개체를 *Left* 하 고 *Right*합니다.

두 번째 및 세 번째 함수는 반환을 `time_point` 시간 간격에 의해 치환 되는 시점을 나타내는 개체 *Dur*, 특정 시점에서 *Time*합니다.

## <a name="op_lt"></a> 연산자&lt;

하나의 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체가 다른 `duration` 또는 `time_point` 개체보다 작은지 여부를 확인합니다.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `duration` 또는 `time_point` 개체입니다.

*오른쪽*\
오른쪽 `duration` 또는 `time_point` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 함수 **true** 하는 경우의 간격 길이가 *Left* 간격 길이 보다 작으면 *Right*합니다. 반환이 고, 그렇지 **false**합니다.

두 번째 함수는 반환 **true** 하는 경우 *Left* 앞에 오는 *Right*합니다. 반환이 고, 그렇지 **false**합니다.

## <a name="op_lt_eq"></a> 연산자&lt;=

하나의 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체가 다른 `duration` 또는 `time_point` 개체보다 작거나 같은지 여부를 확인합니다.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `duration` 또는 `time_point` 개체입니다.

*오른쪽*\
오른쪽 `duration` 또는 `time_point` 개체입니다.

### <a name="return-value"></a>반환 값

각 함수는 `!(Right < Left)`를 반환합니다.

## <a name="op_eq_eq"></a> 연산자 = =

두 `duration` 개체가 길이가 동일한 시간 간격을 나타내는지 여부 또는 두 `time_point` 개체가 동일한 시점을 나타내는지 여부를 확인합니다.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `duration` 또는 `time_point` 개체입니다.

*오른쪽*\
오른쪽 `duration` 또는 `time_point` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 함수 **true** 하는 경우 *Left* 하 고 *Right* 길이가 같은 시간 간격을 나타냅니다. 반환이 고, 그렇지 **false**합니다.

두 번째 함수는 반환 **true** 경우 *Left* 하 고 *Right* 동일한 시각을 나타내는지 합니다. 반환이 고, 그렇지 **false**합니다.

## <a name="op_gt"></a> 연산자&gt;

하나의 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체가 다른 `duration` 또는 `time_point` 개체보다 큰지 여부를 확인합니다.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `duration` 또는 `time_point` 개체입니다.

*오른쪽*\
오른쪽 `duration` 또는 `time_point` 개체입니다.

### <a name="return-value"></a>반환 값

각 함수는 `Right < Left`를 반환합니다.

## <a name="op_gt_eq"></a> 연산자&gt;=

하나의 [duration](../standard-library/duration-class.md) 또는 [time_point](../standard-library/time-point-class.md) 개체가 다른 `duration` 또는 `time_point` 개체보다 크거나 같은지 여부를 확인합니다.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
왼쪽 `duration` 또는 `time_point` 개체입니다.

*오른쪽*\
오른쪽 `duration` 또는 `time_point` 개체입니다.

### <a name="return-value"></a>반환 값

각 함수는 `!(Left < Right)`를 반환합니다.

## <a name="op_modulo"></a> modulo 연산자

[duration](../standard-library/duration-class.md) 개체에 대한 모듈로 연산용 연산자입니다.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<Rep1, Period1, Rep2>::type
   operator%(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>매개 변수

*기간*\
`duration` 개체입니다.

*div*\
정수 값입니다.

*왼쪽*\
왼쪽 `duration` 개체입니다.

*오른쪽*\
오른쪽 `duration` 개체입니다.

### <a name="return-value"></a>반환 값

첫 번째 함수는 `duration` 개체는 간격 길이가 *Dur* 모듈로 *Div*합니다.

두 번째 함수를 나타내는 값을 반환 *Left* 모듈로 *Right*합니다.
