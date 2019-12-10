---
title: 컴파일러 오류 C2134
ms.date: 11/04/2016
f1_keywords:
- C2134
ms.assetid: d45cb3e8-0be4-4bd6-8be9-5f8d2384363f
ms.openlocfilehash: a50a94e195c823176e8463f9d0471530b81734c4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757503"
---
# <a name="compiler-error-c2134"></a>컴파일러 오류 C2134

' function ': 호출이 상수 식을 생성 하지 않습니다.

Constexpr로 선언 된 함수는 constexpr로 선언 된 다른 함수만 호출할 수 있습니다.

다음 샘플에서는 C2134를 생성 합니다.

```cpp
// C2134.cpp
// compile with: /c
int A() {
    return 42;
};

constexpr int B() {
    return A();  // Error C2134: 'A': call does not result in a constant expression.
}
```

가능한 해결 방법:

```cpp
// C2134b.cpp
constexpr int A() {  // add constexpr to A, since it meets the requirements of constexpr.
    return 42;
};

constexpr int B() {
    return A();  // No error
}
```
