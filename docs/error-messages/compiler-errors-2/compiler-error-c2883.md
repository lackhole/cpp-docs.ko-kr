---
title: 컴파일러 오류 C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: cb6b1043d976cfeb8cb92c8780c5b84ea9700b8b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760956"
---
# <a name="compiler-error-c2883"></a>컴파일러 오류 C2883

' name ': 함수 선언이 using 선언에 의해 도입 된 ' identifier '와 충돌 합니다.

함수를 두 번 이상 정의 하려고 했습니다. 첫 번째 정의는 `using` 선언을 사용 하 여 네임 스페이스에서 만들어졌습니다. 두 번째는 로컬 정의입니다.

다음 샘플에서는 C2883를 생성 합니다.

```cpp
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
