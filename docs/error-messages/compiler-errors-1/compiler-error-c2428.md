---
title: 컴파일러 오류 C2428
ms.date: 11/04/2016
f1_keywords:
- C2428
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
ms.openlocfilehash: 9acaa3ba933f6fcf49a31e4973e7f6ddc3e178ea
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744591"
---
# <a name="compiler-error-c2428"></a>컴파일러 오류 C2428

' operation ': ' bool ' 형식의 피연산자에 사용할 수 없습니다.

`bool`형식의 개체에는 감소 연산자를 적용할 수 없습니다.

다음 샘플에서는 C2428를 생성 합니다.

```cpp
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```
