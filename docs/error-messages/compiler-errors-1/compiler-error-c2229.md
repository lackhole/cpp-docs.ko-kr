---
title: 컴파일러 오류 C2229
ms.date: 11/04/2016
f1_keywords:
- C2229
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
ms.openlocfilehash: 998067e9af178c1898c3443c4e84da965c22fa81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301736"
---
# <a name="compiler-error-c2229"></a>컴파일러 오류 C2229

'identifier' 형식이 잘못 되었습니다 크기가 0 인 배열

구조 또는 비트 필드의 멤버에는 마지막 멤버가 없는 크기가 0 인 배열이 포함 됩니다.

0 개 크기의 배열을 구조체의 마지막 멤버로 가질 수 있으므로 구조체를 할당할 때 크기를 지정 해야 합니다.

크기가 0 인 배열 구조체의 마지막 멤버가 없는 경우 컴파일러 나머지 필드에 대 한 오프셋을 계산할 수 없습니다.

다음 샘플에서는 C2229를 생성합니다.

```
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