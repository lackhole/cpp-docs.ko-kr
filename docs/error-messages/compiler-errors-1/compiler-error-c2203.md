---
title: 컴파일러 오류 C2203
ms.date: 11/04/2016
f1_keywords:
- C2203
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
ms.openlocfilehash: db36afa1376a0b64b3e110acd1722d3e0f2af449
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758959"
---
# <a name="compiler-error-c2203"></a>컴파일러 오류 C2203

delete 연산자는 배열의 범위를 지정할 수 없습니다.

**/Za** (ANSI) 옵션을 사용 하는 경우 `delete` 연산자는 배열의 일부 또는 특정 멤버가 아니라 전체 배열을 삭제할 수 있습니다.

다음 샘플에서는 C2203를 생성 합니다.

```cpp
// C2203.cpp
// compile with: /Za
int main() {
   int *ar = new int[10];
   delete [4] ar;   // C2203
   // try the following line instead
   // delete [] ar;
}
```
