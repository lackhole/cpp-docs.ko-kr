---
title: 컴파일러 오류 C2550
ms.date: 11/04/2016
f1_keywords:
- C2550
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
ms.openlocfilehash: 29e907e682e0caae86569fe8bd7c101b3e0b14a3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740821"
---
# <a name="compiler-error-c2550"></a>컴파일러 오류 C2550

' identifier ': 생성자 이니셜라이저 목록은 생성자 정의에만 사용할 수 있습니다.

기본 클래스 이니셜라이저 목록은 생성자가 아닌 함수의 정의에 사용 됩니다.

다음 샘플에서는 C2550를 생성 합니다.

```cpp
// C2550.cpp
// compile with: /c
class C {
public:
   C();
};

class D : public C {
public:
   D();
   void func();
};

void D::func() : C() {}  // C2550
D::D() : C() {}   // OK
```
