---
title: 컴파일러 오류 C3241
ms.date: 11/04/2016
f1_keywords:
- C3241
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
ms.openlocfilehash: 6eab22a8627b817b7a31e4bd34aad86d1f274615
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173506"
---
# <a name="compiler-error-c3241"></a>컴파일러 오류 C3241

'method':이 메서드는 'interface' 도입 되지 않았기

함수를 명시적으로 재정의 하는 경우 함수 시그니처는 재정의 하는 함수에 대 한 선언을 정확히 일치 해야 합니다.

다음 샘플에서는 C3241 오류가 생성 됩니다.

```
// C3241.cpp
#pragma warning(disable:4199)

__interface IX12A {
   void mf();
};

__interface IX12B {
   void mf(int);
};

class CX12 : public IX12A, public IX12B { // C3241
   void IX12A::mf(int);
};
```