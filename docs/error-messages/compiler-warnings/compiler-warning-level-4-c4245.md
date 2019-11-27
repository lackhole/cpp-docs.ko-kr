---
title: 컴파일러 경고(수준 4) C4245
ms.date: 11/04/2016
f1_keywords:
- C4245
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
ms.openlocfilehash: 3d55226a368f81a9506b38fe9271da4332bd1f5b
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541727"
---
# <a name="compiler-warning-level-4-c4245"></a>컴파일러 경고(수준 4) C4245

' conversion ': ' type1 '에서 ' type2 ' (으)로의 변환, 부호 있는/부호 없는 불일치

음수 값을 가진 부호 있는 **const** 를 `unsigned`으로 변환 하려고 했습니다.

다음 샘플에서는 C4245를 생성 합니다.

```cpp
// C4245.cpp
// compile with: /W4 /c
const int i = -1;
unsigned int j = i; // C4245

const int k = 1;
unsigned int l = k; // okay

int m = -1;
unsigned int n = m; // okay

void Test(size_t i) {}

int main() {
   Test( -19 );   // C4245
}
```