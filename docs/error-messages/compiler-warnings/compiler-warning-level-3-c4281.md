---
title: 컴파일러 경고 (수준 3) C4281
ms.date: 11/04/2016
f1_keywords:
- C4281
helpviewer_keywords:
- C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
ms.openlocfilehash: 454118aa9b9cb1fdea5fb10576ac8d26833cb08c
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051688"
---
# <a name="compiler-warning-level-3-c4281"></a>컴파일러 경고 (수준 3) C4281

' type ' 형식을 통해 ' operator > ' 재귀가 발생 했습니다.

코드에서 **>** 자신을 호출 하도록 허용 합니다.

다음 샘플에서는 C4281를 생성 합니다.

```cpp
// C4281.cpp
// compile with: /W3 /WX
struct A;
struct B;
struct C;

struct A
{
   int z;
   B& operator->();
};

struct B
{
   C& operator->();
};

struct C
{
   A& operator->();
};

void f(A p)
{
   int i = p->z; // C4281
}
```