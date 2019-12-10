---
title: 컴파일러 오류 C2703
ms.date: 11/04/2016
f1_keywords:
- C2703
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
ms.openlocfilehash: 7d1f50d7811fd7c54e1236499da36f00add97d70
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757152"
---
# <a name="compiler-error-c2703"></a>컴파일러 오류 C2703

__leave 문이 잘못 되었습니다.

`__leave` 문은 `__try` 블록 내에 있어야 합니다.

다음 샘플에서는 C2703를 생성 합니다.

```cpp
// C2703.cpp
int main() {
   __leave;   // C2703
   __try {
      // try the following line instead
      __leave;
   }
   __finally {}
}
```
