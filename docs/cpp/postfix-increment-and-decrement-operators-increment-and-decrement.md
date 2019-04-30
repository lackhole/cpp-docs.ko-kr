---
title: '후위 증가 및 감소 연산자: ++ 및 --'
ms.date: 11/04/2016
f1_keywords:
- --
- ++
helpviewer_keywords:
- increment operators [C++], syntax
- member-selection operators [C++]
- -- operator [C++], postfix decrement operators
- postfix operators [C++]
- ++ operator [C++], postfix increment operators
- decrement operators [C++], syntax
- operators [C++], postfix
- decrement operators [C++]
ms.assetid: 0204d5c8-51b0-4108-b8a1-074c5754d89c
ms.openlocfilehash: e1a87fe4815a75b97616d7b11a4b9aa4ae65eb9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392143"
---
# <a name="postfix-increment-and-decrement-operators--and---"></a>후위 증가 및 감소 연산자: ++ 및 --

## <a name="syntax"></a>구문

```
postfix-expression ++
postfix-expression --
```

## <a name="remarks"></a>설명

C++는 전위/후위 증가 및 감소 연산자를 제공합니다. 이 단원에서는 후위 증가 및 감소 연산자에 대해서만 설명합니다. (자세한 내용은 [전위 증가 및 감소 연산자](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md).) 둘 사이의 차이점은는 후 위 표기법에서는 연산자 뒤에 표시 됩니다 *후 위 식*전위 표기법에서는 연산자 앞에 표시 하는 반면, *식입니다.* 다음 예제에서는 후위 증가 연산자를 보여 줍니다.

```cpp
i++;
```

후 위 증가 연산자를 적용 한 결과 (**++**)는 피연산자의 값은 적절 한 형식의 단위로 한 단위씩 증가 됩니다. 마찬가지로, 후 위 감소 연산자를 적용 한 결과 (**--**)는 피연산자의 값은 적절 한 형식의 단위로 한 단위씩 감소 됩니다.

후 위 증가 한다는 점에 유의 해야 감소 식이 식의 값 또는 *이전에* 각 연산자를 적용 합니다. 증가 또는 감소 연산은 발생 *후* 피연산자 평가 됩니다. 이 문제는 후위 증가나 감소 연산이 더 큰 수식의 컨텍스트에서 진행할 경우에만 발생합니다.

후위 연산자가 함수 인수에 적용될 때 해당 인수의 값은 함수에 전달된 후에만 증가하거나 감소됩니다.  자세한 내용은 C++ 표준의 1.9.17 단원을 참조하십시오.

형식 개체의 배열에 대 한 포인터를 후 위 증가 연산자를 적용 **긴** 포인터의 내부 표현에 4가 실제로 추가 합니다. 이 동작은 이전에 포인터를 *n*번째 요소를 가리키는 데 배열의 합니다 (*n*+ 1) 번째 요소입니다.

후 위 증가 및 감소 연산자의 피연산자는 수정할 수 있어야 합니다. (되지 **const**) 산술 또는 포인터 형식의 l-value입니다. 결과의 형식은의 것과 동일 합니다 *후 위 식*, 있지만 l-value는 더 이상.

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)): 피연산자는 후 위 증가 또는 감소 연산자는 형식의 되지 않을 수 있습니다 **bool**합니다.

다음 코드에서는 후위 증가 연산자에 대해 설명합니다.

```cpp
// expre_Postfix_Increment_and_Decrement_Operators.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
   int i = 10;
   cout << i++ << endl;
   cout << i << endl;
}
```

후위 증가 및 감소 연산은 열거형 형식에서 지원되지 않습니다.

```cpp
enum Compass { North, South, East, West );
Compass myCompass;
for( myCompass = North; myCompass != West; myCompass++ ) // Error
```

## <a name="see-also"></a>참고자료

[후위 식](../cpp/postfix-expressions.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 후위 증가 및 감소 연산자](../c-language/c-postfix-increment-and-decrement-operators.md)