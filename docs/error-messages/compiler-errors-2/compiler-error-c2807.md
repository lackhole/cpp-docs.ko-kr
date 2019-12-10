---
title: 컴파일러 오류 C2807
ms.date: 11/04/2016
f1_keywords:
- C2807
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
ms.openlocfilehash: 8376f7aba0d090fa43ae675fe32cbfee182a6230
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760610"
---
# <a name="compiler-error-c2807"></a>컴파일러 오류 C2807

후 위 ' operator operator '의 두 번째 형식 매개 변수는 ' i n t ' 여야 합니다.

후 위 연산자에 대 한 두 번째 매개 변수의 형식이 잘못 되었습니다.

다음 샘플에서는 C2807를 생성 합니다.

```cpp
// C2807.cpp
// compile with: /c
class X {
public:
   X operator++ ( X );   // C2807 nonvoid parameter
   X operator++ ( int );   // OK, int parameter
};
```
