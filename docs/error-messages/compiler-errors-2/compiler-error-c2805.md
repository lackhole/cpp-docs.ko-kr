---
title: 컴파일러 오류 C2805
ms.date: 11/04/2016
f1_keywords:
- C2805
helpviewer_keywords:
- C2805
ms.assetid: c997dc56-e199-442f-b94e-ac551ec9b015
ms.openlocfilehash: 500660d70616a530fce3d8674f0f116ce219d1d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760636"
---
# <a name="compiler-error-c2805"></a>컴파일러 오류 C2805

이항 ' operator operator '에 매개 변수가 너무 적습니다.

이항 연산자에는 매개 변수가 없습니다.

다음 샘플에서는 C2805를 생성 합니다.

```cpp
// C2805.cpp
// compile with: /c
class X {
public:
   X operator< ( void );   // C2805 must take one parameter
   X operator< ( X );   // OK
};
```
