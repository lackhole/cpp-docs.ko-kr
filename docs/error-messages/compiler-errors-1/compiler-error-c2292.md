---
title: 컴파일러 오류 C2292
ms.date: 11/04/2016
f1_keywords:
- C2292
helpviewer_keywords:
- C2292
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
ms.openlocfilehash: 82d381fddc4cafd364bc0e45e70e5fb5c1cb3d84
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759115"
---
# <a name="compiler-error-c2292"></a>컴파일러 오류 C2292

' identifier ': 모범 사례 상속 표현입니다. ' representation1 '가 선언 되었지만 ' representation2 '가 필요 합니다.

[/Vmb](../../build/reference/vmb-vmg-representation-method.md) 를 사용 하 여 다음 코드를 컴파일하면 ("모범 사례 항상" 표현) C2292가 발생 합니다.

```cpp
// C2292.cpp
// compile with: /vmb
class __single_inheritance X;

struct A { };
struct B { };
struct X : A, B { };  // C2292, X uses multiple inheritance
```
