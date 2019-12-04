---
title: 컴파일러 오류 C3241
ms.date: 11/04/2016
f1_keywords:
- C3241
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
ms.openlocfilehash: 6a618a9c538558d2aa4b995cbc9071bb8e94a5bc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754580"
---
# <a name="compiler-error-c3241"></a>컴파일러 오류 C3241

' method ':이 메서드는 ' interface '에 의해 정의 되지 않았습니다.

함수를 명시적으로 재정의 하는 경우 함수 시그니처는 재정의 하는 함수에 대 한 선언과 정확히 일치 해야 합니다.

다음 샘플에서는 C3241를 생성 합니다.

```cpp
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
