---
title: 부동 소수점 숫자의 정밀도가 떨어지는 이유
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 387b2f4a7156e42e59bd70c5a6f747943fb54ca7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827917"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>부동 소수점 숫자의 정밀도가 떨어지는 이유

부동 소수점 10 진수 값을 정확 하 게 이진 표현이 없는 일반적으로 합니다. 이 CPU 부동 소수점 데이터를 표시 하는 방법의 부작용으로 나타납니다. 이러한 이유로 일부 정밀도 손실 발생할 수 있습니다 및 부동 소수점 연산에 예기치 않은 결과가 발생할 수 있습니다.

이 동작은 다음 중 하나의 결과일 것입니다.

- 10 진수 숫자의 이진 표현을 정확한 아닐 수 있습니다.

- 있습니다 (예: float 및 double 혼합) 사용 되는 번호 간의 형식이 일치 하지 않습니다.

문제를 해결 하려면 대부분의 프로그래머는 값이 크면 필요 하거나 보다 적은 있는지 확인 하거나 가져오기 및 전체 자릿수를 유지 관리 Binary Coded Decimal (BCD) 라이브러리를 사용 합니다.

부동 소수점 값의 이진 표현을 전체 자릿수와 부동 소수점 계산의 정확도 영향을 줍니다. Microsoft Visual c + +를 사용 하 여 [IEEE 부동 소수점 형식](ieee-floating-point-representation.md)합니다.

## <a name="example"></a>예제

```
// Floating-point_number_precision.c
// Compile options needed: none. Value of c is printed with a decimal
// point precision of 10 and 6 (printf rounded value by default) to
// show the difference
#include <stdio.h>

#define EPSILON 0.0001   // Define your own tolerance
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))

int main() {
   float a, b, c;

   a = 1.345f;
   b = 1.123f;
   c = a + b;
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result
   if (c == 2.468)            // Comment this line for correct result
      printf_s("They are equal.\n");
   else
      printf_s("They are not equal! The value of c is %13.10f "
                "or %f",c,c);
}
```

```Output
They are not equal! The value of c is  2.4679999352 or 2.468000
```

## <a name="comments"></a>설명

EPSILON, FLT_EPSILON 1.192092896e로 float에 대 한 정의 된 상수를 사용할 수 있습니다-07F, 또는 2.2204460492503131e로 double에 대 한 정의 되어 있는 DBL_EPSILON-016 합니다. 이러한 상수에 대 한 float.h를 포함 해야 합니다. 이러한 상수 정의 된 가장 작은 양의으로 x 번호와 같이 x + 1.0과 같지 않은 1.0입니다. 아주 작은 숫자 이기 때문에 매우 큰 숫자를 포함 하는 계산에 대 한 사용자 정의 허용 오차를 사용 해야 합니다.

## <a name="see-also"></a>참고자료

[코드 최적화](optimizing-your-code.md)
