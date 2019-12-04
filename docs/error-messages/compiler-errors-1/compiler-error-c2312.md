---
title: 컴파일러 오류 C2312
ms.date: 11/04/2016
f1_keywords:
- C2312
helpviewer_keywords:
- C2312
ms.assetid: c8bcfd06-12c1-4323-bb53-ba392d36daa4
ms.openlocfilehash: 0a0fbefcb1122e5c3395580a2508420b1ccea17c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748140"
---
# <a name="compiler-error-c2312"></a>컴파일러 오류 C2312

'exception1': 줄 번호에서 'exception2'에 의해 catch되었습니다.

두 개의 처리기가 동일한 예외 형식을 catch합니다.

다음 샘플에서는 C2312를 생성합니다.

```cpp
// C2312.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
    try {
        throw "ooops!";
    }
    catch( signed int ) {}
    catch( int ) {}   // C2312
}
```
