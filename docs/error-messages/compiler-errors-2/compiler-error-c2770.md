---
title: 컴파일러 오류 C2770
ms.date: 11/04/2016
f1_keywords:
- C2770
helpviewer_keywords:
- C2770
ms.assetid: 100001b5-80b0-4971-8ff6-9023f443c926
ms.openlocfilehash: 9397b52838f61449f0475a31d5bb4077dad7f587
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257403"
---
# <a name="compiler-error-c2770"></a>컴파일러 오류 C2770

'template'에 대 한 잘못 된 명시적 template_or_generic 인수

명시적 템플릿 또는 제네릭 인수를 사용 하 여 함수 템플릿 후보 허용 되지 않는 함수 형식에 발생 합니다.

다음 샘플에서는 C2770 오류가 생성 됩니다.

```
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