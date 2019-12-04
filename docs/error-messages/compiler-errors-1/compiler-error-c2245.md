---
title: 컴파일러 오류 C2245
ms.date: 11/04/2016
f1_keywords:
- C2245
helpviewer_keywords:
- C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
ms.openlocfilehash: bc3f8e17d8d3746bdc243193f1349939bca5e164
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759206"
---
# <a name="compiler-error-c2245"></a>컴파일러 오류 C2245

존재하지 않는 멤버 함수 'function'을 Friend로 지정했습니다. 멤버 함수 서명이 오버로드와 일치하지 않습니다.

컴파일러에서 Friend로 지정된 함수를 찾을 수 없습니다.

다음 샘플에서는 C2245를 생성합니다.

```cpp
// C2245.cpp
// compile with: /c
class B {
   void f(int i);
};

class A {
   int m_i;
   friend void B::f(char);   // C2245
   // try the following line instead
   // friend void B::f(int);
};

void B::f(int i) {
   A a;
   a.m_i = 0;
}
```
