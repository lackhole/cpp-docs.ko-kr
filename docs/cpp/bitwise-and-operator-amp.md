---
title: '비트 AND 연산자: &amp;'
ms.date: 11/04/2016
f1_keywords:
- bitand
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
ms.openlocfilehash: b7d0d73802a5af7ab71e980d73eaff5c5b3c4bb8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387710"
---
# <a name="bitwise-and-operator-amp"></a>비트 AND 연산자: &amp;

## <a name="syntax"></a>구문

```
expression & expression
```

## <a name="remarks"></a>설명

식은 다른 and 식이거나 아래에서 설명한 형식 제한에 따라 같음 식, 관계식, 더하기 식, 곱하기 식, 멤버 포인터 식, 캐스트 식, 단항 식, 후위 식 또는 기본 식일 수 있습니다.

비트 AND 연산자 (**&**) 두 번째 피연산자의 해당 비트의 첫 번째 피연산자의 각 비트와 비교 합니다. 양쪽 비트가 모두 1이면 해당 결과 비트는 1로 설정됩니다. 그렇지 않으면 해당 결과 비트는 0으로 설정됩니다.

비트 AND 연산자에 대한 두 피연산자는 모두 정수 계열 형식이어야 합니다. 다루는 일반적인 산술 변환은 [표준 변환](standard-conversions.md), 피연산자에 적용 됩니다.

## <a name="operator-keyword-for-"></a>에 대 한 연산자 키워드 &

합니다 **bitand** 연산자는 해당 하는 텍스트 **&** 합니다. 두 가지 방법으로 액세스 하는 **bitand** 프로그램에서 연산자: 헤더 파일을 포함 `iso646.h`,으로 컴파일하는 [/Za](../build/reference/za-ze-disable-language-extensions.md) (언어 확장명 사용 안 함) 컴파일러 옵션.

## <a name="example"></a>예제

```cpp
// expre_Bitwise_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise AND
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0xFFFF;      // pattern 1111 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...
}
```

## <a name="see-also"></a>참고 항목

[C++ 기본 제공 연산자, 우선 순위 및 결합성](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 비트 연산자](../c-language/c-bitwise-operators.md)