---
title: 컴파일러 경고(수준 1) C4533
ms.date: 11/04/2016
f1_keywords:
- C4533
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
ms.openlocfilehash: 8ac7f00ad3401e88224c0150324822ce71e95018
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160772"
---
# <a name="compiler-warning-level-1-c4533"></a>컴파일러 경고(수준 1) C4533

'variable' 초기화 '명령을' 의해 생략 되었습니다.

명령 프로그램에서 변경, 제어 흐름, 변수를 초기화 하는 명령이 실행 되지 않았습니다. 다음 샘플에서는 C4533 오류가 생성 됩니다.

```
// C4533.cpp
// compile with: /W1
#include <stdio.h>

struct A
{
   int m_data;
};

int main()
{
   if (1)
   {
      goto Label;
   }

   A a = { 100 };

   Label:   // C4533
      printf("\n%d", a.m_data);   // prints an uninitialized value
}
```