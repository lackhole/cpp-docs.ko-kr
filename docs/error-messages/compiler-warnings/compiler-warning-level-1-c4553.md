---
title: 컴파일러 경고(수준 1) C4553
ms.date: 11/04/2016
f1_keywords:
- C4553
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
ms.openlocfilehash: 7a299d4a99818699e9be31e7d15d9e589de05c15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410345"
---
# <a name="compiler-warning-level-1-c4553"></a>컴파일러 경고(수준 1) C4553

'operator': 연산자에 영향을 주지 않습니다. 'operator' 사용 하려고 했습니까?

식 문의 top 식의 부작용 없음 연산자 있으면 실수 때문일 수 있습니다.

다음 샘플에서는 C4553 오류가 생성 됩니다.

```
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```