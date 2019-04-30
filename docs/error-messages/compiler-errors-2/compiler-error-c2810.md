---
title: 컴파일러 오류 C2810
ms.date: 11/04/2016
f1_keywords:
- C2810
helpviewer_keywords:
- C2810
ms.assetid: f63e8f24-d7f6-42ac-904f-72ff49592ba6
ms.openlocfilehash: 171b9d1b3b09b793c55756500cafed1db7eb9d99
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62281783"
---
# <a name="compiler-error-c2810"></a>컴파일러 오류 C2810

'interface': 인터페이스는 다른 인터페이스에서 에서만 상속할 수 있습니다

[인터페이스](../../cpp/interface.md) 다른 인터페이스에서 에서만 상속할 수 있습니다 및 클래스 또는 구조체에서 상속 하지 않을 수 있습니다.

다음 샘플에서는 C2810 오류가 생성 됩니다.

```
// C2810.cpp
#include <unknwn.h>
class CBase1 {
public:
  HRESULT mf1();
  int  m_i;
};

[object, uuid="40719E20-EF37-11D1-978D-0000F805D73B"]
__interface IDerived : public CBase1 {  // C2810
// try the following line instead
// __interface IDerived {
   HRESULT mf2(void *a);
};

struct CBase2 {
   HRESULT mf1(int a, char *b);
   HRESULT mf2();
};
```