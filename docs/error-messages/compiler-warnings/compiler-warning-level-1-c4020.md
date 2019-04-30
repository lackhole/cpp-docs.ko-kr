---
title: 컴파일러 경고 (수준 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 75148c210ddd2a611061d58c036d12c084f442cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400051"
---
# <a name="compiler-warning-level-1-c4020"></a>컴파일러 경고 (수준 1) C4020

'function': 실제 매개 변수가 너무 많습니다.

함수 프로토타입 또는 정의의 정식 매개 변수 수를 초과 하는 함수 호출에서 실제 매개 변수 개수입니다. 컴파일러는 함수의 호출 규칙에 따라 추가 실제 매개 변수를 전달합니다.

다음 샘플에서는 C4020 오류가 생성 됩니다.

```
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

해결 방법:

```
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```