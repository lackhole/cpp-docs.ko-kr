---
title: 컴파일러 오류 C2849
ms.date: 11/04/2016
f1_keywords:
- C2849
helpviewer_keywords:
- C2849
ms.assetid: e28f6b3e-e0e7-4f92-b006-ebaa81d368e6
ms.openlocfilehash: 8a67c81fd58312921ef01209d7bc2f96eecaed4b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738884"
---
# <a name="compiler-error-c2849"></a>컴파일러 오류 C2849

' 소멸자 ': 인터페이스에는 소멸자를 사용할 수 없습니다.

시각적 C++ [인터페이스](../../cpp/interface.md) 에는 소멸자를 사용할 수 없습니다.

다음 샘플에서는 C2849를 생성 합니다.

```cpp
// C2849.cpp
// compile with: /c
__interface C {
   ~C();   // C2849 destructor not allowed in an interface
};
```
