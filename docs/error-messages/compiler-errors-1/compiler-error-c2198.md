---
title: 컴파일러 오류 C2198
ms.date: 11/04/2016
f1_keywords:
- C2198
helpviewer_keywords:
- C2198
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
ms.openlocfilehash: a7fbc5dc6dc91dab5bfea3a81c8d5c045e485161
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182823"
---
# <a name="compiler-error-c2198"></a>컴파일러 오류 C2198

'function': 호출에 매개 변수가 너무 적습니다.

컴파일러가 함수 호출 매개 변수를 너무 적게 발견했거나 잘못된 함수 선언을 발견했습니다.

다음 샘플에서는 C2198 오류가 발생하는 경우를 보여 줍니다.

```
// C2198.c
// compile with: /c
void func( int, int );
int main() {
   func( 1 );   // C2198 only one actual parameter
   func( 1, 1 );   // OK
}
```