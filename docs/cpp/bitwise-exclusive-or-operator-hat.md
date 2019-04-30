---
title: '배타적 비트 OR 연산자: ^'
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
ms.openlocfilehash: 07af1b507cf256b84ac2f0f2db4061790a23555a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232016"
---
# <a name="bitwise-exclusive-or-operator-"></a>배타적 비트 OR 연산자: ^

## <a name="syntax"></a>구문

```
expression ^ expression
```

## <a name="remarks"></a>설명

배타적 비트 OR 연산자(**^**)는 첫 번째 피연산자의 각 비트를 두 번째 피연산자의 해당 비트와 비교합니다. 한 비트가 0이고 다른 비트가 1인 경우 해당 결과 비트는 1로 설정됩니다. 그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.

배타적 비트 OR 연산자에 대한 피연산자는 둘 다 정수 계열 형식이어야 합니다. 산술 변환에서 다루는 일반적인 [표준 변환](standard-conversions.md)은 피연산자에 적용됩니다.

## <a name="operator-keyword-for-"></a>^에 대한 연산자 키워드

**xor** 연산자는 **^** 에 해당하는 텍스트입니다. 프로그램에서 `iso646.h` 헤더 파일을 포함하거나 [/Za](../build/reference/za-ze-disable-language-extensions.md)(언어 확장 사용 안 함) 컴파일러 옵션으로 컴파일하는 두 가지 방법으로 **xor** 연산자에 액세스할 수 있습니다.

## <a name="example"></a>예제

```cpp
// expre_Bitwise_Exclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise exclusive OR
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xFFFF;      // pattern 1111 ...

   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...
}
```

## <a name="see-also"></a>참고 항목

[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)