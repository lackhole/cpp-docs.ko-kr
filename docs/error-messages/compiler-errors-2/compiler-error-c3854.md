---
title: 컴파일러 오류 C3854
ms.date: 11/04/2016
f1_keywords:
- C3854
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
ms.openlocfilehash: 3b48e2c65003537102864fdafe7db70b06ade029
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265531"
---
# <a name="compiler-error-c3854"></a>컴파일러 오류 C3854

왼쪽 '='의 식이 함수로 계산 합니다. (한 함수는 l-value이 아님) 함수에 할당할 수 없습니다.

참조를 다시 초기화할 수 없습니다. 함수에 대 한 참조를 역참조 하 고 할당할 수 없습니다, rvalue가 함수를 생성 합니다. 따라서 함수에 대 한 참조를 통해 할당할 수 없습니다.

다음 샘플에서는 C3854를 생성합니다.

```
// C3854.cpp
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);
typedef int (* pFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   pFunc_t pf = &afunc;   // OK initializing a pointer to function

   *pf = &afunc;   // C3854
   // try the following line instead
   // pf = &afunc;
   *rf = &afunc;   // C3854
}
```