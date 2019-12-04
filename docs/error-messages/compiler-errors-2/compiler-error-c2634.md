---
title: 컴파일러 오류 C2634
ms.date: 11/04/2016
f1_keywords:
- C2634
helpviewer_keywords:
- C2634
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
ms.openlocfilehash: ae53dc8f33920c84bed152cdd7d7bf34e01f165a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759453"
---
# <a name="compiler-error-c2634"></a>컴파일러 오류 C2634

' & class:: member ': 참조 멤버에 대 한 포인터가 잘못 되었습니다.

참조 멤버에 대 한 포인터가 선언 됩니다.

다음 샘플에서는 C2634를 생성 합니다.

```cpp
// C2634.cpp
int mem;
struct S {
   S() : rf(mem) { }
   int &rf;
};
int (S::*pdm) = &S::rf;   // C2634
```
