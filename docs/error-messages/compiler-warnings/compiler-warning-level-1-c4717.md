---
title: 컴파일러 경고(수준 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 0cf9aef8f68ca5972fd3d7886cd8061b88d043ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221143"
---
# <a name="compiler-warning-level-1-c4717"></a>컴파일러 경고(수준 1) C4717

'function': 모든 제어 경로에서 재귀적 함수로 인해 런타임 스택 오버플로

함수를 통해 모든 경로 함수에 대 한 호출을 포함합니다. 자체는 먼저 호출 하지 않고 함수를 재귀적으로 종료 하는 방법이 이므로 함수 종료 되지 않습니다.

다음 샘플에서는 C4717 오류가 생성 됩니다.

```
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