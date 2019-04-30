---
title: 컴파일러 오류 C2849
ms.date: 11/04/2016
f1_keywords:
- C2849
helpviewer_keywords:
- C2849
ms.assetid: e28f6b3e-e0e7-4f92-b006-ebaa81d368e6
ms.openlocfilehash: 4812c836d099e9cbb3849e48046edfdeda24ffc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256908"
---
# <a name="compiler-error-c2849"></a>컴파일러 오류 C2849

'소멸자': 인터페이스는 소멸자를 사용할 수 없습니다.

시각적 개체 C++ [인터페이스](../../cpp/interface.md) 소멸자를 가질 수 없습니다.

다음 샘플에서는 C2849 오류가 생성 됩니다.

```
// C2849.cpp
// compile with: /c
__interface C {
   ~C();   // C2849 destructor not allowed in an interface
};
```