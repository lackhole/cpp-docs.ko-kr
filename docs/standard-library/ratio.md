---
title: '&lt;ratio&gt;'
ms.date: 11/04/2016
f1_keywords:
- ratio/std::mega
- ratio/std::peta
- ratio/std::ratio_greater
- ratio/std::micro
- ratio/std::ratio_add
- ratio/std::ratio_not_equal
- ratio/std::hecto
- ratio/std::nano
- ratio/std::ratio_less_equal
- ratio/std::ratio_less
- ratio/std::centi
- ratio/std::ratio_greater_equal
- ratio/std::ratio_subtract
- <ratio>
- ratio/std::atto
- ratio/std::tera
- ratio/std::milli
- ratio/std::ratio_multiply
- ratio/std::kilo
- ratio/std::ratio_divide
- ratio/std::giga
- ratio/std::pico
- ratio/std::femto
- ratio/std::ratio_equal
- ratio/std::ratio
- ratio/std::exa
- ratio/std::deci
- ratio/std::deca
ms.assetid: 8543e912-2d84-45ea-b3c0-bd7bfacee405
ms.openlocfilehash: 4279aa75bf4e9b8a0c7a86f102f70164bbb620e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62369635"
---
# <a name="ltratiogt"></a>&lt;ratio&gt;

표준 헤더 \<ratio>를 포함하여 컴파일 시간에 유리수를 저장하고 조작하는 데 사용되는 상수와 템플릿을 정의합니다.

## <a name="syntax"></a>구문

```cpp
#include <ratio>
```

### <a name="ratio-template"></a>템플릿 비율

```cpp
template<std::intmax_t Numerator, std::intmax_t Denominator = 1>
struct ratio // holds the ratio of Numerator to Denominator
{
   static constexpr std::intmax_t num;
   static constexpr std::intmax_t den;
   typedef ratio<num, den> type;
}
```

템플릿을 `ratio` 정적 상수를 정의 `num` 하 고 `den` 되도록 `num`  /  `den` 분자 = = / 분모 및 `num` 및 `den` 공약수가 없도록 합니다. `num` / `den` 템플릿 클래스에 의해 표현 되는 값이입니다. 따라서 `type` 인스턴스화 지정 `ratio<num, den>`합니다.

### <a name="specializations"></a>특수화

\<ratio>는 다음 형식으로 된 `ratio` 특수화도 정의합니다.

`template <class R1, class R2> struct ratio_specialization`

각 특수화에서는 템플릿 매개 변수 두 개를 사용하는데, 이 두 매개 변수 역시 `ratio`의 특수화여야 합니다. `type`의 값은 관련 논리 연산을 통해 결정됩니다.

|이름|`type` 값|
|----------|------------------|
|`ratio_add`|`R1 + R2`|
|`ratio_divide`|`R1 / R2`|
|`ratio_equal`|`R1 == R2`|
|`ratio_greater`|`R1 > R2`|
|`ratio_greater_equal`|`R1 >= R2`|
|`ratio_less`|`R1 < R2`|
|`ratio_less_equal`|`R1 <= R2`|
|`ratio_multiply`|`R1 * R2`|
|`ratio_not_equal`|`!(R1 == R2)`|
|`ratio_subtract`|`R1 - R2`|

### <a name="typedefs"></a>형식 정의

편의 위해 헤더는 표준 SI 접두사에 대 한 비율을 정의합니다.

```cpp
typedef ratio<1, 1000000000000000000> atto;
typedef ratio<1, 1000000000000000> femto;
typedef ratio<1, 1000000000000> pico;
typedef ratio<1, 1000000000> nano;
typedef ratio<1, 1000000> micro;
typedef ratio<1, 1000> milli;
typedef ratio<1, 100> centi;
typedef ratio<1, 10> deci;
typedef ratio<10, 1> deca;
typedef ratio<100, 1> hecto;
typedef ratio<1000, 1> kilo;
typedef ratio<1000000, 1> mega;
typedef ratio<1000000000, 1> giga;
typedef ratio<1000000000000, 1> tera;
typedef ratio<1000000000000000, 1> peta;
typedef ratio<1000000000000000000, 1> exa;
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
