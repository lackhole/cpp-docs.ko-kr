---
title: '하나의&#39;s 보수 연산자: ~'
ms.date: 11/04/2016
f1_keywords:
- "~"
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: d8fb8ca56932669ff85646f2aa0c10691122013b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245034"
---
# <a name="one39s-complement-operator-"></a>하나의&#39;s 보수 연산자: ~

## <a name="syntax"></a>구문

```
~ cast-expression
```

## <a name="remarks"></a>설명

"비트 보수" 연산자라고도 하는 1의 보수 연산자(`~`)는 해당 피연산자의 비트 1의 보수를 생성합니다. 즉, 피연산자의 1인 모든 비트는 결과적으로 0입니다. 반대로 피연산자의 0인 모든 비트는 결과적으로 1입니다. 1의 보수 연산자의 피연산자는 정수 계열 형식이어야 합니다.

## <a name="operator-keyword-for-"></a>~에 대한 연산자 키워드

합니다 **compl** 연산자는 해당 하는 텍스트 `~`합니다. 두 가지 방법으로 액세스 하는 **compl** 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하 [/Za](../build/reference/za-ze-disable-language-extensions.md)합니다.

## <a name="example"></a>예제

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

이 예제에서 `y`에 할당된 새 값은 부호 없는 값인 0xFFFF의 1의 보수이거나 0x0000입니다.

정수 계열 확장은 정수 계열 피연산자에서 수행되며, 결과 형식은 피연산자가 확장되는 형식입니다. 참조 [표준 변환](standard-conversions.md) 승격 수행 되는 방법에 대 한 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[단항 산술 연산자](../c-language/unary-arithmetic-operators.md)