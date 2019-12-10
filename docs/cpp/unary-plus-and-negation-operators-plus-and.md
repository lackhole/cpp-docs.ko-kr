---
title: '단항 더하기 및 부정 연산자: + 및 -'
ms.date: 11/04/2016
f1_keywords:
- +
- '-'
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
ms.openlocfilehash: 83fedd9d3cc6cd7c08ba79d2ed83e9f62d919e29
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857244"
---
# <a name="unary-plus-and-negation-operators--and--"></a>단항 더하기 및 부정 연산자: + 및 -

## <a name="syntax"></a>구문

```
+ cast-expression
- cast-expression
```

## <a name="-operator"></a>+ 연산자

단항 더하기 연산자( **+** )의 결과는 피연산자의 값입니다. 단항 더하기 연산자의 피연산자는 산술 형식이어야 합니다.

정수 계열 확장은 정수 계열 피연산자를 대상으로 수행됩니다. 결과 형식은 피연산자가 승격될 형식입니다. 따라서, `+ch`가 `ch` 형식인 **char** 식은 **int** 형식이 되며 그 값은 변경되지 않습니다. 확장 수행 방법에 대한 자세한 내용은 [표준 전환](standard-conversions.md)을 참조하십시오.

## <a name="--operator"></a>- 연산자

단항 부정 연산자( **-** )는 해당 피연산자의 부정을 생성합니다. 단항 부정 연산자의 피연산자는 산술 형식이어야 합니다.

정수 계열 확장은 정수 계열 피연산자에서 수행되며, 결과 형식은 피연산자가 확장되는 형식입니다. 확장 수행 방법에 대한 자세한 내용은 [표준 전환](standard-conversions.md)을 참조하십시오.

**Microsoft 전용**

부호 없는 수량의 단항 부정은 2^n에서 피연산자의 값을 빼서 수행됩니다. 여기서 n은 지정된 부호 없는 형식의 개체에 있는 비트 수입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)