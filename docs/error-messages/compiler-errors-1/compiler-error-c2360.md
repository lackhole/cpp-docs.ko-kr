---
title: 컴파일러 오류 C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: 6e956ccb021dc3bce4d107e4aa6e0bbe4356283b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364729"
---
# <a name="compiler-error-c2360"></a>컴파일러 오류 C2360

'identifier' 초기화 'case' 레이블에 의해 생략 되었습니다.

초기화 `identifier` 건너 뛸 수 있습니다는 `switch` 문입니다. 선언 된 블록으로 묶여 하지 않는 한 이니셜라이저를 사용 하는 선언이 점프할 수 없습니다. (블록 내에서 선언 하지 않으면 변수가 범위 내에서 끝날 때까지 `switch` 문.)

다음 샘플에서는 C2360 오류가 생성 됩니다.

```
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

해결 방법:

```
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