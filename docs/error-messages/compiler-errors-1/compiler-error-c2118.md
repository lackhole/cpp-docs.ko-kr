---
title: 컴파일러 오류 C2118
ms.date: 11/04/2016
f1_keywords:
- C2118
helpviewer_keywords:
- C2118
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
ms.openlocfilehash: 944109ba3531f2e3fca50300f26000fdaf850d19
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755202"
---
# <a name="compiler-error-c2118"></a>컴파일러 오류 C2118

음수 첨자

배열 크기를 정의 하는 값이 최대 배열 크기 보다 크거나 0 보다 작습니다.

다음 샘플에서는 C2118를 생성 합니다.

```cpp
// C2118.cpp
int main() {
   int array1[-1];   // C2118
   int array2[3];   // OK
}
```
