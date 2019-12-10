---
title: 컴파일러 오류 C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: 226fcd8a27c9abdb789b8191a5cf4e59cc4a66cc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759908"
---
# <a name="compiler-error-c2360"></a>컴파일러 오류 C2360

' case ' 레이블에서 ' identifier ' 초기화를 건너뛰었습니다.

`switch` 문에서는 `identifier`의 초기화를 건너뛸 수 있습니다. 선언이 블록에 포함 되지 않은 경우 이니셜라이저를 사용 하 여 선언을 건너뛸 수 없습니다. 블록 내에서 선언 되지 않은 경우 변수는 `switch` 문이 끝날 때까지 범위 내에 있습니다.

다음 샘플에서는 C2360를 생성 합니다.

```cpp
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

가능한 해결 방법:

```cpp
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```
