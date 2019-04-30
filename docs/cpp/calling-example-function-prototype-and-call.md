---
title: '호출 예제: 함수 프로토타입 및 호출'
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: f89f4f1917810baa585dd1661428e0809b93cca0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345104"
---
# <a name="calling-example-function-prototype-and-call"></a>호출 예제: 함수 프로토타입 및 호출

## <a name="microsoft-specific"></a>Microsoft 전용

다음 예제에서는 다양한 호출 규칙을 사용하여 함수를 호출한 결과를 보여 줍니다.

이 예제는 다음과 같은 함수 구조를 기반으로 합니다. `calltype`을 적절한 호출 규칙으로 바꾸십시오.

```
void    calltype MyFunc( char c, short s, int i, double f );
.
.
.
void    MyFunc( char c, short s, int i, double f )
    {
    .
    .
    .
    }
.
.
.
MyFunc ('x', 12, 8192, 2.7183);
```

자세한 내용은 [호출 결과 예](../cpp/results-of-calling-example.md)를 참고하세요.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[호출 규칙](../cpp/calling-conventions.md)