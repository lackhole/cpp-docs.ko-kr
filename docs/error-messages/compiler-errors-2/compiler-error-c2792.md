---
title: 컴파일러 오류 C2792
ms.date: 11/04/2016
f1_keywords:
- C2792
helpviewer_keywords:
- C2792
ms.assetid: 392cf748-4f5e-4e62-a364-3118d5658408
ms.openlocfilehash: 175ec7ff6b842eb5f41896c5ec3cc0a0f5db817c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739534"
---
# <a name="compiler-error-c2792"></a>컴파일러 오류 C2792

' super ':이 키워드 다음에는 ':: '이와 야 합니다.

`__super` 키워드를 따를 수 있는 유일한 토큰은 `::`입니다.

다음 샘플에서는 C2792를 생성 합니다.

```cpp
// C2792.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super.();   // C2792

      // try the following line instead
      // __super::mf();
   }
};
```
