---
title: 컴파일러 오류 C2177
ms.date: 11/04/2016
f1_keywords:
- C2177
helpviewer_keywords:
- C2177
ms.assetid: 2a39a880-cddb-4d3e-a572-645a14c4c478
ms.openlocfilehash: 6b48118c854fa2ec77e93c5b7becd334bfe29849
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737246"
---
# <a name="compiler-error-c2177"></a>컴파일러 오류 C2177

상수가 너무 큽니다.

상수 값이 할당된 변수 형식에 대해 너무 큽니다.

다음 샘플에서는 C2177을 생성합니다.

```cpp
// C2177.cpp
int main() {
   int a=18446744073709551616;   // C2177
   int b=18446744073709551615;   // OK
}
```
