---
title: 컴파일러 오류 C2574
ms.date: 11/04/2016
f1_keywords:
- C2574
helpviewer_keywords:
- C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
ms.openlocfilehash: 764ff36441c563edd538c41be5c23c12f80e2537
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300810"
---
# <a name="compiler-error-c2574"></a>컴파일러 오류 C2574

'소멸자': 정적으로 선언할 수 없습니다.

생성자 나 소멸자를 선언할 수 있습니다 `static`합니다.

다음 샘플에서는 C2574를 생성합니다.

```
// C2574.cpp
// compile with: /c
class A {
   virtual static ~A();   // C2574
   //  try the following line instead
   // virtual ~A();
};
```