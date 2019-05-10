---
title: 컴파일러 오류 C2863
ms.date: 11/04/2016
f1_keywords:
- C2863
helpviewer_keywords:
- C2863
ms.assetid: 32561d67-a795-486b-b3b6-4b90a1acb176
ms.openlocfilehash: c0ee0e2932ef0ce739e14fd29ddde31f7d665f43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227472"
---
# <a name="compiler-error-c2863"></a>컴파일러 오류 C2863

'interface': 인터페이스에 friends를 사용할 수 없습니다.

인터페이스에서 friend를 선언할 수 없습니다.

다음 샘플에서는 C2863를 생성합니다.

```
// C2863.cpp
// compile with: /c
#include <unknwn.h>

class CMyClass {
   void *f();
};

__interface IMyInterface {
   void g();

   friend int h();   // 2863
   friend interface IMyInterface1;  // C2863
   friend void *CMyClass::f();  // C2863
};
```