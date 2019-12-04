---
title: 컴파일러 오류 C2318
ms.date: 11/04/2016
f1_keywords:
- C2318
helpviewer_keywords:
- C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
ms.openlocfilehash: 0af0b0e0fbf8894e5f29482a80c05c9ed1ce141d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748088"
---
# <a name="compiler-error-c2318"></a>컴파일러 오류 C2318

이 catch 처리기와 관련된 try 블록이 없습니다.

`catch` 처리기가 정의되어 있지만 `try` 블록 앞에 오지 않습니다.

다음 샘플에서는 C2318을 생성합니다.

```cpp
// C2318.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   // no try block
   catch( int ) {}   // C2318
}
```

가능한 해결 방법:

```cpp
// C2318b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try{}
   catch( int ) {}
}
```
