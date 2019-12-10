---
title: 컴파일러 오류 C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: a64457c84a48c73ad6714da01e48d41f3cc92efb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748725"
---
# <a name="compiler-error-c2886"></a>컴파일러 오류 C2886

' class:: identifier ':-선언을 사용 하 여 기호를 멤버에 사용할 수 없습니다.

`using` 선언에서는 네임 스페이스 이름과 같은 기호를 사용 합니다. `using` 선언은 기본 클래스 멤버를 선언 하는 데 사용할 수 있습니다.

다음 샘플에서는 C2886를 생성 합니다.

```cpp
// C2886.cpp
// compile with: /c
namespace Z {
    int i;
}

class B {
protected:
    int i;
};

class D : public B {
    // Error: Z is a namespace
    using Z::i;   // C2886

    // OK: B is a base class
    using B::i;
};
```
