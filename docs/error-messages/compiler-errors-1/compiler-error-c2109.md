---
title: 컴파일러 오류 C2109
ms.date: 11/04/2016
f1_keywords:
- C2109
helpviewer_keywords:
- C2109
ms.assetid: 2d1ac79d-a985-4904-a38b-b270578d664d
ms.openlocfilehash: 109b4693a07374f05e8b51c73c15d04c6d9793cd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755735"
---
# <a name="compiler-error-c2109"></a>컴파일러 오류 C2109

첨자는 배열 또는 포인터 형식이 필요 합니다.

첨자가 배열이 아닌 변수에 사용 되었습니다.

다음 샘플에서는 C2109를 생성 합니다.

```cpp
// C2109.cpp
int main() {
   int a, b[10] = {0};
   a[0] = 1;   // C2109
   b[0] = 1;   // OK
}
```
