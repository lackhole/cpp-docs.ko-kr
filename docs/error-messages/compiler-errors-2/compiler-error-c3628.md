---
title: 컴파일러 오류 C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 581aae7e1f979b3dd39caf2ce3d263fdb856c56a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221687"
---
# <a name="compiler-error-c3628"></a>컴파일러 오류 C3628

'base class': 관리 또는 WinRTclasses 공용 상속만 지원

관리 되는 또는 WinRT 사용 하려고 했습니다 클래스는 [사설](../../cpp/private-cpp.md) 또는 [보호](../../cpp/protected-cpp.md) 기본 클래스입니다. 관리 되는 또는 WinRT 클래스는 기본 클래스로 사용할 수 있습니다 [공용](../../cpp/public-cpp.md) 액세스 합니다.

다음 샘플에서는 C3628을 생성하고 해결 방법을 보여 줍니다.

```
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
