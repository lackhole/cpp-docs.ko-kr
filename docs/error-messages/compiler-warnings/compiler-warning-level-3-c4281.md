---
title: 컴파일러 경고(수준 3) C4281
ms.date: 11/04/2016
f1_keywords:
- C4281
helpviewer_keywords:
- C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
ms.openlocfilehash: 69496438d8078ee0298bdb447fcf4f7df1b75464
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402153"
---
# <a name="compiler-warning-level-3-c4281"></a>컴파일러 경고(수준 3) C4281

'type' 형식이 'operator->' 재귀가 발생 했습니다.

코드 **operator->** 자신을 호출 합니다.

다음 샘플에서는 C4281 오류가 생성 됩니다.

```
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