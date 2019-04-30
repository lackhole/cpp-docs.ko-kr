---
title: '&lt;complex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <complex>
- std::<complex>
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
ms.openlocfilehash: afcdb1246d9c02f83dbc8708326d10e802ad2779
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212094"
---
# <a name="ltcomplexgt"></a>&lt;complex&gt;

컨테이너 템플릿 클래스를 정의 `complex` 템플릿과 해당 지원 합니다.

## <a name="syntax"></a>구문

```cpp
#include <complex>
```

## <a name="remarks"></a>설명

복소수는 실수의 순서가 지정된 쌍입니다. 순수하게 기하학적 측면에서 복합 평면은 실제 2차원 평면입니다. 실제 평면과 구분되는 복합 평면의 특성은 추가 대수 구조가 있기 때문입니다. 이 대수 구조에는 두 가지 기본 작업이 있습니다.

- 로 정의 되는 더하기 (*는*를 *b*) + (*c*를 *d*) = (*를* + *c* 하십시오 *b* + *d*)

- 로 정의 되는 곱하기 (*는*, *b*) \* (*c*하십시오 *d*) = (*ac*  -  *bd*하십시오 *ad* + *bc*)

복합 더하기 및 복합 곱하기 연산이 있는 복소수 집합은 표준 대수 측면에서 필드입니다.

- 더하기 및 곱하기 연산은 누적 및 연결되고, 실수 필드의 실제 더하기 및 곱하기와 마찬가지로 곱하기가 더하기에 배포됩니다.

- 복소수 (0, 0)는 덧셈 id 및 (1, 0)은 곱셈 id입니다.

- 복소수의 덧셈 역 (*는*를 *b*)는 (-*는*,-*b*), 및는 이러한 모든 복소수의 곱셈 역 수는 제외 하 고 (0, 0)은

   (*a*/(*a*<sup>2</sup> + *b*<sup>2</sup>), -*b*/(*a*<sup>2</sup> + *b*<sup>2</sup>))

복소수를 나타내는 방법으로 *z* = (*는*를 *b*) 형태로 *z* = *를*  +  *bi*, 여기서 *합니까*<sup>2</sup> =-1, 규칙에 실수 집합의 대 수는 복소수 집합 및 해당 구성 요소에 적용할 수 있습니다. 예를 들어:

   (1 + 2*i*) \* (2 + 3*i*) = 1 \* (2 + 3*i*) + 2*i* \* (2 + 3*i*) = (2 + 3*i*) + (4*i* + 6*i*<sup>2</sup>) = (2 - 6) + (3 + 4)*i* = -4 + 7*i*

복소수 시스템은 필드이지만 순서가 지정된 필드가 아닙니다. 순서가 없다는 복소수의 실수는 복소수를 같지를 적용할 수 없습니다 있도록 실수 및 해당 하위 집합의 필드에 대 한 없기 때문에 있습니다.

복소수 *z*를 나타내는 일반적인 형태로는 다음과 같이 세 가지가 있습니다.

- 데카르트: *z* = *는* + *bi*

- 극좌표 형: *z* = *r* (cos *p* + *하나요* sin *p*)

- 지 수: *z* = *r* \* *e*<sup>*ip*</sup>

복소수의 이러한 표준 표현에 사용되는 용어는 다음과 같이 참조됩니다.

- 직각좌표 실수 성분 또는 실수부 *a*

- 직각좌표 허수 성분 또는 허수부 *b*

- 복소수의 절대값 또는 모듈러스 *r*합니다.

- 인수 또는 위상 각 *p* 라디안에서입니다.

여러 값을 반환할 수 있는 함수는-π 보다 크고 해당 인수에 대 한 보안 주체 값을 반환 하는 데 필요한 지정 되지 않는 보다 크거나 + π 또는 단일 값으로 유지 하 합니다. 모든 각도 라디안으로 나타내야 원 안에 2 π 라디안 (360도) 경우가 있습니다.

### <a name="functions"></a>함수

