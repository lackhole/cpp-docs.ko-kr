---
title: 컴파일러 오류 C2780
ms.date: 11/04/2016
f1_keywords:
- C2780
helpviewer_keywords:
- C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
ms.openlocfilehash: cf327852da325940b1090e4f6199ac10c83ea09b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739963"
---
# <a name="compiler-error-c2780"></a>컴파일러 오류 C2780

'declaration' : 인수가 N개 있어야 하는데 M개를 사용했습니다.

함수 템플릿에 인수가 너무 적거나 너무 많습니다.

다음 샘플에서는 C2780을 생성하고 해결 방법을 보여 줍니다.

```cpp
// C2780.cpp
template<typename T>
void f(T, T){}

int main() {
   f(1);  // C2780
   // try the following line instead
   // f(1,2);
}
```
