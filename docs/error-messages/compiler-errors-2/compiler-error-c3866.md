---
title: 컴파일러 오류 C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: 98014fec77ce47fa4c484645f401e615f1470e2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302302"
---
# <a name="compiler-error-c3866"></a>컴파일러 오류 C3866

인수 목록이 없습니다. 함수 호출

비정적 멤버 함수 내에 종료자 또는 소멸자를 호출 하며 인수 목록의 아닙니다.

다음 샘플에서는 C3866 오류가 생성 됩니다.

```
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