|기능|설명|
|-|-|
|[abs](../standard-library/complex-functions.md#abs)|복소수의 모듈러스를 계산합니다.|
|[arg](../standard-library/complex-functions.md#arg)|복소수에서 인수를 추출합니다.|
|[conj](../standard-library/complex-functions.md#conj)|복소수의 켤레 복소수를 반환합니다.|
|[cos](../standard-library/complex-functions.md#cos)|복소수의 코사인을 반환합니다.|
|[cosh](../standard-library/complex-functions.md#cosh)|복소수의 쌍곡 코사인을 반환합니다.|
|[exp](../standard-library/complex-functions.md#exp)|복소수의 지수 함수를 반환합니다.|
|[imag](../standard-library/complex-functions.md#imag)|복소수의 허수 구성 요소를 추출합니다.|
|[log](../standard-library/complex-functions.md#log)|복소수의 자연 로그를 반환합니다.|
|[log10](../standard-library/complex-functions.md#log10)|복소수의 상용 로그를 반환합니다.|
|[norm](../standard-library/complex-functions.md#norm)|복소수 기준을 추출합니다.|
|[polar](../standard-library/complex-functions.md#polar)|지정한 모듈러스 및 인수에 해당하는 복소수를 데카르트 형태로 반환합니다.|
|[pow](../standard-library/complex-functions.md#pow)|복소수인 밑수를 다른 복소수로 거듭제곱하여 얻은 복소수를 계산합니다.|
|[real](../standard-library/complex-functions.md#real)|복소수의 실수 구성 요소를 추출합니다.|
|[sin](../standard-library/complex-functions.md#sin)|복소수의 사인을 반환합니다.|
|[sinh](../standard-library/complex-functions.md#sinh)|복소수의 쌍곡 사인을 반환합니다.|
|[sqrt](../standard-library/complex-functions.md#sqrt)|복소수의 제곱근을 반환합니다.|
|[tan](../standard-library/complex-functions.md#tan)|복소수의 탄젠트를 반환합니다.|
|[tanh](../standard-library/complex-functions.md#tanh)|복소수의 쌍곡 탄젠트를 반환합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator!=](../standard-library/complex-operators.md#op_neq)|하나 또는 둘 모두 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 같지 않은지 테스트합니다.|
|[operator*](../standard-library/complex-operators.md#op_star)|하나 또는 둘 다 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 곱합니다.|
|[operator+](../standard-library/complex-operators.md#op_add)|하나 또는 둘 다 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 더합니다.|
|[operator-](../standard-library/complex-operators.md#operator-)|하나 또는 둘 다 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 뺍니다.|
|[operator/](../standard-library/complex-operators.md#op_div)|하나 또는 둘 다 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 나눕니다.|
|[operator<\<](../standard-library/complex-operators.md#op_lt_lt)|출력 스트림에 복소수를 삽입하는 템플릿 함수입니다.|
|[연산자==](../standard-library/complex-operators.md#op_eq_eq)|하나 또는 둘 모두 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 같은지 테스트합니다.|
|[operator>>](../standard-library/complex-operators.md#op_gt_gt)|입력 스트림에서 복소수를 추출하는 템플릿 함수입니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[complex\<double>](../standard-library/complex-double.md)|형식의 두 개체의 정렬된 된 쌍을 저장 하는 개체를 설명 하는 명시적으로 특수화 된 템플릿 클래스 **이중**, 여기서 첫 번째 복소수의 실수 부분을 나타내고 두 번째 허수부를 나타냅니다.|
|[complex\<float>](../standard-library/complex-float.md)|형식의 두 개체의 정렬된 된 쌍을 저장 하는 개체를 설명 하는 명시적으로 특수화 된 템플릿 클래스 **float**, 여기서 첫 번째 복소수의 실수 부분을 나타내고 두 번째 허수부를 나타냅니다.|
|[complex\<long double>](../standard-library/complex-long-double.md)|형식의 두 개체의 정렬된 된 쌍을 저장 하는 개체를 설명 하는 명시적으로 특수화 된 템플릿 클래스 **long double**, 여기서 첫 번째 복소수의 실수 부분을 나타내고 두 번째 허수부를 나타냅니다.|
|[complex](../standard-library/complex-class.md)|이 템플릿 클래스는 복소수 체계를 나타내고 복잡한 산술 연산을 수행하는 데 사용되는 개체를 설명합니다.|

### <a name="literals"></a>리터럴

\<complex> 헤더는 실수부가 0이고 허수부가 입력 매개 변수의 값이 되는 복소수를 만드는 다음의 [사용자 정의 리터럴](../cpp/user-defined-literals-cpp.md)을 정의합니다.

|||
|-|-|
|`constexpr complex<long double> operator""il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|이 반환 됩니다. `complex<long double>{0.0L, static_cast<long double>(d)}`|
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|`complex<double>{0.0, static_cast<double>(d)}`를 반환합니다.|
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|`complex<float>{0.0f, static_cast<float>(d)}`를 반환합니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
