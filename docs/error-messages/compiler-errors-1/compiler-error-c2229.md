---
title: 컴파일러 오류 C2229
ms.date: 11/04/2016
f1_keywords:
- C2229
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
ms.openlocfilehash: 2d974c4f0630a592daad956448bf21cea21efb7c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759271"
---
# <a name="compiler-error-c2229"></a>컴파일러 오류 C2229

' identifier ' 형식에 잘못 된 크기가 0 인 배열이 있습니다.

구조체 또는 비트 필드의 멤버에 마지막 멤버가 아닌 크기가 0 인 배열이 포함 되어 있습니다.

구조체의 마지막 멤버로 크기가 0 인 배열을 사용할 수 있으므로 구조체를 할당할 때 크기를 지정 해야 합니다.

크기가 0 인 배열이 구조체의 마지막 멤버가 아닌 경우 컴파일러는 나머지 필드의 오프셋을 계산할 수 없습니다.

다음 샘플에서는 C2229를 생성 합니다.

```cpp
// C2229.cpp
struct S {
   int a[0];  // C2229  zero-sized array
   int b[1];
};

struct S2 {
   int a;
   int b[0];
};

int main() {
   // allocate 7 elements for b field
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];
   s2->b[6] = 100;
}
```
