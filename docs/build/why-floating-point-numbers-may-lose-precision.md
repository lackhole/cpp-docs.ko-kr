---
title: 부동 소수점 숫자의 정밀도가 떨어지는 이유
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 373ce9fa2c2c96fac349940076873a4a637a9dbe
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298716"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>부동 소수점 숫자의 정밀도가 떨어지는 이유

부동 소수점 10 진수 값은 일반적으로 정확한 이진 표시를 포함 하지 않습니다. 이는 CPU가 부동 소수점 데이터를 나타내는 방법의 부작용입니다. 이러한 이유로 전체 자릿수가 손실 될 수 있으며 일부 부동 소수점 연산으로 인해 예기치 않은 결과가 발생할 수 있습니다.

이 동작은 다음 중 하나에 해당 하는 결과입니다.

- 10 진수의 이진 표현은 정확 하지 않을 수 있습니다.

- 사용 된 숫자 (예: float와 double 혼합)의 형식이 일치 하지 않습니다.

대부분의 프로그래머는이 동작을 해결 하기 위해 필요한 값 보다 크거나 작은 값을 확인 하거나 전체 자릿수를 유지 하는 BCD (이진 코딩 된 Decimal) 라이브러리를 가져오고 사용 합니다.

부동 소수점 값의 이진 표현은 부동 소수점 계산의 전체 자릿수 및 정확도에 영향을 줍니다. Microsoft 시각적 C++ 개체는 [IEEE 부동 소수점 형식을](ieee-floating-point-representation.md)사용 합니다.

## <a name="example"></a>예

```c
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

엡실론의 경우 float에 대해 1.192092896로 정의 된 상수 FLT_EPSILON를 사용할 수 있습니다. 2.2204460492503131 e-07F의 경우 016로 정의 된 DBL_EPSILON입니다. 이러한 상수에는 float를 포함 해야 합니다. 이러한 상수는 x + 1.0이 1.0과 같지 않은 가장 작은 양수 x로 정의 됩니다. 이 값은 매우 작으므로 매우 큰 숫자를 포함 하는 계산에 사용자 정의 허용치를 사용 해야 합니다.

## <a name="see-also"></a>참조

[코드 최적화](optimizing-your-code.md)
