---
title: 컴파일러 오류 C2051
ms.date: 11/04/2016
f1_keywords:
- C2051
helpviewer_keywords:
- C2051
ms.assetid: 81c0469a-78e2-49fa-bd76-97cdb135e3ea
ms.openlocfilehash: 51bf9b9bcde7f02210dd0e381f1239507ac56bdb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739105"
---
# <a name="compiler-error-c2051"></a>컴파일러 오류 C2051

case 식이 상수가 아닙니다.

Case 식은 정수 상수 여야 합니다.

다음 샘플에서는 C2051를 생성 합니다.

```cpp
// C2051.cpp
class X {};

int main() {
   static X x;
   int i = 0;

   switch (i) {
      case x:   // C2051 use constant expression to resolve error
         break;
      default:
         break;
   }
}
```

가능한 해결 방법:

```cpp
// C2051b.cpp
class X {};

int main() {
   static X x;
   int i = 0;

   switch (i) {
      case 1:
         break;
      default:
         break;
   }
}
```
