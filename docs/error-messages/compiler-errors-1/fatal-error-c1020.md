---
title: 심각한 오류 C1020
ms.date: 11/04/2016
f1_keywords:
- C1020
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
ms.openlocfilehash: 67cf5067c85d07215f6391d9e5d3d1bcb4978e42
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756905"
---
# <a name="fatal-error-c1020"></a>심각한 오류 C1020

예기치 않은 #endif입니다.

`#endif` 지시문에 일치하는 `#if`, `#ifdef`또는 `#ifndef` 지시문이 없습니다. 각 `#endif` 에 일치하는 지시문이 있어야 합니다.

다음 샘플에서는 C1020을 생성합니다.

```cpp
// C1020.cpp
#endif     // C1020
```

가능한 해결 방법:

```cpp
// C1020b.cpp
// compile with: /c
#if 1
#endif
```
