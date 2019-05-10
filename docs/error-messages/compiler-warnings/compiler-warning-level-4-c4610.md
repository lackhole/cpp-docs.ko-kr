---
title: 컴파일러 경고(수준 4) C4610
ms.date: 11/04/2016
f1_keywords:
- C4610
helpviewer_keywords:
- C4610
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
ms.openlocfilehash: ce671552083f4e6b055c52e7387d3a95e7d47c0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220582"
---
# <a name="compiler-warning-level-4-c4610"></a>컴파일러 경고(수준 4) C4610

'class' 개체를 인스턴스화할 수 없습니다-사용자 정의 생성자가 필요

가 없는 사용자 정의 클래스나 기본 생성자입니다. 없는 인스턴스화 수행 됩니다. 다음 샘플에서는 C4610 오류가 생성 됩니다.

```
// C4610.cpp
// compile with: /W4
struct A {
   int &j;

   A& A::operator=( const A& );
};   // C4610

/* use this structure definition to resolve the warning
struct B {
   int &k;

   B(int i = 0) : k(i) {
   }

   B& B::operator=( const B& );
} b;
*/

int main() {
}
```