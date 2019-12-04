---
title: 컴파일러 오류 C2724
ms.date: 11/04/2016
f1_keywords:
- C2724
helpviewer_keywords:
- C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
ms.openlocfilehash: f48bf45eeed491469b161ac1edcdb57d04eb5863
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760688"
---
# <a name="compiler-error-c2724"></a>컴파일러 오류 C2724

' identifier ': 파일 범위에서 정의 된 멤버 함수에는 ' s t r u e '를 사용할 수 없습니다.

정적 멤버 함수는 외부 링크를 사용 하 여 선언 해야 합니다.

다음 샘플에서는 C2724를 생성 합니다.

```cpp
// C2724.cpp
class C {
   static void func();
};

static void C::func(){};   // C2724
// try the following line instead
// void C::func(){};
```
