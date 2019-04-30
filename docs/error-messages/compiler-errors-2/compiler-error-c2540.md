---
title: 컴파일러 오류 C2540
ms.date: 11/04/2016
f1_keywords:
- C2540
helpviewer_keywords:
- C2540
ms.assetid: 92c805a3-2dd9-46ca-a63d-3845c18ecc95
ms.openlocfilehash: 813733e1ed5079e7b8d1afab1b27b898b0d4a17e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347719"
---
# <a name="compiler-error-c2540"></a>컴파일러 오류 C2540

배열 범위가 상수가 아닌 식

배열에 바인딩된 상수가 있어야 합니다.

다음 샘플에서는 C2540를 생성합니다.

```
// C2540.cpp
void func(int n, int pC[]) {
   int i = ((int [n])pC)[1];   // C2540
}

void func2(int n, int pC[]) {
   int i = (pC)[1];   // OK
}

int main() {
   int pC[100];
   func(100, pC);
   func2(100, pC);
}
```