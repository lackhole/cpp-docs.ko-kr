---
title: '논리 부정 연산자: !'
ms.date: 08/27/2018
f1_keywords:
- '!'
- Not
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: 7b37e5108ca01d782c13508c0cd7a96b096cd745
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216410"
---
# <a name="logical-negation-operator-"></a>논리 부정 연산자: !

## <a name="syntax"></a>구문

```
! cast-expression
```

## <a name="remarks"></a>설명

논리 부정 연산자(**!**)는 해당 피연산자의 의미를 반대로 바꿉니다. 피연산자는 산술 형식, 포인터 형식 또는 산술/포인터 형식으로 계산되는 식이어야 합니다. 피연산자는 암시적으로 **bool** 형식으로 변환됩니다. 변환된 피연산자가 FALSE이면 결과는 TRUE이고 변환된 피연산자가 TRUE이면 결과는 FALSE입니다. 결과는 **bool** 형식입니다.

*e* 식의 경우 단항 식 `!e`는 오버로드된 연산자가 포함되는 부분을 제외하고 `(e == 0)` 식과 동일합니다.

## <a name="operator-keyword-for-"></a>!에 대한 연산자 키워드

**not** 연산자는 **!** 를 텍스트로 표현한 것입니다. 프로그램에서는 헤더 파일 \<iso646.h>를 포함하거나 [/Za](../build/reference/za-ze-disable-language-extensions.md)(언어 확장 사용 안 함) 컴파일러 옵션으로 컴파일하는 두 가지 방법으로 **not** 연산자에 액세스할 수 있습니다.

## <a name="example"></a>예제

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>참고 항목

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[단항 산술 연산자](../c-language/unary-arithmetic-operators.md)<br/>
