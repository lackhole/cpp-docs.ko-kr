---
title: 컴파일러 오류 C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 9976cb2425f8f855ffb2903c07de22822c781e20
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755826"
---
# <a name="compiler-error-c3628"></a>컴파일러 오류 C3628

' base class ': 관리 되는 또는 WinRTclasses는 공용 상속만 지원 합니다.

관리 되는 또는 WinRT 클래스를 [전용](../../cpp/private-cpp.md) 또는 [보호 된](../../cpp/protected-cpp.md) 기본 클래스로 사용 하려고 했습니다. 관리 되는 또는 WinRT 클래스는 [공용](../../cpp/public-cpp.md) 액세스를 사용 하는 기본 클래스로만 사용할 수 있습니다.

다음 샘플에서는 C3628을 생성하고 해결 방법을 보여 줍니다.

```cpp
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
