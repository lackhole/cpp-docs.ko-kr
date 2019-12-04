---
title: 컴파일러 오류 C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: 5c8e33e3760a29e8bff4280cdb4452c15cd32f94
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754760"
---
# <a name="compiler-error-c2624"></a>컴파일러 오류 C2624

지역 클래스는 ' extern ' 변수를 선언 하는 데 사용할 수 없습니다.

지역 클래스 또는 구조체는 `extern` 변수를 선언 하는 데 사용할 수 없습니다.

다음 샘플에서는 C2624를 생성 합니다.

```cpp
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```
