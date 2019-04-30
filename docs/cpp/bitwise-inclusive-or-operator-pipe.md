---
title: '포괄적 비트 OR 연산자: |'
ms.date: 06/14/2018
f1_keywords:
- bitor
- '|'
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 848bf3b2ec61084b59ab5b1ee6807f6066a4675e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184295"
---
# <a name="bitwise-inclusive-or-operator-"></a>포괄적 비트 OR 연산자: |

## <a name="syntax"></a>구문

> *expression1* **|** *expression2*

## <a name="remarks"></a>설명

포괄적 비트 OR 연산자 (**&#124;**)는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교합니다. 어느 한쪽 비트가 1이면 해당 결과 비트는 1로 설정됩니다. 그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.

포괄적 비트 OR 연산자에 대한 두 피연산자는 모두 정수 계열 형식이어야 합니다. 산술 변환에서 다루는 일반적인 [표준 변환](standard-conversions.md)은 피연산자에 적용됩니다.

## <a name="operator-keyword-for-124"></a>&#124;에 대한 연산자 키워드

**bitor** 연산자는 다음의 텍스트 **&#124**;에 해당하는 것입니다. 프로그램에서 **bitor** 연산자에 액세스하는 두 가지 방법이 있습니다. 헤더 파일 \<iso646.h>를 포함하거나 [/Za](../build/reference/za-ze-disable-language-extensions.md)(언어 확장 사용 안 함) 컴파일러 옵션으로 컴파일하는 것입니다.

## <a name="example"></a>예제

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>참고 항목

[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 비트 연산자](../c-language/c-bitwise-operators.md)