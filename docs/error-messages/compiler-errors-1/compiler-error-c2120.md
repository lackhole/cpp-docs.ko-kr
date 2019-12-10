---
title: 컴파일러 오류 C2120
ms.date: 11/04/2016
f1_keywords:
- C2120
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
ms.openlocfilehash: 6b188f4f3e898a17a5f8fbeafaa2d1c3c6e08552
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737974"
---
# <a name="compiler-error-c2120"></a>컴파일러 오류 C2120

모든 형식에 ' l o n '이 잘못 되었습니다.

`void` 형식은 다른 형식의 선언에 사용 됩니다.

다음 샘플에서는 C2120를 생성 합니다.

```cpp
// C2120.cpp
int main() {
   void int i;   // C2120
   int j;   // OK
}
```
