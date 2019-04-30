---
title: extreme_value_distribution 클래스
ms.date: 11/04/2016
f1_keywords:
- random/std::extreme_value_distribution
- random/std::extreme_value_distribution::reset
- random/std::extreme_value_distribution::a
- random/std::extreme_value_distribution::b
- random/std::extreme_value_distribution::param
- random/std::extreme_value_distribution::min
- random/std::extreme_value_distribution::max
- random/std::extreme_value_distribution::operator()
- random/std::extreme_value_distribution::param_type
- random/std::extreme_value_distribution::param_type::a
- random/std::extreme_value_distribution::param_type::b
- random/std::extreme_value_distribution::param_type::operator==
- random/std::extreme_value_distribution::param_type::operator!=
helpviewer_keywords:
- std::extreme_value_distribution [C++]
- std::extreme_value_distribution [C++], reset
- std::extreme_value_distribution [C++], a
- std::extreme_value_distribution [C++], b
- std::extreme_value_distribution [C++], param
- std::extreme_value_distribution [C++], min
- std::extreme_value_distribution [C++], max
- std::extreme_value_distribution [C++], param_type
- std::extreme_value_distribution [C++], param_type
ms.assetid: a0cd8370-0a54-4e26-9388-8b9678fb57da
ms.openlocfilehash: 7eb75fb7b76399fd4bf1d3bea94dcec4b52230f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405146"
---
# <a name="extremevaluedistribution-class"></a>extreme_value_distribution 클래스

극단값 분포를 생성합니다.

## <a name="syntax"></a>구문

```cpp
template<class RealType = double>
class extreme_value_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructor and reset functions
   explicit extreme_value_distribution(result_type a = 0.0, result_type b = 1.0);
   explicit extreme_value_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type a() const;
   result_type b() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>매개 변수

*RealType*<br/>
부동 소수점 결과 형식으로 기본값으로 **이중**합니다. 가능한 형식은 [\<random>](../standard-library/random.md)를 참조하세요.

*URNG*<br/>
임의의 수 생성기 엔진입니다. 가능한 형식은 [\<random>](../standard-library/random.md)를 참조하세요.

## <a name="remarks"></a>설명

부동 소수점는 사용자 지정 값을 생성 하는 분포를 설명 하는 템플릿 클래스 형식 또는 형식 **이중** 극단값 분포에 따라 제공 하지 않으면 배포 합니다. 다음 테이블은 개별 멤버에 대한 문서와 연결되어 있습니다.

||||
|-|-|-|
|[extreme_value_distribution](#extreme_value_distribution)|`extreme_value_distribution::a`|`extreme_value_distribution::param`|
|`extreme_value_distribution::operator()`|`extreme_value_distribution::b`|[param_type](#param_type)|

속성 함수 `a()` 및 `b()`는 저장된 분포 매개 변수인 `a` 및 `b` 각각에 대한 값을 반환합니다.

분포 클래스 및 이러한 클래스의 멤버에 대한 자세한 내용은 [\<random>](../standard-library/random.md)을 참조하세요.

극단값 분포에 대한 자세한 내용은 Wolfram MathWorld 문서 [Extreme Value Distribution](http://go.microsoft.com/fwlink/p/?linkid=401110)(극단값 분포)을 참조하세요.

## <a name="example"></a>예제

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double a, const double b, const int s) {

    // uncomment to use a non-deterministic generator
    //    std::random_device gen;

    std::mt19937 gen(1701);

    std::extreme_value_distribution<> distr(a, b);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "a() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.a() << std::endl;
    std::cout << "b() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.b() << std::endl;

    // generate the distribution as a histogram
    std::map<double, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Distribution for " << s << " samples:" << std::endl;
    int counter = 0;
    for (const auto& elem : histogram) {
        std::cout << std::fixed << std::setw(11) << ++counter << ": "
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double a_dist = 0.0;
    double b_dist = 1;

    int samples = 10;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the \'a\' distribution parameter: ";
    std::cin >> a_dist;
    std::cout << "Enter a floating point value for the \'b\' distribution parameter (must be greater than zero): ";
    std::cin >> b_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(a_dist, b_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'a' distribution parameter: 0
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == -1.79769e+308
max() == 1.79769e+308
a() == 0.0000000000
b() == 1.0000000000
Distribution for 10 samples:
    1: -0.8813940331
    2: -0.7698972281
    3: 0.2951258007
    4: 0.3110450734
    5: 0.4210546820
    6: 0.4210688771
    7: 0.4598857960
    8: 1.3155194200
    9: 1.5379170046
    10: 2.0568757061
```

## <a name="requirements"></a>요구 사항

**헤더:** \<random>

**네임스페이스:** std

## <a name="extreme_value_distribution"></a>  extreme_value_distribution::extreme_value_distribution

분포를 생성합니다.

```cpp
explicit extreme_value_distribution(result_type a_value = 0.0, result_type b_value = 1.0);
explicit extreme_value_distribution(const param_type& parm);
```

### <a name="parameters"></a>매개 변수

*a_value*<br/>
`a` 분포 매개 변수입니다.

*b_value*<br/>
`b` 분포 매개 변수입니다.

*parm*<br/>
분포를 생성하는 데 사용되는 `param_type` 구조체입니다.

### <a name="remarks"></a>설명

**사전 조건:** `0.0 < b`

첫 번째 생성자는 저장된 `a` 값이 *a_value* 값을 보유하고 저장된 `b` 값이 *b_value* 값을 보유하고 있는 개체를 생성합니다.

두 번째 생성자는 저장된 매개 변수가 *parm*에서 초기화되는 개체를 생성합니다. `param()` 멤버 함수를 호출하여 기존 분포의 현재 매개 변수를 가져와 설정할 수 있습니다.

## <a name="param_type"></a>  extreme_value_distribution::param_type

분포의 매개 변수를 저장합니다.

```cpp
struct param_type {
   typedef extreme_value_distribution<result_type> distribution_type;
   param_type(result_type a_value = 0.0, result_type b_value = 1.0);
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>매개 변수

*a_value*<br/>
`a` 분포 매개 변수입니다.

*b_value*<br/>
`b` 분포 매개 변수입니다.

*right*<br/>
이 매개 변수와 비교할 `param_type` 개체입니다.

### <a name="remarks"></a>설명

**사전 조건:** `0.0 < b`

이 구조를 인스턴스화 시에는 분포의 클래스 생성자로, 기존 분포의 저장된 매개 변수를 설정하기 위해서는 `param()` 멤버 함수로, 저장된 매개 변수 대신 사용하기 위해서는 `operator()`로 전달할 수 있습니다.

## <a name="see-also"></a>참고자료

[\<random>](../standard-library/random.md)<br/>
