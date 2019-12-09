---
title: 컴파일러 오류 C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: 907e435b31a825021b03946f08f7307c5e1ed708
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761459"
---
# <a name="compiler-error-c3866"></a>컴파일러 오류 C3866

함수 호출에 인수 목록이 없습니다.

비정적 멤버 함수 내에서 소멸자 또는 종료자 호출에 인수 목록이 없습니다.

다음 샘플에서는 C3866를 생성 합니다.

```cpp
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```
