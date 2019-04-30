---
title: 컴파일러 오류 C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 44f7988f9fedb882972b2823f2fe70d9512d4e87
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408682"
---
# <a name="compiler-error-c2801"></a>컴파일러 오류 C2801

'operator o p 비정적 멤버 여야 합니다.

비정적 멤버로 다음과 같은 연산자를 오버 로드할 수 있습니다.

- 할당 `=`

- 클래스 멤버 액세스 `->`

- 첨자 `[]`

- 함수 호출 `()`

가능한 C2801 원인:

- 오버 로드 된 연산자는 클래스, 구조체 또는 공용 구조체 멤버 아닙니다.

- 오버 로드 된 연산자를 선언 했습니다 `static`합니다.

- 다음 샘플에서는 C2801를 생성합니다.

```
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```