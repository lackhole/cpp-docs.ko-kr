---
title: 컴파일러 오류 C2808
ms.date: 11/04/2016
f1_keywords:
- C2808
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
ms.openlocfilehash: c5be25e8606329589e1ac3a215f30fe6ce74c594
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760597"
---
# <a name="compiler-error-c2808"></a>컴파일러 오류 C2808

단항 ' operator operator '에 정식 매개 변수가 너무 많습니다.

단항 연산자에는 비 void 매개 변수 목록이 있습니다.

다음 샘플에서는 C2808를 생성 합니다.

```cpp
// C2808.cpp
// compile with: /c
class X {
public:
   X operator! ( X );   // C2808 nonvoid parameter list
   X operator! ( void );   // OK
};
```
