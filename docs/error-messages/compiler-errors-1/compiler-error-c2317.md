---
title: 컴파일러 오류 C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: aef89f850ff0a280255e3ec9c4c28ea422038091
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748114"
---
# <a name="compiler-error-c2317"></a>컴파일러 오류 C2317

줄 'number'에서 시작하는 'try' 블록에 catch 처리기가 없습니다.

`try` 블록에는 하나 이상의 catch 처리기가 있어야 합니다.

다음 샘플에서는 C2317을 생성합니다.

```cpp
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

가능한 해결 방법:

```cpp
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
