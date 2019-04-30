---
title: 컴파일러 오류 C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 13840246a5dc6a1c1bdbcb55dc47f212ee353d81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165218"
---
# <a name="compiler-error-c2513"></a>컴파일러 오류 C2513

'type' : no variable declared before '='

형식 지정 자가 변수 식별자 없이 선언에 나타납니다.

다음 샘플에서는 C2513를 생성합니다.

```
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

이 오류는 Visual Studio.NET 2003 컴파일러 규칙 작업의 결과로 생성 될 수 없습니다: 더 이상 사용할 수 없습니다. 형식 정의를 초기화 합니다. Typedef의 초기화를 표준에서 허용 되지 않습니다 하 고 이제 컴파일러 오류를 생성 합니다.

```
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

대신 삭제 하는 것 `typedef` 집합체 이니셜라이저 목록에 있지만이 사용 하 여 변수를 정의할 수 있으므로 권장 되지 않습니다 형식으로 동일한 이름을 가진 변수를 만들 하 고 형식 이름을 숨깁니다.