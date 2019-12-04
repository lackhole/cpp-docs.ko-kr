---
title: 컴파일러 오류 C2630
ms.date: 11/04/2016
f1_keywords:
- C2630
helpviewer_keywords:
- C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
ms.openlocfilehash: 5636b17573cd89c5a32e328aa3800d71136b84fc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754708"
---
# <a name="compiler-error-c2630"></a>컴파일러 오류 C2630

쉼표로 구분 된 목록 이어야 하는 항목에 ' symbol '이 있습니다.

기호가 쉼표를 필요로 하는 컨텍스트에 표시 됩니다.

다음 샘플에서는 C2630를 생성 합니다.

```cpp
// C2630.cpp
// compile with: /c
struct D {
   D(int);
};

struct E {
   E(int);
};

class C : public D, public E {
   C();
};

C::C() : D(0) ; E(0) { }   // C2630
C::C() : D(0), E(0) {}   // OK
```
