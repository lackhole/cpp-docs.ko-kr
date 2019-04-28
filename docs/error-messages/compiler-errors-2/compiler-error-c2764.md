---
title: 컴파일러 오류 C2764
ms.date: 11/04/2016
f1_keywords:
- C2764
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
ms.openlocfilehash: ba16431fc71a0e594b77dcc6dab62ed6c49c9137
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257493"
---
# <a name="compiler-error-c2764"></a>컴파일러 오류 C2764

'param': 템플릿 매개 변수 사용 또는 부분 특수화 'specialization'에서 추론할 수 없습니다

부분 특수화에 템플릿 매개 변수가 사용 되지 않습니다. 이 부분 특수화를 사용할 수 없는 템플릿 매개 변수를 추론할 수 없습니다 때문입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2764를 생성합니다.

```
// C2764.cpp
#include <stdio.h>
template <class T1, class T2>
struct S  {
   int m_i;
};

template <class T1, class T2>
struct S<int, T2*> {   // C2764
// try the following line instead
// struct S<T1(*)(T2), T2*> {
   char m_c;
};

int main() {
   S<int, char> s1;
   S<void (*)(short), short *> s2;
   s2.m_c = 10;
   s1.m_i = s2.m_c;
   printf_s("%d\n", s1.m_i);
}
```