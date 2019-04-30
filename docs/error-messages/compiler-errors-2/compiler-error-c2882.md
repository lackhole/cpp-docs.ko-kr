---
title: 컴파일러 오류 C2882
ms.date: 11/04/2016
f1_keywords:
- C2882
helpviewer_keywords:
- C2882
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
ms.openlocfilehash: e5fd20695f6922ba5832abb1042cce63b7c4f5a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378884"
---
# <a name="compiler-error-c2882"></a>컴파일러 오류 C2882

'name': 식에서 네임 스페이스 식별자를 잘못 사용 했습니다.

식에서 네임 스페이스의 이름을 사용 하려고 했습니다.

다음 샘플에서는 C2882 오류가 생성 됩니다.

```
// C2882.cpp
// compile with: /c
namespace A {
   int k;
}

int i = A;   // C2882, can't assign A to i
```