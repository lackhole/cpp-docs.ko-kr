---
title: 컴파일러 오류 C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: 637433ee22ee77a7106e3692a39eec9973d979c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350597"
---
# <a name="compiler-error-c2317"></a>컴파일러 오류 C2317

줄 'number'에서 시작하는 'try' 블록에 catch 처리기가 없습니다.

`try` 블록에는 하나 이상의 catch 처리기가 있어야 합니다.

다음 샘플에서는 C2317을 생성합니다.

```
// C2317.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   // C2317, no catch handler
}
```

해결 방법:

```
// C2317b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   catch(char*) {}
}
```