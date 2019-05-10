---
title: 컴파일러 경고 (수준 2) C4146
ms.date: 11/04/2016
f1_keywords:
- C4146
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
ms.openlocfilehash: 8b3090f1bc3a64752ede4dab2b1e1b5cd800057d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349791"
---
# <a name="compiler-warning-level-2-c4146"></a>컴파일러 경고 (수준 2) C4146

단항 빼기 연산자 결과 역시 unsigned 부호 없는 형식에 적용

부호 없는 형식은만 음수가 아닌 값을 사용할 수 있으므로 일반적으로 단항 마이너스 (부정) 부호 없는 형식에 적용 하는 경우를 만들지 않습니다. 피연산자와 결과 음수가 아닌 경우

실질적으로 프로그래머는-2147483648는 최소 정수 값을 나타내려고 할 때 발생 합니다. -2147483648으로 식을 두 단계에서 처리 된 것 이므로이 값을 쓸 수 없습니다.

1. 숫자 2147483648 평가 됩니다. -2147483648 유형의 최대 정수 값에서 2147483647 보다 큰 이기 때문에 아닙니다 [int](../../c-language/integer-types.md), 되지만 `unsigned int`합니다.

1. 단항 마이너스는-2147483648 되기도 하는 부호 없는 결과가 발생이 값에 적용 됩니다.

부호 없는 형식의 결과 예기치 않은 동작이 발생할 수 있습니다. 비교에서 결과 사용 하는 경우 부호 없는 비교를 사용할 수도 있습니다 예를 들어 경우 다른 피연산자는 `int`합니다. 아래 예제 프로그램 하나의 줄을 출력 하는 이유를 설명 합니다.

필요한 두 번째 줄 `1 is greater than the most negative int`, 때문에 인쇄 되지 않습니다 `((unsigned int)1) > 2147483648` 은 false입니다.

형식을 포함 하는 limits.h에서 경우 int_min이 사용 하 여 C4146를 방지할 수 있습니다 **int 서명**합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4146 오류가 생성 됩니다.

```
// C4146.cpp
// compile with: /W2
#include <stdio.h>

void check(int i)
{
    if (i > -2147483648)   // C4146
        printf_s("%d is greater than the most negative int\n", i);
}

int main()
{
    check(-100);
    check(1);
}
```