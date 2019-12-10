---
title: 컴파일러 오류 C2334
ms.date: 11/04/2016
f1_keywords:
- C2334
helpviewer_keywords:
- C2334
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
ms.openlocfilehash: f8a096a89bdb076b857e5adc49ad8162551612f2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747698"
---
# <a name="compiler-error-c2334"></a>컴파일러 오류 C2334

': 또는 {' 앞에 예기치 않은 토큰이 있습니다. 명백한 함수 본문을 건너뜁니다.

다음 샘플에서는 C2334를 생성 합니다. 이 오류는 오류 C2059 후에 발생 합니다.

```cpp
// C2334.cpp
// compile with: /c
// C2059 expected
struct s1 {
   s1   {}   // C2334
   s1() {}   // OK
};
```
