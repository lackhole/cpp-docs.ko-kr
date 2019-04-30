---
title: 컴파일러 오류 C2312
ms.date: 11/04/2016
f1_keywords:
- C2312
helpviewer_keywords:
- C2312
ms.assetid: c8bcfd06-12c1-4323-bb53-ba392d36daa4
ms.openlocfilehash: 2c8d360be43c46b1a26c833dbb8aa95a7e3740e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302048"
---
# <a name="compiler-error-c2312"></a>컴파일러 오류 C2312

'exception1': 줄 번호에서 'exception2'에 의해 catch되었습니다.

두 개의 처리기가 동일한 예외 형식을 catch합니다.

다음 샘플에서는 C2312를 생성합니다.

```
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