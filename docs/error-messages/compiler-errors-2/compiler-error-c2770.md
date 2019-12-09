---
title: 컴파일러 오류 C2770
ms.date: 11/04/2016
f1_keywords:
- C2770
helpviewer_keywords:
- C2770
ms.assetid: 100001b5-80b0-4971-8ff6-9023f443c926
ms.openlocfilehash: 4f6c82823dc619982ff148a83e2cc3316b42cfab
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759778"
---
# <a name="compiler-error-c2770"></a>컴파일러 오류 C2770

' template '의 명시적 template_or_generic 인수가 잘못 되었습니다.

명시적 템플릿 또는 제네릭 인수를 사용 하는 함수 템플릿 후보로 인해 함수 형식이 허용 되지 않습니다.

다음 샘플에서는 C2770를 생성 합니다.

```cpp
// C2770.cpp
#include <stdio.h>
template <class T>
int f(typename T::B*);   // expects type with member B

struct Err {};

int main() {
   f<int>(0);   // C2770 int has no B
   // try the following line instead
   f<OK>(0);
}
```
