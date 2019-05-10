---
title: 컴파일러 경고 (수준 3) C4197
ms.date: 11/04/2016
f1_keywords:
- C4197
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
ms.openlocfilehash: 15b2fba94bfc956775a1e454893e7509a32000e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402244"
---
# <a name="compiler-warning-level-3-c4197"></a>컴파일러 경고 (수준 3) C4197

'type': 캐스트의 최상위 volatile은 무시 됩니다.

컴파일러 검색으로 정규화 되기 있는 r-value 형식으로 캐스팅할 [volatile](../../cpp/volatile-cpp.md), 또는 r-value 형식의 있는 volatile을 사용 하 여 정규화 된 형식으로 캐스트 합니다. C 표준 (6.5.3)에 따라 정규화 된 형식 관련 속성 값 (l-value)-식에만 의미가 있습니다.

다음 샘플에서는 C4197 오류가 생성 됩니다.

```
// C4197.cpp
// compile with: /W3
#include <stdio.h>
#include <signal.h>
#include <stdlib.h>

void sigproc(int);
struct S
{
   int i;
} s;

int main()
{
   signal(SIGINT, sigproc);
   s.i = 1;
   S *pS = &s;
   for ( ; (volatile int)pS->i ; )   // C4197
      break;
   // for ( ; *(volatile int *)&pS->i ; )   // OK
   //    break;
}

void sigproc(int) // ctrl-C
{
   signal(SIGINT, sigproc);
   s.i = 0;
}
```