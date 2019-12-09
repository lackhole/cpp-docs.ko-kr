---
title: 컴파일러 오류 C2159
ms.date: 11/04/2016
f1_keywords:
- C2159
helpviewer_keywords:
- C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
ms.openlocfilehash: 8c0ef75f63f5aa57e02297ebd94d4224048b0f2d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755869"
---
# <a name="compiler-error-c2159"></a>컴파일러 오류 C2159

스토리지 클래스를 두 개 이상 지정했습니다.

선언에 스토리지 클래스가 둘 이상 포함되어 있습니다.

다음 샘플에서는 C2159를 생성합니다.

```cpp
// C2159.cpp
// compile with: /c
static int i;   // OK
extern static int i;   // C2159
```
