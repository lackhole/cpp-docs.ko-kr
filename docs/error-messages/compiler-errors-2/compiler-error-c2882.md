---
title: 컴파일러 오류 C2882
ms.date: 11/04/2016
f1_keywords:
- C2882
helpviewer_keywords:
- C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
ms.openlocfilehash: a1c6f20ae33a545ae2e6bd7b373ecf2444e0d1d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736167"
---
# <a name="compiler-error-c2882"></a>컴파일러 오류 C2882

' name ': 식에서 네임 스페이스 식별자를 잘못 사용 했습니다.

식에서 네임 스페이스의 이름을 사용 하려고 했습니다.

다음 샘플에서는 C2882를 생성 합니다.

```cpp
// C2882.cpp
// compile with: /c
namespace A {
   int k;
}

int i = A;   // C2882, can't assign A to i
```
