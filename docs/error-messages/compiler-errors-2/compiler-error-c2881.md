---
title: 컴파일러 오류 C2881
ms.date: 11/04/2016
f1_keywords:
- C2881
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
ms.openlocfilehash: 9c171fd529943bb07a6c512e4ac97f64f13f959d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736284"
---
# <a name="compiler-error-c2881"></a>컴파일러 오류 C2881

' 1 ': 이미 ' orders2 '의 별칭으로 사용 되 고 있습니다.

두 네임 스페이스의 별칭으로 동일한 이름을 사용할 수 없습니다.

다음 샘플에서는 C2881를 생성 합니다.

```cpp
// C2881.cpp
// compile with: /c
namespace A {
   int k;
}

namespace B {
   int i;
}

namespace C = A;
namespace C = B;   // C2881 C is already an alias for A
```
