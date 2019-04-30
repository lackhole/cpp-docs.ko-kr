---
title: 컴파일러 경고(수준 1) C4602
ms.date: 11/04/2016
f1_keywords:
- C4602
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
ms.openlocfilehash: c719ae23ed3799debf2db9c8f2d82b3c49db3156
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406459"
---
# <a name="compiler-warning-level-1-c4602"></a>컴파일러 경고(수준 1) C4602

\#pragma pop_macro: 'macro n'이 식별자에 대 한 이전 #pragma push_macro가 없습니다

특정 매크로 대해 [pop_macro](../../preprocessor/pop-macro.md) 를 사용하는 경우 먼저 해당 매크로 이름을 [push_macro](../../preprocessor/push-macro.md)에 전달했어야 합니다. 예를 들어 다음 샘플에서는 C4602를 생성합니다.

```
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```