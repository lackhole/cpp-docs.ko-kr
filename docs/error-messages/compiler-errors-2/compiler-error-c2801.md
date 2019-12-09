---
title: 컴파일러 오류 C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 0d2ea3677d883fa4843c37a41d733872b23cbba0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760675"
---
# <a name="compiler-error-c2801"></a>컴파일러 오류 C2801

' operator operator '는 비정적 멤버 여야 합니다.

다음 연산자는 비정적 멤버로만 오버 로드 될 수 있습니다.

- 할당 `=`

- 클래스 멤버 액세스 `->`

- 첨자 `[]`

- 함수 호출 `()`

가능한 C2801 원인은 다음과 같습니다.

- 오버 로드 된 연산자가 클래스, 구조체 또는 공용 구조체 멤버가 아닙니다.

- 오버 로드 된 연산자는 `static`선언 됩니다.

- 다음 샘플에서는 C2801를 생성 합니다.

```cpp
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```
