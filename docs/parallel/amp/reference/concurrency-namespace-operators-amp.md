---
title: Concurrency 네임 스페이스 연산자 (AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: e2957aa84ffbf420dcf2672359a442b754866649
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180416"
---
# <a name="concurrency-namespace-operators-amp"></a>Concurrency 네임 스페이스 연산자 (AMP)

||||
|-|-|-|
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[operator*](#operator_star)|
|[operator+](#operator_add)|[operator-](#operator-)|[operator/](#operator_div)|
|[연산자==](#operator_eq_eq)|

##  <a name="operator_eq_eq"></a>  operator==

지정 된 인수를 같은지 여부를 결정 합니다.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
비교할 튜플 중 하나입니다.

*_Rhs*<br/>
비교할 튜플 중 하나입니다.

### <a name="return-value"></a>반환 값

**true 이면** 경우 튜플은 같고, 그렇지 않으면 **false**합니다.

##  <a name="operator_neq"></a>  operator!=

지정 된 인수를가 같은지 여부를 결정 합니다.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
비교할 튜플 중 하나입니다.

*_Rhs*<br/>
비교할 튜플 중 하나입니다.

### <a name="return-value"></a>반환 값

**true 이면** 튜플이 아닌 경우 같고, 그렇지 않으면 **false**합니다.

##  <a name="operator_add"></a>  operator+

지정한 인수의 구성 요소별 합을 계산합니다.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
추가할 인수 중 하나입니다.

*_Rhs*<br/>
추가할 인수 중 하나입니다.

### <a name="return-value"></a>반환 값

지정한 인수의 구성 요소별 합입니다.

##  <a name="operator-"></a>  operator-

지정된 된 인수 사이의 구성 요소별 차이 계산합니다.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
뺄 인수입니다.

*_Rhs*<br/>
뺄 인수입니다.

### <a name="return-value"></a>반환 값

지정된 된 인수 사이의 구성 요소별 차이입니다.

##  <a name="operator_star"></a>  operator*

지정한 인수의 구성 요소별 곱을 계산합니다.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
곱할 튜플 중 하나입니다.

*_Rhs*<br/>
곱할 튜플 중 하나입니다.

### <a name="return-value"></a>반환 값

지정한 인수의 구성 요소별 곱입니다.

##  <a name="operator_div"></a>  operator/

지정한 인수의 구성 요소별 몫을 계산합니다.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
나누기 작업의 대상 튜플입니다.

*_Rhs*<br/>
나눌에 사용할 튜플입니다.

### <a name="return-value"></a>반환 값

지정한 인수의 구성 요소별 몫입니다.

##  <a name="operator_mod"></a>  operator%

지정 된 두 번째 인수에 의해 지정 된 첫 번째 인수의 모듈러스를 계산 합니다.

```
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
튜플 인수의 순위입니다.

*_Lhs*<br/>
튜플의 나머지를 계산 합니다.

*_Rhs*<br/>
에 사용할 튜플 모듈로.

### <a name="return-value"></a>반환 값

결과 첫 번째 지정 된 인수 모듈러스는 두 번째 지정 된 인수입니다.

## <a name="see-also"></a>참고자료

[Namespace 동시성 ](concurrency-namespace-cpp-amp.md)
