---
title: 컴파일러 오류 C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: ca03a42cbf746a1ef32d9c79c23de637f05b56fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364365"
---
# <a name="compiler-error-c2361"></a>컴파일러 오류 C2361

'identifier'의 초기화 'default' 레이블에 의해 생략 되었습니다.

초기화 `identifier` 건너 뛸 수 있습니다는 `switch` 문입니다. 선언 된 블록으로 묶여 하지 않는 한 이니셜라이저를 사용 하는 선언이 점프할 수 없습니다. (블록 내에서 선언 하지 않으면 변수가 범위 내에서 끝날 때까지 `switch` 문.)

다음 샘플에서는 C2361 오류가 생성 됩니다.

```
// C2361.cpp
void func( void ) {
   int x;
   switch (x) {
   case 0 :
      int i = 1;
      { int j = 1; }
   default :   // C2361 error
      int k = 1;
   }
}
```

해결 방법:

```
// C2361b.cpp
// compile with: /c
void func( void ) {
   int x = 0;
   switch (x) {
   case 0 :
      { int j = 1; int i = 1;}
   default :
      int k = 1;
   }
}
```