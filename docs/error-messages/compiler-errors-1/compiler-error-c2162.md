---
title: 컴파일러 오류 C2162
ms.date: 11/04/2016
f1_keywords:
- C2162
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
ms.openlocfilehash: 4b4efd609aaa1f1c5bc50460ff653b36b12061e4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755696"
---
# <a name="compiler-error-c2162"></a>컴파일러 오류 C2162

매크로 정식 매개 변수가 필요 합니다.

문자열 화 연산자 (#) 뒤에 있는 토큰은 정식 매개 변수 이름이 아닙니다.

## <a name="example"></a>예제

다음 샘플에서는 C2162를 생성 합니다.

```cpp
// C2162.cpp
// compile with: /c
#include <stdio.h>

#define print(a) printf_s(b)   // OK
#define print(a) printf_s(#b)    // C2162
```
