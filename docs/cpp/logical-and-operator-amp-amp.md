---
title: '논리 AND 연산자: &amp;&amp;'
ms.date: 11/04/2016
f1_keywords:
- '&&'
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
ms.openlocfilehash: 0843ba95467c3ae0d735476de48a8195a59788f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368658"
---
# <a name="logical-and-operator-ampamp"></a>논리 AND 연산자: &amp;&amp;

## <a name="syntax"></a>구문

```
expression && expression
```

## <a name="remarks"></a>설명

논리 AND 연산자 (**&&**) 두 피연산자가 TRUE 부울 값 TRUE를 반환 하 고 그렇지 않으면 FALSE를 반환 합니다. 피연산자 형식으로 암시적으로 변환 됩니다 **bool** 형식입니다. 평가 및 결과에 이전 **bool**합니다. 논리 AND에는 왼쪽에서 오른쪽으로의 결합성이 있습니다.

논리 AND 연산자의 피연산자는 동일한 형식일 필요는 없지만 정수 계열 또는 포인터 형식이어야 합니다. 피연산자는 일반적으로 관계형 또는 동등 식입니다.

첫째 피연산자가 완전히 계산되고 의도하지 않은 모든 결과가 논리 AND 식의 계산을 계속하기 전에 완료됩니다.

둘째 피연산자는 첫째 피연산자가 true(0이 아님)인 경우에만 계산됩니다. 이 계산으로 인해 논리 AND 식이 false일 때 둘째 피연산자의 불필요한 계산이 배제됩니다. 다음 예제와 같이 이 단락(short-circuit) 계산을 사용하여 null 포인터 역참조를 방지할 수 있습니다.

```cpp
char *pch = 0;
...
(pch) && (*pch = 'a');
```

`pch`가 null(0)인 경우 식의 오른쪽이 계산되지 않습니다. 따라서 null 포인터를 통해 할당할 수 없습니다.

## <a name="operator-keyword-for-"></a>에 대 한 연산자 키워드 & &

합니다 **하 고** 연산자는 해당 하는 텍스트 **&&** 합니다. 두 가지 방법으로 액세스 하는 **및** 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하는 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션.

## <a name="example"></a>예제

```cpp
// expre_Logical_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate logical AND
#include <iostream>

using namespace std;

int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b && b < c yields "
         << (a < b && b < c) << endl
         << "The false expression "
         << "a > b && b < c yields "
         << (a > b && b < c) << endl;
}
```

## <a name="see-also"></a>참고자료

[C++기본 제공 연산자 우선순위 및 결합성](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 논리 연산자](../c-language/c-logical-operators.md)