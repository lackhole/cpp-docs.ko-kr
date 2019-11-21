---
title: 컴파일러 경고 (수준 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 0bc95cc770914a1c02a7a40f9754415c2f013d63
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051341"
---
# <a name="compiler-warning-level-1-c4717"></a>컴파일러 경고 (수준 1) C4717

' function ': 모든 제어 경로에서 재귀적 이므로 함수는 런타임 스택 오버플로를 발생 시킵니다.

함수를 통한 모든 경로에는 함수에 대 한 호출이 포함 됩니다. 먼저 자신을 재귀적으로 호출 하지 않고 함수를 종료할 방법이 없으므로 함수는 종료 되지 않습니다.

다음 샘플에서는 C4717를 생성 합니다.

```cpp
// C4717.cpp
// compile with: /W1 /c
// C4717 expected
int func(int x) {
   if (x > 1)
      return func(x - 1); // recursive call
   else {
      int y = func(0) + 1; // recursive call
      return y;
   }
}

int main(){
   func(1);
}
```